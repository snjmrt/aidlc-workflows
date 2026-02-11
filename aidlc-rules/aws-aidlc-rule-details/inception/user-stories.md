# User Stories - Detailed Steps

# User Stories - 詳細手順

# User Stories - 詳細手順

## Purpose

**Convert requirements into user-centered stories with acceptance criteria**

## 目的

**要件をユーザー中心のストーリーと受け入れ基準に変換する**

User Stories focus on:

- Translating business requirements into user-centered narratives
- Defining clear acceptance criteria for each story
- Creating user personas that represent different stakeholder types
- Establishing shared understanding across teams
- Providing testable specifications for implementation

User Stories の焦点:

- ビジネス要件をユーザー中心の物語に変換
- 各ストーリーの明確な受け入れ基準を定義
- 異なるステークホルダーを表すユーザーペルソナを作成
- チーム間の共通理解を確立
- 実装のためのテスト可能な仕様を提供

## Prerequisites

- Workspace Detection must be complete
- Requirements Analysis recommended (can reference requirements if available)
- Workflow Planning must indicate User Stories stage should execute

## 前提条件

- Workspace Detection が完了していること
- Requirements Analysis を推奨（利用可能なら要件を参照）
- Workflow Planning で User Stories ステージの実行が指定されていること

## Intelligent Assessment Guidelines

## インテリジェント評価ガイドライン

## インテリジェント評価ガイドライン

**WHEN TO EXECUTE USER STORIES**: Use this enhanced assessment before proceeding:
**User Stories を実行するタイミング**: 次の強化評価を実施してから進める:

**User Stories を実行するタイミング**: 次の強化評価を実施してから進める:

### High Priority Execution (ALWAYS Execute)

- **New User Features**: Any new functionality users will directly interact with
- **User Experience Changes**: Modifications to existing user workflows or interfaces
- **Multi-Persona Systems**: Applications serving different types of users
- **Customer-Facing APIs**: Services that external users or systems will consume
- **Complex Business Logic**: Requirements with multiple scenarios or business rules
- **Cross-Team Projects**: Work requiring shared understanding across multiple teams

### 高優先度の実行（常に実行）

- **新しいユーザー機能**: ユーザーが直接操作する新機能
- **ユーザー体験の変更**: 既存のワークフローや UI 変更
- **複数ペルソナのシステム**: 異なるユーザー種別を扱うアプリ
- **顧客向け API**: 外部ユーザー/システムが利用するサービス
- **複雑なビジネスロジック**: 複数シナリオ/ルールを含む要件
- **横断チームプロジェクト**: 複数チームの共通理解が必要

### 高優先度の実行（常に実行）

- **新しいユーザー機能**: ユーザーが直接操作する新機能
- **ユーザー体験の変更**: 既存のワークフローや UI 変更
- **複数ペルソナのシステム**: 異なるユーザー種別を扱うアプリ
- **顧客向け API**: 外部ユーザー/システムが利用するサービス
- **複雑なビジネスロジック**: 複数シナリオ/ルールを含む要件
- **横断チームプロジェクト**: 複数チームの共通理解が必要

### Medium Priority Execution (Assess Complexity)

- **Backend User Impact**: Internal changes that indirectly affect user experience
- **Performance Improvements**: Enhancements with user-visible benefits
- **Integration Work**: Connecting systems that affect user workflows
- **Data Changes**: Modifications affecting user data, reports, or analytics
- **Security Enhancements**: Changes affecting user authentication or permissions

### 中優先度の実行（複雑さで判断）

- **バックエンド影響**: 間接的にユーザー体験に影響
- **性能改善**: ユーザーに見える利点がある改善
- **統合作業**: ユーザーのワークフローに影響する連携
- **データ変更**: ユーザーデータ/レポート/分析への影響
- **セキュリティ強化**: 認証/権限に影響する変更

### 中優先度の実行（複雑さで判断）

- **バックエンド影響**: 間接的にユーザー体験に影響
- **性能改善**: ユーザーに見える利点がある改善
- **統合作業**: ユーザーのワークフローに影響する連携
- **データ変更**: ユーザーデータ/レポート/分析への影響
- **セキュリティ強化**: 認証/権限に影響する変更

### Complexity Assessment Factors

For medium priority cases, execute user stories if ANY of these apply:

- **Scope**: Changes span multiple components or user touchpoints
- **Ambiguity**: Requirements have unclear aspects that stories could clarify
- **Risk**: High business impact or potential for misunderstanding
- **Stakeholders**: Multiple business stakeholders involved in requirements
- **Testing**: User acceptance testing will be required
- **Options**: Multiple valid implementation approaches exist

### 複雑性評価要因

中優先度の場合、以下に該当すれば実行:

- **スコープ**: 複数コンポーネントまたはユーザー接点にまたがる
- **あいまいさ**: ストーリーで明確化できる不明点がある
- **リスク**: 事業影響が大きい/誤解の可能性
- **ステークホルダー**: 複数の関係者が関与
- **テスト**: ユーザー受け入れテストが必要
- **選択肢**: 有効な実装アプローチが複数存在

### 複雑性評価要因

