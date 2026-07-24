# 医療データ利用制度の比較サマリー（エビデンスURL付き）

## 対象

- オンタリオ州 / ICES
- フィンランド / Findata
- デンマーク / Danish Health Data Authority
- デンマーク / Statistics Denmark

## 比較軸

1. 研究者がデータを触るための審査・資格
2. 研究者が触れるデータを誰がどのように作成するか
3. 研究者が触れるデータの状態
4. 公開時の審査と加工レベル
5. 公開時のデータ状態

---

# 1. 全体比較

| 項目 | オンタリオ / ICES | Findata / フィンランド | デンマーク Health Data Authority | Statistics Denmark |
|---|---|---|---|---|
| 研究者の利用許可 | プロジェクト審査・アクセス管理 | Data Permit | 研究プロジェクト・データアクセス審査 | 研究者・組織による承認済みアクセス |
| 研究者個人の資格 | 一般的な国家資格ではない | Data Permitに記載された人物 | 認証されたユーザー | 承認された研究者・組織 |
| 研究者が触るデータ | 集計データ、Small Cellが存在し得る | 仮名化個人レベルデータ | 仮名化個人レベルデータ | 仮名化個人・企業レベルデータ |
| 分析場所 | ICESの管理環境／プロジェクト環境 | SPE / Kapseli等 | Secure Research Platform | Researcher Machine |
| Small Cell | 内部集計データではあり得る | 分析中はあり得る | 分析中はあり得る | 分析中はあり得る |
| 外部公開 | RIRA・公開用データ化 | Permit Holderが匿名化＋Findata検証 | 匿名化・集計済みのみ | Statistical Disclosure Control |
| 明確な最小セル | 公開データは6未満不可 | ガイドライン上、n<3を含めないことが基本 | 統計抽出は通常5未満をぼかす | 原則3観測以上、データによっては5以上 |
| 特異値・最小値 | 文脈を含む再識別リスク評価 | 個人に紐づく可能性があれば要注意 | 個人識別につながれば不可 | 開示制御の対象 |

---

# 2. オンタリオ州：ICES

## A. 研究者がデータを使うための審査・資格

ICESでは、研究者個人の国家資格というより、**研究プロジェクト単位の審査とアクセス管理**が中心です。

概念的には：

```text
研究プロジェクト
    ↓
組織・研究者の適格性
    ↓
データ利用目的
    ↓
ICESによる審査
    ↓
プロジェクト単位のアクセス
```

### 主要エビデンス

- ICESの研究者向けデータアクセス案内  
  https://www.ices.on.ca/services-for-researchers/public-sector-researchers/access-to-ices-data/
- ICESのDe-Identification and Aggregation Policy  
  https://www.ices.on.ca/wp-content/uploads/2025/11/De-Identification-and-Aggregation-Policy.pdf

---

## B. 研究者が触れるデータを誰が作るか

ICESのDe-Identification and Aggregation Policyでは、**Aggregate Data (Summary Output)** と **Publishable Data** を区別しています。

特に、Aggregate Data (Summary Output)については、Small Cellが存在し得ることを前提に、Project TeamのCollaborating Researchersへの共有条件が規定されています。

つまり、概念的には：

```text
元の識別可能な医療データ
        ↓
ICESが加工・集計
        ↓
Aggregate Data (Summary Output)
        ↓
Project Teamが利用
```

です。

### 重要な点

研究者に必ずSmall Cellを含むデータを渡すという意味ではありません。

正確には、

> **Small Cellを含むAggregate Dataが存在し得て、一定の条件下でProject Team内で共有され得る**

という規定です。

### エビデンス

ICESのポリシーは、Small Cellを含むAggregate Dataについて、以下を明示しています。

- Small Cells may be present
- Project TeamのCollaborating Researchersに共有可能
- PIA上で研究者として特定されていること
- Non-Disclosure Agreementが必要

URL：

https://www.ices.on.ca/wp-content/uploads/2025/11/De-Identification-and-Aggregation-Policy.pdf

---

## C. 研究者が触るデータの状態

ICESのこのポリシーの対象となる研究プロジェクトでは、研究者が触るデータは主に**集計データ**です。

例：

```text
地域A × 疾患X = 3
```

のようなSmall Cellを含む集計結果が存在し得ます。

### 研究者が触る状態

```text
集計データ
```

ただし、これはFindataやデンマークのように、

