# Application Design - Detailed Steps
# Application Design - 詳細手順

# Application Design - 詳細手順

## Purpose
**High-level component identification and service layer design**
## 目的
**高レベルのコンポーネント特定とサービス層設計**

## 目的
**高レベルのコンポーネント特定とサービス層設計**

Application Design focuses on:
- Identifying main functional components and their responsibilities
- Defining component interfaces (not detailed business logic)
- Designing service layer for orchestration
- Establishing component dependencies and communication patterns
Application Design の焦点:
- 主要な機能コンポーネントと責務の特定
- コンポーネントインターフェイスの定義（詳細なビジネスロジックは除外）
- オーケストレーションのためのサービス層設計
- コンポーネント依存関係と通信パターンの確立

Application Design の焦点:
- 主要な機能コンポーネントと責務の特定
- コンポーネントインターフェイスの定義（詳細なビジネスロジックは除外）
- オーケストレーションのためのサービス層設計
- コンポーネント依存関係と通信パターンの確立

**Note**: Detailed business logic design happens later in Functional Design (per-unit, CONSTRUCTION phase)
**注記**: 詳細なビジネスロジック設計は後続の Functional Design（ユニットごと、CONSTRUCTION フェーズ）で行う

**注記**: 詳細なビジネスロジック設計は後続の Functional Design（ユニットごと、CONSTRUCTION フェーズ）で行う

## Prerequisites
- Context Assessment must be complete
- Requirements Assessment recommended (provides functional context)
- Story Development recommended (user stories guide design decisions)
- Execution plan must indicate Application Design stage should execute
## 前提条件
- Context Assessment が完了していること
- Requirements Assessment を推奨（機能コンテキストを提供）
- Story Development を推奨（ユーザーストーリーが設計判断を導く）
- 実行計画で Application Design が実行対象となっていること

## 前提条件
- Context Assessment が完了していること
- Requirements Assessment を推奨（機能コンテキストを提供）
- Story Development を推奨（ユーザーストーリーが設計判断を導く）
- 実行計画で Application Design が実行対象となっていること

## Step-by-Step Execution
## 実行手順

## 実行手順

### 1. Analyze Context
- Read `aidlc-docs/inception/requirements/requirements.md` and `aidlc-docs/inception/user-stories/stories.md`
- Identify key business capabilities and functional areas
- Determine design scope and complexity
### 1. コンテキスト分析
- `aidlc-docs/inception/requirements/requirements.md` と `aidlc-docs/inception/user-stories/stories.md` を読む
- 主要ビジネス能力と機能領域を特定
- 設計のスコープと複雑さを判断

### 1. コンテキスト分析
- `aidlc-docs/inception/requirements/requirements.md` と `aidlc-docs/inception/user-stories/stories.md` を読む
- 主要ビジネス能力と機能領域を特定
- 設計のスコープと複雑さを判断

### 2. Create Application Design Plan
- Generate plan with checkboxes [] for application design
- Focus on components, responsibilities, methods, business rules, and services
- Each step and sub-step should have a checkbox []
### 2. Application Design 計画の作成
- アプリ設計用のチェックボックス [] 付き計画を作成
- コンポーネント、責務、メソッド、ビジネスルール、サービスに焦点
- 各ステップとサブステップにチェックボックス [] を付ける

### 2. Application Design 計画の作成
- アプリ設計用のチェックボックス [] 付き計画を作成
- コンポーネント、責務、メソッド、ビジネスルール、サービスに焦点
- 各ステップとサブステップにチェックボックス [] を付ける

### 3. Include Mandatory Design Artifacts in Plan
- **ALWAYS** include these mandatory artifacts in the design plan:
  - [ ] Generate components.md with component definitions and high-level responsibilities
  - [ ] Generate component-methods.md with method signatures (business rules detailed later in Functional Design)
  - [ ] Generate services.md with service definitions and orchestration patterns
  - [ ] Generate component-dependency.md with dependency relationships and communication patterns
  - [ ] Validate design completeness and consistency
### 3. 必須設計成果物を計画に含める
- **必ず** 次の成果物を計画に含める:
  - [ ] コンポーネント定義と高レベル責務を含む components.md を生成
  - [ ] メソッドシグネチャを含む component-methods.md を生成（詳細ルールは後の Functional Design）
  - [ ] サービス定義とオーケストレーションパターンを含む services.md を生成
  - [ ] 依存関係と通信パターンを含む component-dependency.md を生成
  - [ ] 設計の完全性と一貫性を検証