中優先度の場合、以下に該当すれば実行:

- **スコープ**: 複数コンポーネントまたはユーザー接点にまたがる
- **あいまいさ**: ストーリーで明確化できる不明点がある
- **リスク**: 事業影響が大きい/誤解の可能性
- **ステークホルダー**: 複数の関係者が関与
- **テスト**: ユーザー受け入れテストが必要
- **選択肢**: 有効な実装アプローチが複数存在

### Skip Only For Simple Cases

- **Pure Refactoring**: Internal code improvements with zero user impact
- **Isolated Bug Fixes**: Simple, well-defined fixes with clear scope
- **Infrastructure Only**: Changes with no user-facing effects
- **Developer Tooling**: Build processes, CI/CD, or development environment changes
- **Documentation**: Updates that don't affect functionality

### 単純ケースのみスキップ

- **純粋なリファクタ**: ユーザー影響ゼロの内部改善
- **限定的なバグ修正**: スコープが明確な簡易修正
- **インフラのみ**: ユーザー向け影響なし
- **開発者ツール**: ビルド/CI/CD/開発環境の変更
- **ドキュメント**: 機能に影響しない更新

### 単純ケースのみスキップ

- **純粋なリファクタ**: ユーザー影響ゼロの内部改善
- **限定的なバグ修正**: スコープが明確な簡易修正
- **インフラのみ**: ユーザー向け影響なし
- **開発者ツール**: ビルド/CI/CD/開発環境の変更
- **ドキュメント**: 機能に影響しない更新

### Default Decision Rule

**When in doubt, include user stories AND ask clarifying questions.** The overhead of creating comprehensive stories with proper clarification is typically outweighed by the benefits of:

- Clearer requirements understanding
- Better team alignment
- Improved testing criteria
- Enhanced stakeholder communication
- Reduced implementation risks
- Fewer costly changes during development
- Better user experience outcomes

### デフォルト判断ルール

**迷ったら User Stories を含め、確認質問を行う。** 包括的なストーリー作成は、次の利点により負担を上回る:

- 要件理解の明確化
- チームの整合性向上
- テスト基準の改善
- ステークホルダー連携の強化
- 実装リスクの低減
- 手戻りの削減
- より良いユーザー体験

### デフォルト判断ルール

**迷ったら User Stories を含め、確認質問を行う。** 包括的なストーリー作成は、次の利点により負担を上回る:

- 要件理解の明確化
- チームの整合性向上
- テスト基準の改善
- ステークホルダー連携の強化
- 実装リスクの低減
- 手戻りの削減
- より良いユーザー体験

---

---

---

# PART 1: PLANNING

# PART 1: PLANNING

# PART 1: PLANNING

## Step 1: Validate User Stories Need (MANDATORY)

## ステップ 1: User Stories の必要性を検証（必須）

## ステップ 1: User Stories の必要性を検証（必須）

**CRITICAL**: Before proceeding with user stories, perform this assessment:
**重要**: User Stories を進める前に、次の評価を行う:

**重要**: User Stories を進める前に、次の評価を行う:

### Assessment Process

1. **Analyze Request Context**:
   - Review the original user request and requirements
   - Identify user-facing vs internal-only changes
   - Assess complexity and scope of the work
   - Evaluate business stakeholder involvement

### 評価プロセス

1. **要求コンテキストを分析**:
   - 元のユーザー要求と要件を確認
   - ユーザー向け変更と内部変更を区別
   - 作業の複雑さとスコープを評価
   - ビジネス関係者の関与を評価

### 評価プロセス

1. **要求コンテキストを分析**:
   - 元のユーザー要求と要件を確認
   - ユーザー向け変更と内部変更を区別
   - 作業の複雑さとスコープを評価
   - ビジネス関係者の関与を評価

2. **Apply Assessment Criteria**:
   - Check against High Priority indicators (always execute)
   - Evaluate Medium Priority factors (complexity-based decision)
   - Confirm this isn't a simple case that should be skipped
3. **評価基準の適用**:
   - 高優先度指標を確認（常に実行）
   - 中優先度要因を評価（複雑性で判断）
   - 単純ケースでスキップすべきでないことを確認

4. **評価基準の適用**:
   - 高優先度指標を確認（常に実行）
   - 中優先度要因を評価（複雑性で判断）
   - 単純ケースでスキップすべきでないことを確認

5. **Document Assessment Decision**:
   - Create `aidlc-docs/inception/plans/user-stories-assessment.md`
   - Include reasoning for why user stories are valuable for this request
   - Reference specific assessment criteria that apply
   - Explain expected benefits (clarity, testing, stakeholder alignment)
6. **評価結果を文書化**:
   - `aidlc-docs/inception/plans/user-stories-assessment.md` を作成
   - User Stories の価値がある理由を記載
   - 適用された評価基準を明記
   - 期待される利点（明確化、テスト、整合性）を説明

7. **評価結果を文書化**:
   - `aidlc-docs/inception/plans/user-stories-assessment.md` を作成
   - User Stories の価値がある理由を記載
   - 適用された評価基準を明記
   - 期待される利点（明確化、テスト、整合性）を説明