```text
仮名化個人レベルデータ
```

を研究者が安全な環境で分析するモデルとは異なります。

---

## D. 公開時の審査と加工

ICESでは、**Publishable Data**が別に定義されています。

公開可能なデータについては、主に以下が必要です。

- 6未満のセルサイズを含まない
- Re-Identification Risk Assessment（RIRA）
- ICES Confidential Informationを含まないことの確認

概念的には：

```text
研究プロジェクト内部
    ↓
Small Cellあり得る集計データ
    ↓
公開前
    ↓
RIRA
    ↓
Small Cell < 6 を除去／抑制
    ↓
機密情報確認
    ↓
Publishable Data
    ↓
論文・レポート・公開
```

### 重要なエビデンス

ICESのポリシーでは、Publishable Dataについて、

- Manuscript submissions / Reportsへの掲載が可能
- Cell sizeが6未満であってはならない
- RIRAを実施する
- ICES Confidential Informationがないことを確認する

とされています。

URL：

https://www.ices.on.ca/wp-content/uploads/2025/11/De-Identification-and-Aggregation-Policy.pdf

---

# 3. Findata：フィンランド

## A. 研究者がデータを使うための審査・資格

Findataでは、中心になるのは**Data Permit（データ利用許可）**です。

Data Permitは、特定の研究目的等のために個人レベルの個人データを利用する期限付きの公的許可です。

許可された人物だけがデータを処理できます。

概念的には：

```text
研究プロジェクト
        ↓
Data Permit申請
        ↓
目的・必要データ・利用者を審査
        ↓
許可された人物のみアクセス
```

### エビデンス

Findata公式：

https://findata.fi/en/faq/what-is-a-data-permit/

Findataは、Data Permitを「特定の明確な目的のために個人レベルの個人データを使用するための、期限付きの公的な許可」と説明しています。

また、データは必要な範囲に限定され、名前・個人識別コードはコードに置き換えられ、指定された人物だけがアクセスできます。

---

## B. 研究者が触れるデータを誰が作るか

Findataが、

- データ提供元からデータを取得
- 必要なデータを抽出
- データを結合
- 前処理
- 直接識別子を除去
- 仮名化
- 必要に応じて一般化

して、研究用データセットを作ります。

概念的には：

```text
データ提供元
    ↓
Findata
    ↓
結合・前処理・仮名化
    ↓
SPE / Kapseli
    ↓
研究者
```

### エビデンス

FindataのData Permitsページ：

https://findata.fi/en/permits/data-permits/

このページでは、Data Permit発行後、

- 各データ管理者がデータを抽出
- Findataへ安全に送付
- Findataが前処理
- 必要に応じてデータを結合
- 直接識別子を削除
- Pseudo IDを生成
- 安全な処理環境へ移送

という流れが説明されています。

---

## C. 研究者が触るデータの状態

Findataでは、**個人レベルの仮名化データ**を安全な処理環境内で分析します。

これは匿名化データではありません。

Findata公式の説明：

- individual-level pseudonymised personal data
- secure processing environment
- re-identification禁止
- copying禁止
- permitに記載された人物のみ処理可能

### エビデンス

https://findata.fi/en/course/data-protection-for-researchers/lessons/secure-data-processing-in-the-processing-environment/

また、FindataのData Permit FAQ：

https://findata.fi/en/faq/what-is-a-data-permit/

---

## D. Small Cell

Findataでは、研究者は個人レコード単位の仮名化データを分析します。

したがって、研究者が内部で、

```text
疾患X × 地域A = 2人
```

のようなSmall Cellを含む集計結果を作ることは可能です。

ここで重要なのは、

> **研究者がSmall Cellを直接見ないようにする制度ではない**

ことです。

研究者は個人レベルデータを分析し、その結果としてSmall Cellが発生する可能性があります。

---

## E. 公開時の審査と加工

外部へ結果を出す場合は、

```text
研究者／Permit Holder
    ↓
結果を匿名化
    ↓
Findataへ出力予定を通知
    ↓
Findataがリスクベースで匿名性を検証
    ↓
匿名化された結果のみ外部へ
```

という流れです。

### エビデンス

Findataの公式ガイド：

https://findata.fi/en/services-and-instructions/producing-anonymous-results/

また、Data Permitの条件：

https://findata.fi/en/permits/conditions-of-data-permit/

この条件では、

