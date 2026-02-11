# NFR Design
# NFR Design

# NFR Design

## Prerequisites
- NFR Requirements must be complete for the unit
- NFR requirements artifacts must be available
- Execution plan must indicate NFR Design stage should execute
## 前提条件
- ユニットの NFR Requirements が完了していること
- NFR Requirements 成果物が利用可能であること
- 実行計画で NFR Design ステージが実行対象であること

## 前提条件
- ユニットの NFR Requirements が完了していること
- NFR Requirements 成果物が利用可能であること
- 実行計画で NFR Design ステージが実行対象であること

## Overview
Incorporate NFR requirements into unit design using patterns and logical components.
## 概要
NFR 要件を、パターンと論理コンポーネントを用いてユニット設計に組み込む。

## 概要
NFR 要件を、パターンと論理コンポーネントを用いてユニット設計に組み込む。

## Steps to Execute
## 実行手順

## 実行手順

### Step 1: Analyze NFR Requirements
- Read NFR requirements from `aidlc-docs/construction/{unit-name}/nfr-requirements/`
- Understand scalability, performance, availability, security needs
### ステップ 1: NFR Requirements の分析
- `aidlc-docs/construction/{unit-name}/nfr-requirements/` から NFR 要件を読む
- スケーラビリティ、性能、可用性、セキュリティの要求を理解

### ステップ 1: NFR Requirements の分析
- `aidlc-docs/construction/{unit-name}/nfr-requirements/` から NFR 要件を読む
- スケーラビリティ、性能、可用性、セキュリティの要求を理解

### Step 2: Create NFR Design Plan
- Generate plan with checkboxes [] for NFR design
- Focus on design patterns and logical components
- Each step should have a checkbox []
### ステップ 2: NFR Design 計画の作成
- NFR Design 用のチェックボックス [] 付き計画を作成
- 設計パターンと論理コンポーネントに集中
- 各ステップにチェックボックス [] を付ける

### ステップ 2: NFR Design 計画の作成
- NFR Design 用のチェックボックス [] 付き計画を作成
- 設計パターンと論理コンポーネントに集中
- 各ステップにチェックボックス [] を付ける

### Step 3: Generate Context-Appropriate Questions
**DIRECTIVE**: Analyze the NFR requirements to generate ONLY questions relevant to THIS specific unit's NFR design. Use the categories below as inspiration, NOT as a mandatory checklist. Skip entire categories if not applicable.
### ステップ 3: コンテキストに適した質問の生成
**指示**: NFR 要件を分析し、このユニットの NFR 設計に**関係する質問のみ**を作成する。以下カテゴリは参考であり必須チェックリストではない。該当しないカテゴリはスキップしてよい。

### ステップ 3: コンテキストに適した質問の生成
**指示**: NFR 要件を分析し、このユニットの NFR 設計に**関係する質問のみ**を作成する。以下カテゴリは参考であり必須チェックリストではない。該当しないカテゴリはスキップしてよい。

- EMBED questions using [Answer]: tag format
- Focus on ambiguities and missing information specific to this unit
- Generate questions only where user input is needed for pattern and component decisions
- [Answer]: タグ形式で質問を埋め込む
- このユニット特有のあいまいさや欠落情報に焦点
- パターン/コンポーネント判断にユーザー入力が必要な場合のみ質問を作成

- [Answer]: タグ形式で質問を埋め込む
- このユニット特有のあいまいさや欠落情報に焦点
- パターン/コンポーネント判断にユーザー入力が必要な場合のみ質問を作成

**Example question categories** (adapt as needed):
- **Resilience Patterns** - Only if fault tolerance approach needs clarification
- **Scalability Patterns** - Only if scaling mechanisms are unclear
- **Performance Patterns** - Only if performance optimization strategy is ambiguous
- **Security Patterns** - Only if security implementation approach needs input
- **Logical Components** - Only if infrastructure components (queues, caches, etc.) need clarification
**質問カテゴリ例**（必要に応じて調整）:
- **レジリエンスパターン** - 耐障害アプローチの明確化が必要な場合のみ
- **スケーラビリティパターン** - スケーリング機構が不明な場合のみ
- **性能パターン** - 性能最適化方針が不明な場合のみ
- **セキュリティパターン** - 実装方針に入力が必要な場合のみ
- **論理コンポーネント** - キュー/キャッシュ等のインフラ要素が不明な場合のみ

