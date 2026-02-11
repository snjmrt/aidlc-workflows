# Units Generation - Detailed Steps
# Units Generation - 詳細手順

# Units Generation - 詳細手順

## Overview
This stage decomposes the system into manageable units of work through two integrated parts:
- **Part 1 - Planning**: Create decomposition plan with questions, collect answers, analyze for ambiguities, get approval
- **Part 2 - Generation**: Execute approved plan to generate unit artifacts
## 概要
このステージは 2 部構成でシステムを作業単位へ分解する:
- **パート 1 - 計画**: 分解計画を作成し質問を収集、あいまいさを分析、承認を取得
- **パート 2 - 生成**: 承認済み計画を実行しユニット成果物を生成

## 概要
このステージは 2 部構成でシステムを作業単位へ分解する:
- **パート 1 - 計画**: 分解計画を作成し質問を収集、あいまいさを分析、承認を取得
- **パート 2 - 生成**: 承認済み計画を実行しユニット成果物を生成

**DEFINITION**: A unit of work is a logical grouping of stories for development purposes. For microservices, each unit becomes an independently deployable service. For monoliths, the single unit represents the entire application with logical modules.
**定義**: Unit of Work は開発のためのストーリー群の論理的まとまり。マイクロサービスの場合、各ユニットは独立デプロイ可能なサービスになる。モノリスの場合、単一ユニットがアプリ全体を表し、内部に論理モジュールを持つ。

**定義**: Unit of Work は開発のためのストーリー群の論理的まとまり。マイクロサービスの場合、各ユニットは独立デプロイ可能なサービスになる。モノリスの場合、単一ユニットがアプリ全体を表し、内部に論理モジュールを持つ。

**Terminology**: Use "Service" for independently deployable components, "Module" for logical groupings within a service, "Unit of Work" for planning context.
**用語**: 独立デプロイ可能なコンポーネントは "Service"、サービス内の論理グループは "Module"、計画文脈では "Unit of Work" を使用。

**用語**: 独立デプロイ可能なコンポーネントは "Service"、サービス内の論理グループは "Module"、計画文脈では "Unit of Work" を使用。

## Prerequisites
- Context Assessment must be complete
- Requirements Assessment recommended (provides functional scope)
- Story Development recommended (stories map to units)
- Application Design phase REQUIRED (determines components, methods, and services)
- Execution plan must indicate Design phase should execute
## 前提条件
- Context Assessment が完了していること
- Requirements Assessment を推奨（機能スコープを提供）
- Story Development を推奨（ストーリーがユニットに対応）
- Application Design フェーズが必須（コンポーネント/メソッド/サービスを決定）
- 実行計画で Design フェーズが実行対象になっていること

## 前提条件
- Context Assessment が完了していること
- Requirements Assessment を推奨（機能スコープを提供）
- Story Development を推奨（ストーリーがユニットに対応）
- Application Design フェーズが必須（コンポーネント/メソッド/サービスを決定）
- 実行計画で Design フェーズが実行対象になっていること

---
---

---

# PART 1: PLANNING
# PART 1: PLANNING

# PART 1: PLANNING

## Step 1: Create Unit of Work Plan
- Generate plan with checkboxes [] for decomposing system into units of work
- Focus on breaking down the system into manageable development units
- Each step and sub-step should have a checkbox []
## ステップ 1: Unit of Work 計画の作成
- システムを作業単位に分解するためのチェックボックス [] 付き計画を作成
- システムを管理可能な開発単位に分解することに集中
- 各ステップとサブステップにチェックボックス [] を付ける

## ステップ 1: Unit of Work 計画の作成
- システムを作業単位に分解するためのチェックボックス [] 付き計画を作成
- システムを管理可能な開発単位に分解することに集中
- 各ステップとサブステップにチェックボックス [] を付ける

