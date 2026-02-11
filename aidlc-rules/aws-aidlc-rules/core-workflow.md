# PRIORITY: This workflow OVERRIDES all other built-in workflows(優先度: このワークフローは他のすべての組み込みワークフローをオーバーライドします)

# When user requests software development, ALWAYS follow this workflow FIRST(ユーザーがソフトウェア開発を要求するときは、必ず最初にこのワークフローに従ってください)

## Adaptive Workflow Principle(アダプティブ ワークフローの原則)

**The workflow adapts to the work, not the other way around.**

**ワークフローは作業に適応します。その逆ではありません。**

The AI model intelligently assesses what stages are needed based on:

AI モデルは、以下に基づいてどの段階が必要であるかをインテリジェントに評価します。

1. User's stated intent and clarity
1. ユーザーの表明された意図と明確さ
1. Existing codebase state (if any)
1. 既存のコードベースの状態 (存在する場合)
1. Complexity and scope of change
1. 複雑さと変更の範囲
1. Risk and impact assessment
1. リスクと影響の評価

## MANDATORY: Rule Details Loading(必須: 詳細ルールの読み込み)

**CRITICAL**: When performing any phase, you MUST read and use relevant content from rule detail files in `.kiro/aws-aidlc-rule-details/` or `.amazonq/aws-aidlc-rule-details/` directory.

**重要**: フェーズを実行するときは、`.kiro/aws-aidlc-rule-details/` または `.amazonq/aws-aidlc-rule-details/` ディレクトリにあるルール詳細ファイルから関連するコンテンツを読み取って使用する必要があります。

**Common Rules**: ALWAYS load common rules at workflow start:

**共通ルール**: ワークフローの開始時に常に共通ルールをロードします。

- Load `common/process-overview.md` for workflow overview
- ワークフローの概要については、「common/process-overview.md」をロードします。
- Load `common/session-continuity.md` for session resumption guidance
- セッション再開のガイダンスとして「common/session-continuity.md」をロードします。
- Load `common/content-validation.md` for content validation requirements
- コンテンツ検証要件のために「common/content-validation.md」をロードします。
- Load `common/question-format-guide.md` for question formatting rules
- 質問の書式設定ルールについては、「common/question-format-guide.md」をロードします。
- Reference these throughout the workflow execution
- ワークフローの実行全体でこれらを参照します。

## MANDATORY: Content Validation(必須: コンテンツの検証)

**CRITICAL**: Before creating ANY file, you MUST validate content according to `common/content-validation.md` rules:

**重要**: ファイルを作成する前に、「common/content-validation.md」ルールに従ってコンテンツを検証する必要があります。

- Validate Mermaid diagram syntax
- マーメイド図の構文を検証する
- Validate ASCII art diagrams (see `common/ascii-diagram-standards.md`)
- ASCII アート図を検証します (「common/ascii-diagram-standards.md」を参照)
- Escape special characters properly
- 特殊文字を適切にエスケープする
- Provide text alternatives for complex visual content
- 複雑なビジュアルコンテンツに代替テキストを提供する
- Test content parsing compatibility
- コンテンツ解析の互換性をテストする

## MANDATORY: Question File Format(必須: 質問ファイル形式)

**CRITICAL**: When asking questions at any phase, you MUST follow question format guidelines.

**重要**: どのフェーズでも質問するときは、質問形式のガイドラインに従う必要があります。

**See `common/question-format-guide.md` for complete question formatting rules including**:

**以下を含む完全な質問フォーマット ルールについては、`common/question-format-guide.md` を参照してください。**:

- Multiple choice format (A, B, C, D, E options)
- 多肢選択形式 (A、B、C、D、E 選択肢)
- [Answer]: tag usage
- [答え]: タグの使用法
- Answer validation and ambiguity resolution
- 回答の検証と曖昧さの解決

## MANDATORY: Custom Welcome Message(必須: カスタムウェルカムメッセージ)

**CRITICAL**: When starting ANY software development request, you MUST display the welcome message.

**重要**: ソフトウェア開発リクエストを開始するときは、ウェルカム メッセージを表示する必要があります。

**How to Display Welcome Message**:
**ウェルカムメッセージの表示方法**:

1. Load the welcome message from `.kiro/aws-aidlc-rule-details/common/welcome-message.md` or `.amazonq/aws-aidlc-rule-details/common/welcome-message.md`
1. `.kiro/aws-aidlc-rule-details/common/welcome-message.md` または `.amazonq/aws-aidlc-rule-details/common/welcome-message.md` からウェルカムメッセージをロードします。
1. Display the complete message to the user
1. 完全なメッセージをユーザーに表示します
1. This should only be done ONCE at the start of a new workflow
1. これは、新しいワークフローの開始時に 1 回だけ実行してください。
1. Do NOT load this file in subsequent interactions to save context space
1. コンテキストスペースを節約するために、後続の対話ではこのファイルをロードしないでください。

# Adaptive Software Development Workflow(適応型ソフトウェア開発ワークフロー)

# INCEPTION PHASE(導入フェーズ)

**Purpose**: Planning, requirements gathering, and architectural decisions

**目的**: 計画、要件の収集、およびアーキテクチャの決定

**Focus**: Determine WHAT to build and WHY

**焦点**: 何を構築するのか、そしてなぜ構築するのかを決定する

**Stages in INCEPTION PHASE**:

**開始フェーズの段階**:

- Workspace Detection (ALWAYS)
- ワークスペースの検出 (常に)
- Reverse Engineering (CONDITIONAL - Brownfield only)
- リバース エンジニアリング (条件付き - ブラウンフィールドのみ)
- Requirements Analysis (ALWAYS - Adaptive depth)
- 要件分析 (常に - 適応深さ)
- User Stories (CONDITIONAL)
- ユーザー ストーリー (条件付き)
- Workflow Planning (ALWAYS)
- ワークフロー計画 (常に)
- Application Design (CONDITIONAL)
- アプリケーション設計 (条件付き)
- Units Generation (CONDITIONAL)
- ユニットの生成 (条件付き)