8. **Proceed Only If Justified**:
   - User stories must add clear value to the project
   - Assessment must show concrete benefits outweigh overhead
   - Decision should be defensible to project stakeholders
9. **正当化できる場合のみ進行**:
   - User Stories が明確な価値を提供すること
   - 効果が負担を上回ることを示す
   - ステークホルダーに説明可能な判断であること

10. **正当化できる場合のみ進行**:
    - User Stories が明確な価値を提供すること
    - 効果が負担を上回ることを示す
    - ステークホルダーに説明可能な判断であること

### Assessment Documentation Template

```markdown
# User Stories Assessment

## Request Analysis

- **Original Request**: [Brief summary]
- **User Impact**: [Direct/Indirect/None]
- **Complexity Level**: [Simple/Medium/Complex]
- **Stakeholders**: [List involved parties]

## Assessment Criteria Met

- [ ] High Priority: [List applicable criteria]
- [ ] Medium Priority: [List applicable criteria with complexity justification]
- [ ] Benefits: [Expected value from user stories]

## Decision

**Execute User Stories**: [Yes/No]
**Reasoning**: [Detailed justification]

## Expected Outcomes

- [List specific benefits user stories will provide]
- [How stories will improve project success]
```

### 評価ドキュメントテンプレート

```markdown
# User Stories Assessment

## Request Analysis

- **Original Request**: [Brief summary]
- **User Impact**: [Direct/Indirect/None]
- **Complexity Level**: [Simple/Medium/Complex]
- **Stakeholders**: [List involved parties]

## Assessment Criteria Met

- [ ] High Priority: [List applicable criteria]
- [ ] Medium Priority: [List applicable criteria with complexity justification]
- [ ] Benefits: [Expected value from user stories]

## Decision

**Execute User Stories**: [Yes/No]
**Reasoning**: [Detailed justification]

## Expected Outcomes

- [List specific benefits user stories will provide]
- [How stories will improve project success]
```

### 評価ドキュメントテンプレート

```markdown
# User Stories Assessment

## Request Analysis

- **Original Request**: [Brief summary]
- **User Impact**: [Direct/Indirect/None]
- **Complexity Level**: [Simple/Medium/Complex]
- **Stakeholders**: [List involved parties]

## Assessment Criteria Met

- [ ] High Priority: [List applicable criteria]
- [ ] Medium Priority: [List applicable criteria with complexity justification]
- [ ] Benefits: [Expected value from user stories]

## Decision

**Execute User Stories**: [Yes/No]
**Reasoning**: [Detailed justification]

## Expected Outcomes

- [List specific benefits user stories will provide]
- [How stories will improve project success]
```

## Step 2: Create Story Plan

- Assume the role of a product owner
- Generate a comprehensive plan with step-by-step execution checklist for story development
- Each step and sub-step should have a checkbox []
- Focus on methodology and approach for converting requirements into user stories

## ステップ 2: ストーリープランの作成

- プロダクトオーナーの役割を担う
- ストーリー開発のためのステップバイステップの実行チェックリストを含む包括的計画を作成
- 各ステップとサブステップにチェックボックス [] を付ける
- 要件をユーザーストーリーに変換する方法論とアプローチに集中

## ステップ 2: ストーリープランの作成

- プロダクトオーナーの役割を担う
- ストーリー開発のためのステップバイステップの実行チェックリストを含む包括的計画を作成
- 各ステップとサブステップにチェックボックス [] を付ける
- 要件をユーザーストーリーに変換する方法論とアプローチに集中

## Step 3: Generate Context-Appropriate Questions

**DIRECTIVE**: Thoroughly analyze the requirements and context to identify ALL areas where clarification would improve story quality and team understanding. Be proactive in asking questions to ensure comprehensive user story development.

## ステップ 3: コンテキストに合う質問の生成

**指示**: 要件とコンテキストを徹底分析し、ストーリー品質とチーム理解を高めるための確認が必要な領域をすべて特定する。積極的に質問を行う。

## ステップ 3: コンテキストに合う質問の生成

**指示**: 要件とコンテキストを徹底分析し、ストーリー品質とチーム理解を高めるための確認が必要な領域をすべて特定する。積極的に質問を行う。

**CRITICAL**: Default to asking questions when there is ANY ambiguity or missing detail that could affect story quality. It's better to ask too many questions than to create incomplete or unclear stories.
**重要**: あいまいさや欠落が少しでもあれば質問することをデフォルトにする。不完全/不明瞭なストーリーを作るより、質問しすぎる方がよい。

**重要**: あいまいさや欠落が少しでもあれば質問することをデフォルトにする。不完全/不明瞭なストーリーを作るより、質問しすぎる方がよい。

**See `common/question-format-guide.md` for question formatting rules**
**質問フォーマットは `common/question-format-guide.md` を参照**

**質問フォーマットは `common/question-format-guide.md` を参照**

- EMBED questions using [Answer]: tag format
- Focus on ANY ambiguities, missing information, or areas needing clarification
- Generate questions wherever user input would improve story creation decisions
- **When in doubt, ask the question** - overconfidence leads to poor stories
- [Answer]: タグ形式で質問を埋め込む
- あいまい/欠落/確認が必要な領域に焦点
- ユーザー入力が意思決定に有益なら質問を生成
- **迷ったら質問する** - 過信は不十分なストーリーを生む

