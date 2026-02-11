# Reverse Engineering
# Reverse Engineering

# Reverse Engineering

**Purpose**: Analyze existing codebase and generate comprehensive design artifacts
**目的**: 既存コードベースを分析し、包括的な設計成果物を生成する

**目的**: 既存コードベースを分析し、包括的な設計成果物を生成する

**Execute when**: Brownfield project detected (existing code found in workspace)
**実行条件**: ブラウンフィールド（ワークスペースに既存コード）

**実行条件**: ブラウンフィールド（ワークスペースに既存コード）

**Skip when**: Greenfield project (no existing code)
**スキップ条件**: グリーンフィールド（既存コードなし）

**スキップ条件**: グリーンフィールド（既存コードなし）

**Rerun behavior**: Always rerun when brownfield project detected, even if artifacts exist. This ensures artifacts reflect current code state
**再実行の挙動**: ブラウンフィールドが検出された場合は、成果物が存在していても常に再実行する。これにより成果物が現在のコード状態を反映する。

**再実行の挙動**: ブラウンフィールドが検出された場合は、成果物が存在していても常に再実行する。これにより成果物が現在のコード状態を反映する。

## Step 1: Multi-Package Discovery
## ステップ 1: マルチパッケージの検出

## ステップ 1: マルチパッケージの検出

### 1.1 Scan Workspace
- All packages (not just mentioned ones)
- Package relationships via config files
- Package types: Application, CDK/Infrastructure, Models, Clients, Tests
### 1.1 ワークスペースのスキャン
- 言及されたものだけでなく **全パッケージ** を対象
- 設定ファイルを介したパッケージ関係
- パッケージ種別: Application, CDK/Infrastructure, Models, Clients, Tests

### 1.1 ワークスペースのスキャン
- 言及されたものだけでなく **全パッケージ** を対象
- 設定ファイルを介したパッケージ関係
- パッケージ種別: Application, CDK/Infrastructure, Models, Clients, Tests

### 1.2 Understand the Business Context
- The core business that the system is implementing overall
- The business overview of every package
- List of Business Transactions that are implemented in the system
### 1.2 ビジネス文脈の理解
- システム全体が実装しているコアビジネス
- 各パッケージのビジネス概要
- システムが実装しているビジネストランザクションの一覧

### 1.2 ビジネス文脈の理解
- システム全体が実装しているコアビジネス
- 各パッケージのビジネス概要
- システムが実装しているビジネストランザクションの一覧

### 1.3 Infrastructure Discovery
- CDK packages (package.json with CDK dependencies)
- Terraform (.tf files)
- CloudFormation (.yaml/.json templates)
- Deployment scripts
### 1.3 インフラ検出
- CDK パッケージ（CDK 依存を含む package.json）
- Terraform（.tf ファイル）
- CloudFormation（.yaml/.json テンプレート）
- デプロイスクリプト

### 1.3 インフラ検出
- CDK パッケージ（CDK 依存を含む package.json）
- Terraform（.tf ファイル）
- CloudFormation（.yaml/.json テンプレート）
- デプロイスクリプト

### 1.4 Build System Discovery
- Build systems: Brazil, Maven, Gradle, npm
- Config files for build-system declarations
- Build dependencies between packages
### 1.4 ビルドシステムの検出
- ビルドシステム: Brazil, Maven, Gradle, npm
- ビルド宣言の設定ファイル
- パッケージ間のビルド依存

### 1.4 ビルドシステムの検出
- ビルドシステム: Brazil, Maven, Gradle, npm
- ビルド宣言の設定ファイル
- パッケージ間のビルド依存

### 1.5 Service Architecture Discovery
- Lambda functions (handlers, triggers)
- Container services (Docker/ECS configs)
- API definitions (Smithy models, OpenAPI specs)
- Data stores (DynamoDB, S3, etc.)
### 1.5 サービスアーキテクチャの検出
- Lambda 関数（ハンドラ、トリガー）
- コンテナサービス（Docker/ECS 設定）
- API 定義（Smithy モデル、OpenAPI 仕様）
- データストア（DynamoDB、S3 など）

### 1.5 サービスアーキテクチャの検出
- Lambda 関数（ハンドラ、トリガー）
- コンテナサービス（Docker/ECS 設定）
- API 定義（Smithy モデル、OpenAPI 仕様）
- データストア（DynamoDB、S3 など）

