# Functional Design
# Functional Design

# Functional Design

## Purpose
**Detailed business logic design per unit**
## 目的
**ユニットごとの詳細なビジネスロジック設計**

## 目的
**ユニットごとの詳細なビジネスロジック設計**

Functional Design focuses on:
- Detailed business logic and algorithms for the unit
- Domain models with entities and relationships
- Detailed business rules, validation logic, and constraints
- Technology-agnostic design (no infrastructure concerns)
Functional Design の焦点:
- ユニットの詳細なビジネスロジックとアルゴリズム
- エンティティと関係を含むドメインモデル
- 詳細なビジネスルール、検証ロジック、制約
- 技術非依存の設計（インフラは扱わない）

Functional Design の焦点:
- ユニットの詳細なビジネスロジックとアルゴリズム
- エンティティと関係を含むドメインモデル
- 詳細なビジネスルール、検証ロジック、制約
- 技術非依存の設計（インフラは扱わない）

**Note**: This builds upon high-level component design from Application Design (INCEPTION phase)
**注記**: Application Design（INCEPTION フェーズ）の高レベル設計を土台とする

**注記**: Application Design（INCEPTION フェーズ）の高レベル設計を土台とする

## Prerequisites
- Units Generation must be complete
- Unit of work artifacts must be available
- Application Design recommended (provides high-level component structure)
- Execution plan must indicate Functional Design stage should execute
## 前提条件
- Units Generation が完了していること
- Unit of Work 成果物が利用可能であること
- Application Design を推奨（高レベル構造を提供）
- 実行計画で Functional Design ステージが実行対象であること

## 前提条件
- Units Generation が完了していること
- Unit of Work 成果物が利用可能であること
- Application Design を推奨（高レベル構造を提供）
- 実行計画で Functional Design ステージが実行対象であること

## Overview
Design detailed business logic for the unit, technology-agnostic and focused purely on business functions.
## 概要
技術非依存で、ビジネス機能に集中したユニットの詳細設計を行う。

## 概要
技術非依存で、ビジネス機能に集中したユニットの詳細設計を行う。

## Steps to Execute
## 実行手順

## 実行手順

### Step 1: Analyze Unit Context
- Read unit definition from `aidlc-docs/inception/application-design/unit-of-work.md`
- Read assigned stories from `aidlc-docs/inception/application-design/unit-of-work-story-map.md`
- Understand unit responsibilities and boundaries
### ステップ 1: ユニットコンテキストの分析
- `aidlc-docs/inception/application-design/unit-of-work.md` からユニット定義を読む
- `aidlc-docs/inception/application-design/unit-of-work-story-map.md` から割り当てストーリーを読む
- ユニットの責務と境界を理解

### ステップ 1: ユニットコンテキストの分析
- `aidlc-docs/inception/application-design/unit-of-work.md` からユニット定義を読む
- `aidlc-docs/inception/application-design/unit-of-work-story-map.md` から割り当てストーリーを読む
- ユニットの責務と境界を理解

### Step 2: Create Functional Design Plan
- Generate plan with checkboxes [] for functional design
- Focus on business logic, domain models, business rules
- Each step should have a checkbox []
### ステップ 2: Functional Design 計画の作成
- Functional Design 用のチェックボックス [] 付き計画を作成
- ビジネスロジック、ドメインモデル、ビジネスルールに集中
- 各ステップにチェックボックス [] を付ける

### ステップ 2: Functional Design 計画の作成
- Functional Design 用のチェックボックス [] 付き計画を作成
- ビジネスロジック、ドメインモデル、ビジネスルールに集中
- 各ステップにチェックボックス [] を付ける

### Step 3: Generate Context-Appropriate Questions
**DIRECTIVE**: Thoroughly analyze the unit definition and functional design artifacts to identify ALL areas where clarification would improve the functional design. Be proactive in asking questions to ensure comprehensive understanding.
### ステップ 3: コンテキストに適した質問の生成
**指示**: ユニット定義と設計成果物を徹底分析し、設計品質を高めるための確認点をすべて特定する。積極的に質問する。

### ステップ 3: コンテキストに適した質問の生成
**指示**: ユニット定義と設計成果物を徹底分析し、設計品質を高めるための確認点をすべて特定する。積極的に質問する。

**CRITICAL**: Default to asking questions when there is ANY ambiguity or missing detail that could affect functional design quality. It's better to ask too many questions than to make incorrect assumptions.
**重要**: あいまいさや欠落が少しでもあれば質問することをデフォルトにする。誤った仮定をするより、質問しすぎる方がよい。

