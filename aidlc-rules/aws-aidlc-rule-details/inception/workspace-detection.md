# Workspace Detection

**目的**: ワークスペースの状態を判断し、既存の AI-DLC プロジェクトを確認する

## ステップ 1: 既存 AI-DLC プロジェクトの確認

`aidlc-docs/aidlc-state.md` が存在するか確認:
- **存在する場合**: 最後のフェーズから再開（前フェーズのコンテキストを読み込む）
- **存在しない場合**: 新規プロジェクトとして評価を継続

## ステップ 2: 既存コードのスキャン

**ワークスペースに既存コードがあるか判断する:**
- ソースコードファイルをスキャン（.java, .py, .js, .ts, .jsx, .tsx, .kt, .kts, .scala, .groovy, .go, .rs, .rb, .php, .c, .h, .cpp, .hpp, .cc, .cs, .fs など）
- ビルドファイルの確認（pom.xml, package.json, build.gradle など）
- プロジェクト構造の指標を確認
- ワークスペースのルートディレクトリを特定（aidlc-docs/ ではない）

**調査結果を記録:**
```markdown
## Workspace State
- **Existing Code**: [Yes/No]
- **Programming Languages**: [List if found]
- **Build System**: [Maven/Gradle/npm/etc. if found]
- **Project Structure**: [Monolith/Microservices/Library/Empty]
- **Workspace Root**: [Absolute path]
```

## ステップ 3: 次のフェーズ決定

**ワークスペースが空（既存コードなし）の場合**:
- フラグ設定: `brownfield = false`
- 次のフェーズ: Requirements Analysis

**ワークスペースに既存コードがある場合**:
- フラグ設定: `brownfield = true`
- `aidlc-docs/inception/reverse-engineering/` に既存のリバースエンジニアリング成果物があるか確認
- **成果物がある場合**: 読み込み後、Requirements Analysis へ
- **成果物がない場合**: 次のフェーズは Reverse Engineering

## ステップ 4: 初期状態ファイルの作成

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

## ステップ 5: 完了メッセージの提示

**ブラウンフィールドの場合:**
```markdown
# 🔍 Workspace Detection Complete

Workspace analysis findings:
• **Project Type**: Brownfield project
• [AI-generated summary of workspace findings in bullet points]
• **Next Step**: Proceeding to **Reverse Engineering** to analyze existing codebase...
```

**グリーンフィールドの場合:**
```markdown
# 🔍 Workspace Detection Complete

Workspace analysis findings:
• **Project Type**: Greenfield project
• **Next Step**: Proceeding to **Requirements Analysis**...
```

## ステップ 6: 自動的に次へ

- **ユーザー承認不要** - 情報提供のみ
- 次のフェーズへ自動移行:
  - **ブラウンフィールド**: Reverse Engineering（成果物がない場合）または Requirements Analysis（成果物がある場合）
  - **グリーンフィールド**: Requirements Analysis