### 1.6 Code Quality Analysis
- Programming languages and frameworks
- Test coverage indicators
- Linting configurations
- CI/CD pipelines
### 1.6 コード品質分析
- 使用言語とフレームワーク
- テストカバレッジ指標
- Lint 設定
- CI/CD パイプライン

### 1.6 コード品質分析
- 使用言語とフレームワーク
- テストカバレッジ指標
- Lint 設定
- CI/CD パイプライン

## Step 1: Generate Business Overview Documentation
## ステップ 1: ビジネス概要ドキュメントの生成

## ステップ 1: ビジネス概要ドキュメントの生成

Create `aidlc-docs/inception/reverse-engineering/business-overview.md`:
`aidlc-docs/inception/reverse-engineering/business-overview.md` を作成:

`aidlc-docs/inception/reverse-engineering/business-overview.md` を作成:

```markdown
# Business Overview

## Business Context Diagram
[Mermaid diagram showing the Business Context]

## Business Description
- **Business Description**: [Overall Business description of what the system does]
- **Business Transactions**: [List of Business Transactions that the system implements and their descriptions]
- **Business Dictionary**: [Business dictionary terms that the system follows and their meaning]

## Component Level Business Descriptions
### [Package/Component Name]
- **Purpose**: [What it does from the business perspective]
- **Responsibilities**: [Key responsibilities]
```
```markdown
# Business Overview

## Business Context Diagram
[Mermaid diagram showing the Business Context]

## Business Description
- **Business Description**: [Overall Business description of what the system does]
- **Business Transactions**: [List of Business Transactions that the system implements and their descriptions]
- **Business Dictionary**: [Business dictionary terms that the system follows and their meaning]

## Component Level Business Descriptions
### [Package/Component Name]
- **Purpose**: [What it does from the business perspective]
- **Responsibilities**: [Key responsibilities]
```

```markdown
# Business Overview

## Business Context Diagram
[Mermaid diagram showing the Business Context]

## Business Description
- **Business Description**: [Overall Business description of what the system does]
- **Business Transactions**: [List of Business Transactions that the system implements and their descriptions]
- **Business Dictionary**: [Business dictionary terms that the system follows and their meaning]

## Component Level Business Descriptions
### [Package/Component Name]
- **Purpose**: [What it does from the business perspective]
- **Responsibilities**: [Key responsibilities]
```

## Step 2: Generate Architecture Documentation
## ステップ 2: アーキテクチャドキュメントの生成

## ステップ 2: アーキテクチャドキュメントの生成

Create `aidlc-docs/inception/reverse-engineering/architecture.md`:
`aidlc-docs/inception/reverse-engineering/architecture.md` を作成:

`aidlc-docs/inception/reverse-engineering/architecture.md` を作成:

```markdown
# System Architecture

## System Overview
[High-level description of the system]

## Architecture Diagram
[Mermaid diagram showing all packages, services, data stores, relationships]

## Component Descriptions
### [Package/Component Name]
- **Purpose**: [What it does]
- **Responsibilities**: [Key responsibilities]
- **Dependencies**: [What it depends on]
- **Type**: [Application/Infrastructure/Model/Client/Test]

## Data Flow
[Mermaid sequence diagram of key workflows]

## Integration Points
- **External APIs**: [List with purposes]
- **Databases**: [List with purposes]
- **Third-party Services**: [List with purposes]

## Infrastructure Components
- **CDK Stacks**: [List with purposes]
- **Deployment Model**: [Description]
- **Networking**: [VPC, subnets, security groups]
```
```markdown
# System Architecture

## System Overview
[High-level description of the system]

## Architecture Diagram
[Mermaid diagram showing all packages, services, data stores, relationships]

## Component Descriptions
### [Package/Component Name]
- **Purpose**: [What it does]
- **Responsibilities**: [Key responsibilities]
- **Dependencies**: [What it depends on]
- **Type**: [Application/Infrastructure/Model/Client/Test]

## Data Flow
[Mermaid sequence diagram of key workflows]

## Integration Points
- **External APIs**: [List with purposes]
- **Databases**: [List with purposes]
- **Third-party Services**: [List with purposes]

## Infrastructure Components
- **CDK Stacks**: [List with purposes]
- **Deployment Model**: [Description]
- **Networking**: [VPC, subnets, security groups]
```