### 3. 必須設計成果物を計画に含める
- **必ず** 次の成果物を計画に含める:
  - [ ] コンポーネント定義と高レベル責務を含む components.md を生成
  - [ ] メソッドシグネチャを含む component-methods.md を生成（詳細ルールは後の Functional Design）
  - [ ] サービス定義とオーケストレーションパターンを含む services.md を生成
  - [ ] 依存関係と通信パターンを含む component-dependency.md を生成
  - [ ] 設計の完全性と一貫性を検証

### 4. Generate Context-Appropriate Questions
**DIRECTIVE**: Analyze the requirements and stories to generate ONLY questions relevant to THIS specific application design. Use the categories below as inspiration, NOT as a mandatory checklist. Skip entire categories if not applicable.
### 4. コンテキストに適した質問の生成
**指示**: 要件とストーリーを分析し、このアプリ設計に**関係する質問のみ**を作成する。以下カテゴリは参考であり、必須チェックリストではない。該当しないカテゴリはスキップしてよい。

### 4. コンテキストに適した質問の生成
**指示**: 要件とストーリーを分析し、このアプリ設計に**関係する質問のみ**を作成する。以下カテゴリは参考であり、必須チェックリストではない。該当しないカテゴリはスキップしてよい。

- EMBED questions using [Answer]: tag format
- Focus on ambiguities and missing information specific to this context
- Generate questions only where user input is needed for design decisions
- [Answer]: タグ形式で質問を埋め込む
- この文脈特有のあいまいさや欠落情報に焦点
- 設計判断にユーザー入力が必要な場合のみ質問を作成

- [Answer]: タグ形式で質問を埋め込む
- この文脈特有のあいまいさや欠落情報に焦点
- 設計判断にユーザー入力が必要な場合のみ質問を作成

**Example question categories** (adapt as needed):
- **Component Identification** - Only if component boundaries or organization is unclear
- **Component Methods** - Only if method signatures need clarification (detailed business rules come later)
- **Service Layer Design** - Only if service orchestration or boundaries are ambiguous
- **Component Dependencies** - Only if communication patterns or dependency management is unclear
- **Design Patterns** - Only if architectural style or pattern choice needs user input
**質問カテゴリ例**（必要に応じて調整）:
- **コンポーネント特定** - 境界や構成が不明な場合のみ
- **コンポーネントメソッド** - シグネチャの明確化が必要な場合のみ
- **サービス層設計** - オーケストレーションや境界が不明な場合のみ
- **コンポーネント依存** - 通信/依存管理が不明な場合のみ
- **設計パターン** - アーキテクチャ/パターン選択に入力が必要な場合のみ

**質問カテゴリ例**（必要に応じて調整）:
- **コンポーネント特定** - 境界や構成が不明な場合のみ
- **コンポーネントメソッド** - シグネチャの明確化が必要な場合のみ
- **サービス層設計** - オーケストレーションや境界が不明な場合のみ
- **コンポーネント依存** - 通信/依存管理が不明な場合のみ
- **設計パターン** - アーキテクチャ/パターン選択に入力が必要な場合のみ

### 5. Store Application Design Plan
- Save as `aidlc-docs/inception/plans/application-design-plan.md`
- Include all [Answer]: tags for user input
- Ensure plan covers all design aspects
### 5. Application Design 計画の保存
- `aidlc-docs/inception/plans/application-design-plan.md` として保存
- ユーザー入力用に [Answer]: タグをすべて含める
- 設計の全側面をカバーすることを確認

### 5. Application Design 計画の保存
- `aidlc-docs/inception/plans/application-design-plan.md` として保存
- ユーザー入力用に [Answer]: タグをすべて含める
- 設計の全側面をカバーすることを確認

### 6. Request User Input
- Ask user to fill [Answer]: tags directly in the plan document
- Emphasize importance of design decisions
- Provide clear instructions on completing the [Answer]: tags
### 6. ユーザー入力の依頼
- 計画文書内の [Answer]: タグに回答してもらう
- 設計判断の重要性を強調
- [Answer]: タグの記入方法を明確に案内

### 6. ユーザー入力の依頼
- 計画文書内の [Answer]: タグに回答してもらう
- 設計判断の重要性を強調
- [Answer]: タグの記入方法を明確に案内

### 7. Collect Answers
- Wait for user to provide answers to all questions using [Answer]: tags in the document
- Do not proceed until ALL [Answer]: tags are completed
- Review the document to ensure no [Answer]: tags are left blank
### 7. 回答収集
- 文書内の [Answer]: タグでの回答を待つ
- **すべて**の [Answer]: タグが埋まるまで進めない
- 空欄がないことを確認