## Workspace Detection (ALWAYS EXECUTE)(ワークスペースの検出 (常に実行))

1. **MANDATORY**: Log initial user request in audit.md with complete raw input
1. **必須**: 完全な生の入力を使用して最初のユーザー リクエストを Audit.md に記録します。
1. Load all steps from `inception/workspace-detection.md`
1. `inception/workspace-detection.md` からすべてのステップをロードします。
1. Execute workspace detection:
1. ワークスペース検出を実行します。
   - Check for existing aidlc-state.md (resume if found)
   - 既存のaidlc-state.mdを確認します（見つかった場合は再開します）
   - Scan workspace for existing code
   - ワークスペースで既存のコードをスキャンします
   - Determine if brownfield or greenfield
   - ブラウンフィールドかグリーンフィールドかを判断する
   - Check for existing reverse engineering artifacts
   - 既存のリバース エンジニアリング アーティファクトを確認する
1. Determine next phase: Reverse Engineering (if brownfield and no artifacts) OR Requirements Analysis
1. 次のフェーズを決定します: リバース エンジニアリング (ブラウンフィールドでアーティファクトがない場合) または要件分析
1. **MANDATORY**: Log findings in audit.md
1. **必須**: 結果を Audit.md に記録します
1. Present completion message to user (see workspace-detection.md for message formats)
1. 完了メッセージをユーザーに提示します (メッセージ形式については workspace-detection.md を参照してください)。
1. Automatically proceed to next phase
1. 自動的に次のフェーズに進みます

## Reverse Engineering (CONDITIONAL - Brownfield Only)(リバース エンジニアリング (条件付き - ブラウンフィールドのみ))

**Execute IF**:

**IF を実行**:

- Existing codebase detected
- 既存のコードベースが検出されました
- No previous reverse engineering artifacts found
- 以前のリバース エンジニアリング アーティファクトは見つかりませんでした

**Skip IF**:

**IF をスキップ**:

- Greenfield project
- グリーンフィールドプロジェクト
- Previous reverse engineering artifacts exist
- 以前のリバース エンジニアリング アーティファクトが存在する

**Execution**:

**実行**：

1. **MANDATORY**: Log start of reverse engineering in audit.md
1. **必須**: リバース エンジニアリングの開始を Audit.md に記録します。
1. Load all steps from `inception/reverse-engineering.md`
1. 「inception/reverse-engineering.md」からすべてのステップをロードします。
1. Execute reverse engineering:
1. リバースエンジニアリングを実行します。
   - Analyze all packages and components
   - すべてのパッケージとコンポーネントを分析する
   - Generate a business overview of the whole system covering the business transactions
   - ビジネストランザクションをカバーするシステム全体のビジネス概要を生成します
   - Generate architecture documentation
   - アーキテクチャドキュメントの生成
   - Generate code structure documentation
   - コード構造ドキュメントの生成
   - Generate API documentation
   - APIドキュメントの生成
   - Generate component inventory
   - コンポーネントインベントリの生成
   - Generate Interaction Diagrams depicting how business transactions are implemented across components
   - ビジネストランザクションがコンポーネント間でどのように実装されるかを示す相互作用図を生成します。
   - Generate technology stack documentation
   - テクノロジースタックドキュメントの生成
   - Generate dependencies documentation
   - 依存関係のドキュメントを生成する
1. **Wait for Explicit Approval**: Present detailed completion message (see reverse-engineering.md for message format) - DO NOT PROCEED until user confirms
1. **明示的な承認を待ちます**: 詳細な完了メッセージが表示されます (メッセージ形式については reverse-engineering.md を参照) - ユーザーが確認するまで続行しないでください。
1. **MANDATORY**: Log user's response in audit.md with complete raw input
1. **必須**: ユーザーの応答を完全な生の入力で Audit.md に記録します。

## Requirements Analysis (ALWAYS EXECUTE - Adaptive Depth)(要件分析 (常に実行 - 適応深さ))

**Always executes** but depth varies based on request clarity and complexity:

**常に実行** ただし、深さはリクエストの明確さと複雑さに応じて異なります。

- **Minimal**: Simple, clear request - just document intent analysis
- **最小限**: シンプルで明確なリクエスト - 意図分析を文書化するだけです
- **Standard**: Normal complexity - gather functional and non-functional requirements
- **標準**: 通常の複雑さ - 機能要件と非機能要件を収集します
- **Comprehensive**: Complex, high-risk - detailed requirements with traceability
- **包括的**: 複雑でリスクが高く、トレーサビリティのある詳細な要件

**Execution**:

**実行**：

1. **MANDATORY**: Log any user input during this phase in audit.md
1. **必須**: このフェーズ中のユーザー入力を Audit.md に記録します。
1. Load all steps from `inception/requirements-analysis.md`
1. `inception/requirements-analysis.md` からすべてのステップをロードします。
1. Execute requirements analysis:
1. 要件分析を実行します。
   - Load reverse engineering artifacts (if brownfield)

- リバース エンジニアリング アーティファクトをロードします (ブラウンフィールドの場合)
- Analyze user request (intent analysis)
- ユーザーリクエストの分析（インテント分析）
- Determine requirements depth needed
- 必要な要件の深さを決定する
- Assess current requirements
- 現在の要件を評価する
- Ask clarifying questions (if needed)
- 明確な質問をする (必要な場合)
- Generate requirements document
- 要件ドキュメントの生成