```markdown
# System Architecture

## System Overview
[High-level description of the system]

## Architecture Diagram
[Mermaid diagram showing all packages, services, data stores, relationships]

## Component Descriptions
### [Package/Component Name]
- **Purpose**: [What it does]
- **Responsibilities**: [Key responsibilities]
- **Dependencies**: [What it depends on]
- **Type**: [Application/Infrastructure/Model/Client/Test]

## Data Flow
[Mermaid sequence diagram of key workflows]

## Integration Points
- **External APIs**: [List with purposes]
- **Databases**: [List with purposes]
- **Third-party Services**: [List with purposes]

## Infrastructure Components
- **CDK Stacks**: [List with purposes]
- **Deployment Model**: [Description]
- **Networking**: [VPC, subnets, security groups]
```

## Step 3: Generate Code Structure Documentation
## ステップ 3: コード構造ドキュメントの生成

## ステップ 3: コード構造ドキュメントの生成

Create `aidlc-docs/inception/reverse-engineering/code-structure.md`:
`aidlc-docs/inception/reverse-engineering/code-structure.md` を作成:

`aidlc-docs/inception/reverse-engineering/code-structure.md` を作成:

```markdown
# Code Structure

## Build System
- **Type**: [Maven/Gradle/npm/Brazil]
- **Configuration**: [Key build files and settings]

## Key Classes/Modules
[Mermaid class diagram or module hierarchy]

### Existing Files Inventory
[List all source files with their purposes - these are candidates for modification in brownfield projects]

**Example format**:
- `[path/to/file]` - [Purpose/responsibility]

## Design Patterns
### [Pattern Name]
- **Location**: [Where used]
- **Purpose**: [Why used]
- **Implementation**: [How implemented]

## Critical Dependencies
### [Dependency Name]
- **Version**: [Version number]
- **Usage**: [How and where used]
- **Purpose**: [Why needed]
```
```markdown
# Code Structure

## Build System
- **Type**: [Maven/Gradle/npm/Brazil]
- **Configuration**: [Key build files and settings]

## Key Classes/Modules
[Mermaid class diagram or module hierarchy]

### Existing Files Inventory
[List all source files with their purposes - these are candidates for modification in brownfield projects]

**Example format**:
- `[path/to/file]` - [Purpose/responsibility]

## Design Patterns
### [Pattern Name]
- **Location**: [Where used]
- **Purpose**: [Why used]
- **Implementation**: [How implemented]

## Critical Dependencies
### [Dependency Name]
- **Version**: [Version number]
- **Usage**: [How and where used]
- **Purpose**: [Why needed]
```

```markdown
# Code Structure

## Build System
- **Type**: [Maven/Gradle/npm/Brazil]
- **Configuration**: [Key build files and settings]

## Key Classes/Modules
[Mermaid class diagram or module hierarchy]

### Existing Files Inventory
[List all source files with their purposes - these are candidates for modification in brownfield projects]

**Example format**:
- `[path/to/file]` - [Purpose/responsibility]

## Design Patterns
### [Pattern Name]
- **Location**: [Where used]
- **Purpose**: [Why used]
- **Implementation**: [How implemented]

## Critical Dependencies
### [Dependency Name]
- **Version**: [Version number]
- **Usage**: [How and where used]
- **Purpose**: [Why needed]
```

## Step 4: Generate API Documentation
## ステップ 4: API ドキュメントの生成

## ステップ 4: API ドキュメントの生成

Create `aidlc-docs/inception/reverse-engineering/api-documentation.md`:
`aidlc-docs/inception/reverse-engineering/api-documentation.md` を作成:

`aidlc-docs/inception/reverse-engineering/api-documentation.md` を作成:

