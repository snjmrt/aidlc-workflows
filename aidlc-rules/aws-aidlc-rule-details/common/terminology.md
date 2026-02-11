# AI-DLC Terminology Glossary
# AI-DLC 用語集

# AI-DLC 用語集

## Core Terminology
## 基本用語

## 基本用語

### Phase vs Stage
### フェーズとステージ

### フェーズとステージ

**Phase**: One of the three high-level lifecycle phases in AI-DLC
- 🔵 **INCEPTION PHASE** - Planning & Architecture (WHAT and WHY)
- 🟢 **CONSTRUCTION PHASE** - Design, Implementation & Test (HOW)
- 🟡 **OPERATIONS PHASE** - Deployment & Monitoring (future expansion)
**フェーズ（Phase）**: AI-DLC の 3 つの上位ライフサイクルフェーズのいずれか
- 🔵 **INCEPTION フェーズ** - 計画 & アーキテクチャ（WHAT と WHY）
- 🟢 **CONSTRUCTION フェーズ** - 設計、実装 & テスト（HOW）
- 🟡 **OPERATIONS フェーズ** - デプロイ & 監視（将来拡張）

**フェーズ（Phase）**: AI-DLC の 3 つの上位ライフサイクルフェーズのいずれか
- 🔵 **INCEPTION フェーズ** - 計画 & アーキテクチャ（WHAT と WHY）
- 🟢 **CONSTRUCTION フェーズ** - 設計、実装 & テスト（HOW）
- 🟡 **OPERATIONS フェーズ** - デプロイ & 監視（将来拡張）

**Stage**: An individual workflow activity within a phase
- Examples: Context Assessment stage, Requirements Assessment stage, Code Planning stage
- Each stage has specific prerequisites, steps, and outputs
- Stages can be ALWAYS-EXECUTE or CONDITIONAL
**ステージ（Stage）**: フェーズ内の個別ワークフロー活動
- 例: Context Assessment ステージ、Requirements Assessment ステージ、Code Planning ステージ
- 各ステージには前提条件、手順、成果物がある
- ステージは ALWAYS-EXECUTE または CONDITIONAL

**ステージ（Stage）**: フェーズ内の個別ワークフロー活動
- 例: Context Assessment ステージ、Requirements Assessment ステージ、Code Planning ステージ
- 各ステージには前提条件、手順、成果物がある
- ステージは ALWAYS-EXECUTE または CONDITIONAL

**Usage Examples**:
- ✅ "The CONSTRUCTION phase contains 7 stages"
- ✅ "The Code Planning stage is always executed"
- ✅ "We're in the INCEPTION phase, executing the Requirements Assessment stage"
- ❌ "The Requirements Assessment phase" (should be "stage")
- ❌ "The CONSTRUCTION stage" (should be "phase")
**使用例**:
- ✅ "CONSTRUCTION フェーズには 7 つのステージがある"
- ✅ "Code Planning ステージは常に実行される"
- ✅ "INCEPTION フェーズで Requirements Assessment ステージを実行中"
- ❌ "Requirements Assessment フェーズ"（正しくは "ステージ"）
- ❌ "CONSTRUCTION ステージ"（正しくは "フェーズ"）

**使用例**:
- ✅ "CONSTRUCTION フェーズには 7 つのステージがある"
- ✅ "Code Planning ステージは常に実行される"
- ✅ "INCEPTION フェーズで Requirements Assessment ステージを実行中"
- ❌ "Requirements Assessment フェーズ"（正しくは "ステージ"）
- ❌ "CONSTRUCTION ステージ"（正しくは "フェーズ"）

## Three-Phase Lifecycle
## 3 フェーズライフサイクル

## 3 フェーズライフサイクル

### INCEPTION PHASE
**Purpose**: Planning and architectural decisions  
**Focus**: Determine WHAT to build and WHY  
**Location**: `inception/` directory
### INCEPTION フェーズ
**目的**: 計画とアーキテクチャ上の意思決定  
**焦点**: 何を作るかと、なぜ作るか  
**場所**: `inception/` ディレクトリ

### INCEPTION フェーズ
**目的**: 計画とアーキテクチャ上の意思決定  
**焦点**: 何を作るかと、なぜ作るか  
**場所**: `inception/` ディレクトリ

