# NFR Design

## 前提条件
- ユニットの NFR Requirements が完了していること
- NFR Requirements 成果物が利用可能であること
- 実行計画で NFR Design ステージが実行対象であること

## 概要
NFR 要件を、パターンと論理コンポーネントを用いてユニット設計に組み込む。

## 実行手順

### ステップ 1: NFR Requirements の分析
- `aidlc-docs/construction/{unit-name}/nfr-requirements/` から NFR 要件を読む
- スケーラビリティ、性能、可用性、セキュリティの要求を理解

### ステップ 2: NFR Design 計画の作成
- NFR Design 用のチェックボックス [] 付き計画を作成
- 設計パターンと論理コンポーネントに集中
- 各ステップにチェックボックス [] を付ける

### ステップ 3: コンテキストに適した質問の生成
**指示**: NFR 要件を分析し、このユニットの NFR 設計に**関係する質問のみ**を作成する。以下カテゴリは参考であり必須チェックリストではない。該当しないカテゴリはスキップしてよい。

- [Answer]: タグ形式で質問を埋め込む
- このユニット特有のあいまいさや欠落情報に焦点
- パターン/コンポーネント判断にユーザー入力が必要な場合のみ質問を作成

**質問カテゴリ例**（必要に応じて調整）:
- **レジリエンスパターン** - 耐障害アプローチの明確化が必要な場合のみ
- **スケーラビリティパターン** - スケーリング機構が不明な場合のみ
- **性能パターン** - 性能最適化方針が不明な場合のみ
- **セキュリティパターン** - 実装方針に入力が必要な場合のみ
- **論理コンポーネント** - キュー/キャッシュ等のインフラ要素が不明な場合のみ

### ステップ 4: 計画の保存
- `aidlc-docs/construction/plans/{unit-name}-nfr-design-plan.md` として保存
- ユーザー入力用に [Answer]: タグをすべて含める

### ステップ 5: 回答収集と分析
- ユーザーがすべての [Answer]: タグを埋めるまで待つ
- あいまい/不明瞭な回答を確認
- 必要に応じてフォロー質問を追加

### ステップ 6: NFR Design 成果物の生成
- `aidlc-docs/construction/{unit-name}/nfr-design/nfr-design-patterns.md` を作成
- `aidlc-docs/construction/{unit-name}/nfr-design/logical-components.md` を作成

### ステップ 7: 完了メッセージの提示
- 次の構造で完了メッセージを提示:
     1. **完了告知**（必須）: 必ずこれで開始

```markdown
# 🎨 NFR Design Complete - [unit-name]
```

     2. **AI 要約**（任意）: NFR Design の構造化要約
        - 形式: "NFR design has incorporated [description]:"
        - 実装した主要パターンを列挙
        - 論理コンポーネントやインフラ要素を列挙
        - レジリエンス/スケール/性能パターンに言及
        - ワークフロー指示は含めない（"please review"、"let me know"、"proceed to next phase"、"before we proceed" など）
        - 事実ベースかつ内容中心にする
     3. **フォーマット済みワークフローメッセージ**（必須）: 必ず以下の形式で終了

```markdown
> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the NFR design at: `aidlc-docs/construction/[unit-name]/nfr-design/`



> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the NFR design based on your review  
> ✅ **Continue to Next Stage** - Approve NFR design and proceed to **[next-stage-name]**

---
```

### ステップ 8: 明示的承認待ち
- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があれば設計を更新し、承認プロセスを繰り返す

### ステップ 9: 承認記録と進捗更新
- audit.md に承認をタイムスタンプ付きで記録
- ユーザーの承認回答をタイムスタンプ付きで記録
- aidlc-state.md で NFR Design を完了にする