### 7. 回答収集
- 文書内の [Answer]: タグでの回答を待つ
- **すべて**の [Answer]: タグが埋まるまで進めない
- 空欄がないことを確認

### 8. ANALYZE ANSWERS (MANDATORY)
Before proceeding, you MUST carefully review all user answers for:
- **Vague or ambiguous responses**: "mix of", "somewhere between", "not sure", "depends"
- **Undefined criteria or terms**: References to concepts without clear definitions
- **Contradictory answers**: Responses that conflict with each other
- **Missing design details**: Answers that lack specific guidance
- **Answers that combine options**: Responses that merge different approaches without clear decision rules
### 8. 回答分析（必須）
進行前に必ず以下を確認:
- **曖昧/あいまいな回答**: "mix of", "somewhere between", "not sure", "depends"
- **未定義の基準/用語**: 定義がない概念への参照
- **矛盾する回答**: 回答同士の衝突
- **設計詳細の欠落**: 具体的な指針がない
- **選択肢の混在**: 判断ルールなくアプローチを混合

### 8. 回答分析（必須）
進行前に必ず以下を確認:
- **曖昧/あいまいな回答**: "mix of", "somewhere between", "not sure", "depends"
- **未定義の基準/用語**: 定義がない概念への参照
- **矛盾する回答**: 回答同士の衝突
- **設計詳細の欠落**: 具体的な指針がない
- **選択肢の混在**: 判断ルールなくアプローチを混合

### 9. MANDATORY Follow-up Questions
If the analysis in step 8 reveals ANY ambiguous answers, you MUST:
- Add specific follow-up questions to the plan document using [Answer]: tags
- DO NOT proceed to approval until all ambiguities are resolved
- Examples of required follow-ups:
  - "You mentioned 'mix of A and B' - what specific criteria should determine when to use A vs B?"
  - "You said 'somewhere between A and B' - can you define the exact middle ground approach?"
  - "You indicated 'not sure' - what additional information would help you decide?"
  - "You mentioned 'depends on complexity' - how do you define complexity levels?"
### 9. フォロー質問（必須）
ステップ 8 であいまいさがあれば必ず:
- [Answer]: タグを使って計画文書に具体的なフォロー質問を追加
- すべてのあいまいさが解消されるまで承認に進まない
- フォロー例:
  - "'mix of A and B' とありましたが、A と B を使い分ける具体的基準は？"
  - "'somewhere between A and B' の中間案を具体化してください"
  - "'not sure' とありました。判断に必要な追加情報は？"
  - "'depends on complexity' とありました。複雑さの定義と閾値は？"

### 9. フォロー質問（必須）
ステップ 8 であいまいさがあれば必ず:
- [Answer]: タグを使って計画文書に具体的なフォロー質問を追加
- すべてのあいまいさが解消されるまで承認に進まない
- フォロー例:
  - "'mix of A and B' とありましたが、A と B を使い分ける具体的基準は？"
  - "'somewhere between A and B' の中間案を具体化してください"
  - "'not sure' とありました。判断に必要な追加情報は？"
  - "'depends on complexity' とありました。複雑さの定義と閾値は？"

### 10. Generate Application Design Artifacts
- Execute the approved plan to generate design artifacts
- Create `aidlc-docs/inception/application-design/components.md` with:
  - Component name and purpose
  - Component responsibilities
  - Component interfaces
- Create `aidlc-docs/inception/application-design/component-methods.md` with:
  - Method signatures for each component
  - High-level purpose of each method
  - Input/output types
  - Note: Detailed business rules will be defined in Functional Design (per-unit, CONSTRUCTION phase)
- Create `aidlc-docs/inception/application-design/services.md` with:
  - Service definitions
  - Service responsibilities
  - Service interactions and orchestration
- Create `aidlc-docs/inception/application-design/component-dependency.md` with:
  - Dependency matrix showing relationships
  - Communication patterns between components
  - Data flow diagrams
### 10. Application Design 成果物の生成
- 承認済み計画を実行して成果物を生成
- `aidlc-docs/inception/application-design/components.md` を作成:
  - コンポーネント名と目的
  - コンポーネント責務
  - コンポーネントインターフェイス
- `aidlc-docs/inception/application-design/component-methods.md` を作成:
  - 各コンポーネントのメソッドシグネチャ
  - 各メソッドの高レベル目的
  - 入出力型
  - 注記: 詳細ビジネスルールは Functional Design（ユニットごと、CONSTRUCTION フェーズ）で定義