**Stages**:
- Workspace Detection (ALWAYS)
- Reverse Engineering (CONDITIONAL - Brownfield only)
- Requirements Analysis (ALWAYS - Adaptive depth)
- User Stories (CONDITIONAL)
- Workflow Planning (ALWAYS)
- Application Design (CONDITIONAL)
- Design - Units Planning/Generation (CONDITIONAL)
**ステージ**:
- Workspace Detection（常に実行）
- Reverse Engineering（条件付き - ブラウンフィールドのみ）
- Requirements Analysis（常に実行 - 深さは適応）
- User Stories（条件付き）
- Workflow Planning（常に実行）
- Application Design（条件付き）
- Design - Units Planning/Generation（条件付き）

**ステージ**:
- Workspace Detection（常に実行）
- Reverse Engineering（条件付き - ブラウンフィールドのみ）
- Requirements Analysis（常に実行 - 深さは適応）
- User Stories（条件付き）
- Workflow Planning（常に実行）
- Application Design（条件付き）
- Design - Units Planning/Generation（条件付き）

**Outputs**: Requirements, user stories, architectural decisions, unit definitions
**成果物**: 要件、ユーザーストーリー、アーキテクチャ判断、ユニット定義

**成果物**: 要件、ユーザーストーリー、アーキテクチャ判断、ユニット定義

### CONSTRUCTION PHASE
**Purpose**: Detailed design and implementation  
**Focus**: Determine HOW to build it  
**Location**: `construction/` directory
### CONSTRUCTION フェーズ
**目的**: 詳細設計と実装  
**焦点**: どのように作るか  
**場所**: `construction/` ディレクトリ

### CONSTRUCTION フェーズ
**目的**: 詳細設計と実装  
**焦点**: どのように作るか  
**場所**: `construction/` ディレクトリ

**Stages**:
- Functional Design (CONDITIONAL, per-unit)
- NFR Requirements (CONDITIONAL, per-unit)
- NFR Design (CONDITIONAL, per-unit)
- Infrastructure Design (CONDITIONAL, per-unit)
- Code Planning (ALWAYS)
- Code Generation (ALWAYS)
- Build and Test (ALWAYS)
**ステージ**:
- Functional Design（条件付き、ユニットごと）
- NFR Requirements（条件付き、ユニットごと）
- NFR Design（条件付き、ユニットごと）
- Infrastructure Design（条件付き、ユニットごと）
- Code Planning（常に実行）
- Code Generation（常に実行）
- Build and Test（常に実行）

**ステージ**:
- Functional Design（条件付き、ユニットごと）
- NFR Requirements（条件付き、ユニットごと）
- NFR Design（条件付き、ユニットごと）
- Infrastructure Design（条件付き、ユニットごと）
- Code Planning（常に実行）
- Code Generation（常に実行）
- Build and Test（常に実行）

**Outputs**: Design artifacts, NFR implementations, code, tests
**成果物**: 設計成果物、NFR 実装、コード、テスト

**成果物**: 設計成果物、NFR 実装、コード、テスト

### OPERATIONS PHASE
**Purpose**: Deployment and operational readiness  
**Focus**: How to DEPLOY and RUN it  
**Location**: `operations/` directory
### OPERATIONS フェーズ
**目的**: デプロイと運用準備  
**焦点**: どのようにデプロイして運用するか  
**場所**: `operations/` ディレクトリ

### OPERATIONS フェーズ
**目的**: デプロイと運用準備  
**焦点**: どのようにデプロイして運用するか  
**場所**: `operations/` ディレクトリ

**Stages**:
- Operations (PLACEHOLDER)
**ステージ**:
- Operations（プレースホルダー）

**ステージ**:
- Operations（プレースホルダー）

**Outputs**: Build instructions, deployment guides, monitoring setup, verification procedures
**成果物**: ビルド手順、デプロイ手順、監視設定、検証手順

**成果物**: ビルド手順、デプロイ手順、監視設定、検証手順

---
---

---

## Workflow Stages
## ワークフローステージ

## ワークフローステージ