- [Answer]: タグ形式で質問を埋め込む
- あいまい/欠落/確認が必要な領域に焦点
- ユーザー入力が意思決定に有益なら質問を生成
- **迷ったら質問する** - 過信は不十分なストーリーを生む

**Question categories to evaluate** (consider ALL categories):

- **User Personas** - Ask about user types, roles, characteristics, and motivations
- **Story Granularity** - Ask about appropriate level of detail, story size, and breakdown approach
- **Story Format** - Ask about format preferences, template usage, and documentation standards
- **Breakdown Approach** - Ask about organization method, prioritization, and grouping strategies
- **Acceptance Criteria** - Ask about detail level, format, testing approach, and validation methods
- **User Journeys** - Ask about user workflows, interaction patterns, and experience flows
- **Business Context** - Ask about business goals, success metrics, and stakeholder needs
- **Technical Constraints** - Ask about technical limitations, integration requirements, and system boundaries
  **評価すべき質問カテゴリ**（すべて考慮）:
- **ユーザーペルソナ** - ユーザー種別、役割、特徴、動機
- **ストーリー粒度** - 詳細レベル、サイズ、分解方針
- **ストーリー形式** - フォーマット嗜好、テンプレート、記述基準
- **分解アプローチ** - 整理方法、優先度、グルーピング
- **受け入れ基準** - 詳細度、形式、テスト方法、検証方法
- **ユーザージャーニー** - ワークフロー、操作パターン、体験フロー
- **ビジネス文脈** - 目標、成功指標、関係者ニーズ
- **技術的制約** - 技術制限、統合要件、システム境界

**評価すべき質問カテゴリ**（すべて考慮）:

- **ユーザーペルソナ** - ユーザー種別、役割、特徴、動機
- **ストーリー粒度** - 詳細レベル、サイズ、分解方針
- **ストーリー形式** - フォーマット嗜好、テンプレート、記述基準
- **分解アプローチ** - 整理方法、優先度、グルーピング
- **受け入れ基準** - 詳細度、形式、テスト方法、検証方法
- **ユーザージャーニー** - ワークフロー、操作パターン、体験フロー
- **ビジネス文脈** - 目標、成功指標、関係者ニーズ
- **技術的制約** - 技術制限、統合要件、システム境界

## Step 4: Include Mandatory Story Artifacts in Plan

- **ALWAYS** include these mandatory artifacts in the story plan:
  - [ ] Generate stories.md with user stories following INVEST criteria
  - [ ] Generate personas.md with user archetypes and characteristics
  - [ ] Ensure stories are Independent, Negotiable, Valuable, Estimable, Small, Testable
  - [ ] Include acceptance criteria for each story
  - [ ] Map personas to relevant user stories

## ステップ 4: 必須ストーリー成果物を計画に含める

- **常に** 次の必須成果物を含める:
  - [ ] INVEST 基準に従った user stories を含む stories.md を生成
  - [ ] ユーザーアーキタイプと特徴を含む personas.md を生成
  - [ ] ストーリーが Independent, Negotiable, Valuable, Estimable, Small, Testable であることを確認
  - [ ] 各ストーリーに受け入れ基準を含める
  - [ ] ペルソナと関連ストーリーをマッピング

## ステップ 4: 必須ストーリー成果物を計画に含める

- **常に** 次の必須成果物を含める:
  - [ ] INVEST 基準に従った user stories を含む stories.md を生成
  - [ ] ユーザーアーキタイプと特徴を含む personas.md を生成
  - [ ] ストーリーが Independent, Negotiable, Valuable, Estimable, Small, Testable であることを確認
  - [ ] 各ストーリーに受け入れ基準を含める
  - [ ] ペルソナと関連ストーリーをマッピング

## Step 5: Present Story Options

- Include different approaches for story breakdown in the plan document:
  - **User Journey-Based**: Stories follow user workflows and interactions
  - **Feature-Based**: Stories organized around system features and capabilities
  - **Persona-Based**: Stories grouped by different user types and their needs
  - **Domain-Based**: Stories organized around business domains or contexts
  - **Epic-Based**: Stories structured as hierarchical epics with sub-stories
- Explain trade-offs and benefits of each approach
- Allow for hybrid approaches with clear decision criteria

## ステップ 5: ストーリー分解の選択肢提示

- 計画文書に分解アプローチの選択肢を含める:
  - **ユーザージャーニー基準**: ユーザーのワークフロー/操作に沿う
  - **機能基準**: 機能や能力で整理
  - **ペルソナ基準**: ユーザー種別ごとにグルーピング
  - **ドメイン基準**: ビジネスドメイン/文脈で整理
  - **エピック基準**: エピックとサブストーリーの階層構造
- 各アプローチのトレードオフと利点を説明
- ハイブリッドも可能にし、明確な判断基準を示す

## ステップ 5: ストーリー分解の選択肢提示