**質問カテゴリ例**（必要に応じて調整）:
- **レジリエンスパターン** - 耐障害アプローチの明確化が必要な場合のみ
- **スケーラビリティパターン** - スケーリング機構が不明な場合のみ
- **性能パターン** - 性能最適化方針が不明な場合のみ
- **セキュリティパターン** - 実装方針に入力が必要な場合のみ
- **論理コンポーネント** - キュー/キャッシュ等のインフラ要素が不明な場合のみ

### Step 4: Store Plan
- Save as `aidlc-docs/construction/plans/{unit-name}-nfr-design-plan.md`
- Include all [Answer]: tags for user input
### ステップ 4: 計画の保存
- `aidlc-docs/construction/plans/{unit-name}-nfr-design-plan.md` として保存
- ユーザー入力用に [Answer]: タグをすべて含める

### ステップ 4: 計画の保存
- `aidlc-docs/construction/plans/{unit-name}-nfr-design-plan.md` として保存
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

### Step 6: Generate NFR Design Artifacts
- Create `aidlc-docs/construction/{unit-name}/nfr-design/nfr-design-patterns.md`
- Create `aidlc-docs/construction/{unit-name}/nfr-design/logical-components.md`
### ステップ 6: NFR Design 成果物の生成
- `aidlc-docs/construction/{unit-name}/nfr-design/nfr-design-patterns.md` を作成
- `aidlc-docs/construction/{unit-name}/nfr-design/logical-components.md` を作成

### ステップ 6: NFR Design 成果物の生成
- `aidlc-docs/construction/{unit-name}/nfr-design/nfr-design-patterns.md` を作成
- `aidlc-docs/construction/{unit-name}/nfr-design/logical-components.md` を作成

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
# 🎨 NFR Design Complete - [unit-name]
```
```markdown
# 🎨 NFR Design Complete - [unit-name]
```

```markdown
# 🎨 NFR Design Complete - [unit-name]
```

     2. **AI Summary** (optional): Provide structured bullet-point summary of NFR design
        - Format: "NFR design has incorporated [description]:"
        - List key design patterns implemented (bullet points)
        - List logical components and infrastructure elements
        - Mention resilience, scalability, and performance patterns applied
        - DO NOT include workflow instructions ("please review", "let me know", "proceed to next phase", "before we proceed")
        - Keep factual and content-focused
     3. **Formatted Workflow Message** (mandatory): Always end with this exact format:
     2. **AI 要約**（任意）: NFR Design の構造化要約
        - 形式: "NFR design has incorporated [description]:"
        - 実装した主要パターンを列挙
        - 論理コンポーネントやインフラ要素を列挙
        - レジリエンス/スケール/性能パターンに言及
        - ワークフロー指示は含めない（"please review"、"let me know"、"proceed to next phase"、"before we proceed" など）
        - 事実ベースかつ内容中心にする
     3. **フォーマット済みワークフローメッセージ**（必須）: 必ず以下の形式で終了

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

### Step 8: Wait for Explicit Approval
- Do not proceed until the user explicitly approves the NFR design
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
- Mark NFR Design stage complete in aidlc-state.md
### ステップ 9: 承認記録と進捗更新
- audit.md に承認をタイムスタンプ付きで記録
- ユーザーの承認回答をタイムスタンプ付きで記録
- aidlc-state.md で NFR Design を完了にする

### ステップ 9: 承認記録と進捗更新
- audit.md に承認をタイムスタンプ付きで記録
- ユーザーの承認回答をタイムスタンプ付きで記録
- aidlc-state.md で NFR Design を完了にする