### Always-Execute Stages
- **Workspace Detection**: Initial analysis of workspace state and project type
- **Requirements Analysis**: Gathering requirements (depth varies based on complexity)
- **Workflow Planning**: Creating execution plan for which phases to run
- **Code Planning**: Creating detailed implementation plans for code generation
- **Code Generation**: Generating actual code based on plans and prior artifacts
- **Build and Test**: Building all units and executing comprehensive testing
### 常に実行されるステージ
- **Workspace Detection**: ワークスペース状態とプロジェクト種別の初期分析
- **Requirements Analysis**: 要件収集（深さは複雑さで変化）
- **Workflow Planning**: 実行するフェーズの計画作成
- **Code Planning**: コード生成の詳細実装計画を作成
- **Code Generation**: 計画と成果物に基づくコード生成
- **Build and Test**: 全ユニットのビルドと包括的テスト

### 常に実行されるステージ
- **Workspace Detection**: ワークスペース状態とプロジェクト種別の初期分析
- **Requirements Analysis**: 要件収集（深さは複雑さで変化）
- **Workflow Planning**: 実行するフェーズの計画作成
- **Code Planning**: コード生成の詳細実装計画を作成
- **Code Generation**: 計画と成果物に基づくコード生成
- **Build and Test**: 全ユニットのビルドと包括的テスト

### Conditional Stages
- **Reverse Engineering**: Analyzing existing codebase (brownfield projects only)
- **User Stories**: Creating user stories and personas (includes Story Planning and Story Generation)
- **Application Design**: Designing application components, methods, business rules, and services
- **Design**: Designing system components (includes Units Planning, Units Generation, per-unit design)
- **Functional Design**: Technology-agnostic business logic design (per-unit)
- **NFR Requirements**: Determining NFRs and selecting tech stack (per-unit)
- **NFR Design**: Incorporating NFR patterns and logical components (per-unit)
- **Infrastructure Design**: Mapping to actual infrastructure services (per-unit)
### 条件付きステージ
- **Reverse Engineering**: 既存コードベース分析（ブラウンフィールドのみ）
- **User Stories**: ユーザーストーリーとペルソナ作成（Story Planning と Story Generation を含む）
- **Application Design**: コンポーネント、メソッド、ビジネスルール、サービスの設計
- **Design**: システムコンポーネントの設計（Units Planning, Units Generation, ユニットごとの設計）
- **Functional Design**: 技術非依存のビジネスロジック設計（ユニットごと）
- **NFR Requirements**: NFR の決定と技術スタック選定（ユニットごと）
- **NFR Design**: NFR パターンと論理コンポーネントの取り込み（ユニットごと）
- **Infrastructure Design**: 実際のインフラサービスへのマッピング（ユニットごと）

### 条件付きステージ
- **Reverse Engineering**: 既存コードベース分析（ブラウンフィールドのみ）
- **User Stories**: ユーザーストーリーとペルソナ作成（Story Planning と Story Generation を含む）
- **Application Design**: コンポーネント、メソッド、ビジネスルール、サービスの設計
- **Design**: システムコンポーネントの設計（Units Planning, Units Generation, ユニットごとの設計）
- **Functional Design**: 技術非依存のビジネスロジック設計（ユニットごと）
- **NFR Requirements**: NFR の決定と技術スタック選定（ユニットごと）
- **NFR Design**: NFR パターンと論理コンポーネントの取り込み（ユニットごと）
- **Infrastructure Design**: 実際のインフラサービスへのマッピング（ユニットごと）

## Application Design Terms
## アプリケーション設計用語

## アプリケーション設計用語

- **Component**: A functional unit with specific responsibilities
- **Method**: A function or operation within a component with defined business rules
- **Business Rule**: Logic that governs method behavior and validation
- **Service**: Orchestration layer that coordinates business logic across components
- **Component Dependency**: Relationship and communication pattern between components
- **Component**: 特定の責務を持つ機能単位
- **Method**: コンポーネント内の関数/操作（ビジネスルールを含む）
- **Business Rule**: メソッドの挙動と検証を制御するロジック
- **Service**: 複数コンポーネントのビジネスロジックを調整するオーケストレーション層
- **Component Dependency**: コンポーネント間の関係と通信パターン

- **Component**: 特定の責務を持つ機能単位
- **Method**: コンポーネント内の関数/操作（ビジネスルールを含む）
- **Business Rule**: メソッドの挙動と検証を制御するロジック
- **Service**: 複数コンポーネントのビジネスロジックを調整するオーケストレーション層
- **Component Dependency**: コンポーネント間の関係と通信パターン

## Architecture Terms (Infrastructure)
## アーキテクチャ用語（インフラ）