```markdown
# API Documentation

## REST APIs
### [Endpoint Name]
- **Method**: [GET/POST/PUT/DELETE]
- **Path**: [/api/path]
- **Purpose**: [What it does]
- **Request**: [Request format]
- **Response**: [Response format]

## Internal APIs
### [Interface/Class Name]
- **Methods**: [List with signatures]
- **Parameters**: [Parameter descriptions]
- **Return Types**: [Return type descriptions]

## Data Models
### [Model Name]
- **Fields**: [Field descriptions]
- **Relationships**: [Related models]
- **Validation**: [Validation rules]
```
```markdown
# API Documentation

## REST APIs
### [Endpoint Name]
- **Method**: [GET/POST/PUT/DELETE]
- **Path**: [/api/path]
- **Purpose**: [What it does]
- **Request**: [Request format]
- **Response**: [Response format]

## Internal APIs
### [Interface/Class Name]
- **Methods**: [List with signatures]
- **Parameters**: [Parameter descriptions]
- **Return Types**: [Return type descriptions]

## Data Models
### [Model Name]
- **Fields**: [Field descriptions]
- **Relationships**: [Related models]
- **Validation**: [Validation rules]
```

```markdown
# API Documentation

## REST APIs
### [Endpoint Name]
- **Method**: [GET/POST/PUT/DELETE]
- **Path**: [/api/path]
- **Purpose**: [What it does]
- **Request**: [Request format]
- **Response**: [Response format]

## Internal APIs
### [Interface/Class Name]
- **Methods**: [List with signatures]
- **Parameters**: [Parameter descriptions]
- **Return Types**: [Return type descriptions]

## Data Models
### [Model Name]
- **Fields**: [Field descriptions]
- **Relationships**: [Related models]
- **Validation**: [Validation rules]
```

## Step 5: Generate Component Inventory
## ステップ 5: コンポーネント在庫の生成

## ステップ 5: コンポーネント在庫の生成

Create `aidlc-docs/inception/reverse-engineering/component-inventory.md`:
`aidlc-docs/inception/reverse-engineering/component-inventory.md` を作成:

`aidlc-docs/inception/reverse-engineering/component-inventory.md` を作成:

```markdown
# Component Inventory

## Application Packages
- [Package name] - [Purpose]

## Infrastructure Packages
- [Package name] - [CDK/Terraform] - [Purpose]

## Shared Packages
- [Package name] - [Models/Utilities/Clients] - [Purpose]

## Test Packages
- [Package name] - [Integration/Load/Unit] - [Purpose]

## Total Count
- **Total Packages**: [Number]
- **Application**: [Number]
- **Infrastructure**: [Number]
- **Shared**: [Number]
- **Test**: [Number]
```
```markdown
# Component Inventory

## Application Packages
- [Package name] - [Purpose]

## Infrastructure Packages
- [Package name] - [CDK/Terraform] - [Purpose]

## Shared Packages
- [Package name] - [Models/Utilities/Clients] - [Purpose]

## Test Packages
- [Package name] - [Integration/Load/Unit] - [Purpose]

## Total Count
- **Total Packages**: [Number]
- **Application**: [Number]
- **Infrastructure**: [Number]
- **Shared**: [Number]
- **Test**: [Number]
```

```markdown
# Component Inventory

## Application Packages
- [Package name] - [Purpose]

## Infrastructure Packages
- [Package name] - [CDK/Terraform] - [Purpose]

## Shared Packages
- [Package name] - [Models/Utilities/Clients] - [Purpose]

## Test Packages
- [Package name] - [Integration/Load/Unit] - [Purpose]

## Total Count
- **Total Packages**: [Number]
- **Application**: [Number]
- **Infrastructure**: [Number]
- **Shared**: [Number]
- **Test**: [Number]
```

## Step 6: Generate Technology Stack Documentation
## ステップ 6: 技術スタックドキュメントの生成

## ステップ 6: 技術スタックドキュメントの生成

Create `aidlc-docs/inception/reverse-engineering/technology-stack.md`:
`aidlc-docs/inception/reverse-engineering/technology-stack.md` を作成:

`aidlc-docs/inception/reverse-engineering/technology-stack.md` を作成:

```markdown
# Technology Stack

## Programming Languages
- [Language] - [Version] - [Usage]

## Frameworks
- [Framework] - [Version] - [Purpose]

## Infrastructure
- [Service] - [Purpose]

## Build Tools
- [Tool] - [Version] - [Purpose]

## Testing Tools
- [Tool] - [Version] - [Purpose]
```
```markdown
# Technology Stack

## Programming Languages
- [Language] - [Version] - [Usage]

## Frameworks
- [Framework] - [Version] - [Purpose]

## Infrastructure
- [Service] - [Purpose]

## Build Tools
- [Tool] - [Version] - [Purpose]

## Testing Tools
- [Tool] - [Version] - [Purpose]
```