## Step 2: Include Mandatory Unit Artifacts in Plan
**ALWAYS** include these mandatory artifacts in the unit plan:
- [ ] Generate `aidlc-docs/inception/application-design/unit-of-work.md` with unit definitions and responsibilities
- [ ] Generate `aidlc-docs/inception/application-design/unit-of-work-dependency.md` with dependency matrix
- [ ] Generate `aidlc-docs/inception/application-design/unit-of-work-story-map.md` mapping stories to units
- [ ] **Greenfield only**: Document code organization strategy in `unit-of-work.md` (see code-generation.md for structure patterns)
- [ ] Validate unit boundaries and dependencies
- [ ] Ensure all stories are assigned to units
## ステップ 2: 必須ユニット成果物を計画に含める
**必ず** 次の成果物を計画に含める:
- [ ] ユニット定義と責務を含む `aidlc-docs/inception/application-design/unit-of-work.md` を生成
- [ ] 依存関係マトリクスを含む `aidlc-docs/inception/application-design/unit-of-work-dependency.md` を生成
- [ ] ストーリーとユニットのマッピングを含む `aidlc-docs/inception/application-design/unit-of-work-story-map.md` を生成
- [ ] **グリーンフィールドのみ**: `unit-of-work.md` にコード構成戦略を記載（構造パターンは code-generation.md を参照）
- [ ] ユニット境界と依存関係を検証
- [ ] すべてのストーリーがユニットに割り当てられていることを確認

## ステップ 2: 必須ユニット成果物を計画に含める
**必ず** 次の成果物を計画に含める:
- [ ] ユニット定義と責務を含む `aidlc-docs/inception/application-design/unit-of-work.md` を生成
- [ ] 依存関係マトリクスを含む `aidlc-docs/inception/application-design/unit-of-work-dependency.md` を生成
- [ ] ストーリーとユニットのマッピングを含む `aidlc-docs/inception/application-design/unit-of-work-story-map.md` を生成
- [ ] **グリーンフィールドのみ**: `unit-of-work.md` にコード構成戦略を記載（構造パターンは code-generation.md を参照）
- [ ] ユニット境界と依存関係を検証
- [ ] すべてのストーリーがユニットに割り当てられていることを確認

## Step 3: Generate Context-Appropriate Questions
**DIRECTIVE**: Analyze the requirements, stories, and application design to generate ONLY questions relevant to THIS specific decomposition problem. Use the categories below as inspiration, NOT as a mandatory checklist. Skip entire categories if not applicable.
## ステップ 3: コンテキストに適した質問の生成
**指示**: 要件、ストーリー、アプリ設計を分析し、この分解問題に**関係する質問のみ**を作成する。以下カテゴリは参考であり必須チェックリストではない。該当しないカテゴリはスキップしてよい。

## ステップ 3: コンテキストに適した質問の生成
**指示**: 要件、ストーリー、アプリ設計を分析し、この分解問題に**関係する質問のみ**を作成する。以下カテゴリは参考であり必須チェックリストではない。該当しないカテゴリはスキップしてよい。

- EMBED questions using [Answer]: tag format
- Focus on ambiguities and missing information specific to this context
- Generate questions only where user input is needed for decision-making
- [Answer]: タグ形式で質問を埋め込む
- この文脈特有のあいまいさや欠落情報に焦点
- 意思決定にユーザー入力が必要な場合のみ質問を作成

- [Answer]: タグ形式で質問を埋め込む
- この文脈特有のあいまいさや欠落情報に焦点
- 意思決定にユーザー入力が必要な場合のみ質問を作成

**Example question categories** (adapt as needed):
- **Story Grouping** - Only if multiple stories exist and grouping strategy is unclear
- **Dependencies** - Only if multiple units likely and integration approach is ambiguous
- **Team Alignment** - Only if team structure or ownership is unclear
- **Technical Considerations** - Only if scalability/deployment requirements differ across units
- **Business Domain** - Only if domain boundaries or bounded contexts are unclear
- **Code Organization (Greenfield multi-unit only)** - Ask deployment model and directory structure preferences
**質問カテゴリ例**（必要に応じて調整）:
- **ストーリーのグルーピング** - 複数ストーリーがあり戦略が不明な場合のみ
- **依存関係** - 複数ユニットが見込まれ、統合アプローチが不明な場合のみ
- **チーム整合** - チーム構造/責務が不明な場合のみ
- **技術的考慮** - ユニット間でスケール/デプロイ要件が異なる場合のみ
- **ビジネスドメイン** - ドメイン境界や境界づけられたコンテキストが不明な場合のみ
- **コード構成（グリーンフィールド複数ユニットのみ）** - デプロイモデルとディレクトリ構成の嗜好を質問

