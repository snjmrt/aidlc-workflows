# Workspace Detection
# Workspace Detection

# Workspace Detection

**Purpose**: Determine workspace state and check for existing AI-DLC projects
**目的**: ワークスペースの状態を判断し、既存の AI-DLC プロジェクトを確認する

**目的**: ワークスペースの状態を判断し、既存の AI-DLC プロジェクトを確認する

## Step 1: Check for Existing AI-DLC Project
## ステップ 1: 既存 AI-DLC プロジェクトの確認

## ステップ 1: 既存 AI-DLC プロジェクトの確認

Check if `aidlc-docs/aidlc-state.md` exists:
- **If exists**: Resume from last phase (load context from previous phases)
- **If not exists**: Continue with new project assessment
`aidlc-docs/aidlc-state.md` が存在するか確認:
- **存在する場合**: 最後のフェーズから再開（前フェーズのコンテキストを読み込む）
- **存在しない場合**: 新規プロジェクトとして評価を継続

`aidlc-docs/aidlc-state.md` が存在するか確認:
- **存在する場合**: 最後のフェーズから再開（前フェーズのコンテキストを読み込む）
- **存在しない場合**: 新規プロジェクトとして評価を継続

## Step 2: Scan Workspace for Existing Code
## ステップ 2: 既存コードのスキャン

## ステップ 2: 既存コードのスキャン

**Determine if workspace has existing code:**
- Scan workspace for source code files (.java, .py, .js, .ts, .jsx, .tsx, .kt, .kts, .scala, .groovy, .go, .rs, .rb, .php, .c, .h, .cpp, .hpp, .cc, .cs, .fs, etc.)
- Check for build files (pom.xml, package.json, build.gradle, etc.)
- Look for project structure indicators
- Identify workspace root directory (NOT aidlc-docs/)
**ワークスペースに既存コードがあるか判断する:**
- ソースコードファイルをスキャン（.java, .py, .js, .ts, .jsx, .tsx, .kt, .kts, .scala, .groovy, .go, .rs, .rb, .php, .c, .h, .cpp, .hpp, .cc, .cs, .fs など）
- ビルドファイルの確認（pom.xml, package.json, build.gradle など）
- プロジェクト構造の指標を確認
- ワークスペースのルートディレクトリを特定（aidlc-docs/ ではない）

**ワークスペースに既存コードがあるか判断する:**
- ソースコードファイルをスキャン（.java, .py, .js, .ts, .jsx, .tsx, .kt, .kts, .scala, .groovy, .go, .rs, .rb, .php, .c, .h, .cpp, .hpp, .cc, .cs, .fs など）
- ビルドファイルの確認（pom.xml, package.json, build.gradle など）
- プロジェクト構造の指標を確認
- ワークスペースのルートディレクトリを特定（aidlc-docs/ ではない）

**Record findings:**
```markdown
## Workspace State
- **Existing Code**: [Yes/No]
- **Programming Languages**: [List if found]
- **Build System**: [Maven/Gradle/npm/etc. if found]
- **Project Structure**: [Monolith/Microservices/Library/Empty]
- **Workspace Root**: [Absolute path]
```
**調査結果を記録:**
```markdown
## Workspace State
- **Existing Code**: [Yes/No]
- **Programming Languages**: [List if found]
- **Build System**: [Maven/Gradle/npm/etc. if found]
- **Project Structure**: [Monolith/Microservices/Library/Empty]
- **Workspace Root**: [Absolute path]
```

**調査結果を記録:**
```markdown
## Workspace State
- **Existing Code**: [Yes/No]
- **Programming Languages**: [List if found]
- **Build System**: [Maven/Gradle/npm/etc. if found]
- **Project Structure**: [Monolith/Microservices/Library/Empty]
- **Workspace Root**: [Absolute path]
```

## Step 3: Determine Next Phase
## ステップ 3: 次のフェーズ決定

## ステップ 3: 次のフェーズ決定

**IF workspace is empty (no existing code)**:
- Set flag: `brownfield = false`
- Next phase: Requirements Analysis
**ワークスペースが空（既存コードなし）の場合**:
- フラグ設定: `brownfield = false`
- 次のフェーズ: Requirements Analysis

**ワークスペースが空（既存コードなし）の場合**:
- フラグ設定: `brownfield = false`
- 次のフェーズ: Requirements Analysis

**IF workspace has existing code**:
- Set flag: `brownfield = true`
- Check for existing reverse engineering artifacts in `aidlc-docs/inception/reverse-engineering/`
- **IF reverse engineering artifacts exist**: Load them, skip to Requirements Analysis
- **IF no reverse engineering artifacts**: Next phase is Reverse Engineering
**ワークスペースに既存コードがある場合**:
- フラグ設定: `brownfield = true`
- `aidlc-docs/inception/reverse-engineering/` に既存のリバースエンジニアリング成果物があるか確認
- **成果物がある場合**: 読み込み後、Requirements Analysis へ
- **成果物がない場合**: 次のフェーズは Reverse Engineering