- 計画文書に分解アプローチの選択肢を含める:
  - **ユーザージャーニー基準**: ユーザーのワークフロー/操作に沿う
  - **機能基準**: 機能や能力で整理
  - **ペルソナ基準**: ユーザー種別ごとにグルーピング
  - **ドメイン基準**: ビジネスドメイン/文脈で整理
  - **エピック基準**: エピックとサブストーリーの階層構造
- 各アプローチのトレードオフと利点を説明
- ハイブリッドも可能にし、明確な判断基準を示す

## Step 6: Store Story Plan

- Save the complete story plan with embedded questions in `aidlc-docs/inception/plans/` directory
- Filename: `story-generation-plan.md`
- Include all [Answer]: tags for user input
- Ensure plan is comprehensive and covers all story development aspects

## ステップ 6: ストーリープランの保存

- 埋め込み質問を含む完全なプランを `aidlc-docs/inception/plans/` に保存
- ファイル名: `story-generation-plan.md`
- すべての [Answer]: タグを含める
- ストーリー開発の全側面をカバーする包括的な内容にする

## ステップ 6: ストーリープランの保存

- 埋め込み質問を含む完全なプランを `aidlc-docs/inception/plans/` に保存
- ファイル名: `story-generation-plan.md`
- すべての [Answer]: タグを含める
- ストーリー開発の全側面をカバーする包括的な内容にする

## Step 7: Request User Input

- Ask user to fill in all [Answer]: tags directly in the story plan document
- Emphasize importance of audit trail and decision documentation
- Provide clear instructions on how to fill in the [Answer]: tags
- Explain that all questions must be answered before proceeding

## ステップ 7: ユーザー入力の依頼

- ストーリープラン文書内の [Answer]: タグにすべて回答してもらう
- 監査ログと意思決定記録の重要性を強調
- [Answer]: タグの記入方法を明確に案内
- すべての質問が回答されるまで進めないことを伝える

## ステップ 7: ユーザー入力の依頼

- ストーリープラン文書内の [Answer]: タグにすべて回答してもらう
- 監査ログと意思決定記録の重要性を強調
- [Answer]: タグの記入方法を明確に案内
- すべての質問が回答されるまで進めないことを伝える

## Step 8: Collect Answers

- Wait for user to provide answers to all questions using [Answer]: tags in the document
- Do not proceed until ALL [Answer]: tags are completed
- Review the document to ensure no [Answer]: tags are left blank

## ステップ 8: 回答収集

- ユーザーが文書内の [Answer]: タグで回答するのを待つ
- **すべて**の [Answer]: タグが埋まるまで進めない
- 文書を確認し、空欄がないことを確認

## ステップ 8: 回答収集

- ユーザーが文書内の [Answer]: タグで回答するのを待つ
- **すべて**の [Answer]: タグが埋まるまで進めない
- 文書を確認し、空欄がないことを確認

## Step 9: ANALYZE ANSWERS (MANDATORY)

Before proceeding, you MUST carefully review all user answers for:

- **Vague or ambiguous responses**: "mix of", "somewhere between", "not sure", "depends", "maybe", "probably"
- **Undefined criteria or terms**: References to concepts without clear definitions
- **Contradictory answers**: Responses that conflict with each other
- **Missing generation details**: Answers that lack specific guidance for implementation
- **Answers that combine options**: Responses that merge different approaches without clear decision rules
- **Incomplete explanations**: Answers that reference external factors without defining them
- **Assumption-based responses**: Answers that assume knowledge not explicitly stated

## ステップ 9: 回答分析（必須）

進行前に、ユーザー回答を必ず精査する:

- **あいまい/曖昧な回答**: "mix of", "somewhere between", "not sure", "depends", "maybe", "probably"
- **未定義の用語/基準**: 定義がない概念への参照
- **矛盾する回答**: 回答同士が衝突
- **生成詳細の欠落**: 実装に必要な具体性がない
- **選択肢の混在**: ルールなしに複数アプローチを混合
- **不完全な説明**: 外部要因に言及するが定義がない
- **仮定に基づく回答**: 明示されていない知識を前提

## ステップ 9: 回答分析（必須）

進行前に、ユーザー回答を必ず精査する:

- **あいまい/曖昧な回答**: "mix of", "somewhere between", "not sure", "depends", "maybe", "probably"
- **未定義の用語/基準**: 定義がない概念への参照
- **矛盾する回答**: 回答同士が衝突
- **生成詳細の欠落**: 実装に必要な具体性がない
- **選択肢の混在**: ルールなしに複数アプローチを混合
- **不完全な説明**: 外部要因に言及するが定義がない
- **仮定に基づく回答**: 明示されていない知識を前提

## Step 10: MANDATORY Follow-up Questions

If the analysis in step 9 reveals ANY ambiguous answers, you MUST:

- Create a separate clarification questions file using [Answer]: tags
- DO NOT proceed to approval until ALL ambiguities are completely resolved
- **CRITICAL**: Be thorough - ask follow-up questions for every unclear response
- Examples of required follow-ups:
  - "You mentioned 'mix of A and B' - what specific criteria should determine when to use A vs B?"
  - "You said 'somewhere between A and B' - can you define the exact middle ground approach?"
  - "You indicated 'not sure' - what additional information would help you decide?"
  - "You mentioned 'depends on complexity' - how do you define complexity levels and thresholds?"
  - "You chose 'hybrid approach' - what are the specific rules for when to use each method?"
  - "You said 'probably X' - what factors would make it definitely X vs definitely not X?"
  - "You referenced 'standard practice' - can you define what that standard practice is?"