1. Execute at appropriate depth (minimal/standard/comprehensive)
2. 適切な深さで実行 (最小/標準/包括)
3. **Wait for Explicit Approval**: Follow approval format from requirements-analysis.md detailed steps - DO NOT PROCEED until user confirms
4. **明示的な承認を待ちます**: 要件分析.md の詳細な手順の承認形式に従います - ユーザーが確認するまで続行しないでください。
5. **MANDATORY**: Log user's response in audit.md with complete raw input
6. **必須**: ユーザーの応答を完全な生の入力で Audit.md に記録します。

## User Stories (CONDITIONAL)

## ユーザー ストーリー (条件付き)

**INTELLIGENT ASSESSMENT**: Use multi-factor analysis to determine if user stories add value:

**インテリジェントな評価**: 多要素分析を使用して、ユーザー ストーリーに価値が付加されているかどうかを判断します。

**ALWAYS Execute IF** (High Priority Indicators):

**常に IF を実行** (高優先度インジケーター):

- New user-facing features or functionality
- 新しいユーザー向けの機能または機能
- Changes affecting user workflows or interactions
- ユーザーのワークフローまたはインタラクションに影響を与える変更
- Multiple user types or personas involved
- 複数のユーザー タイプまたはペルソナが関与する
- Complex business requirements with acceptance criteria needs
- 承認基準が必要な複雑なビジネス要件
- Cross-functional team collaboration required
- 部門を超えたチームのコラボレーションが必要
- Customer-facing API or service changes
- 顧客向けの API またはサービスの変更
- New product capabilities or enhancements
- 新しい製品の機能または機能強化

**LIKELY Execute IF** (Medium Priority - Assess Complexity):

**IF を実行する可能性があります** (優先度が中 - 複雑さを評価):

- Modifications to existing user-facing features
- 既存のユーザー向け機能の変更
- Backend changes that indirectly affect user experience
- ユーザー エクスペリエンスに間接的に影響を与えるバックエンドの変更
- Integration work that impacts user workflows
- ユーザーのワークフローに影響を与える統合作業
- Performance improvements with user-visible benefits
- ユーザーが目に見えるメリットによるパフォーマンスの向上
- Security enhancements affecting user interactions
- ユーザー操作に影響を与えるセキュリティの強化
- Data model changes affecting user data or reports
- ユーザーデータまたはレポートに影響を与えるデータモデルの変更

**COMPLEXITY-BASED ASSESSMENT**: For medium priority cases, execute user stories if:

**複雑さベースの評価**: 優先度が中程度のケースでは、次の場合にユーザー ストーリーを実行します。

- Request involves multiple components or services
- リクエストには複数のコンポーネントまたはサービスが含まれます
- Changes span multiple user touchpoints
- 変更は複数のユーザータッチポイントにまたがります
- Business logic is complex or has multiple scenarios
- ビジネス ロジックが複雑であるか、複数のシナリオがある
- Requirements have ambiguity that stories could clarify
- 要件にはあいまいさがあり、ストーリーで明確になる可能性があります
- Implementation affects multiple user journeys
- 実装は複数のユーザー ジャーニーに影響します
- Change has significant business impact or risk
- 変化はビジネスに重大な影響またはリスクをもたらします

**SKIP ONLY IF** (Low Priority - Simple Cases):

**次の場合のみスキップ** (優先度が低い - 単純なケース):

- Pure internal refactoring with zero user impact
- ユーザーに影響を与えない純粋な内部リファクタリング
- Simple bug fixes with clear, isolated scope
- 明確で独立した範囲でのシンプルなバグ修正
- Infrastructure changes with no user-facing effects
- ユーザーに影響を与えないインフラストラクチャの変更
- Technical debt cleanup with no functional changes
- 機能的な変更を伴わない技術的負債のクリーンアップ
- Developer tooling or build process improvements
- 開発者ツールまたはビルドプロセスの改善
- Documentation-only updates
- ドキュメントのみの更新

**ASSESSMENT CRITERIA**: When in doubt, favor inclusion of user stories for:

**評価基準**: 疑わしい場合は、次のユーザー ストーリーを含めることを推奨します。

- Requests with business stakeholder involvement
- ビジネス関係者の関与を伴うリクエスト
- Changes requiring user acceptance testing
- ユーザー受け入れテストが必要な変更
- Features with multiple implementation approaches
- 複数の実装アプローチによる機能
- Work that benefits from shared team understanding
- チームの共通理解から恩恵を受ける仕事
- Projects where requirements clarity is valuable
- 要件の明確さが重要なプロジェクト

**ASSESSMENT PROCESS**:

**評価プロセス**:

1. Analyze request complexity and scope
1. リクエストの複雑さと範囲を分析する
1. Identify user impact (direct or indirect)
1. ユーザーへの影響（直接的または間接的）を特定する
1. Evaluate business context and stakeholder needs
1. ビジネスの背景と利害関係者のニーズを評価する
1. Consider team collaboration benefits
1. チームコラボレーションの利点を考慮する
1. Default to inclusion for borderline cases
1. 境界例の場合はデフォルトで含める

**Note**: If Requirements Analysis executed, Stories can reference and build upon those requirements.

**注意**: 要件分析が実行されると、ストーリーはそれらの要件を参照し、それに基づいて構築できます。

**User Stories has two parts within one stage**:

**ユーザー ストーリーには 1 つのステージ内に 2 つの部分があります**:

1. **Part 1 - Planning**: Create story plan with questions, collect answers, analyze for ambiguities, get approval
1. **パート 1 - 計画**: 質問を含むストーリー プランを作成し、回答を収集し、あいまいさを分析し、承認を得る
1. **Part 2 - Generation**: Execute approved plan to generate stories and personas
1. **パート 2 - 生成**: 承認された計画を実行してストーリーとペルソナを生成します

**Execution**:

**実行**：