**重要**: あいまいさや欠落が少しでもあれば質問することをデフォルトにする。誤った仮定をするより、質問しすぎる方がよい。

- EMBED questions using [Answer]: tag format
- Focus on ANY ambiguities, missing information, or areas needing clarification
- Generate questions wherever user input would improve functional design decisions
- **When in doubt, ask the question** - overconfidence leads to poor designs
- [Answer]: タグ形式で質問を埋め込む
- あいまい/欠落/確認が必要な領域に焦点
- 設計判断にユーザー入力が有益なら質問を作成
- **迷ったら質問する** - 過信は不十分な設計につながる

- [Answer]: タグ形式で質問を埋め込む
- あいまい/欠落/確認が必要な領域に焦点
- 設計判断にユーザー入力が有益なら質問を作成
- **迷ったら質問する** - 過信は不十分な設計につながる

**Question categories to consider** (evaluate ALL categories):
- **Business Logic Modeling** - Ask about core entities, workflows, data transformations, and business processes
- **Domain Model** - Ask about domain concepts, entity relationships, data structures, and business objects
- **Business Rules** - Ask about decision rules, validation logic, constraints, and business policies
- **Data Flow** - Ask about data inputs, outputs, transformations, and persistence requirements
- **Integration Points** - Ask about external system interactions, APIs, and data exchange
- **Error Handling** - Ask about error scenarios, validation failures, and exception handling
- **Business Scenarios** - Ask about edge cases, alternative flows, and complex business situations
- **Frontend Components** (if applicable) - Ask about UI component structure, user interactions, state management, and form handling
**検討すべき質問カテゴリ**（すべて評価）:
- **ビジネスロジックのモデル化** - エンティティ、ワークフロー、変換、ビジネスプロセス
- **ドメインモデル** - ドメイン概念、エンティティ関係、データ構造、ビジネスオブジェクト
- **ビジネスルール** - 判断ルール、検証ロジック、制約、ポリシー
- **データフロー** - 入力、出力、変換、永続化要件
- **統合ポイント** - 外部システム連携、API、データ交換
- **エラーハンドリング** - エラーシナリオ、検証失敗、例外処理
- **ビジネスシナリオ** - エッジケース、代替フロー、複雑な状況

**検討すべき質問カテゴリ**（すべて評価）:
- **ビジネスロジックのモデル化** - エンティティ、ワークフロー、変換、ビジネスプロセス
- **ドメインモデル** - ドメイン概念、エンティティ関係、データ構造、ビジネスオブジェクト
- **ビジネスルール** - 判断ルール、検証ロジック、制約、ポリシー
- **データフロー** - 入力、出力、変換、永続化要件
- **統合ポイント** - 外部システム連携、API、データ交換
- **エラーハンドリング** - エラーシナリオ、検証失敗、例外処理
- **ビジネスシナリオ** - エッジケース、代替フロー、複雑な状況

### Step 4: Store Plan
- Save as `aidlc-docs/construction/plans/{unit-name}-functional-design-plan.md`
- Include all [Answer]: tags for user input
### ステップ 4: 計画の保存
- `aidlc-docs/construction/plans/{unit-name}-functional-design-plan.md` として保存
- ユーザー入力用に [Answer]: タグをすべて含める

### ステップ 4: 計画の保存
- `aidlc-docs/construction/plans/{unit-name}-functional-design-plan.md` として保存
- ユーザー入力用に [Answer]: タグをすべて含める

### Step 5: Collect and Analyze Answers
- Wait for user to complete all [Answer]: tags
- **MANDATORY**: Carefully review ALL responses for vague or ambiguous answers
- **CRITICAL**: Add follow-up questions for ANY unclear responses - do not proceed with ambiguity
- Look for responses like "depends", "maybe", "not sure", "mix of", "somewhere between"
- Create clarification questions file if ANY ambiguities are detected
- **Do not proceed until ALL ambiguities are resolved**
### ステップ 5: 回答収集と分析
- ユーザーがすべての [Answer]: タグを埋めるまで待つ
- **必須**: すべての回答のあいまいさを丁寧に確認
- **重要**: 不明瞭な回答には必ずフォロー質問を追加し、曖昧なまま進めない
- "depends", "maybe", "not sure", "mix of", "somewhere between" のような回答に注意
- あいまいさがあれば確認質問ファイルを作成
- **すべての曖昧さが解消されるまで進めない**

### ステップ 5: 回答収集と分析
- ユーザーがすべての [Answer]: タグを埋めるまで待つ
- **必須**: すべての回答のあいまいさを丁寧に確認
- **重要**: 不明瞭な回答には必ずフォロー質問を追加し、曖昧なまま進めない
- "depends", "maybe", "not sure", "mix of", "somewhere between" のような回答に注意
- あいまいさがあれば確認質問ファイルを作成
- **すべての曖昧さが解消されるまで進めない**

