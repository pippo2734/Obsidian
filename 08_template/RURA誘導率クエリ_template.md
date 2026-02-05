<%*
const date_from = await tp.system.prompt("開始日を入力", tp.date.now("YYYY-MM-DD", -7));
const date_to = await tp.system.prompt("終了日を入力", tp.date.now("YYYY-MM-DD"));
const time_from = await tp.system.prompt("開始時刻を入力", "11:00:00");
const time_to = await tp.system.prompt("終了時刻を入力", "21:00:00");
-%>
---
tags: [SQL, RURA, 誘導率, クエリ]
created: <% tp.date.now("YYYY-MM-DD HH:mm") %>
date_from: <% date_from %>
date_to: <% date_to %>
time_from: <% time_from %>
time_to: <% time_to %>
---

# RURA誘導率集計クエリ

## パラメータ
| 項目 | 値 |
|------|-----|
| 開始日 | <% date_from %> |
| 終了日 | <% date_to %> |
| 開始時刻 | <% time_from %> |
| 終了時刻 | <% time_to %> |

## 集計クエリ（ピボット形式）

以下のクエリをコピーしてSQLで実行してください。

```sql
DECLARE
  @date_from date = '<% date_from %>',
  @date_to   date = '<% date_to %>',
  @time_from time = '<% time_from %>',
  @time_to   time = '<% time_to %>';

WITH TARGET_CLUB AS (
  SELECT CLUB_CD, CLUB_RS_NM
  FROM CLUBM
  WHERE CLUB_CD IN(
    '001145','001150','002500','003320','005460','005480','007160','001470','001740','002420','005340','005710','007170','007540',/*202511以前導入*/
    '002170','002460','002480','002490','002650','002710','002750','002810','002850','003150','003400','004610','004720','004830','005410','005650','006450','006460','006470','007120','007130','007150',/*202512導入*/
    '001110','001410','001420','001440','001610','001710','001770','002630','002680','002990','003040','003070','003090','003170','003230','003250','004210','004820','006430','006440','007140','007410','007420','007710'/*202502導入*/
  )
),
BASE_DATA AS (
  SELECT
    TC.CLUB_CD,
    TC.CLUB_RS_NM,
    CASE
      WHEN TC.CLUB_CD IN ('001145','001150','002500','003320','005460','005480','007160')
        THEN 2
      ELSE 3
    END AS PHASE,
    CASE
      WHEN (SELECT b.SYU_NM FROM MSCSM b WHERE b.SYU_CD = M.MAE_SYU_CD) LIKE N'%おためし%'
       AND M.TODOKE_KBN = '2'
        THEN 1
      ELSE 0
    END AS OTA_HEN_FLG,
    CASE
      WHEN LEFT(M.CLI_NO, 1) IN ('T','Z','X') THEN 1 ELSE 0
    END AS RURA_FLG,
    M.TODOKE_KBN
  FROM TARGET_CLUB TC
  LEFT JOIN MEMRJ M
    ON TC.CLUB_CD = M.CLUB_CD
   AND M.SHORI_YMD BETWEEN @date_from AND @date_to
   AND CONVERT(time, M.CSYSDT) BETWEEN @time_from AND @time_to
   AND M.TODOKE_KBN BETWEEN 2 AND 4
   AND NOT (
     M.TODOKE_KBN = 4
     AND (
       TRY_CAST(M.BUM_CD AS int) BETWEEN 2 AND 24
       OR TRY_CAST(M.BUM_CD AS int) BETWEEN 103 AND 106
     )
   )
)

SELECT
  PHASE AS [フェーズ],
  CLUB_CD AS [クラブCD],
  CLUB_RS_NM AS [クラブ],
  -- 諸届:2（変更）
  SUM(CASE WHEN TODOKE_KBN = '2' THEN 1 ELSE 0 END) AS [変更_全件数],
  SUM(CASE WHEN TODOKE_KBN = '2' AND RURA_FLG = 1 THEN 1 ELSE 0 END) AS [変更_RURA件数],
  -- 諸届:3（休会）
  SUM(CASE WHEN TODOKE_KBN = '3' THEN 1 ELSE 0 END) AS [休会_全件数],
  SUM(CASE WHEN TODOKE_KBN = '3' AND RURA_FLG = 1 THEN 1 ELSE 0 END) AS [休会_RURA件数],
  -- 諸届:4（退会）
  SUM(CASE WHEN TODOKE_KBN = '4' THEN 1 ELSE 0 END) AS [退会_全件数],
  SUM(CASE WHEN TODOKE_KBN = '4' AND RURA_FLG = 1 THEN 1 ELSE 0 END) AS [退会_RURA件数],
  -- 全体
  COUNT(TODOKE_KBN) AS [全体の全件数],
  SUM(RURA_FLG) AS [全体のRURA件数],
  -- 誘導率
  CASE
    WHEN COUNT(TODOKE_KBN) > 0
    THEN CAST(ROUND(SUM(RURA_FLG) * 100.0 / COUNT(TODOKE_KBN), 1) AS DECIMAL(5,1))
    ELSE 0
  END AS [誘導率%]
FROM BASE_DATA
WHERE OTA_HEN_FLG = 0  -- おためし会員の会員種別変更手続きを除く
GROUP BY PHASE, CLUB_CD, CLUB_RS_NM
ORDER BY PHASE, CLUB_CD;
```

## 総計を含むクエリ（ROLLUP版）

