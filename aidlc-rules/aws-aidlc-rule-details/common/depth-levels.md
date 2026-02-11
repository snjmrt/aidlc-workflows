# Adaptive Depth (適応的な詳細度)

**Purpose**: Explain how AI-DLC adapts detail level to problem complexity

**目的**: AI-DLC が問題の複雑さに応じて詳細度を調整する方法を説明

## Core Principle(基本原則)

##

## 基本原則

**When a stage executes, ALL its defined artifacts are created. The "depth" refers to the level of detail and rigor within those artifacts, which adapts to the problem's complexity.**
**ステージが実行される場合、そのステージで定義された成果物はすべて作成される。"詳細度" は成果物内の記述の詳細さと厳密さを指し、問題の複雑さに応じて調整される。**

**ステージが実行される場合、そのステージで定義された成果物はすべて作成される。"詳細度" は成果物内の記述の詳細さと厳密さを指し、問題の複雑さに応じて調整される。**

## Stage Selection vs Detail Level

## ステージ選択と詳細度

## ステージ選択と詳細度

### Stage Selection (Binary)

- **Workflow Planning** decides: EXECUTE or SKIP for each stage
- **If EXECUTE**: Stage runs and creates ALL its defined artifacts
- **If SKIP**: Stage doesn't run at all

### ステージ選択（2 値）

- **Workflow Planning** が各ステージを実行/スキップを決定
- **実行する場合**: ステージが実行され、定義済み成果物をすべて作成
- **スキップする場合**: ステージは実行されない

### ステージ選択（2 値）

- **Workflow Planning** が各ステージを実行/スキップを決定
- **実行する場合**: ステージが実行され、定義済み成果物をすべて作成
- **スキップする場合**: ステージは実行されない

### Detail Level (Adaptive)

- **Simple problems**: Concise artifacts with essential detail
- **Complex problems**: Comprehensive artifacts with extensive detail
- **Model decides**: Based on problem characteristics, not prescriptive rules

### 詳細度（適応）

- **単純な問題**: 必要最小限の簡潔な成果物
- **複雑な問題**: 詳細かつ包括的な成果物
- **モデルが判断**: 問題特性に基づき判断し、固定ルールには従わない

### 詳細度（適応）

- **単純な問題**: 必要最小限の簡潔な成果物
- **複雑な問題**: 詳細かつ包括的な成果物
- **モデルが判断**: 問題特性に基づき判断し、固定ルールには従わない

## Factors Influencing Detail Level

## 詳細度に影響する要因

## 詳細度に影響する要因

The model considers these factors when determining appropriate detail:
適切な詳細度を判断する際、モデルは以下を考慮する:

適切な詳細度を判断する際、モデルは以下を考慮する:

1. **Request Clarity**: How clear and complete is the user's request?
2. **Problem Complexity**: How intricate is the solution space?
3. **Scope**: Single file, component, multiple components, or system-wide?
4. **Risk Level**: What's the impact of errors or omissions?
5. **Available Context**: Greenfield vs brownfield, existing documentation
6. **User Preferences**: Has user expressed preference for brevity or detail?
7. **要求の明確さ**: ユーザーの要求はどれだけ明確か
8. **問題の複雑さ**: 解の空間はどれだけ複雑か
9. **スコープ**: 単一ファイル、コンポーネント、複数コンポーネント、システム全体か
10. **リスクレベル**: 失敗や漏れの影響度
11. **利用可能なコンテキスト**: グリーンフィールドかブラウンフィールドか、既存ドキュメント
12. **ユーザーの嗜好**: 簡潔さや詳細さの希望があるか

13. **要求の明確さ**: ユーザーの要求はどれだけ明確か
14. **問題の複雑さ**: 解の空間はどれだけ複雑か
15. **スコープ**: 単一ファイル、コンポーネント、複数コンポーネント、システム全体か
16. **リスクレベル**: 失敗や漏れの影響度
17. **利用可能なコンテキスト**: グリーンフィールドかブラウンフィールドか、既存ドキュメント
18. **ユーザーの嗜好**: 簡潔さや詳細さの希望があるか

## Example: Requirements Analysis Artifacts

## 例: Requirements Analysis の成果物

## 例: Requirements Analysis の成果物

**All scenarios create the same artifacts**:

- `requirement-verification-questions.md` (if needed)
- `requirements.md`
  **どのケースでも同じ成果物を作成**:
- `requirement-verification-questions.md`（必要な場合）
- `requirements.md`

