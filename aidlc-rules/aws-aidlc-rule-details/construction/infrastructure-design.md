# Infrastructure Design
# Infrastructure Design

# Infrastructure Design

## Prerequisites
- Functional Design must be complete for the unit
- NFR Design recommended (provides logical components to map)
- Execution plan must indicate Infrastructure Design stage should execute
## 前提条件
- ユニットの Functional Design が完了していること
- NFR Design を推奨（マッピングする論理コンポーネントを提供）
- 実行計画で Infrastructure Design ステージが実行対象であること

## 前提条件
- ユニットの Functional Design が完了していること
- NFR Design を推奨（マッピングする論理コンポーネントを提供）
- 実行計画で Infrastructure Design ステージが実行対象であること

## Overview
Map logical software components to actual infrastructure choices for deployment environments.
## 概要
論理的なソフトウェアコンポーネントを、デプロイ環境の実インフラにマッピングする。

## 概要
論理的なソフトウェアコンポーネントを、デプロイ環境の実インフラにマッピングする。

## Steps to Execute
## 実行手順

## 実行手順

### Step 1: Analyze Design Artifacts
- Read functional design from `aidlc-docs/construction/{unit-name}/functional-design/`
- Read NFR design from `aidlc-docs/construction/{unit-name}/nfr-design/` (if exists)
- Identify logical components needing infrastructure
### ステップ 1: 設計成果物の分析
- `aidlc-docs/construction/{unit-name}/functional-design/` から Functional Design を読む
- `aidlc-docs/construction/{unit-name}/nfr-design/` から NFR Design を読む（存在する場合）
- インフラが必要な論理コンポーネントを特定

### ステップ 1: 設計成果物の分析
- `aidlc-docs/construction/{unit-name}/functional-design/` から Functional Design を読む
- `aidlc-docs/construction/{unit-name}/nfr-design/` から NFR Design を読む（存在する場合）
- インフラが必要な論理コンポーネントを特定

### Step 2: Create Infrastructure Design Plan
- Generate plan with checkboxes [] for infrastructure design
- Focus on mapping to actual services (AWS, Azure, GCP, on-premise)
- Each step should have a checkbox []
### ステップ 2: Infrastructure Design 計画の作成
- Infrastructure Design 用のチェックボックス [] 付き計画を作成
- 実際のサービス（AWS、Azure、GCP、オンプレ）へのマッピングに集中
- 各ステップにチェックボックス [] を付ける

### ステップ 2: Infrastructure Design 計画の作成
- Infrastructure Design 用のチェックボックス [] 付き計画を作成
- 実際のサービス（AWS、Azure、GCP、オンプレ）へのマッピングに集中
- 各ステップにチェックボックス [] を付ける

### Step 3: Generate Context-Appropriate Questions
**DIRECTIVE**: Analyze the functional and NFR design to generate ONLY questions relevant to THIS specific unit's infrastructure needs. Use the categories below as inspiration, NOT as a mandatory checklist. Skip entire categories if not applicable.
### ステップ 3: コンテキストに適した質問の生成
**指示**: Functional/NFR 設計を分析し、このユニットのインフラ要件に**関係する質問のみ**を作成する。以下カテゴリは参考であり必須チェックリストではない。該当しないカテゴリはスキップしてよい。

### ステップ 3: コンテキストに適した質問の生成
**指示**: Functional/NFR 設計を分析し、このユニットのインフラ要件に**関係する質問のみ**を作成する。以下カテゴリは参考であり必須チェックリストではない。該当しないカテゴリはスキップしてよい。

- EMBED questions using [Answer]: tag format
- Focus on ambiguities and missing information specific to this unit
- Generate questions only where user input is needed for infrastructure decisions
- [Answer]: タグ形式で質問を埋め込む
- このユニット特有のあいまいさや欠落情報に焦点
- インフラ判断にユーザー入力が必要な場合のみ質問を作成

- [Answer]: タグ形式で質問を埋め込む
- このユニット特有のあいまいさや欠落情報に焦点
- インフラ判断にユーザー入力が必要な場合のみ質問を作成

**Example question categories** (adapt as needed):
- **Deployment Environment** - Only if cloud provider or environment setup is unclear
- **Compute Infrastructure** - Only if compute service choice needs clarification
- **Storage Infrastructure** - Only if database or storage selection is ambiguous
- **Messaging Infrastructure** - Only if messaging/queuing services need specification
- **Networking Infrastructure** - Only if load balancing or API gateway approach is unclear
- **Monitoring Infrastructure** - Only if observability tooling needs clarification
- **Shared Infrastructure** - Only if infrastructure sharing strategy is ambiguous
**質問カテゴリ例**（必要に応じて調整）:
- **デプロイ環境** - クラウドプロバイダ/環境構成が不明な場合のみ
- **計算基盤** - 計算サービス選定が不明な場合のみ
- **ストレージ基盤** - DB/ストレージ選定が不明な場合のみ
- **メッセージング基盤** - キュー/メッセージングが不明な場合のみ
- **ネットワーク基盤** - LB/API Gateway が不明な場合のみ
- **監視基盤** - 可観測性ツールが不明な場合のみ
- **共有インフラ** - 共有方針が不明な場合のみ