1. **MANDATORY**: Log any user input during this phase in audit.md
1. **必須**: このフェーズ中のユーザー入力を Audit.md に記録します。
1. Load all steps from `inception/user-stories.md`
1. `inception/user-stories.md` からすべてのステップをロードします。
1. **MANDATORY**: Perform intelligent assessment (Step 1 in user-stories.md) to validate user stories are needed
1. **必須**: インテリジェントな評価 (user-stories.md のステップ 1) を実行して、ユーザー ストーリーが必要であることを検証します。
1. Load reverse engineering artifacts (if brownfield)
1. リバース エンジニアリング アーティファクトをロードします (ブラウンフィールドの場合)
1. If Requirements exist, reference them when creating stories
1. 要件が存在する場合は、ストーリーを作成するときにそれを参照します
1. Execute at appropriate depth (minimal/standard/comprehensive)
1. 適切な深さで実行 (最小/標準/包括)
1. **PART 1 - Planning**: Create story plan with questions, wait for user answers, analyze for ambiguities, get approval
1. **パート 1 - 計画**: 質問を含むストーリー プランを作成し、ユーザーの回答を待ち、あいまいさを分析し、承認を得る
1. **PART 2 - Generation**: Execute approved plan to generate stories and personas
1. **パート 2 - 生成**: ストーリーとペルソナを生成するための承認された計画を実行します。
1. **Wait for Explicit Approval**: Follow approval format from user-stories.md detailed steps - DO NOT PROCEED until user confirms
1. **明示的な承認を待ちます**: user-stories.md の詳細な手順の承認形式に従います - ユーザーが確認するまで続行しないでください
1. **MANDATORY**: Log user's response in audit.md with complete raw input
1. **必須**: ユーザーの応答を完全な生の入力で Audit.md に記録します。

## Workflow Planning (ALWAYS EXECUTE)(ワークフロー計画 (常に実行))

1. **MANDATORY**: Log any user input during this phase in audit.md
1. **必須**: このフェーズ中のユーザー入力を Audit.md に記録します。
1. Load all steps from `inception/workflow-planning.md`
1. `inception/workflow-planning.md` からすべてのステップをロードします。
1. **MANDATORY**: Load content validation rules from `common/content-validation.md`
1. **必須**: `common/content-validation.md` からコンテンツ検証ルールをロードします。
1. Load all prior context:
1. 以前のコンテキストをすべてロードします。
   - Reverse engineering artifacts (if brownfield)
   - リバース エンジニアリング アーティファクト (ブラウンフィールドの場合)
   - Intent analysis
   - 意図の分析
   - Requirements (if executed)
   - 要件 (実行される場合)
   - User stories (if executed)
   - ユーザーストーリー (実行された場合)
1. Execute workflow planning:
1. ワークフロー計画を実行します。
   - Determine which phases to execute
   - どのフェーズを実行するかを決定する
   - Determine depth level for each phase
   - 各フェーズの深さレベルを決定します
   - Create multi-package change sequence (if brownfield)
   - マルチパッケージ変更シーケンスの作成 (ブラウンフィールドの場合)
   - Generate workflow visualization (VALIDATE Mermaid syntax before writing)
   - ワークフロー視覚化の生成 (書き込み前に Mermaid 構文を検証)
1. **MANDATORY**: Validate all content before file creation per content-validation.md rules
1. **必須**: content-validation.md ルールに従って、ファイル作成前にすべてのコンテンツを検証します。
1. **Wait for Explicit Approval**: Present recommendations using language from workflow-planning.md Step 9, emphasizing user control to override recommendations - DO NOT PROCEED until user confirms
1. **明示的な承認を待ちます**: workflow-planning.md ステップ 9 の文言を使用して推奨事項を提示します。推奨事項を上書きするためのユーザー制御を強調します - ユーザーが確認するまで続行しないでください。
1. **MANDATORY**: Log user's response in audit.md with complete raw input
1. **必須**: ユーザーの応答を完全な生の入力で Audit.md に記録します。

## Application Design (CONDITIONAL)(アプリケーション設計 (条件付き))

**Execute IF**:

**IF を実行**:

- New components or services needed
- 新しいコンポーネントまたはサービスが必要
- Component methods and business rules need definition
- コンポーネントメソッドとビジネスルールの定義が必要
- Service layer design required
- サービス層の設計が必要
- Component dependencies need clarification
- コンポーネントの依存関係を明確にする必要がある

**Skip IF**:

**IF をスキップ**:

- Changes within existing component boundaries
- 既存のコンポーネントの境界内での変更
- No new components or methods
- 新しいコンポーネントやメソッドはありません
- Pure implementation changes
- 純粋な実装の変更

**Execution**:

**実行**：

1. **MANDATORY**: Log any user input during this phase in audit.md
1. **必須**: このフェーズ中のユーザー入力を Audit.md に記録します。
1. Load all steps from `inception/application-design.md`
1. 「inception/application-design.md」からすべてのステップをロードします。
1. Load reverse engineering artifacts (if brownfield)
1. リバース エンジニアリング アーティファクトをロードします (ブラウンフィールドの場合)
1. Execute at appropriate depth (minimal/standard/comprehensive)
1. 適切な深さで実行 (最小/標準/包括)
1. **Wait for Explicit Approval**: Present detailed completion message (see application-design.md for message format) - DO NOT PROCEED until user confirms
1. **明示的な承認を待ちます**: 詳細な完了メッセージが表示されます (メッセージ形式については application-design.md を参照) - ユーザーが確認するまで続行しないでください。
1. **MANDATORY**: Log user's response in audit.md with complete raw input
1. **必須**: ユーザーの応答を完全な生の入力で Audit.md に記録します。

## Units Generation (CONDITIONAL)(ユニットの生成 (条件付き))

**Execute IF**:

**IF を実行**:

- System needs decomposition into multiple units of work
- システムは複数の作業単位に分解する必要がある
- Multiple services or modules required
- 複数のサービスまたはモジュールが必要
- Complex system requiring structured breakdown
- 構造化されたブレークダウンを必要とする複雑なシステム