## アーキテクチャ用語（インフラ）

### Unit of Work
A logical grouping of user stories for development purposes. The term used during planning and decomposition.
### Unit of Work
開発のためのユーザーストーリーの論理的グルーピング。計画と分解で使う用語。

### Unit of Work
開発のためのユーザーストーリーの論理的グルーピング。計画と分解で使う用語。

**Usage**: "We need to decompose the system into units of work"
**使用例**: "システムをユニット・オブ・ワークに分解する必要がある"

**使用例**: "システムをユニット・オブ・ワークに分解する必要がある"

### Service
An independently deployable component in a microservices architecture. Each service is a separate unit of work.
### Service
マイクロサービスアーキテクチャで独立してデプロイ可能なコンポーネント。各サービスは独立したユニット。

### Service
マイクロサービスアーキテクチャで独立してデプロイ可能なコンポーネント。各サービスは独立したユニット。

**Usage**: "The Payment Service handles all payment processing"
**使用例**: "Payment Service がすべての決済処理を担当"

**使用例**: "Payment Service がすべての決済処理を担当"

### Module
A logical grouping of functionality within a single service or monolith. Modules are not independently deployable.
### Module
単一サービスまたはモノリス内の機能の論理的グルーピング。独立デプロイ不可。

### Module
単一サービスまたはモノリス内の機能の論理的グルーピング。独立デプロイ不可。

**Usage**: "The authentication module within the User Service"
**使用例**: "User Service 内の認証モジュール"

**使用例**: "User Service 内の認証モジュール"

### Component
A reusable building block within a service or module. Components are classes, functions, or packages that provide specific functionality.
### Component
サービスやモジュール内の再利用可能なビルディングブロック。クラス、関数、パッケージなど。

### Component
サービスやモジュール内の再利用可能なビルディングブロック。クラス、関数、パッケージなど。

**Usage**: "The EmailValidator component validates email addresses"
**使用例**: "EmailValidator コンポーネントがメールアドレスを検証"

**使用例**: "EmailValidator コンポーネントがメールアドレスを検証"

## Terminology Guidelines
## 用語の使い分け

## 用語の使い分け

### When to Use Each Term
### 各用語の使用タイミング

### 各用語の使用タイミング

**Unit of Work**:
- During Units Planning and Units Generation phases
- When discussing system decomposition
- In planning documents and discussions
- Example: "How should we decompose this into units of work?"
**Unit of Work**:
- Units Planning/Units Generation フェーズ中
- システム分解の議論
- 計画ドキュメントや議論で使用
- 例: "これをユニット・オブ・ワークにどう分解すべきか？"

**Unit of Work**:
- Units Planning/Units Generation フェーズ中
- システム分解の議論
- 計画ドキュメントや議論で使用
- 例: "これをユニット・オブ・ワークにどう分解すべきか？"

**Service**:
- When referring to independently deployable components
- In microservices architecture contexts
- In deployment and infrastructure discussions
- Example: "The Order Service will be deployed to ECS"
**Service**:
- 独立デプロイ可能なコンポーネントを指す場合
- マイクロサービス文脈
- デプロイ/インフラの議論
- 例: "Order Service は ECS にデプロイされる"

**Service**:
- 独立デプロイ可能なコンポーネントを指す場合
- マイクロサービス文脈
- デプロイ/インフラの議論
- 例: "Order Service は ECS にデプロイされる"

**Module**:
- When referring to logical groupings within a service
- In monolith architecture contexts
- When discussing internal organization
- Example: "The reporting module generates all reports"
**Module**:
- サービス内の論理グループを指す場合
- モノリス文脈
- 内部構成の議論
- 例: "レポーティングモジュールがすべてのレポートを生成"

**Module**:
- サービス内の論理グループを指す場合
- モノリス文脈
- 内部構成の議論
- 例: "レポーティングモジュールがすべてのレポートを生成"

**Component**:
- When referring to specific classes, functions, or packages
- In design and implementation discussions
- When discussing reusable building blocks
- Example: "The DatabaseConnection component manages connections"
**Component**:
- 具体的なクラス/関数/パッケージを指す場合
- 設計/実装の議論
- 再利用ビルディングブロックの議論
- 例: "DatabaseConnection コンポーネントが接続を管理"