- `aidlc-docs/inception/application-design/services.md` を作成:
  - サービス定義
  - サービス責務
  - サービスの相互作用とオーケストレーション
- `aidlc-docs/inception/application-design/component-dependency.md` を作成:
  - 関係を示す依存マトリクス
  - コンポーネント間の通信パターン
  - データフロー図

### 10. Application Design 成果物の生成
- 承認済み計画を実行して成果物を生成
- `aidlc-docs/inception/application-design/components.md` を作成:
  - コンポーネント名と目的
  - コンポーネント責務
  - コンポーネントインターフェイス
- `aidlc-docs/inception/application-design/component-methods.md` を作成:
  - 各コンポーネントのメソッドシグネチャ
  - 各メソッドの高レベル目的
  - 入出力型
  - 注記: 詳細ビジネスルールは Functional Design（ユニットごと、CONSTRUCTION フェーズ）で定義
- `aidlc-docs/inception/application-design/services.md` を作成:
  - サービス定義
  - サービス責務
  - サービスの相互作用とオーケストレーション
- `aidlc-docs/inception/application-design/component-dependency.md` を作成:
  - 関係を示す依存マトリクス
  - コンポーネント間の通信パターン
  - データフロー図

### 11. Log Approval
- Log approval prompt with timestamp in `aidlc-docs/audit.md`
- Include complete approval prompt text
- Use ISO 8601 timestamp format
### 11. 承認ログ
- 承認プロンプト全文を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ISO 8601 形式を使用

### 11. 承認ログ
- 承認プロンプト全文を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ISO 8601 形式を使用

### 12. Present Completion Message
### 12. 完了メッセージの提示

### 12. 完了メッセージの提示

```markdown
# 🏗️ Application Design Complete

[AI-generated summary of application design artifacts created in bullet points]

> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the application design artifacts at: `aidlc-docs/inception/application-design/`

> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the application design if required
> [IF Units Generation is skipped:]
> 📝 **Add Units Generation** - Choose to include **Units Generation** stage (currently skipped)
> ✅ **Approve & Continue** - Approve design and proceed to **[Units Generation/CONSTRUCTION PHASE]**
```
```markdown
# 🏗️ Application Design Complete

[AI-generated summary of application design artifacts created in bullet points]

> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the application design artifacts at: `aidlc-docs/inception/application-design/`

> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the application design if required
> [IF Units Generation is skipped:]
> 📝 **Add Units Generation** - Choose to include **Units Generation** stage (currently skipped)
> ✅ **Approve & Continue** - Approve design and proceed to **[Units Generation/CONSTRUCTION PHASE]**
```

```markdown
# 🏗️ Application Design Complete

[AI-generated summary of application design artifacts created in bullet points]

> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the application design artifacts at: `aidlc-docs/inception/application-design/`

> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the application design if required
> [IF Units Generation is skipped:]
> 📝 **Add Units Generation** - Choose to include **Units Generation** stage (currently skipped)
> ✅ **Approve & Continue** - Approve design and proceed to **[Units Generation/CONSTRUCTION PHASE]**
```

### 13. Wait for Explicit Approval
- Do not proceed until the user explicitly approves the application design
- Approval must be clear and unambiguous
- If user requests changes, update the design and repeat the approval process
### 13. 明示的承認待ち
- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があれば設計を更新し、承認プロセスを繰り返す

### 13. 明示的承認待ち
- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があれば設計を更新し、承認プロセスを繰り返す

### 14. Record Approval Response
- Log the user's approval response with timestamp in `aidlc-docs/audit.md`
- Include the exact user response text
- Mark the approval status clearly
### 14. 承認応答の記録
- ユーザーの承認回答を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ユーザーの回答を正確に記録
- 承認状態を明確に記載

### 14. 承認応答の記録
- ユーザーの承認回答を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ユーザーの回答を正確に記録
- 承認状態を明確に記載

### 15. Update Progress
- Mark Application Design stage complete in `aidlc-docs/aidlc-state.md`
- Update the "Current Status" section
- Prepare for transition to next stage
### 15. 進捗更新
- `aidlc-docs/aidlc-state.md` で Application Design を完了にする
- "Current Status" セクションを更新
- 次ステージへの移行準備

### 15. 進捗更新
- `aidlc-docs/aidlc-state.md` で Application Design を完了にする
- "Current Status" セクションを更新
- 次ステージへの移行準備