**Skip IF**:

**IF をスキップ**:

- Single simple unit
- 単一のシンプルなユニット
- No decomposition needed
- 分解は必要ありません
- Straightforward single-component implementation
- 単一コンポーネントの簡単な実装

**Execution**:

**実行**：

1. **MANDATORY**: Log any user input during this phase in audit.md
1. **必須**: このフェーズ中のユーザー入力を Audit.md に記録します。
1. Load all steps from `inception/units-generation.md`
1. `inception/units-generation.md` からすべてのステップをロードします。
1. Load reverse engineering artifacts (if brownfield)
1. リバース エンジニアリング アーティファクトをロードします (ブラウンフィールドの場合)
1. Execute at appropriate depth (minimal/standard/comprehensive)
1. 適切な深さで実行 (最小/標準/包括)
1. **Wait for Explicit Approval**: Present detailed completion message (see units-generation.md for message format) - DO NOT PROCEED until user confirms
1. **明示的な承認を待ちます**: 詳細な完了メッセージが表示されます (メッセージ形式については、units-generation.md を参照) - ユーザーが確認するまで続行しないでください。
1. **MANDATORY**: Log user's response in audit.md with complete raw input
1. **必須**: ユーザーの応答を完全な生の入力で Audit.md に記録します。

# 🟢 CONSTRUCTION PHASE(🟢 構築フェーズ）

**Purpose**: Detailed design, NFR implementation, and code generation

**目的**: 詳細設計、NFR 実装、コード生成

**Focus**: Determine HOW to build it

**焦点**: 構築方法を決定する

**Stages in CONSTRUCTION PHASE**:

**構築フェーズの段階**:

- Per-Unit Loop (executes for each unit):
- ユニットごとのループ (ユニットごとに実行):
- Functional Design (CONDITIONAL, per-unit)
- 機能的なデザイン (条件付き、ユニットごと)
- NFR Requirements (CONDITIONAL, per-unit)
- NFR 要件 (条件付き、ユニットごと)
- NFR Design (CONDITIONAL, per-unit)
- NFR 設計 (条件付き、ユニットごと)
- Infrastructure Design (CONDITIONAL, per-unit)
- インフラストラクチャ設計 (条件付き、ユニットごと)
- Code Generation (ALWAYS, per-unit)
- コード生成 (常に、ユニットごと)
- Build and Test (ALWAYS - after all units complete)
- ビルドとテスト (常に - すべてのユニットが完了した後)

**Note**: Each unit is completed fully (design + code) before moving to the next unit.

**注意**: 次の単元に進む前に、各単元は完全に完了しています (設計 + コード)。

## Per-Unit Loop (Executes for Each Unit)(ユニットごとのループ (ユニットごとに実行))

**For each unit of work, execute the following stages in sequence:**

**作業単位ごとに、次のステージを順番に実行します。**

### Functional Design (CONDITIONAL, per-unit)

### 機能設計 (条件付き、ユニットごと)

**Execute IF**:

**IF を実行**:

- New data models or schemas
- 新しいデータ モデルまたはスキーマ
- Complex business logic
- 複雑なビジネスロジック
- Business rules need detailed design
- ビジネスルールは詳細な設計が必要

**Skip IF**:

**IF をスキップ**:

- Simple logic changes
- 単純なロジックの変更
- No new business logic
- 新しいビジネス ロジックはありません

**Execution**:

**実行**：

1. **MANDATORY**: Log any user input during this stage in audit.md
1. **必須**: この段階でのユーザー入力を Audit.md に記録します。
1. Load all steps from `construction/functional-design.md`
1. `construction/function-design.md` からすべてのステップをロードします。
1. Execute functional design for this unit
1. 本機の機能設計を行う
1. **MANDATORY**: Present standardized 2-option completion message as defined in functional-design.md - DO NOT use emergent 3-option behavior
1. **必須**: function-design.md で定義されている標準化された 2 オプション完了メッセージを表示します。緊急の 3 オプション動作は使用しないでください。
1. **Wait for Explicit Approval**: User must choose between "Request Changes" or "Continue to Next Stage" - DO NOT PROCEED until user confirms
1. **明示的な承認を待ちます**: ユーザーは「変更のリクエスト」または「次の段階に進む」のいずれかを選択する必要があります - ユーザーが確認するまで続行しないでください。
1. **MANDATORY**: Log user's response in audit.md with complete raw input
1. **必須**: ユーザーの応答を完全な生の入力で Audit.md に記録します。

### NFR Requirements (CONDITIONAL, per-unit)(非機能要件 (条件付き、ユニットごと))

**Execute IF**:

**IF を実行**:

- Performance requirements exist
- パフォーマンス要件が存在します
- Security considerations needed
- セキュリティに関する考慮事項が必要
- Scalability concerns present
- スケーラビリティに関する懸念がある
- Tech stack selection required
- 技術スタックの選択が必要です

**Skip IF**:

**IF をスキップ**:

- No NFR requirements
- NFR要件なし
- Tech stack already determined
- 技術スタックはすでに決定されています

**Execution**:

**実行**：

1. **MANDATORY**: Log any user input during this stage in audit.md
1. **必須**: この段階でのユーザー入力を Audit.md に記録します。
1. Load all steps from `construction/nfr-requirements.md`
1. `construction/nfr-requirements.md` からすべてのステップをロードします。
1. Execute NFR assessment for this unit
1. 本機のNFR評価を実行する
1. **MANDATORY**: Present standardized 2-option completion message as defined in nfr-requirements.md - DO NOT use emergent behavior
1. **必須**: nfr-requirements.md で定義されている標準化された 2 オプションの完了メッセージを提示します - 緊急動作は使用しないでください
1. **Wait for Explicit Approval**: User must choose between "Request Changes" or "Continue to Next Stage" - DO NOT PROCEED until user confirms
1. **明示的な承認を待ちます**: ユーザーは「変更のリクエスト」または「次の段階に進む」のいずれかを選択する必要があります - ユーザーが確認するまで続行しないでください。
1. **MANDATORY**: Log user's response in audit.md with complete raw input
1. **必須**: ユーザーの応答を完全な生の入力で Audit.md に記録します。

