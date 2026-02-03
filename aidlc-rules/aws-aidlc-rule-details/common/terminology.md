# AI-DLC 用語集

## 基本用語

### フェーズとステージ

**フェーズ（Phase）**: AI-DLC の 3 つの上位ライフサイクルフェーズのいずれか
- 🔵 **INCEPTION フェーズ** - 計画 & アーキテクチャ（WHAT と WHY）
- 🟢 **CONSTRUCTION フェーズ** - 設計、実装 & テスト（HOW）
- 🟡 **OPERATIONS フェーズ** - デプロイ & 監視（将来拡張）

**ステージ（Stage）**: フェーズ内の個別ワークフロー活動
- 例: Context Assessment ステージ、Requirements Assessment ステージ、Code Planning ステージ
- 各ステージには前提条件、手順、成果物がある
- ステージは ALWAYS-EXECUTE または CONDITIONAL

**使用例**:
- ✅ "CONSTRUCTION フェーズには 7 つのステージがある"
- ✅ "Code Planning ステージは常に実行される"
- ✅ "INCEPTION フェーズで Requirements Assessment ステージを実行中"
- ❌ "Requirements Assessment フェーズ"（正しくは "ステージ"）
- ❌ "CONSTRUCTION ステージ"（正しくは "フェーズ"）

## 3 フェーズライフサイクル

### INCEPTION フェーズ
**目的**: 計画とアーキテクチャ上の意思決定  
**焦点**: 何を作るかと、なぜ作るか  
**場所**: `inception/` ディレクトリ

**ステージ**:
- Workspace Detection（常に実行）
- Reverse Engineering（条件付き - ブラウンフィールドのみ）
- Requirements Analysis（常に実行 - 深さは適応）
- User Stories（条件付き）
- Workflow Planning（常に実行）
- Application Design（条件付き）
- Design - Units Planning/Generation（条件付き）

**成果物**: 要件、ユーザーストーリー、アーキテクチャ判断、ユニット定義

### CONSTRUCTION フェーズ
**目的**: 詳細設計と実装  
**焦点**: どのように作るか  
**場所**: `construction/` ディレクトリ

**ステージ**:
- Functional Design（条件付き、ユニットごと）
- NFR Requirements（条件付き、ユニットごと）
- NFR Design（条件付き、ユニットごと）
- Infrastructure Design（条件付き、ユニットごと）
- Code Planning（常に実行）
- Code Generation（常に実行）
- Build and Test（常に実行）

**成果物**: 設計成果物、NFR 実装、コード、テスト

### OPERATIONS フェーズ
**目的**: デプロイと運用準備  
**焦点**: どのようにデプロイして運用するか  
**場所**: `operations/` ディレクトリ

**ステージ**:
- Operations（プレースホルダー）

**成果物**: ビルド手順、デプロイ手順、監視設定、検証手順

---

## ワークフローステージ

### 常に実行されるステージ
- **Workspace Detection**: ワークスペース状態とプロジェクト種別の初期分析
- **Requirements Analysis**: 要件収集（深さは複雑さで変化）
- **Workflow Planning**: 実行するフェーズの計画作成
- **Code Planning**: コード生成の詳細実装計画を作成
- **Code Generation**: 計画と成果物に基づくコード生成
- **Build and Test**: 全ユニットのビルドと包括的テスト

### 条件付きステージ
- **Reverse Engineering**: 既存コードベース分析（ブラウンフィールドのみ）
- **User Stories**: ユーザーストーリーとペルソナ作成（Story Planning と Story Generation を含む）
- **Application Design**: コンポーネント、メソッド、ビジネスルール、サービスの設計
- **Design**: システムコンポーネントの設計（Units Planning, Units Generation, ユニットごとの設計）
- **Functional Design**: 技術非依存のビジネスロジック設計（ユニットごと）
- **NFR Requirements**: NFR の決定と技術スタック選定（ユニットごと）
- **NFR Design**: NFR パターンと論理コンポーネントの取り込み（ユニットごと）
- **Infrastructure Design**: 実際のインフラサービスへのマッピング（ユニットごと）

## アプリケーション設計用語

- **Component**: 特定の責務を持つ機能単位
- **Method**: コンポーネント内の関数/操作（ビジネスルールを含む）
- **Business Rule**: メソッドの挙動と検証を制御するロジック
- **Service**: 複数コンポーネントのビジネスロジックを調整するオーケストレーション層
- **Component Dependency**: コンポーネント間の関係と通信パターン

## アーキテクチャ用語（インフラ）

### Unit of Work
開発のためのユーザーストーリーの論理的グルーピング。計画と分解で使う用語。

**使用例**: "システムをユニット・オブ・ワークに分解する必要がある"

### Service
マイクロサービスアーキテクチャで独立してデプロイ可能なコンポーネント。各サービスは独立したユニット。

**使用例**: "Payment Service がすべての決済処理を担当"

### Module
単一サービスまたはモノリス内の機能の論理的グルーピング。独立デプロイ不可。

**使用例**: "User Service 内の認証モジュール"

### Component
サービスやモジュール内の再利用可能なビルディングブロック。クラス、関数、パッケージなど。

**使用例**: "EmailValidator コンポーネントがメールアドレスを検証"

## 用語の使い分け

### 各用語の使用タイミング

**Unit of Work**:
- Units Planning/Units Generation フェーズ中
- システム分解の議論
- 計画ドキュメントや議論で使用
- 例: "これをユニット・オブ・ワークにどう分解すべきか？"

**Service**:
- 独立デプロイ可能なコンポーネントを指す場合
- マイクロサービス文脈
- デプロイ/インフラの議論
- 例: "Order Service は ECS にデプロイされる"

**Module**:
- サービス内の論理グループを指す場合
- モノリス文脈
- 内部構成の議論
- 例: "レポーティングモジュールがすべてのレポートを生成"

**Component**:
- 具体的なクラス/関数/パッケージを指す場合
- 設計/実装の議論
- 再利用ビルディングブロックの議論
- 例: "DatabaseConnection コンポーネントが接続を管理"

## ステージ用語

### Planning と Generation
- **Planning**: 質問とチェックボックス付きの実行計画を作成
- **Generation**: 計画を実行して成果物を生成

例:
- Story Planning → Story Generation
- Units Planning → Units Generation
- Unit Design Planning → Unit Design Generation
- NFR Planning → NFR Generation
- Code Planning → Code Generation

### 詳細度レベル
- **Minimal**: 単純な変更向けの迅速で焦点を絞った実行
- **Standard**: 一般的なプロジェクト向けの標準的な深さ
- **Comprehensive**: 複雑/高リスク向けの完全な深さ

## 成果物の種類

### Plans
実行を導くチェックボックスと質問を含む文書。
- `aidlc-docs/plans/` に配置
- 例: `story-generation-plan.md`, `unit-of-work-plan.md`

### Artifacts
計画を実行して生成される成果物。
- `aidlc-docs/` 配下の各サブディレクトリ
- 例: `requirements.md`, `stories.md`, `design.md`

### State Files
ワークフローの進捗と状態を追跡するファイル。
- `aidlc-state.md`: ワークフロー全体の状態
- `audit.md`: すべてのやり取りの監査ログ

## よく使う略語

- **AI-DLC**: AI-Driven Development Life Cycle
- **NFR**: Non-Functional Requirements
- **UOW**: Unit of Work
- **API**: Application Programming Interface
- **CDK**: Cloud Development Kit (AWS)