**質問カテゴリ例**（必要に応じて調整）:
- **ストーリーのグルーピング** - 複数ストーリーがあり戦略が不明な場合のみ
- **依存関係** - 複数ユニットが見込まれ、統合アプローチが不明な場合のみ
- **チーム整合** - チーム構造/責務が不明な場合のみ
- **技術的考慮** - ユニット間でスケール/デプロイ要件が異なる場合のみ
- **ビジネスドメイン** - ドメイン境界や境界づけられたコンテキストが不明な場合のみ
- **コード構成（グリーンフィールド複数ユニットのみ）** - デプロイモデルとディレクトリ構成の嗜好を質問

## Step 4: Store UOW Plan
- Save as `aidlc-docs/inception/plans/unit-of-work-plan.md`
- Include all [Answer]: tags for user input
- Ensure plan covers all aspects of system decomposition
## ステップ 4: UOW 計画の保存
- `aidlc-docs/inception/plans/unit-of-work-plan.md` として保存
- ユーザー入力用に [Answer]: タグをすべて含める
- システム分解の全側面をカバーすることを確認

## ステップ 4: UOW 計画の保存
- `aidlc-docs/inception/plans/unit-of-work-plan.md` として保存
- ユーザー入力用に [Answer]: タグをすべて含める
- システム分解の全側面をカバーすることを確認

## Step 5: Request User Input
- Ask user to fill [Answer]: tags directly in the plan document
- Emphasize importance of decomposition decisions
- Provide clear instructions on completing the [Answer]: tags
## ステップ 5: ユーザー入力の依頼
- 計画文書内の [Answer]: タグに回答してもらう
- 分解判断の重要性を強調
- [Answer]: タグの記入方法を明確に案内

## ステップ 5: ユーザー入力の依頼
- 計画文書内の [Answer]: タグに回答してもらう
- 分解判断の重要性を強調
- [Answer]: タグの記入方法を明確に案内

## Step 6: Collect Answers
- Wait for user to provide answers to all questions using [Answer]: tags in the document
- Do not proceed until ALL [Answer]: tags are completed
- Review the document to ensure no [Answer]: tags are left blank
## ステップ 6: 回答収集
- 文書内の [Answer]: タグでの回答を待つ
- **すべて**の [Answer]: タグが埋まるまで進めない
- 空欄がないことを確認

## ステップ 6: 回答収集
- 文書内の [Answer]: タグでの回答を待つ
- **すべて**の [Answer]: タグが埋まるまで進めない
- 空欄がないことを確認

## Step 7: ANALYZE ANSWERS (MANDATORY)
Before proceeding, you MUST carefully review all user answers for:
- **Vague or ambiguous responses**: "mix of", "somewhere between", "not sure", "depends"
- **Undefined criteria or terms**: References to concepts without clear definitions
- **Contradictory answers**: Responses that conflict with each other
- **Missing generation details**: Answers that lack specific guidance
- **Answers that combine options**: Responses that merge different approaches without clear decision rules
## ステップ 7: 回答分析（必須）
進行前に必ず以下を確認:
- **曖昧/あいまいな回答**: "mix of", "somewhere between", "not sure", "depends"
- **未定義の基準/用語**: 定義がない概念への参照
- **矛盾する回答**: 回答同士の衝突
- **生成詳細の欠落**: 具体的な指針がない
- **選択肢の混在**: 判断ルールなくアプローチを混合

## ステップ 7: 回答分析（必須）
進行前に必ず以下を確認:
- **曖昧/あいまいな回答**: "mix of", "somewhere between", "not sure", "depends"
- **未定義の基準/用語**: 定義がない概念への参照
- **矛盾する回答**: 回答同士の衝突
- **生成詳細の欠落**: 具体的な指針がない
- **選択肢の混在**: 判断ルールなくアプローチを混合