## ステップ 10: フォロー質問（必須）

ステップ 9 であいまいさがあれば必ず:

- [Answer]: タグを使った別の確認質問ファイルを作成
- あいまいさが完全に解消されるまで承認に進まない
- **重要**: 徹底的に行い、不明瞭な回答ごとに質問
- フォロー例:
  - "'mix of A and B' とありましたが、A と B を使い分ける具体的基準は？"
  - "'somewhere between A and B' の具体的な中間案は？"
  - "'not sure' とありました。判断に必要な追加情報は？"
  - "'depends on complexity' とありました。複雑さの定義と閾値は？"
  - "'hybrid approach' を選択しました。各手法の使い分けルールは？"
  - "'probably X' とありました。X になる/ならない要因は？"
  - "'standard practice' とありました。その標準手法を定義してください"

## ステップ 10: フォロー質問（必須）

ステップ 9 であいまいさがあれば必ず:

- [Answer]: タグを使った別の確認質問ファイルを作成
- あいまいさが完全に解消されるまで承認に進まない
- **重要**: 徹底的に行い、不明瞭な回答ごとに質問
- フォロー例:
  - "'mix of A and B' とありましたが、A と B を使い分ける具体的基準は？"
  - "'somewhere between A and B' の具体的な中間案は？"
  - "'not sure' とありました。判断に必要な追加情報は？"
  - "'depends on complexity' とありました。複雑さの定義と閾値は？"
  - "'hybrid approach' を選択しました。各手法の使い分けルールは？"
  - "'probably X' とありました。X になる/ならない要因は？"
  - "'standard practice' とありました。その標準手法を定義してください"

## Step 11: Avoid Implementation Details

- Focus on story creation methodology, not prioritization or development tasks
- Do not discuss technical generation at this stage
- Avoid creating development timelines or sprint planning
- Keep focus on story structure and format decisions

## ステップ 11: 実装詳細を避ける

- ストーリー作成手法に集中し、優先順位や開発タスクは扱わない
- 技術的な生成について議論しない
- 開発スプリントやタイムラインを作らない
- ストーリー構造と形式の判断に集中

## ステップ 11: 実装詳細を避ける

- ストーリー作成手法に集中し、優先順位や開発タスクは扱わない
- 技術的な生成について議論しない
- 開発スプリントやタイムラインを作らない
- ストーリー構造と形式の判断に集中

## Step 12: Log Approval Prompt

- Before asking for approval, log the prompt with timestamp in `aidlc-docs/audit.md`
- Include the complete approval prompt text
- Use ISO 8601 timestamp format

## ステップ 12: 承認プロンプトの記録

- 承認を求める前に、プロンプト全文を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ISO 8601 形式を使用

## ステップ 12: 承認プロンプトの記録

- 承認を求める前に、プロンプト全文を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ISO 8601 形式を使用

## Step 13: Wait for Explicit Approval of Plan

- Do not proceed until the user explicitly approves the story approach
- Approval must be clear and unambiguous
- If user requests changes, update the plan and repeat the approval process

## ステップ 13: 計画の明示的承認を待つ

- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があれば計画を更新し、承認プロセスを繰り返す

## ステップ 13: 計画の明示的承認を待つ

- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があれば計画を更新し、承認プロセスを繰り返す

## Step 14: Record Approval Response

- Log the user's approval response with timestamp in `aidlc-docs/audit.md`
- Include the exact user response text
- Mark the approval status clearly

## ステップ 14: 承認応答の記録

- ユーザーの承認回答を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ユーザーの回答を正確に記録
- 承認状態を明確に記載

## ステップ 14: 承認応答の記録

- ユーザーの承認回答を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ユーザーの回答を正確に記録
- 承認状態を明確に記載

---

---

---

# PART 2: GENERATION

# PART 2: GENERATION

# PART 2: GENERATION

## Step 15: Load Story Generation Plan

- [ ] Read the complete story plan from `aidlc-docs/inception/plans/story-generation-plan.md`
- [ ] Identify the next uncompleted step (first [ ] checkbox)
- [ ] Load the context and requirements for that step

## ステップ 15: ストーリー生成計画の読み込み

- [ ] `aidlc-docs/inception/plans/story-generation-plan.md` から完全な計画を読み込む
- [ ] 次の未完了ステップ（最初の [ ]）を特定
- [ ] 該当ステップのコンテキストと要件を読み込む

## ステップ 15: ストーリー生成計画の読み込み

- [ ] `aidlc-docs/inception/plans/story-generation-plan.md` から完全な計画を読み込む
- [ ] 次の未完了ステップ（最初の [ ]）を特定
- [ ] 該当ステップのコンテキストと要件を読み込む

## Step 16: Execute Current Step