```markdown
# Technology Stack

## Programming Languages
- [Language] - [Version] - [Usage]

## Frameworks
- [Framework] - [Version] - [Purpose]

## Infrastructure
- [Service] - [Purpose]

## Build Tools
- [Tool] - [Version] - [Purpose]

## Testing Tools
- [Tool] - [Version] - [Purpose]
```

## Step 7: Generate Dependencies Documentation
## ステップ 7: 依存関係ドキュメントの生成

## ステップ 7: 依存関係ドキュメントの生成

Create `aidlc-docs/inception/reverse-engineering/dependencies.md`:
`aidlc-docs/inception/reverse-engineering/dependencies.md` を作成:

`aidlc-docs/inception/reverse-engineering/dependencies.md` を作成:

```markdown
# Dependencies

## Internal Dependencies
[Mermaid diagram showing package dependencies]

### [Package A] depends on [Package B]
- **Type**: [Compile/Runtime/Test]
- **Reason**: [Why dependency exists]

## External Dependencies
### [Dependency Name]
- **Version**: [Version]
- **Purpose**: [Why used]
- **License**: [License type]
```
```markdown
# Dependencies

## Internal Dependencies
[Mermaid diagram showing package dependencies]

### [Package A] depends on [Package B]
- **Type**: [Compile/Runtime/Test]
- **Reason**: [Why dependency exists]

## External Dependencies
### [Dependency Name]
- **Version**: [Version]
- **Purpose**: [Why used]
- **License**: [License type]
```

```markdown
# Dependencies

## Internal Dependencies
[Mermaid diagram showing package dependencies]

### [Package A] depends on [Package B]
- **Type**: [Compile/Runtime/Test]
- **Reason**: [Why dependency exists]

## External Dependencies
### [Dependency Name]
- **Version**: [Version]
- **Purpose**: [Why used]
- **License**: [License type]
```

## Step 8: Generate Code Quality Assessment
## ステップ 8: コード品質評価の生成

## ステップ 8: コード品質評価の生成

Create `aidlc-docs/inception/reverse-engineering/code-quality-assessment.md`:
`aidlc-docs/inception/reverse-engineering/code-quality-assessment.md` を作成:

`aidlc-docs/inception/reverse-engineering/code-quality-assessment.md` を作成:

```markdown
# Code Quality Assessment

## Test Coverage
- **Overall**: [Percentage or Good/Fair/Poor/None]
- **Unit Tests**: [Status]
- **Integration Tests**: [Status]

## Code Quality Indicators
- **Linting**: [Configured/Not configured]
- **Code Style**: [Consistent/Inconsistent]
- **Documentation**: [Good/Fair/Poor]

## Technical Debt
- [Issue description and location]

## Patterns and Anti-patterns
- **Good Patterns**: [List]
- **Anti-patterns**: [List with locations]
```
```markdown
# Code Quality Assessment

## Test Coverage
- **Overall**: [Percentage or Good/Fair/Poor/None]
- **Unit Tests**: [Status]
- **Integration Tests**: [Status]

## Code Quality Indicators
- **Linting**: [Configured/Not configured]
- **Code Style**: [Consistent/Inconsistent]
- **Documentation**: [Good/Fair/Poor]

## Technical Debt
- [Issue description and location]

## Patterns and Anti-patterns
- **Good Patterns**: [List]
- **Anti-patterns**: [List with locations]
```

```markdown
# Code Quality Assessment

## Test Coverage
- **Overall**: [Percentage or Good/Fair/Poor/None]
- **Unit Tests**: [Status]
- **Integration Tests**: [Status]

## Code Quality Indicators
- **Linting**: [Configured/Not configured]
- **Code Style**: [Consistent/Inconsistent]
- **Documentation**: [Good/Fair/Poor]

## Technical Debt
- [Issue description and location]

## Patterns and Anti-patterns
- **Good Patterns**: [List]
- **Anti-patterns**: [List with locations]
```

## Step 9: Create Timestamp File
## ステップ 9: タイムスタンプファイルの作成

## ステップ 9: タイムスタンプファイルの作成