```sql
DECLARE
  @date_from date = '<% date_from %>',
  @date_to   date = '<% date_to %>',
  @time_from time = '<% time_from %>',
  @time_to   time = '<% time_to %>';

WITH TARGET_CLUB AS (
  SELECT CLUB_CD, CLUB_RS_NM
  FROM CLUBM
  WHERE CLUB_CD IN(
    '001145','001150','002500','003320','005460','005480','007160','001470','001740','002420','005340','005710','007170','007540',
    '002170','002460','002480','002490','002650','002710','002750','002810','002850','003150','003400','004610','004720','004830','005410','005650','006450','006460','006470','007120','007130','007150',
    '001110','001410','001420','001440','001610','001710','001770','002630','002680','002990','003040','003070','003090','003170','003230','003250','004210','004820','006430','006440','007140','007410','007420','007710'
  )
),
BASE_DATA AS (
  SELECT
    TC.CLUB_CD,
    TC.CLUB_RS_NM,
    CASE
      WHEN TC.CLUB_CD IN ('001145','001150','002500','003320','005460','005480','007160')
        THEN 2
      ELSE 3
    END AS PHASE,
    CASE
      WHEN (SELECT b.SYU_NM FROM MSCSM b WHERE b.SYU_CD = M.MAE_SYU_CD) LIKE N'%おためし%'
       AND M.TODOKE_KBN = '2'
        THEN 1
      ELSE 0
    END AS OTA_HEN_FLG,
    CASE
      WHEN LEFT(M.CLI_NO, 1) IN ('T','Z','X') THEN 1 ELSE 0
    END AS RURA_FLG,
    M.TODOKE_KBN
  FROM TARGET_CLUB TC
  LEFT JOIN MEMRJ M
    ON TC.CLUB_CD = M.CLUB_CD
   AND M.SHORI_YMD BETWEEN @date_from AND @date_to
   AND CONVERT(time, M.CSYSDT) BETWEEN @time_from AND @time_to
   AND M.TODOKE_KBN BETWEEN 2 AND 4
   AND NOT (
     M.TODOKE_KBN = 4
     AND (
       TRY_CAST(M.BUM_CD AS int) BETWEEN 2 AND 24
       OR TRY_CAST(M.BUM_CD AS int) BETWEEN 103 AND 106
     )
   )
)

SELECT
  COALESCE(CAST(PHASE AS VARCHAR), '総計') AS [フェーズ],
  COALESCE(CLUB_CD, '') AS [クラブCD],
  COALESCE(CLUB_RS_NM, CASE WHEN GROUPING(PHASE) = 1 THEN '総計' ELSE 'フェーズ小計' END) AS [クラブ],
  SUM(CASE WHEN TODOKE_KBN = '2' THEN 1 ELSE 0 END) AS [変更_全件数],
  SUM(CASE WHEN TODOKE_KBN = '2' AND RURA_FLG = 1 THEN 1 ELSE 0 END) AS [変更_RURA件数],
  SUM(CASE WHEN TODOKE_KBN = '3' THEN 1 ELSE 0 END) AS [休会_全件数],
  SUM(CASE WHEN TODOKE_KBN = '3' AND RURA_FLG = 1 THEN 1 ELSE 0 END) AS [休会_RURA件数],
  SUM(CASE WHEN TODOKE_KBN = '4' THEN 1 ELSE 0 END) AS [退会_全件数],
  SUM(CASE WHEN TODOKE_KBN = '4' AND RURA_FLG = 1 THEN 1 ELSE 0 END) AS [退会_RURA件数],
  COUNT(TODOKE_KBN) AS [全体の全件数],
  SUM(RURA_FLG) AS [全体のRURA件数],
  CASE
    WHEN COUNT(TODOKE_KBN) > 0
    THEN CAST(ROUND(SUM(RURA_FLG) * 100.0 / COUNT(TODOKE_KBN), 1) AS DECIMAL(5,1))
    ELSE 0
  END AS [誘導率%]
FROM BASE_DATA
WHERE OTA_HEN_FLG = 0
GROUP BY ROLLUP(PHASE, (CLUB_CD, CLUB_RS_NM))
ORDER BY
  CASE WHEN GROUPING(PHASE) = 1 THEN 1 ELSE 0 END,
  PHASE,
  CASE WHEN GROUPING(CLUB_CD) = 1 THEN 1 ELSE 0 END,
  CLUB_CD;
```

---

## 使い方

### 基本的な使い方
1. コマンドパレット（`Ctrl/Cmd + P`）を開く
2. 「Templater: Create new note from template」を選択
3. 「RURA誘導率クエリ_template」を選択
4. 日付と時刻を入力するプロンプトが表示される
5. 生成されたSQLをコピーしてSSMSやA5:SQL Mk-2等で実行

### ワンボタンで使うための設定（推奨）

#### 方法1: ホットキーを設定
1. 設定 → ホットキー → 「Templater: Insert RURA誘導率クエリ_template」を検索
2. 好きなキー（例: `Ctrl+Shift+R`）を割り当て
3. 以降はそのキーを押すだけで実行可能

#### 方法2: QuickAddマクロを設定
1. QuickAdd設定を開く
2. 「Add Choice」→「Template」を選択
3. 名前を「RURA誘導率クエリ生成」等に設定
4. テンプレートパスに「08_template/RURA誘導率クエリ_template」を指定
5. 「Create file」にチェック
6. ファイル名フォーマットを `03_Project/01_RURA/誘導率クエリ_{{DATE:YYYY-MM-DD}}` に設定
7. コマンドパレットからQuickAddで呼び出し可能に

### クエリの違い
- **集計クエリ（ピボット形式）**: クラブごとの集計結果を表示
- **総計を含むクエリ（ROLLUP版）**: フェーズごとの小計と総計も含めて表示