### Step 6: Generate Functional Design Artifacts
- Create `aidlc-docs/construction/{unit-name}/functional-design/business-logic-model.md`
- Create `aidlc-docs/construction/{unit-name}/functional-design/business-rules.md`
- Create `aidlc-docs/construction/{unit-name}/functional-design/domain-entities.md`
- If unit includes frontend/UI: Create `aidlc-docs/construction/{unit-name}/functional-design/frontend-components.md`
  - Component hierarchy and structure
  - Props and state definitions for each component
  - User interaction flows
  - Form validation rules
  - API integration points (which backend endpoints each component uses)
### ステップ 6: Functional Design 成果物の生成
- `aidlc-docs/construction/{unit-name}/functional-design/business-logic-model.md` を作成
- `aidlc-docs/construction/{unit-name}/functional-design/business-rules.md` を作成
- `aidlc-docs/construction/{unit-name}/functional-design/domain-entities.md` を作成

### ステップ 6: Functional Design 成果物の生成
- `aidlc-docs/construction/{unit-name}/functional-design/business-logic-model.md` を作成
- `aidlc-docs/construction/{unit-name}/functional-design/business-rules.md` を作成
- `aidlc-docs/construction/{unit-name}/functional-design/domain-entities.md` を作成

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
# 🔧 Functional Design Complete - [unit-name]
```
```markdown
# 🔧 Functional Design Complete - [unit-name]
```

```markdown
# 🔧 Functional Design Complete - [unit-name]
```

     2. **AI Summary** (optional): Provide structured bullet-point summary of functional design
        - Format: "Functional design has created [description]:"
        - List key business logic models and entities (bullet points)
        - List business rules and validation logic defined
        - Mention domain model structure and relationships
        - DO NOT include workflow instructions ("please review", "let me know", "proceed to next phase", "before we proceed")
        - Keep factual and content-focused
     3. **Formatted Workflow Message** (mandatory): Always end with this exact format:
     2. **AI 要約**（任意）: Functional Design の構造化要約
        - 形式: "Functional design has created [description]:"
        - 主要なビジネスロジックモデルとエンティティを列挙
        - 定義したビジネスルールと検証ロジックを列挙
        - ドメインモデル構造と関係に言及
        - ワークフロー指示は含めない（"please review"、"let me know"、"proceed to next phase"、"before we proceed" など）
        - 事実ベースかつ内容中心にする
     3. **フォーマット済みワークフローメッセージ**（必須）: 必ず以下の形式で終了

     2. **AI 要約**（任意）: Functional Design の構造化要約
        - 形式: "Functional design has created [description]:"
        - 主要なビジネスロジックモデルとエンティティを列挙
        - 定義したビジネスルールと検証ロジックを列挙
        - ドメインモデル構造と関係に言及
        - ワークフロー指示は含めない（"please review"、"let me know"、"proceed to next phase"、"before we proceed" など）
        - 事実ベースかつ内容中心にする
     3. **フォーマット済みワークフローメッセージ**（必須）: 必ず以下の形式で終了

```markdown
> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the functional design artifacts at: `aidlc-docs/construction/[unit-name]/functional-design/`



> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the functional design based on your review  
> ✅ **Continue to Next Stage** - Approve functional design and proceed to **[next-stage-name]**

---
```
```markdown
> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the functional design artifacts at: `aidlc-docs/construction/[unit-name]/functional-design/`



> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the functional design based on your review  
> ✅ **Continue to Next Stage** - Approve functional design and proceed to **[next-stage-name]**

---
```

```markdown
> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the functional design artifacts at: `aidlc-docs/construction/[unit-name]/functional-design/`



> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the functional design based on your review  
> ✅ **Continue to Next Stage** - Approve functional design and proceed to **[next-stage-name]**

---
```

### Step 8: Wait for Explicit Approval
- Do not proceed until the user explicitly approves the functional design
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
- Mark Functional Design stage complete in aidlc-state.md
### ステップ 9: 承認記録と進捗更新
- audit.md に承認をタイムスタンプ付きで記録
- ユーザーの承認回答をタイムスタンプ付きで記録
- aidlc-state.md で Functional Design を完了にする

### ステップ 9: 承認記録と進捗更新
- audit.md に承認をタイムスタンプ付きで記録
- ユーザーの承認回答をタイムスタンプ付きで記録
- aidlc-state.md で Functional Design を完了にする