**質問カテゴリ例**（必要に応じて調整）:
- **デプロイ環境** - クラウドプロバイダ/環境構成が不明な場合のみ
- **計算基盤** - 計算サービス選定が不明な場合のみ
- **ストレージ基盤** - DB/ストレージ選定が不明な場合のみ
- **メッセージング基盤** - キュー/メッセージングが不明な場合のみ
- **ネットワーク基盤** - LB/API Gateway が不明な場合のみ
- **監視基盤** - 可観測性ツールが不明な場合のみ
- **共有インフラ** - 共有方針が不明な場合のみ

### Step 4: Store Plan
- Save as `aidlc-docs/construction/plans/{unit-name}-infrastructure-design-plan.md`
- Include all [Answer]: tags for user input
### ステップ 4: 計画の保存
- `aidlc-docs/construction/plans/{unit-name}-infrastructure-design-plan.md` として保存
- ユーザー入力用に [Answer]: タグをすべて含める

### ステップ 4: 計画の保存
- `aidlc-docs/construction/plans/{unit-name}-infrastructure-design-plan.md` として保存
- ユーザー入力用に [Answer]: タグをすべて含める

### Step 5: Collect and Analyze Answers
- Wait for user to complete all [Answer]: tags
- Review for vague or ambiguous responses
- Add follow-up questions if needed
### ステップ 5: 回答収集と分析
- ユーザーがすべての [Answer]: タグを埋めるまで待つ
- あいまい/不明瞭な回答を確認
- 必要に応じてフォロー質問を追加

### ステップ 5: 回答収集と分析
- ユーザーがすべての [Answer]: タグを埋めるまで待つ
- あいまい/不明瞭な回答を確認
- 必要に応じてフォロー質問を追加

### Step 6: Generate Infrastructure Design Artifacts
- Create `aidlc-docs/construction/{unit-name}/infrastructure-design/infrastructure-design.md`
- Create `aidlc-docs/construction/{unit-name}/infrastructure-design/deployment-architecture.md`
- If shared infrastructure: Create `aidlc-docs/construction/shared-infrastructure.md`
### ステップ 6: Infrastructure Design 成果物の生成
- `aidlc-docs/construction/{unit-name}/infrastructure-design/infrastructure-design.md` を作成
- `aidlc-docs/construction/{unit-name}/infrastructure-design/deployment-architecture.md` を作成
- 共有インフラがある場合: `aidlc-docs/construction/shared-infrastructure.md` を作成

### ステップ 6: Infrastructure Design 成果物の生成
- `aidlc-docs/construction/{unit-name}/infrastructure-design/infrastructure-design.md` を作成
- `aidlc-docs/construction/{unit-name}/infrastructure-design/deployment-architecture.md` を作成
- 共有インフラがある場合: `aidlc-docs/construction/shared-infrastructure.md` を作成

### Step 7: Present Completion Message
- Present completion message in this structure:
     1. **Completion Announcement** (mandatory): Always start with this:
### ステップ 7: 完了メッセージの提示
- 次の構造で完了メッセージを提示:
     1. **完了告知**（必須）: 必ずこれで開始

### ステップ 7: 完了メッセージの提示
- 次の構造で完了メッセージを提示:
     1. **完了告知**（必須）: 必ずこれで開始

```markdown
# 🏢 Infrastructure Design Complete - [unit-name]
```
```markdown
# 🏢 Infrastructure Design Complete - [unit-name]
```

```markdown
# 🏢 Infrastructure Design Complete - [unit-name]
```

     2. **AI Summary** (optional): Provide structured bullet-point summary of infrastructure design
        - Format: "Infrastructure design has mapped [description]:"
        - List key infrastructure services and components (bullet points)
        - List deployment architecture decisions and rationale
        - Mention cloud provider choices and service mappings
        - DO NOT include workflow instructions ("please review", "let me know", "proceed to next phase", "before we proceed")
        - Keep factual and content-focused
     3. **Formatted Workflow Message** (mandatory): Always end with this exact format:
     2. **AI 要約**（任意）: インフラ設計の構造化要約
        - 形式: "Infrastructure design has mapped [description]:"
        - 主要インフラサービス/コンポーネントを列挙
        - デプロイアーキテクチャの判断と理由を列挙
        - クラウドプロバイダとサービスマッピングに言及
        - ワークフロー指示は含めない（"please review"、"let me know"、"proceed to next phase"、"before we proceed" など）
        - 事実ベースかつ内容中心にする
     3. **フォーマット済みワークフローメッセージ**（必須）: 必ず以下の形式で終了

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

### Step 8: Wait for Explicit Approval
- Do not proceed until the user explicitly approves the infrastructure design
- Approval must be clear and unambiguous
- If user requests changes, update the design and repeat the approval process
### ステップ 8: 明示的承認待ち
- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があれば設計を更新し、承認プロセスを繰り返す

### ステップ 8: 明示的承認待ち
- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があれば設計を更新し、承認プロセスを繰り返す

### Step 9: Record Approval and Update Progress
- Log approval in audit.md with timestamp
- Record the user's approval response with timestamp
- Mark Infrastructure Design stage complete in aidlc-state.md
### ステップ 9: 承認記録と進捗更新
- audit.md に承認をタイムスタンプ付きで記録
- ユーザーの承認回答をタイムスタンプ付きで記録
- aidlc-state.md で Infrastructure Design を完了にする

### ステップ 9: 承認記録と進捗更新
- audit.md に承認をタイムスタンプ付きで記録
- ユーザーの承認回答をタイムスタンプ付きで記録
- aidlc-state.md で Infrastructure Design を完了にする