- Permit Holderが外部出力結果を匿名化
- Findataへ出力意図を通知
- Findataがリスクベース評価で匿名性を検証

することが明記されています。

---

## F. 最小セル・特異値

Findataの匿名化結果ガイドでは、cell-specific frequenciesについて、**n < 3を含めないこと**がチェック項目になっています。

ただし、

> n ≥ 3なら自動的に安全

という意味ではありません。

以下も考慮されます。

- 0%
- 100%
- 小さな母集団
- 他の表から抑制値を推測できる場合
- 他の情報との組み合わせによる再識別

また、Minimum / Maximumなども、単一個人に対応する可能性があるため注意が必要です。

### エビデンス

https://findata.fi/en/services-and-instructions/producing-anonymous-results/

---

# 4. デンマーク：Danish Health Data Authority

## A. 研究者の利用許可

研究者は、Danish Health Data AuthorityのResearch Servicesを通じて、研究プロジェクトとしてデータアクセスを申請します。

申請には、少なくとも、

- Project description
- Data extraction description
- Data order form
- Data controllerによる承認
- 必要に応じた追加の承認・許可

が必要です。

### エビデンス

https://english.sundhedsdatastyrelsen.dk/health-data-and-registers/research-services/apply-for-data

---

## B. 外国研究者の場合

デンマーク国外の研究者・組織の場合、Danish Health Data Authorityは、データ管理責任を担うデンマークの機関との協力を求めています。

その機関が、

- データ責任を担う
- 研究プロジェクトに関与する
- Secure Research Platformへの認証に必要なMitIDを提供する

という構造です。

### エビデンス

https://english.sundhedsdatastyrelsen.dk/health-data-and-registers/research-services

---

## C. 研究者が触るデータの状態

Secure Research Platform上のデータは、**仮名化された個人レベルデータ**です。

具体的には、

- 個人識別番号を暗号化
- 氏名・住所を削除
- 医療従事者番号等を暗号化

します。

また、

- インターネットに接続されない閉じた環境
- MitIDによる二要素ログイン
- 個人レベルデータの外部送信禁止

という構造です。

### エビデンス

https://english.sundhedsdatastyrelsen.dk/health-data-and-registers/research-services/the-secure-research-platform

---

## D. 研究者が触れるデータを誰が作るか

基本的には、

```text
国の医療レジストリ
    ↓
Danish Health Data Authority
    ↓
Secure Research Platform
    ↓
研究者
```

です。

Research Servicesが、プロジェクトの承認された範囲に基づいてデータアクセスを設定します。

固定データセットを作る場合は、Research Servicesがデータを収集・整理することもあります。

### エビデンス

https://english.sundhedsdatastyrelsen.dk/health-data-and-registers/research-services/the-secure-research-platform/fixed-data-sets-or-views

---

## E. Small Cell

研究者は個人レベルの仮名化データを分析できるため、内部では、

```text
疾患X × 地域A = 2人
```

のような集計結果を作る可能性があります。

つまり、Findataと同様に、

> **研究者が触るデータそのものをSmall Cellのない集計データに限定する**

というモデルではありません。

---

## F. 公開・持ち出し時

分析結果を外部に出す場合、

- 個人レベルデータは禁止
- 結果は匿名化されている必要がある
- 個人・企業を直接または間接に識別できない程度に集計する必要がある
- ユーザーが抽出前にファイルを確認する
- Research Servicesが送信ファイルをランダムチェックする

という仕組みです。

### エビデンス

https://english.sundhedsdatastyrelsen.dk/health-data-and-registers/research-services/the-secure-research-platform/extracting-analysis-results

---

## G. 統計抽出の場合

個人レベルデータを必要としない場合は、Research Servicesが統計表を作成する「Statistics extraction」もあります。

この場合：

- すべての統計抽出はdiscretionised
- 原則として5人未満／5観測未満のフィールドをぼかす
- 個人レベルデータではないため、直接メール送信可能

とされています。

### エビデンス

https://english.sundhedsdatastyrelsen.dk/health-data-and-registers/research-services/apply-for-data/statistics-extraction

---

# 5. デンマーク：Statistics Denmark

## A. 研究者が触るデータ

Statistics DenmarkのResearcher Machineでは、研究者等が安全な環境内で個人・企業レベルのデータを分析します。

基本的なモデルは、