Create `aidlc-docs/inception/reverse-engineering/reverse-engineering-timestamp.md`:
`aidlc-docs/inception/reverse-engineering/reverse-engineering-timestamp.md` を作成:

`aidlc-docs/inception/reverse-engineering/reverse-engineering-timestamp.md` を作成:

```markdown
# Reverse Engineering Metadata

**Analysis Date**: [ISO timestamp]
**Analyzer**: AI-DLC
**Workspace**: [Workspace path]
**Total Files Analyzed**: [Number]

## Artifacts Generated
- [x] architecture.md
- [x] code-structure.md
- [x] api-documentation.md
- [x] component-inventory.md
- [x] technology-stack.md
- [x] dependencies.md
- [x] code-quality-assessment.md
```
```markdown
# Reverse Engineering Metadata

**Analysis Date**: [ISO timestamp]
**Analyzer**: AI-DLC
**Workspace**: [Workspace path]
**Total Files Analyzed**: [Number]

## Artifacts Generated
- [x] architecture.md
- [x] code-structure.md
- [x] api-documentation.md
- [x] component-inventory.md
- [x] technology-stack.md
- [x] dependencies.md
- [x] code-quality-assessment.md
```

```markdown
# Reverse Engineering Metadata

**Analysis Date**: [ISO timestamp]
**Analyzer**: AI-DLC
**Workspace**: [Workspace path]
**Total Files Analyzed**: [Number]

## Artifacts Generated
- [x] architecture.md
- [x] code-structure.md
- [x] api-documentation.md
- [x] component-inventory.md
- [x] technology-stack.md
- [x] dependencies.md
- [x] code-quality-assessment.md
```

## Step 10: Update State Tracking
## ステップ 10: 状態追跡の更新

## ステップ 10: 状態追跡の更新

Update `aidlc-docs/aidlc-state.md`:
`aidlc-docs/aidlc-state.md` を更新:

`aidlc-docs/aidlc-state.md` を更新:

```markdown
## Reverse Engineering Status
- [x] Reverse Engineering - Completed on [timestamp]
- **Artifacts Location**: aidlc-docs/inception/reverse-engineering/
```
```markdown
## Reverse Engineering Status
- [x] Reverse Engineering - Completed on [timestamp]
- **Artifacts Location**: aidlc-docs/inception/reverse-engineering/
```

```markdown
## Reverse Engineering Status
- [x] Reverse Engineering - Completed on [timestamp]
- **Artifacts Location**: aidlc-docs/inception/reverse-engineering/
```

## Step 11: Present Completion Message to User
## ステップ 11: 完了メッセージの提示

## ステップ 11: 完了メッセージの提示

```markdown
# 🔍 Reverse Engineering Complete

[AI-generated summary of key findings from analysis in the form of bullet points]

> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the reverse engineering artifacts at: `aidlc-docs/inception/reverse-engineering/`

> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the reverse engineering analysis if required
> ✅ **Approve & Continue** - Approve analysis and proceed to **Requirements Analysis**
```
```markdown
# 🔍 Reverse Engineering Complete

[AI-generated summary of key findings from analysis in the form of bullet points]

> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the reverse engineering artifacts at: `aidlc-docs/inception/reverse-engineering/`

> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the reverse engineering analysis if required
> ✅ **Approve & Continue** - Approve analysis and proceed to **Requirements Analysis**
```

```markdown
# 🔍 Reverse Engineering Complete

[AI-generated summary of key findings from analysis in the form of bullet points]

> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the reverse engineering artifacts at: `aidlc-docs/inception/reverse-engineering/`

> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the reverse engineering analysis if required
> ✅ **Approve & Continue** - Approve analysis and proceed to **Requirements Analysis**
```

## Step 12: Wait for User Approval
## ステップ 12: ユーザー承認待ち

## ステップ 12: ユーザー承認待ち

- **MANDATORY**: Do not proceed until user explicitly approves
- **MANDATORY**: Log user's response in audit.md with complete raw input
- **必須**: ユーザーが明示的に承認するまで進めない
- **必須**: ユーザーの応答を生の入力として audit.md に記録

- **必須**: ユーザーが明示的に承認するまで進めない
- **必須**: ユーザーの応答を生の入力として audit.md に記録