### NFR Design (CONDITIONAL, per-unit)(非機能要件設計 (条件付き、ユニットごと))

**Execute IF**:

**IF を実行**:

- NFR Requirements was executed
- NFR要件が実行されました
- NFR patterns need to be incorporated
- NFRパターンを組み込む必要がある

**Skip IF**:

**IF をスキップ**:

- No NFR requirements
- NFR要件なし
- NFR Requirements Assessment was skipped
- NFR 要件評価がスキップされました

**Execution**:

**実行**：

1. **MANDATORY**: Log any user input during this stage in audit.md
1. **必須**: この段階でのユーザー入力を Audit.md に記録します。
1. Load all steps from `construction/nfr-design.md`
1. `construction/nfr-design.md` からすべてのステップをロードします。
1. Execute NFR design for this unit
1. 本機のNFR設計を実行
1. **MANDATORY**: Present standardized 2-option completion message as defined in nfr-design.md - DO NOT use emergent behavior
1. **必須**: nfr-design.md で定義されている標準化された 2 オプションの完了メッセージを表示します - 緊急動作は使用しないでください
1. **Wait for Explicit Approval**: User must choose between "Request Changes" or "Continue to Next Stage" - DO NOT PROCEED until user confirms
1. **明示的な承認を待ちます**: ユーザーは「変更のリクエスト」または「次の段階に進む」のいずれかを選択する必要があります - ユーザーが確認するまで続行しないでください。
1. **MANDATORY**: Log user's response in audit.md with complete raw input
1. **必須**: ユーザーの応答を完全な生の入力で Audit.md に記録します。

### Infrastructure Design (CONDITIONAL, per-unit)(インフラストラクチャ設計 (条件付き、ユニットごと))

**Execute IF**:

**IF を実行**:

- Infrastructure services need mapping
- インフラストラクチャ サービスにはマッピングが必要です
- Deployment architecture required
- 展開アーキテクチャが必要です
- Cloud resources need specification
- クラウドリソースには仕様が必要です

**Skip IF**:

**IF をスキップ**:

- No infrastructure changes
- インフラストラクチャの変更なし
- Infrastructure already defined
- インフラストラクチャはすでに定義されています

**Execution**:

**実行**：

1. **MANDATORY**: Log any user input during this stage in audit.md
1. **必須**: この段階でのユーザー入力を Audit.md に記録します。
1. Load all steps from `construction/infrastructure-design.md`
1. 「construction/infrastruction-design.md」からすべてのステップをロードします。
1. Execute infrastructure design for this unit
1. 本機のインフラ設計を実施
1. **MANDATORY**: Present standardized 2-option completion message as defined in infrastructure-design.md - DO NOT use emergent behavior
1. **必須**:インフラストラクチャデザイン.md で定義されている標準化された 2 オプションの完了メッセージを表示します - 緊急動作は使用しないでください
1. **Wait for Explicit Approval**: User must choose between "Request Changes" or "Continue to Next Stage" - DO NOT PROCEED until user confirms
1. **明示的な承認を待ちます**: ユーザーは「変更のリクエスト」または「次の段階に進む」のいずれかを選択する必要があります - ユーザーが確認するまで続行しないでください。
1. **MANDATORY**: Log user's response in audit.md with complete raw input
1. **必須**: ユーザーの応答を完全な生の入力で Audit.md に記録します。

### Code Generation (ALWAYS EXECUTE, per-unit)

### コード生成 (常に実行、ユニットごと)

**Always executes for each unit**

**ユニットごとに常に実行**

**Code Generation has two parts within one stage**:

**コード生成は 1 つのステージ内に 2 つの部分があります**:

1. **Part 1 - Planning**: Create detailed code generation plan with explicit steps
1. **パート 1 - 計画**: 明示的な手順を含む詳細なコード生成計画を作成します。
1. **Part 2 - Generation**: Execute approved plan to generate code, tests, and artifacts
1. **パート 2 - 生成**: 承認された計画を実行して、コード、テスト、成果物を生成します。

**Execution**:

**実行**：

1. **MANDATORY**: Log any user input during this stage in audit.md
1. **必須**: この段階でのユーザー入力を Audit.md に記録します。
1. Load all steps from `construction/code-generation.md`
1. `construction/code-generation.md` からすべてのステップをロードします。
1. **PART 1 - Planning**: Create code generation plan with checkboxes, get user approval
1. **パート 1 - 計画**: チェックボックスを使用してコード生成計画を作成し、ユーザーの承認を取得します。
1. **PART 2 - Generation**: Execute approved plan to generate code for this unit
1. **パート 2 - 生成**: 承認された計画を実行して、このユニットのコードを生成します
1. **MANDATORY**: Present standardized 2-option completion message as defined in code-generation.md - DO NOT use emergent behavior
1. **必須**: code-generate.md で定義されているように、標準化された 2 オプションの完了メッセージを提示します - 緊急動作は使用しないでください
1. **Wait for Explicit Approval**: User must choose between "Request Changes" or "Continue to Next Stage" - DO NOT PROCEED until user confirms
1. **明示的な承認を待ちます**: ユーザーは「変更のリクエスト」または「次の段階に進む」のいずれかを選択する必要があります。ユーザーが確認するまで続行しないでください。
1. **MANDATORY**: Log user's response in audit.md with complete raw input
1. **必須**: ユーザーの応答を完全な生の入力で Audit.md に記録します。

## Build and Test (ALWAYS EXECUTE)(ビルドとテスト (常に実行))