**どのケースでも同じ成果物を作成**:

- `requirement-verification-questions.md`（必要な場合）
- `requirements.md`

**Note**: User's initial request is captured in `audit.md` (no separate user-intent.md needed)
**注記**: ユーザーの初期要求は `audit.md` に記録される（別途 user-intent.md は不要）

**注記**: ユーザーの初期要求は `audit.md` に記録される（別途 user-intent.md は不要）

**Detail level varies by complexity**:
**詳細度は複雑さで変化**:

**詳細度は複雑さで変化**:

### Simple Scenario (Bug Fix)

- **requirement-verification-questions.md**: necessary clarifying questions
- **requirements.md**: Concise functional requirement, minimal sections

### 単純なシナリオ（バグ修正）

- **requirement-verification-questions.md**: 必要な確認質問のみ
- **requirements.md**: 簡潔な機能要件、最小限のセクション

### 単純なシナリオ（バグ修正）

- **requirement-verification-questions.md**: 必要な確認質問のみ
- **requirements.md**: 簡潔な機能要件、最小限のセクション

### Complex Scenario (System Migration)

- **requirement-verification-questions.md**: Multiple rounds, 10+ questions
- **requirements.md**: Comprehensive functional + non-functional requirements, traceability, acceptance criteria

### 複雑なシナリオ（システム移行）

- **requirement-verification-questions.md**: 複数ラウンド、10 問以上
- **requirements.md**: 機能/非機能要件の包括的記述、トレーサビリティ、受け入れ基準

### 複雑なシナリオ（システム移行）

- **requirement-verification-questions.md**: 複数ラウンド、10 問以上
- **requirements.md**: 機能/非機能要件の包括的記述、トレーサビリティ、受け入れ基準

## Example: Application Design Artifacts

## 例: Application Design の成果物

## 例: Application Design の成果物

**All scenarios create the same artifacts**:

- `application-design.md`
- `component-diagram.md`
  **どのケースでも同じ成果物を作成**:
- `application-design.md`
- `component-diagram.md`

**どのケースでも同じ成果物を作成**:

- `application-design.md`
- `component-diagram.md`

**Detail level varies by complexity**:
**詳細度は複雑さで変化**:

**詳細度は複雑さで変化**:

### Simple Scenario (Single Component)

- **application-design.md**: Basic component description, key methods
- **component-diagram.md**: Simple diagram with essential relationships

### 単純なシナリオ（単一コンポーネント）

- **application-design.md**: 基本的なコンポーネント説明と主要メソッド
- **component-diagram.md**: 必要最低限の関係を示す簡易図

### 単純なシナリオ（単一コンポーネント）

- **application-design.md**: 基本的なコンポーネント説明と主要メソッド
- **component-diagram.md**: 必要最低限の関係を示す簡易図

### Complex Scenario (Multi-Component System)

- **application-design.md**: Detailed component responsibilities, all methods with signatures, design patterns, alternatives considered
- **component-diagram.md**: Comprehensive diagram with all relationships, data flows, integration points

### 複雑なシナリオ（複数コンポーネント）

- **application-design.md**: 役割の詳細、全メソッドのシグネチャ、設計パターン、検討した代替案
- **component-diagram.md**: すべての関係、データフロー、統合ポイントを含む詳細図

### 複雑なシナリオ（複数コンポーネント）

- **application-design.md**: 役割の詳細、全メソッドのシグネチャ、設計パターン、検討した代替案
- **component-diagram.md**: すべての関係、データフロー、統合ポイントを含む詳細図

## Guiding Principle for Model

## モデルの指針

## モデルの指針

**"Create exactly the detail needed for the problem at hand - no more, no less."**
**"目の前の問題に必要な詳細を、過不足なく作成する"**

**"目の前の問題に必要な詳細を、過不足なく作成する"**

- Don't artificially inflate simple problems with unnecessary detail
- Don't shortchange complex problems by omitting critical detail
- Let problem characteristics drive detail level naturally
- All required artifacts are always created when stage executes
- 単純な問題を不必要に膨らませない
- 複雑な問題で重要な詳細を省かない
- 問題特性に基づき自然に詳細度を決定
- ステージ実行時は必ず成果物を作成する

- 単純な問題を不必要に膨らませない
- 複雑な問題で重要な詳細を省かない
- 問題特性に基づき自然に詳細度を決定
- ステージ実行時は必ず成果物を作成する