```text
仮名化された個人・企業レベルデータ
        ↓
Researcher Machine
        ↓
研究者／承認された利用者が分析
        ↓
統計的開示制御
        ↓
分析結果のみ外部へ
```

です。

---

## B. 公開・持ち出し時

Statistics Denmarkは、Statistical Disclosure Controlを明確に要求しています。

分析結果を外部へ移転するには、少なくとも、

1. 個人・企業レベルデータと仮名化キー変数を除去
2. 直接・間接の識別ができない
3. 十分な統計的開示制御を行う
4. 承認されたファイル形式・転送方法を使う

ことが必要です。

### エビデンス

https://www.dst.dk/en/TilSalg/data-til-forskning/regler-og-datasikkerhed/regler-for-hjemtagelse-af-analyseresultater

---

## C. 最小セル

個人データについては、

> **原則としてテーブルセルごとに最低3観測**

が必要です。

ただし、レジスターによっては、

> **最低5観測**

など、より厳しいルールが適用される場合があります。

また、

- Backward calculation
- Cross reading

によって、隠された値や抑制された値を推測できてはいけません。

つまり、

```text
セルが3以上
```

だけでは十分ではありません。

### エビデンス

https://www.dst.dk/en/TilSalg/data-til-forskning/regler-og-datasikkerhed/regler-for-hjemtagelse-af-analyseresultater

---

# 6. 「誰がどの状態のデータを作るか」の比較

## ICES

```text
ICES
  ↓
研究者に渡す集計データを作成
  ↓
研究者
  ↓
集計データを分析
```

### 研究者が触る状態

```text
集計データ
```

Small Cellを含む可能性あり。

---

## Findata

```text
データ提供元
  ↓
Findata
  ↓
結合・前処理・仮名化
  ↓
SPE
  ↓
研究者
```

### 研究者が触る状態

```text
仮名化された個人レベルデータ
```

Small Cellは、研究者が分析結果として作る可能性あり。

---

## Denmark Health Data Authority

```text
データ提供元
  ↓
Danish Health Data Authority
  ↓
仮名化
  ↓
Secure Research Platform
  ↓
研究者
```

### 研究者が触る状態

```text
仮名化された個人レベルデータ
```

---

## Statistics Denmark

```text
統計局
  ↓
仮名化・安全な研究環境
  ↓
研究者／企業
  ↓
個人・企業レベルデータを分析
  ↓
Disclosure Control
```

### 研究者が触る状態

```text
仮名化された個人・企業レベルデータ
```

---

# 7. 公開時の比較

| 項目 | ICES | Findata | Denmark Health Data Authority | Statistics Denmark |
|---|---|---|---|---|
| 公開前の主体 | ICES | Permit Holder + Findata | Research Services /環境管理 | Statistics Denmarkのルールに基づく利用者・環境 |
| Small Cell基準 | 公開データは <6不可 | ガイドライン上 n<3を含めないことが基本 | 統計抽出は通常 <5をぼかす | 原則3観測以上、場合により5以上 |
| 単純な閾値で十分か | いいえ | いいえ | いいえ | いいえ |
| 他の表との組合せ | RIRAで評価 | リスクベース評価 | 間接識別禁止 | Backward calculation / cross reading防止 |
| 最小値・最大値 | 文脈リスク | 個人に対応する場合要注意 | 個人識別不可が必要 | 開示制御 |
| 特異値 | 再識別リスク評価の対象 | 最小・最大等は要注意 | 匿名性を損なえば不可 | 開示制御対象 |
| 個人レベルデータ公開 | 不可 | 不可 | 不可 | 不可 |

---

# 8. Small Cellをどの段階で扱うか

今回の比較で最も大きな違いは、**Small Cellをどの段階で扱うか**です。

## ICES

```text
研究者が触るデータ
    ↓
すでに集計済み
    ↓
Small Cellが存在する可能性
```

## Findata / デンマーク

```text
研究者が触るデータ
    ↓
個人レベルの仮名化データ
    ↓
研究者が分析
    ↓
その結果としてSmall Cellが発生
    ↓
公開時にDisclosure Control
```

---

# 9. 制度の分類

## A. 「集計データを渡す」モデル

### ICES

研究者に渡る段階で、すでに集計されたデータが中心。

---

## B. 「個人レベル仮名化データを安全な環境で分析させる」モデル

### Findata

### Danish Health Data Authority