- [ ] Perform exactly what the current step describes
- [ ] Generate story artifacts as specified in the plan
- [ ] Follow the approved methodology and format from Planning
- [ ] Use the story breakdown approach specified in the plan

## ステップ 16: 現在ステップの実行

- [ ] 計画に記載された内容を正確に実行
- [ ] 計画で指定されたストーリー成果物を生成
- [ ] Planning で承認済みの方法論と形式に従う
- [ ] 計画で指定された分解アプローチを使用

## ステップ 16: 現在ステップの実行

- [ ] 計画に記載された内容を正確に実行
- [ ] 計画で指定されたストーリー成果物を生成
- [ ] Planning で承認済みの方法論と形式に従う
- [ ] 計画で指定された分解アプローチを使用

## Step 17: Update Progress

- [ ] Mark the completed step as [x] in the story generation plan
- [ ] Update `aidlc-docs/aidlc-state.md` current status
- [ ] Save all generated artifacts

## ステップ 17: 進捗更新

- [ ] 完了ステップをストーリー生成計画で [x] にする
- [ ] `aidlc-docs/aidlc-state.md` の現在状況を更新
- [ ] 生成成果物を保存

## ステップ 17: 進捗更新

- [ ] 完了ステップをストーリー生成計画で [x] にする
- [ ] `aidlc-docs/aidlc-state.md` の現在状況を更新
- [ ] 生成成果物を保存

## Step 18: Continue or Complete Generation

- [ ] If more steps remain, return to Step 14
- [ ] If all steps complete, verify stories are ready for next stage
- [ ] Ensure all mandatory artifacts are generated

## ステップ 18: 継続または完了

- [ ] 残りがあればステップ 14 に戻る
- [ ] すべて完了なら次ステージへ進める状態を確認
- [ ] すべての必須成果物が生成されていることを確認

## ステップ 18: 継続または完了

- [ ] 残りがあればステップ 14 に戻る
- [ ] すべて完了なら次ステージへ進める状態を確認
- [ ] すべての必須成果物が生成されていることを確認

## Step 19: Log Approval Prompt

- Before asking for approval, log the prompt with timestamp in `aidlc-docs/audit.md`
- Include the complete approval prompt text
- Use ISO 8601 timestamp format

## ステップ 19: 承認プロンプトの記録

- 承認前にプロンプト全文を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ISO 8601 形式を使用

## ステップ 19: 承認プロンプトの記録

- 承認前にプロンプト全文を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ISO 8601 形式を使用

## Step 20: Present Completion Message

- Present completion message in this structure:
  1.  **Completion Announcement** (mandatory): Always start with this:

## ステップ 20: 完了メッセージの提示

- 次の構造で完了メッセージを提示:
  1.  **完了告知**（必須）: 必ずこれで開始

## ステップ 20: 完了メッセージの提示

- 次の構造で完了メッセージを提示:
  1.  **完了告知**（必須）: 必ずこれで開始

```markdown
# 📚 User Stories Complete
```

```markdown
# 📚 User Stories Complete
```

```markdown
# 📚 User Stories Complete
```

     2. **AI Summary** (optional): Provide structured bullet-point summary of generated stories
        - Format: "User stories generation has created [description]:"
        - List key personas generated (bullet points)
        - List user stories created with counts and organization
        - Mention story structure and compliance (INVEST criteria, acceptance criteria)
        - DO NOT include workflow instructions ("please review", "let me know", "proceed to next phase", "before we proceed")
        - Keep factual and content-focused
     3. **Formatted Workflow Message** (mandatory): Always end with this exact format:
     2. **AI 要約**（任意）: 生成ストーリーの構造化箇条書き要約
        - 形式: "User stories generation has created [description]:"
        - 生成された主要ペルソナを列挙
        - ストーリーの数と構成を列挙
        - ストーリー構造と適合性（INVEST、受け入れ基準）に言及
        - ワークフロー指示は含めない（"please review"、"let me know"、"proceed to next phase"、"before we proceed" など）
        - 事実ベースかつ内容中心にする
     3. **フォーマット済みワークフローメッセージ**（必須）: 必ず以下の形式で終了

     2. **AI 要約**（任意）: 生成ストーリーの構造化箇条書き要約
        - 形式: "User stories generation has created [description]:"
        - 生成された主要ペルソナを列挙
        - ストーリーの数と構成を列挙
        - ストーリー構造と適合性（INVEST、受け入れ基準）に言及
        - ワークフロー指示は含めない（"please review"、"let me know"、"proceed to next phase"、"before we proceed" など）
        - 事実ベースかつ内容中心にする
     3. **フォーマット済みワークフローメッセージ**（必須）: 必ず以下の形式で終了

```markdown
> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the user stories and personas at: `aidlc-docs/inception/user-stories/stories.md` and `aidlc-docs/inception/user-stories/personas.md`

> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the stories or personas based on your review  
> ✅ **Approve & Continue** - Approve user stories and proceed to **Workflow Planning**

---
```

```markdown
> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the user stories and personas at: `aidlc-docs/inception/user-stories/stories.md` and `aidlc-docs/inception/user-stories/personas.md`

> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the stories or personas based on your review  
> ✅ **Approve & Continue** - Approve user stories and proceed to **Workflow Planning**

---
```