1. **MANDATORY**: Log any user input during this phase in audit.md
1. **必須**: このフェーズ中のユーザー入力を Audit.md に記録します。
1. Load all steps from `construction/build-and-test.md`
1. `construction/build-and-test.md` からすべてのステップをロードします。
1. Generate comprehensive build and test instructions:
1. 包括的なビルドおよびテスト手順を生成します。
   - Build instructions for all units
   - すべてのユニットの組み立て説明書
   - Unit test execution instructions
   - 単体テストの実行命令
   - Integration test instructions (test interactions between units)
   - 結合テスト指示（ユニット間の相互作用のテスト）
   - Performance test instructions (if applicable)
   - パフォーマンス テストの手順 (該当する場合)
   - Additional test instructions as needed (contract tests, security tests, e2e tests)
   - 必要に応じて追加のテスト手順 (契約テスト、セキュリティ テスト、e2e テスト)
1. Create instruction files in build-and-test/ subdirectory: build-instructions.md, unit-test-instructions.md, integration-test-instructions.md, performance-test-instructions.md, build-and-test-summary.md
1. build-and-test/ サブディレクトリに命令ファイルを作成します: build-instructions.md、unit-test-instructions.md、integration-test-instructions.md、performance-test-instructions.md、build-and-test-summary.md
1. **Wait for Explicit Approval**: Ask: "**Build and test instructions complete. Ready to proceed to Operations stage?**" - DO NOT PROCEED until user confirms
1. **明示的な承認を待ちます**: 「**ビルドとテストの手順が完了しました。運用段階に進む準備はできましたか?**」と質問します。ユーザーが確認するまで続行しないでください。
1. **MANDATORY**: Log user's response in audit.md with complete raw input
1. **必須**: ユーザーの応答を完全な生の入力で Audit.md に記録します。

# 🟡 OPERATIONS PHASE(🟡 運用フェーズ)

**Purpose**: Placeholder for future deployment and monitoring workflows

**目的**: 将来の展開およびワークフローの監視のためのプレースホルダー

**Focus**: How to DEPLOY and RUN it (future expansion)

**焦点**: 導入して実行する方法 (将来の拡張)

**Stages in OPERATIONS PHASE**:

**運用フェーズの段階**:

- Operations (PLACEHOLDER)
- 操作 (プレースホルダー)

## Operations (PLACEHOLDER)(操作 (PLACEHOLDER))

**Status**: This stage is currently a placeholder for future expansion.

**ステータス**: このステージは現在、将来の拡張のためのプレースホルダーです。

The Operations stage will eventually include:
運用ステージには最終的に次のものが含まれます。

- Deployment planning and execution
- 導入の計画と実行
- Monitoring and observability setup
- 監視と可観測性のセットアップ
- Incident response procedures
- インシデント対応手順
- Maintenance and support workflows
- メンテナンスおよびサポートのワークフロー
- Production readiness checklists
- 本番準備チェックリスト

**Current State**: All build and test activities are handled in the CONSTRUCTION phase.

**現在の状態**: すべてのビルドおよびテスト アクティビティは、構築フェーズで処理されます。

## Key Principles(重要な原則)

- **Adaptive Execution**: Only execute stages that add value
- **アダプティブ実行**: 価値を追加するステージのみを実行します
- **Transparent Planning**: Always show execution plan before starting
- **透明性のある計画**: 開始する前に必ず実行計画を表示します。
- **User Control**: User can request stage inclusion/exclusion
- **ユーザー制御**: ユーザーはステージの包含/除外をリクエストできます。
- **Progress Tracking**: Update aidlc-state.md with executed and skipped stages
- **進行状況の追跡**: 実行されたステージとスキップされたステージを含むaidlc-state.mdを更新します。
- **Complete Audit Trail**: Log ALL user inputs and AI responses in audit.md with timestamps
- **完全な監査証跡**: すべてのユーザー入力と AI 応答をタイムスタンプ付きで Audit.md に記録します。
  - **CRITICAL**: Capture user's COMPLETE RAW INPUT exactly as provided
- **重要**: ユーザーの完全な RAW 入力を提供されたとおりに正確にキャプチャします。
  - **CRITICAL**: Never summarize or paraphrase user input in audit log
- **重要**: 監査ログ内のユーザー入力を要約したり言い換えたりしないでください。
  - **CRITICAL**: Log every interaction, not just approvals
- **重要**: 承認だけでなく、すべてのやり取りを記録します。
- **Quality Focus**: Complex changes get full treatment, simple changes stay efficient
- **品質重視**: 複雑な変更は完全に処理され、単純な変更は効率を維持します
- **Content Validation**: Always validate content before file creation per content-validation.md rules
- **コンテンツの検証**: content-validation.md ルールに従って、ファイルを作成する前に常にコンテンツを検証します。
- **NO EMERGENT BEHAVIOR**: Construction phases MUST use standardized 2-option completion messages as defined in their respective rule files. DO NOT create 3-option menus or other emergent navigation patterns.
- **緊急動作は禁止**: 構築フェーズでは、それぞれのルール ファイルで定義されている、標準化された 2 オプションの完了メッセージを使用しなければなりません。 3 オプション メニューやその他の緊急ナビゲーション パターンは作成しないでください。

## MANDATORY: Plan-Level Checkbox Enforcement(必須: プランレベルのチェックボックスの強制)

### MANDATORY RULES FOR PLAN EXECUTION(計画実行のための必須ルール)

1. **NEVER complete any work without updating plan checkboxes**
1. **計画チェックボックスを更新せずに作業を完了しないでください**
1. **IMMEDIATELY after completing ANY step described in a plan file, mark that step [x]**
1. **計画ファイルに記述されているステップを完了したらすぐに、そのステップに [x] のマークを付けます**
1. **This must happen in the SAME interaction where the work is completed**
1. **これは、作業が完了したときと同じ対話内で発生する必要があります**
1. **NO EXCEPTIONS**: Every plan step completion MUST be tracked with checkbox updates
1. **例外なし**: すべての計画ステップの完了は、チェックボックスの更新で追跡する必要があります。

