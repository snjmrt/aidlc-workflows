# Reverse Engineering

**目的**: 既存コードベースを分析し、包括的な設計成果物を生成する

**実行条件**: ブラウンフィールド（ワークスペースに既存コード）

**スキップ条件**: グリーンフィールド（既存コードなし）

**再実行の挙動**: ブラウンフィールドが検出された場合は、成果物が存在していても常に再実行する。これにより成果物が現在のコード状態を反映する。

## ステップ 1: マルチパッケージの検出

### 1.1 ワークスペースのスキャン
- 言及されたものだけでなく **全パッケージ** を対象
- 設定ファイルを介したパッケージ関係
- パッケージ種別: Application, CDK/Infrastructure, Models, Clients, Tests

### 1.2 ビジネス文脈の理解
- システム全体が実装しているコアビジネス
- 各パッケージのビジネス概要
- システムが実装しているビジネストランザクションの一覧

### 1.3 インフラ検出
- CDK パッケージ（CDK 依存を含む package.json）
- Terraform（.tf ファイル）
- CloudFormation（.yaml/.json テンプレート）
- デプロイスクリプト

### 1.4 ビルドシステムの検出
- ビルドシステム: Brazil, Maven, Gradle, npm
- ビルド宣言の設定ファイル
- パッケージ間のビルド依存

### 1.5 サービスアーキテクチャの検出
- Lambda 関数（ハンドラ、トリガー）
- コンテナサービス（Docker/ECS 設定）
- API 定義（Smithy モデル、OpenAPI 仕様）
- データストア（DynamoDB、S3 など）

### 1.6 コード品質分析
- 使用言語とフレームワーク
- テストカバレッジ指標
- Lint 設定
- CI/CD パイプライン

## ステップ 1: ビジネス概要ドキュメントの生成

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

## ステップ 2: アーキテクチャドキュメントの生成

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

## ステップ 3: コード構造ドキュメントの生成

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

## ステップ 4: API ドキュメントの生成

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

## ステップ 5: コンポーネント在庫の生成

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

## ステップ 6: 技術スタックドキュメントの生成

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

## ステップ 7: 依存関係ドキュメントの生成

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

## ステップ 8: コード品質評価の生成

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

## ステップ 9: タイムスタンプファイルの作成

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

## ステップ 10: 状態追跡の更新

`aidlc-docs/aidlc-state.md` を更新:

```markdown
## Reverse Engineering Status
- [x] Reverse Engineering - Completed on [timestamp]
- **Artifacts Location**: aidlc-docs/inception/reverse-engineering/
```

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

## ステップ 12: ユーザー承認待ち

- **必須**: ユーザーが明示的に承認するまで進めない
- **必須**: ユーザーの応答を生の入力として audit.md に記録