```markdown
> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the user stories and personas at: `aidlc-docs/inception/user-stories/stories.md` and `aidlc-docs/inception/user-stories/personas.md`

> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the stories or personas based on your review  
> ✅ **Approve & Continue** - Approve user stories and proceed to **Workflow Planning**

---
```

## Step 21: Wait for Explicit Approval of Generated Stories

- Do not proceed until the user explicitly approves the generated stories
- Approval must be clear and unambiguous
- If user requests changes, update stories and repeat the approval process

## ステップ 21: 生成されたストーリーの明示的承認を待つ

- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があればストーリーを更新し、承認プロセスを繰り返す

## ステップ 21: 生成されたストーリーの明示的承認を待つ

- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があればストーリーを更新し、承認プロセスを繰り返す

## Step 22: Record Approval Response

- Log the user's approval response with timestamp in `aidlc-docs/audit.md`
- Include the exact user response text
- Mark the approval status clearly

## ステップ 22: 承認応答の記録

- ユーザーの承認回答を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ユーザーの回答を正確に記録
- 承認状態を明確に記載

## ステップ 22: 承認応答の記録

- ユーザーの承認回答を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ユーザーの回答を正確に記録
- 承認状態を明確に記載

## Step 23: Update Progress

- Mark User Stories stage complete in `aidlc-state.md`
- Update the "Current Status" section
- Prepare for transition to next stage

## ステップ 23: 進捗更新

- aidlc-state.md で User Stories ステージを完了にする
- "Current Status" セクションを更新
- 次ステージへの移行準備

## ステップ 23: 進捗更新

- aidlc-state.md で User Stories ステージを完了にする
- "Current Status" セクションを更新
- 次ステージへの移行準備

---

---

---

# CRITICAL RULES

# 重要ルール

# 重要ルール

## Planning Phase Rules

- **CONTEXT-APPROPRIATE QUESTIONS**: Only ask questions relevant to this specific context
- **MANDATORY ANSWER ANALYSIS**: Always analyze answers for ambiguities before proceeding
- **NO PROCEEDING WITH AMBIGUITY**: Must resolve all vague answers before generation
- **EXPLICIT APPROVAL REQUIRED**: User must approve plan before generation starts

## Planning フェーズのルール

- **コンテキストに適した質問**: この文脈に関係する質問のみ
- **必須の回答分析**: 進む前に必ずあいまいさを分析
- **曖昧なまま進めない**: すべての曖昧さを解消する
- **明示的承認必須**: 生成前にユーザー承認を得る

## Planning フェーズのルール

- **コンテキストに適した質問**: この文脈に関係する質問のみ
- **必須の回答分析**: 進む前に必ずあいまいさを分析
- **曖昧なまま進めない**: すべての曖昧さを解消する
- **明示的承認必須**: 生成前にユーザー承認を得る

## Generation Phase Rules

- **NO HARDCODED LOGIC**: Only execute what's written in the story generation plan
- **FOLLOW PLAN EXACTLY**: Do not deviate from the step sequence
- **UPDATE CHECKBOXES**: Mark [x] immediately after completing each step
- **USE APPROVED METHODOLOGY**: Follow the story approach from Planning
- **VERIFY COMPLETION**: Ensure all story artifacts are complete before proceeding

## Generation フェーズのルール

- **ハードコード禁止**: 計画に書かれた内容のみ実行
- **計画に厳密に従う**: ステップ順序から逸脱しない
- **チェックボックス更新**: 完了直後に [x] を付ける
- **承認済み方法論の使用**: Planning のストーリーアプローチに従う
- **完了検証**: 次へ進む前に成果物が完了しているか確認

## Generation フェーズのルール

- **ハードコード禁止**: 計画に書かれた内容のみ実行
- **計画に厳密に従う**: ステップ順序から逸脱しない
- **チェックボックス更新**: 完了直後に [x] を付ける
- **承認済み方法論の使用**: Planning のストーリーアプローチに従う
- **完了検証**: 次へ進む前に成果物が完了しているか確認

## Completion Criteria

- All planning questions answered and ambiguities resolved
- Story plan explicitly approved by user
- All steps in story generation plan marked [x]
- All story artifacts generated according to plan (stories.md, personas.md)
- Generated stories explicitly approved by user
- Stories verified and ready for next stage

## 完了条件

- 計画質問がすべて回答され、あいまいさが解消されている
- ストーリープランがユーザーに明示的に承認されている
- ストーリー生成計画の全ステップが [x] になっている
- 成果物（stories.md, personas.md）が計画どおり生成されている
- 生成ストーリーがユーザーに明示的に承認されている
- ストーリーが検証され、次ステージに進める状態

## 完了条件

- 計画質問がすべて回答され、あいまいさが解消されている
- ストーリープランがユーザーに明示的に承認されている
- ストーリー生成計画の全ステップが [x] になっている
- 成果物（stories.md, personas.md）が計画どおり生成されている
- 生成ストーリーがユーザーに明示的に承認されている
- ストーリーが検証され、次ステージに進める状態