**Component**:
- 具体的なクラス/関数/パッケージを指す場合
- 設計/実装の議論
- 再利用ビルディングブロックの議論
- 例: "DatabaseConnection コンポーネントが接続を管理"

## Stage Terminology
## ステージ用語

## ステージ用語

### Planning vs Generation
- **Planning**: Creating a plan with questions and checkboxes for execution
- **Generation**: Executing the plan to create artifacts
### Planning と Generation
- **Planning**: 質問とチェックボックス付きの実行計画を作成
- **Generation**: 計画を実行して成果物を生成

### Planning と Generation
- **Planning**: 質問とチェックボックス付きの実行計画を作成
- **Generation**: 計画を実行して成果物を生成

Examples:
- Story Planning → Story Generation
- Units Planning → Units Generation
- Unit Design Planning → Unit Design Generation
- NFR Planning → NFR Generation
- Code Planning → Code Generation
例:
- Story Planning → Story Generation
- Units Planning → Units Generation
- Unit Design Planning → Unit Design Generation
- NFR Planning → NFR Generation
- Code Planning → Code Generation

例:
- Story Planning → Story Generation
- Units Planning → Units Generation
- Unit Design Planning → Unit Design Generation
- NFR Planning → NFR Generation
- Code Planning → Code Generation

### Depth Levels
- **Minimal**: Quick, focused execution for simple changes
- **Standard**: Normal depth with standard artifacts for typical projects
- **Comprehensive**: Full depth with all artifacts for complex/high-risk projects
### 詳細度レベル
- **Minimal**: 単純な変更向けの迅速で焦点を絞った実行
- **Standard**: 一般的なプロジェクト向けの標準的な深さ
- **Comprehensive**: 複雑/高リスク向けの完全な深さ

### 詳細度レベル
- **Minimal**: 単純な変更向けの迅速で焦点を絞った実行
- **Standard**: 一般的なプロジェクト向けの標準的な深さ
- **Comprehensive**: 複雑/高リスク向けの完全な深さ

## Artifact Types
## 成果物の種類

## 成果物の種類

### Plans
Documents with checkboxes and questions that guide execution.
- Located in `aidlc-docs/plans/`
- Examples: `story-generation-plan.md`, `unit-of-work-plan.md`
### Plans
実行を導くチェックボックスと質問を含む文書。
- `aidlc-docs/plans/` に配置
- 例: `story-generation-plan.md`, `unit-of-work-plan.md`

### Plans
実行を導くチェックボックスと質問を含む文書。
- `aidlc-docs/plans/` に配置
- 例: `story-generation-plan.md`, `unit-of-work-plan.md`

### Artifacts
Generated outputs from executing plans.
- Located in various `aidlc-docs/` subdirectories
- Examples: `requirements.md`, `stories.md`, `design.md`
### Artifacts
計画を実行して生成される成果物。
- `aidlc-docs/` 配下の各サブディレクトリ
- 例: `requirements.md`, `stories.md`, `design.md`

### Artifacts
計画を実行して生成される成果物。
- `aidlc-docs/` 配下の各サブディレクトリ
- 例: `requirements.md`, `stories.md`, `design.md`

### State Files
Files tracking workflow progress and status.
- `aidlc-state.md`: Overall workflow state
- `audit.md`: Complete audit trail of all interactions
### State Files
ワークフローの進捗と状態を追跡するファイル。
- `aidlc-state.md`: ワークフロー全体の状態
- `audit.md`: すべてのやり取りの監査ログ

### State Files
ワークフローの進捗と状態を追跡するファイル。
- `aidlc-state.md`: ワークフロー全体の状態
- `audit.md`: すべてのやり取りの監査ログ

## Common Abbreviations
## よく使う略語

## よく使う略語

- **AI-DLC**: AI-Driven Development Life Cycle
- **NFR**: Non-Functional Requirements
- **UOW**: Unit of Work
- **API**: Application Programming Interface
- **CDK**: Cloud Development Kit (AWS)
- **AI-DLC**: AI-Driven Development Life Cycle
- **NFR**: Non-Functional Requirements
- **UOW**: Unit of Work
- **API**: Application Programming Interface
- **CDK**: Cloud Development Kit (AWS)

- **AI-DLC**: AI-Driven Development Life Cycle
- **NFR**: Non-Functional Requirements
- **UOW**: Unit of Work
- **API**: Application Programming Interface
- **CDK**: Cloud Development Kit (AWS)