## Step 8: MANDATORY Follow-up Questions
If the analysis in step 7 reveals ANY ambiguous answers, you MUST:
- Add specific follow-up questions to the plan document using [Answer]: tags
- DO NOT proceed to approval until all ambiguities are resolved
- Examples of required follow-ups:
  - "You mentioned 'mix of A and B' - what specific criteria should determine when to use A vs B?"
  - "You said 'somewhere between A and B' - can you define the exact middle ground approach?"
  - "You indicated 'not sure' - what additional information would help you decide?"
  - "You mentioned 'depends on complexity' - how do you define complexity levels?"
## ステップ 8: フォロー質問（必須）
ステップ 7 であいまいさがあれば必ず:
- [Answer]: タグで計画文書に具体的なフォロー質問を追加
- すべてのあいまいさが解消されるまで承認に進まない
- フォロー例:
  - "'mix of A and B' とありましたが、A と B を使い分ける具体的基準は？"
  - "'somewhere between A and B' の中間案を具体化してください"
  - "'not sure' とありました。判断に必要な追加情報は？"
  - "'depends on complexity' とありました。複雑さの定義と閾値は？"

## ステップ 8: フォロー質問（必須）
ステップ 7 であいまいさがあれば必ず:
- [Answer]: タグで計画文書に具体的なフォロー質問を追加
- すべてのあいまいさが解消されるまで承認に進まない
- フォロー例:
  - "'mix of A and B' とありましたが、A と B を使い分ける具体的基準は？"
  - "'somewhere between A and B' の中間案を具体化してください"
  - "'not sure' とありました。判断に必要な追加情報は？"
  - "'depends on complexity' とありました。複雑さの定義と閾値は？"

## Step 9: Request Approval
- Ask: "**Unit of work plan complete. Review the plan in aidlc-docs/inception/plans/unit-of-work-plan.md. Ready to proceed to generation?**"
- DO NOT PROCEED until user confirms
## ステップ 9: 承認依頼
- 質問: "**Unit of work plan complete. Review the plan in aidlc-docs/inception/plans/unit-of-work-plan.md. Ready to proceed to generation?**"
- ユーザー確認があるまで進めない

## ステップ 9: 承認依頼
- 質問: "**Unit of work plan complete. Review the plan in aidlc-docs/inception/plans/unit-of-work-plan.md. Ready to proceed to generation?**"
- ユーザー確認があるまで進めない

## Step 10: Log Approval
- Log prompt and response in audit.md with timestamp
- Use ISO 8601 timestamp format
- Include complete approval prompt text
## ステップ 10: 承認ログ
- audit.md にプロンプトと応答をタイムスタンプ付きで記録
- ISO 8601 形式を使用
- 承認プロンプト全文を含める

## ステップ 10: 承認ログ
- audit.md にプロンプトと応答をタイムスタンプ付きで記録
- ISO 8601 形式を使用
- 承認プロンプト全文を含める

## Step 11: Update Progress
- Mark Units Planning complete in aidlc-state.md
- Update the "Current Status" section
- Prepare for transition to Units Generation
## ステップ 11: 進捗更新
- aidlc-state.md で Units Planning を完了にする
- "Current Status" セクションを更新
- Units Generation への移行準備

## ステップ 11: 進捗更新
- aidlc-state.md で Units Planning を完了にする
- "Current Status" セクションを更新
- Units Generation への移行準備

---
---

---

# PART 2: GENERATION
# PART 2: GENERATION

# PART 2: GENERATION

## Step 12: Load Unit of Work Plan
- [ ] Read the complete plan from `aidlc-docs/inception/plans/unit-of-work-plan.md`
- [ ] Identify the next uncompleted step (first [ ] checkbox)
- [ ] Load the context and requirements for that step
## ステップ 12: Unit of Work 計画の読み込み
- [ ] `aidlc-docs/inception/plans/unit-of-work-plan.md` から完全な計画を読み込む
- [ ] 次の未完了ステップ（最初の [ ]）を特定
- [ ] 該当ステップのコンテキストと要件を読み込む

