# Infrastructure Design

## 前提条件
- ユニットの Functional Design が完了していること
- NFR Design を推奨（マッピングする論理コンポーネントを提供）
- 実行計画で Infrastructure Design ステージが実行対象であること

## 概要
論理的なソフトウェアコンポーネントを、デプロイ環境の実インフラにマッピングする。

## 実行手順

### ステップ 1: 設計成果物の分析
- `aidlc-docs/construction/{unit-name}/functional-design/` から Functional Design を読む
- `aidlc-docs/construction/{unit-name}/nfr-design/` から NFR Design を読む（存在する場合）
- インフラが必要な論理コンポーネントを特定

### ステップ 2: Infrastructure Design 計画の作成
- Infrastructure Design 用のチェックボックス [] 付き計画を作成
- 実際のサービス（AWS、Azure、GCP、オンプレ）へのマッピングに集中
- 各ステップにチェックボックス [] を付ける

### ステップ 3: コンテキストに適した質問の生成
**指示**: Functional/NFR 設計を分析し、このユニットのインフラ要件に**関係する質問のみ**を作成する。以下カテゴリは参考であり必須チェックリストではない。該当しないカテゴリはスキップしてよい。

- [Answer]: タグ形式で質問を埋め込む
- このユニット特有のあいまいさや欠落情報に焦点
- インフラ判断にユーザー入力が必要な場合のみ質問を作成

**質問カテゴリ例**（必要に応じて調整）:
- **デプロイ環境** - クラウドプロバイダ/環境構成が不明な場合のみ
- **計算基盤** - 計算サービス選定が不明な場合のみ
- **ストレージ基盤** - DB/ストレージ選定が不明な場合のみ
- **メッセージング基盤** - キュー/メッセージングが不明な場合のみ
- **ネットワーク基盤** - LB/API Gateway が不明な場合のみ
- **監視基盤** - 可観測性ツールが不明な場合のみ
- **共有インフラ** - 共有方針が不明な場合のみ

### ステップ 4: 計画の保存
- `aidlc-docs/construction/plans/{unit-name}-infrastructure-design-plan.md` として保存
- ユーザー入力用に [Answer]: タグをすべて含める

### ステップ 5: 回答収集と分析
- ユーザーがすべての [Answer]: タグを埋めるまで待つ
- あいまい/不明瞭な回答を確認
- 必要に応じてフォロー質問を追加

### ステップ 6: Infrastructure Design 成果物の生成
- `aidlc-docs/construction/{unit-name}/infrastructure-design/infrastructure-design.md` を作成
- `aidlc-docs/construction/{unit-name}/infrastructure-design/deployment-architecture.md` を作成
- 共有インフラがある場合: `aidlc-docs/construction/shared-infrastructure.md` を作成

### ステップ 7: 完了メッセージの提示
- 次の構造で完了メッセージを提示:
     1. **完了告知**（必須）: 必ずこれで開始

```markdown
# 🏢 Infrastructure Design Complete - [unit-name]
```

     2. **AI 要約**（任意）: インフラ設計の構造化要約
        - 形式: "Infrastructure design has mapped [description]:"
        - 主要インフラサービス/コンポーネントを列挙
        - デプロイアーキテクチャの判断と理由を列挙
        - クラウドプロバイダとサービスマッピングに言及
        - ワークフロー指示は含めない（"please review"、"let me know"、"proceed to next phase"、"before we proceed" など）
        - 事実ベースかつ内容中心にする
     3. **フォーマット済みワークフローメッセージ**（必須）: 必ず以下の形式で終了

```markdown
> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the infrastructure design at: `aidlc-docs/construction/[unit-name]/infrastructure-design/`



> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the infrastructure design based on your review  
> ✅ **Continue to Next Stage** - Approve infrastructure design and proceed to **Code Generation**

---
```

### ステップ 8: 明示的承認待ち
- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があれば設計を更新し、承認プロセスを繰り返す

### ステップ 9: 承認記録と進捗更新
- audit.md に承認をタイムスタンプ付きで記録
- ユーザーの承認回答をタイムスタンプ付きで記録
- aidlc-state.md で Infrastructure Design を完了にする