研究者は個人レベルの仮名化データを分析し、外部出力時に匿名化・開示制御を受ける。

---

## C. 「個人・企業レベルデータ＋厳格な統計的開示制御」モデル

### Statistics Denmark

個人・企業レベルデータを安全な環境で分析し、出力時にStatistical Disclosure Controlを適用する。

---

# 10. 日本制度との比較におけるポイント

日本の「仮名加工医療情報を認定事業者が扱う」という制度との比較では、以下の観点が重要です。

| 観点 | ICES | Findata / デンマーク |
|---|---|---|
| 研究者に渡す前の加工 | 集計・匿名化 | 仮名化・結合・前処理 |
| 研究者が触る単位 | 集計データ | 個人レコード |
| Small Cellの扱い | 研究者が触る集計データに存在し得る | 分析結果として発生し得る |
| 公開前の制御 | RIRA・最小セル等 | 匿名性評価・開示制御 |
| データの外部持ち出し | 公開可能データのみ | 匿名化済み結果のみ |
| 主な安全性の考え方 | データを先に集計 | 安全な環境＋出力制御 |

## 最も重要な結論

> **ICESは「研究者に渡すデータを先に集計・制御する」モデル。**

> **Findataやデンマークは「研究者に仮名化された個人レベルデータを安全な環境で分析させ、外部に出す結果を匿名化・開示制御する」モデル。**

この違いが、Small Cellを含むデータを研究者が扱えるかどうかを考える際の核心です。

---

# 11. 主要エビデンスURL一覧

## ICES

- De-Identification and Aggregation Policy  
  https://www.ices.on.ca/wp-content/uploads/2025/11/De-Identification-and-Aggregation-Policy.pdf

- Access to ICES Data  
  https://www.ices.on.ca/services-for-researchers/public-sector-researchers/access-to-ices-data/

## Findata

- What is a Data Permit?  
  https://findata.fi/en/faq/what-is-a-data-permit/

- Data Permits  
  https://findata.fi/en/permits/data-permits/

- Conditions of Data Permit  
  https://findata.fi/en/permits/conditions-of-data-permit/

- Secure Data Processing in the Processing Environment  
  https://findata.fi/en/course/data-protection-for-researchers/lessons/secure-data-processing-in-the-processing-environment/

- Producing Anonymous Results  
  https://findata.fi/en/services-and-instructions/producing-anonymous-results/

- Can individuals be identified from the data?  
  https://findata.fi/en/faq/can-individuals-be-identified-from-the-data/

## Denmark Health Data Authority

- Research Services  
  https://english.sundhedsdatastyrelsen.dk/health-data-and-registers/research-services

- Apply for Data  
  https://english.sundhedsdatastyrelsen.dk/health-data-and-registers/research-services/apply-for-data

- The Secure Research Platform  
  https://english.sundhedsdatastyrelsen.dk/health-data-and-registers/research-services/the-secure-research-platform

- Extracting Analysis Results  
  https://english.sundhedsdatastyrelsen.dk/health-data-and-registers/research-services/the-secure-research-platform/extracting-analysis-results

- Statistics Extraction  
  https://english.sundhedsdatastyrelsen.dk/health-data-and-registers/research-services/apply-for-data/statistics-extraction

- Fixed Data Sets or Views  
  https://english.sundhedsdatastyrelsen.dk/health-data-and-registers/research-services/the-secure-research-platform/fixed-data-sets-or-views

## Statistics Denmark

- Rules on Transfer of Analysis Results  
  https://www.dst.dk/en/TilSalg/data-til-forskning/regler-og-datasikkerhed/regler-for-hjemtagelse-af-analyseresultater

---

## 注意

この比較では、各制度の「通常の研究利用ルート」を比較しています。

特にFindata、Danish Health Data Authority、Statistics Denmarkでは、データの種類・研究目的・プロジェクト構成によって例外ルートや追加の許可が存在します。

したがって、制度を日本の「仮名加工医療情報」制度と厳密に比較する場合は、次の3点を分けて検討する必要があります。

1. **データアクセス許可**
2. **研究者・組織・処理環境の認証／アクセス管理**
3. **研究結果の匿名化・統計的開示制御**

特にFindataやデンマークの制度では、1と2によって研究者が仮名化された個人レベルデータを分析できる一方、3によって外部公開時の再識別リスクを制御する、という構造が明確です。