## ステップ 12: Unit of Work 計画の読み込み
- [ ] `aidlc-docs/inception/plans/unit-of-work-plan.md` から完全な計画を読み込む
- [ ] 次の未完了ステップ（最初の [ ]）を特定
- [ ] 該当ステップのコンテキストと要件を読み込む

## Step 13: Execute Current Step
- [ ] Perform exactly what the current step describes
- [ ] Generate unit artifacts as specified in the plan
- [ ] Follow the approved decomposition approach from Planning
- [ ] Use the criteria and boundaries specified in the plan
## ステップ 13: 現在ステップの実行
- [ ] 計画に記載された内容を正確に実行
- [ ] 計画で指定されたユニット成果物を生成
- [ ] Planning で承認済みの分解アプローチに従う
- [ ] 計画で指定された基準と境界を使用

## ステップ 13: 現在ステップの実行
- [ ] 計画に記載された内容を正確に実行
- [ ] 計画で指定されたユニット成果物を生成
- [ ] Planning で承認済みの分解アプローチに従う
- [ ] 計画で指定された基準と境界を使用

## Step 14: Update Progress
- [ ] Mark the completed step as [x] in the unit of work plan
- [ ] Update `aidlc-docs/aidlc-state.md` current status
- [ ] Save all generated artifacts
## ステップ 14: 進捗更新
- [ ] 完了ステップを Unit of Work 計画で [x] にする
- [ ] `aidlc-docs/aidlc-state.md` の現在状況を更新
- [ ] 生成成果物を保存

## ステップ 14: 進捗更新
- [ ] 完了ステップを Unit of Work 計画で [x] にする
- [ ] `aidlc-docs/aidlc-state.md` の現在状況を更新
- [ ] 生成成果物を保存

## Step 15: Continue or Complete
- [ ] If more steps remain, return to Step 12
- [ ] If all steps complete, verify units are ready for design stages
- [ ] Mark Units Generation stage as complete
## ステップ 15: 継続または完了
- [ ] 残りがあればステップ 12 に戻る
- [ ] すべて完了なら設計ステージに進める状態を確認
- [ ] Units Generation ステージを完了にする

## ステップ 15: 継続または完了
- [ ] 残りがあればステップ 12 に戻る
- [ ] すべて完了なら設計ステージに進める状態を確認
- [ ] Units Generation ステージを完了にする

## Step 16: Present Completion Message
## ステップ 16: 完了メッセージの提示

## ステップ 16: 完了メッセージの提示

```markdown
# 🔧 Units Generation Complete

[AI-generated summary of units and decomposition created in bullet points]

> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the units generation artifacts at: `aidlc-docs/inception/application-design/`

> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the units generation if required
> ✅ **Approve & Continue** - Approve units and proceed to **CONSTRUCTION PHASE**
```
```markdown
# 🔧 Units Generation Complete

[AI-generated summary of units and decomposition created in bullet points]

> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the units generation artifacts at: `aidlc-docs/inception/application-design/`

> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the units generation if required
> ✅ **Approve & Continue** - Approve units and proceed to **CONSTRUCTION PHASE**
```

```markdown
# 🔧 Units Generation Complete

[AI-generated summary of units and decomposition created in bullet points]

> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the units generation artifacts at: `aidlc-docs/inception/application-design/`

> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the units generation if required
> ✅ **Approve & Continue** - Approve units and proceed to **CONSTRUCTION PHASE**
```

## Step 17: Wait for Explicit Approval
- Do not proceed until the user explicitly approves the units generation
- Approval must be clear and unambiguous
- If user requests changes, update the units and repeat the approval process
## ステップ 17: 明示的承認待ち
- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があればユニットを更新し、承認プロセスを繰り返す

## ステップ 17: 明示的承認待ち
- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があればユニットを更新し、承認プロセスを繰り返す

## Step 18: Record Approval Response
- Log the user's approval response with timestamp in `aidlc-docs/audit.md`
- Include the exact user response text
- Mark the approval status clearly
## ステップ 18: 承認応答の記録
- ユーザーの承認回答を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ユーザーの回答を正確に記録
- 承認状態を明確に記載