**ワークスペースに既存コードがある場合**:
- フラグ設定: `brownfield = true`
- `aidlc-docs/inception/reverse-engineering/` に既存のリバースエンジニアリング成果物があるか確認
- **成果物がある場合**: 読み込み後、Requirements Analysis へ
- **成果物がない場合**: 次のフェーズは Reverse Engineering

## Step 4: Create Initial State File
## ステップ 4: 初期状態ファイルの作成

## ステップ 4: 初期状態ファイルの作成

Create `aidlc-docs/aidlc-state.md`:
`aidlc-docs/aidlc-state.md` を作成:

`aidlc-docs/aidlc-state.md` を作成:

```markdown
# AI-DLC State Tracking

## Project Information
- **Project Type**: [Greenfield/Brownfield]
- **Start Date**: [ISO timestamp]
- **Current Stage**: INCEPTION - Workspace Detection

## Workspace State
- **Existing Code**: [Yes/No]
- **Reverse Engineering Needed**: [Yes/No]
- **Workspace Root**: [Absolute path]

## Code Location Rules
- **Application Code**: Workspace root (NEVER in aidlc-docs/)
- **Documentation**: aidlc-docs/ only
- **Structure patterns**: See code-generation.md Critical Rules

## Stage Progress
[Will be populated as workflow progresses]
```
```markdown
# AI-DLC State Tracking

## Project Information
- **Project Type**: [Greenfield/Brownfield]
- **Start Date**: [ISO timestamp]
- **Current Stage**: INCEPTION - Workspace Detection

## Workspace State
- **Existing Code**: [Yes/No]
- **Reverse Engineering Needed**: [Yes/No]
- **Workspace Root**: [Absolute path]

## Code Location Rules
- **Application Code**: Workspace root (NEVER in aidlc-docs/)
- **Documentation**: aidlc-docs/ only
- **Structure patterns**: See code-generation.md Critical Rules

## Stage Progress
[Will be populated as workflow progresses]
```

```markdown
# AI-DLC State Tracking

## Project Information
- **Project Type**: [Greenfield/Brownfield]
- **Start Date**: [ISO timestamp]
- **Current Stage**: INCEPTION - Workspace Detection

## Workspace State
- **Existing Code**: [Yes/No]
- **Reverse Engineering Needed**: [Yes/No]
- **Workspace Root**: [Absolute path]

## Code Location Rules
- **Application Code**: Workspace root (NEVER in aidlc-docs/)
- **Documentation**: aidlc-docs/ only
- **Structure patterns**: See code-generation.md Critical Rules

## Stage Progress
[Will be populated as workflow progresses]
```

## Step 5: Present Completion Message
## ステップ 5: 完了メッセージの提示

## ステップ 5: 完了メッセージの提示

**For Brownfield Projects:**
```markdown
# 🔍 Workspace Detection Complete

Workspace analysis findings:
• **Project Type**: Brownfield project
• [AI-generated summary of workspace findings in bullet points]
• **Next Step**: Proceeding to **Reverse Engineering** to analyze existing codebase...
```
**ブラウンフィールドの場合:**
```markdown
# 🔍 Workspace Detection Complete

Workspace analysis findings:
• **Project Type**: Brownfield project
• [AI-generated summary of workspace findings in bullet points]
• **Next Step**: Proceeding to **Reverse Engineering** to analyze existing codebase...
```

**ブラウンフィールドの場合:**
```markdown
# 🔍 Workspace Detection Complete

Workspace analysis findings:
• **Project Type**: Brownfield project
• [AI-generated summary of workspace findings in bullet points]
• **Next Step**: Proceeding to **Reverse Engineering** to analyze existing codebase...
```

**For Greenfield Projects:**
```markdown
# 🔍 Workspace Detection Complete

Workspace analysis findings:
• **Project Type**: Greenfield project
• **Next Step**: Proceeding to **Requirements Analysis**...
```
**グリーンフィールドの場合:**
```markdown
# 🔍 Workspace Detection Complete

Workspace analysis findings:
• **Project Type**: Greenfield project
• **Next Step**: Proceeding to **Requirements Analysis**...
```

**グリーンフィールドの場合:**
```markdown
# 🔍 Workspace Detection Complete

Workspace analysis findings:
• **Project Type**: Greenfield project
• **Next Step**: Proceeding to **Requirements Analysis**...
```

## Step 6: Automatically Proceed
## ステップ 6: 自動的に次へ

## ステップ 6: 自動的に次へ

- **No user approval required** - this is informational only
- Automatically proceed to next phase:
  - **Brownfield**: Reverse Engineering (if no existing artifacts) or Requirements Analysis (if artifacts exist)
  - **Greenfield**: Requirements Analysis
- **ユーザー承認不要** - 情報提供のみ
- 次のフェーズへ自動移行:
  - **ブラウンフィールド**: Reverse Engineering（成果物がない場合）または Requirements Analysis（成果物がある場合）
  - **グリーンフィールド**: Requirements Analysis

- **ユーザー承認不要** - 情報提供のみ
- 次のフェーズへ自動移行:
  - **ブラウンフィールド**: Reverse Engineering（成果物がない場合）または Requirements Analysis（成果物がある場合）
  - **グリーンフィールド**: Requirements Analysis
