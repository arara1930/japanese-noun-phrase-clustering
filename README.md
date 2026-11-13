# Japanese Noun Phrase Clustering

## Overview

本リポジトリは、以下の研究論文に関連する資料および実装を公開するためのものです。

**論文名**

ファクトチェックのための文同一性判定に向けた係り受け解析に基づく名詞句クラスタリング

**English Title**

Noun Phrase Clustering Based on Dependency Parsing for Sentence Identity Detection in Fact-Checking

本研究では、日本語ニュース記事を対象として、係り受け解析に基づくルールベースの名詞句クラスタリング手法を提案しています。

現在は、論文中の比較実験で使用したLLMプロンプトおよび詳細な評価結果を公開しています。

将来的には、提案手法の実装コード、評価プログラム、実行環境の設定、サンプルデータなどを追加する予定です。

## Repository Structure

現在のディレクトリ構成は以下のとおりです。

```text
japanese-noun-phrase-clustering/
├── README.md
└── supplementary/
    ├── prompts/
    │   └── llm_noun_clustering.md
    └── results/
        └── corpus_level_detailed.md
```

## Supplementary Materials

論文の紙面の都合上、掲載を省略した補足資料を `supplementary/` に公開しています。

### 1. LLM Prompt

**File:** [llm_noun_clustering.md](supplementary/prompts/llm_noun_clustering.md)

**Models:** GPT-6, Claude Fable 5.1

比較実験において、両モデルに共通して与えたプロンプトの全文を掲載しています。

プロンプトでは、記事全体の文脈に基づく同一対象の判定、入力された名詞句の保持、および出力形式を指定しています。

末尾の `{{INPUT_JSON}}` には、各評価記事に対応する入力データを挿入して使用しました。

### 2. Detailed Evaluation Results

**File:** [corpus_level_detailed.md](supplementary/results/corpus_level_detailed.md)

論文に掲載したCorpus-level評価結果について、各評価指標の詳細な数値をMarkdown形式で公開しています。

**評価データ**

| 項目 | 数値 |
|---|---:|
| Documents | 2 |
| Mentions | 174 |
| Gold Clusters | 112 |

**評価指標**

- MUC（Precision、Recall、F1）
- B³（Precision、Recall、F1）
- CEAF-e（F1）
- CoNLL F1

CoNLL F1は、MUC、B³、CEAF-eのF1スコアの算術平均です。

## Implementation

提案手法の実装コードは、現時点では公開していません。

将来的には、以下のプログラムおよび関連資料の公開を予定しています。

- 名詞句抽出プログラム
- ルールベースの名詞句クラスタリングプログラム
- クラスタリング結果の評価プログラム
- 実行環境および設定ファイル
- 動作確認用のサンプルデータ

実装を公開する際には、実行方法や依存関係を含むドキュメントを整備する予定です。

## Reproducibility

`sup​​plementary/` に掲載したプロンプトおよび評価結果は、論文中の比較実験に対応しています。

現時点では、実装コードおよび評価用データセットを公開していないため、本リポジトリの資料のみで実験全体を再実行することはできません。

将来的な実装公開にあたっては、論文の評価実験で使用した実装と、その後の改善版を区別し、バージョンを管理する方針です。

## Versioning

論文投稿時点の資料を保存するため、GitHub Releasesを利用してバージョンを管理する予定です。

今後、実装コードの公開や手法の改善を行う場合は、既存の公開版を維持しながら、新しいバージョンとして追加します。