## ステップ 18: 承認応答の記録
- ユーザーの承認回答を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ユーザーの回答を正確に記録
- 承認状態を明確に記載

## Step 19: Update Progress
- Mark Units Generation stage complete in `aidlc-docs/aidlc-state.md`
- Update the "Current Status" section
- Prepare for transition to CONSTRUCTION PHASE
## ステップ 19: 進捗更新
- `aidlc-docs/aidlc-state.md` で Units Generation を完了にする
- "Current Status" セクションを更新
- CONSTRUCTION フェーズへの移行準備

## ステップ 19: 進捗更新
- `aidlc-docs/aidlc-state.md` で Units Generation を完了にする
- "Current Status" セクションを更新
- CONSTRUCTION フェーズへの移行準備

---
---

---

## Critical Rules
## 重要ルール

## 重要ルール

### Planning Phase Rules
- Generate ONLY context-relevant questions
- Use [Answer]: tag format for all questions
- Analyze all answers for ambiguities before proceeding
- Resolve ALL ambiguities with follow-up questions
- Get explicit user approval before generation
### Planning フェーズのルール
- コンテキストに関係する質問のみ生成
- すべての質問は [Answer]: タグ形式
- 進行前に回答のあいまいさを分析
- すべてのあいまいさをフォロー質問で解消
- 生成前にユーザーの明示的承認を得る

### Planning フェーズのルール
- コンテキストに関係する質問のみ生成
- すべての質問は [Answer]: タグ形式
- 進行前に回答のあいまいさを分析
- すべてのあいまいさをフォロー質問で解消
- 生成前にユーザーの明示的承認を得る

### Generation Phase Rules
- **NO HARDCODED LOGIC**: Only execute what's written in the unit of work plan
- **FOLLOW PLAN EXACTLY**: Do not deviate from the step sequence
- **UPDATE CHECKBOXES**: Mark [x] immediately after completing each step
- **USE APPROVED APPROACH**: Follow the decomposition methodology from Planning
- **VERIFY COMPLETION**: Ensure all unit artifacts are complete before proceeding
### Generation フェーズのルール
- **ハードコード禁止**: Unit of Work 計画に書かれた内容のみ実行
- **計画に厳密に従う**: ステップ順序から逸脱しない
- **チェックボックス更新**: 完了直後に [x] を付ける
- **承認済みアプローチの使用**: Planning の分解方法に従う
- **完了検証**: 次へ進む前に成果物が完了しているか確認

### Generation フェーズのルール
- **ハードコード禁止**: Unit of Work 計画に書かれた内容のみ実行
- **計画に厳密に従う**: ステップ順序から逸脱しない
- **チェックボックス更新**: 完了直後に [x] を付ける
- **承認済みアプローチの使用**: Planning の分解方法に従う
- **完了検証**: 次へ進む前に成果物が完了しているか確認

## Completion Criteria
- All planning questions answered and ambiguities resolved
- User approval obtained for the plan
- All steps in unit of work plan marked [x]
- All unit artifacts generated according to plan:
  - `unit-of-work.md` with unit definitions
  - `unit-of-work-dependency.md` with dependency matrix
  - `unit-of-work-story-map.md` with story mappings
- Units verified and ready for per-unit design stages
## 完了条件
- 計画質問がすべて回答され、あいまいさが解消されている
- 計画へのユーザー承認が取得済み
- Unit of Work 計画の全ステップが [x]
- 計画どおりに成果物が生成されている:
  - `unit-of-work.md`（ユニット定義）
  - `unit-of-work-dependency.md`（依存マトリクス）
  - `unit-of-work-story-map.md`（ストーリーマッピング）
- ユニットが検証され、ユニットごとの設計ステージに進める状態

## 完了条件
- 計画質問がすべて回答され、あいまいさが解消されている
- 計画へのユーザー承認が取得済み
- Unit of Work 計画の全ステップが [x]
- 計画どおりに成果物が生成されている:
  - `unit-of-work.md`（ユニット定義）
  - `unit-of-work-dependency.md`（依存マトリクス）
  - `unit-of-work-story-map.md`（ストーリーマッピング）
- ユニットが検証され、ユニットごとの設計ステージに進める状態