### Two-Level Checkbox Tracking System(2 レベルのチェックボックス追跡システム)

- **Plan-Level**: Track detailed execution progress within each stage
- **計画レベル**: 各ステージ内の実行の詳細な進行状況を追跡します。
- **Stage-Level**: Track overall workflow progress in aidlc-state.md
- **ステージレベル**: ワークフロー全体の進行状況をaidlc-state.mdで追跡します。
- **Update immediately**: All progress updates in SAME interaction where work is completed
- **すぐに更新**: 作業が完了した場合と同じインタラクションで、すべての進行状況が更新されます。

## Prompts Logging Requirements(ロギング要件を求めるプロンプト)

- **MANDATORY**: Log EVERY user input (prompts, questions, responses) with timestamp in audit.md
- **必須**: すべてのユーザー入力 (プロンプト、質問、応答) をタイムスタンプ付きで Audit.md に記録します。
- **MANDATORY**: Capture user's COMPLETE RAW INPUT exactly as provided (never summarize)
- **必須**: ユーザーの完全な RAW 入力を提供されたとおりに正確にキャプチャします (決して要約しないでください)。
- **MANDATORY**: Log every approval prompt with timestamp before asking the user
- **必須**: ユーザーに質問する前に、すべての承認プロンプトをタイムスタンプ付きで記録します。
- **MANDATORY**: Record every user response with timestamp after receiving it
- **必須**: すべてのユーザー応答を受信後、タイムスタンプ付きで記録します。
- **CRITICAL**: ALWAYS append changes to EDIT audit.md file, NEVER use tools and commands that completely overwrite its contents
- **重要**: 常に変更を編集audit.mdファイルに追加し、その内容を完全に上書きするツールやコマンドは決して使用しないでください。
- **CRITICAL**: Using file writing tools and commands that overwrite contents of the entire audit.md and cause duplication
- **重要**: Audit.md 全体の内容を上書きし、重複を引き起こすファイル書き込みツールやコマンドを使用する
- When adding an entry to audit.md:
- Audit.md にエントリを追加する場合:
  1. Run a system command to get the current date and time in ISO 8601 format (YYYY-MM-DDTHH:MM:SS). Use whatever command is appropriate for the current OS and shell environment.
  2. システム コマンドを実行して、現在の日付と時刻を ISO 8601 形式 (YYYY-MM-DDTHH:MM:SS) で取得します。現在の OS とシェル環境に適したコマンドを使用してください。
  3. Use the command output exactly as the **Timestamp** value.
  4. コマンド出力を **タイムスタンプ** 値として正確に使用します。
- Do not use placeholder (e.g., T00:00:00Z), estimated, or fabricated times.
- プレースホルダー (例: T00:00:00Z)、推定時刻、または捏造された時刻は使用しないでください。
- Include stage context for each entry
- 各エントリにステージコンテキストを含める

### Audit Log Format:(監査ログの形式)

```markdown
## [Stage Name or Interaction Type][ステージ名またはインタラクション タイプ]

**Timestamp**: [ISO timestamp]
**タイムスタンプ**: [ISO タイムスタンプ]
**User Input**: "[Complete raw user input - never summarized]"
**ユーザー入力**: "[完全な生のユーザー入力 - 要約されることはありません]"
**AI Response**: "[AI's response or action taken]"
**AI の応答**: 「[AI の応答または実行されたアクション]」
**Context**: [Stage, action, or decision made]
**コンテキスト**: [段階、アクション、または決定が行われた]
```

### Correct Tool Usage for audit.md(Audit.md の正しいツールの使用法)

✅ CORRECT:
✅ 正:

1. Read the audit.md file
1. audit.md ファイルを読み取ります。
1. Append/Edit the file to make changes
1. ファイルを追加/編集して変更を加えます

❌ WRONG:
❌ 間違い:

1. Read the audit.md file
1. audit.md ファイルを読み取ります。
1. Completely overwrite the audit.md with the contents of what you read, plus the new changes you want to add to it
1. 読み取った内容とそれに追加する新しい変更を加えて、audit.md を完全に上書きします。

## Directory Structure(ディレクトリ構造)

```text
<WORKSPACE-ROOT>/                   # ⚠️ APPLICATION CODE HERE
├── [project-specific structure]    # Varies by project (see code-generation.md)
│
├── aidlc-docs/                     # 📄 DOCUMENTATION ONLY
│   ├── inception/                  # 🔵 INCEPTION PHASE
│   │   ├── plans/
│   │   ├── reverse-engineering/    # Brownfield only
│   │   ├── requirements/
│   │   ├── user-stories/
│   │   └── application-design/
│   ├── construction/               # 🟢 CONSTRUCTION PHASE
│   │   ├── plans/
│   │   ├── {unit-name}/
│   │   │   ├── functional-design/
│   │   │   ├── nfr-requirements/
│   │   │   ├── nfr-design/
│   │   │   ├── infrastructure-design/
│   │   │   └── code/               # Markdown summaries only
│   │   └── build-and-test/
│   ├── operations/                 # 🟡 OPERATIONS PHASE (placeholder)
│   ├── aidlc-state.md
│   └── audit.md
```

**CRITICAL RULE**:

**重要なルール**:

- Application code: Workspace root (NEVER in aidlc-docs/)
- アプリケーション コード: ワークスペース ルート (aidlc-docs/ には決して含まない)
- Documentation: aidlc-docs/ only
- ドキュメント: aidlc-docs/ のみ
- Project structure: See code-generation.md for patterns by project type
- プロジェクト構造: プロジェクト タイプ別のパターンについては code-generate.md を参照してください。
