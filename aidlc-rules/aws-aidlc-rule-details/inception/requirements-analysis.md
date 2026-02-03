# Requirements Analysis（適応）

**プロダクトオーナーの役割を担う**

**適応フェーズ**: 常に実行。詳細度は問題の複雑さに応じて適応。

**適応的詳細度の説明は [depth-levels.md](../common/depth-levels.md) を参照**

## 前提条件
- Workspace Detection が完了していること
- Reverse Engineering が完了していること（ブラウンフィールドの場合）

## 実行手順

### ステップ 1: リバースエンジニアリングのコンテキスト読み込み（可能な場合）

**ブラウンフィールドの場合**:
- `aidlc-docs/inception/reverse-engineering/architecture.md` を読み込む
- `aidlc-docs/inception/reverse-engineering/component-inventory.md` を読み込む
- `aidlc-docs/inception/reverse-engineering/technology-stack.md` を読み込む
- これらを使って、要求分析時に既存システムを理解する

### ステップ 2: ユーザー要求の分析（意図分析）

#### 2.1 要求の明確さ
- **明確**: 具体的で定義済み、実行可能
- **曖昧**: 一般的で不明確、明確化が必要
- **不完全**: 重要情報が欠落

#### 2.2 要求タイプ
- **新機能**: 新しい機能の追加
- **バグ修正**: 既存の不具合修正
- **リファクタリング**: コード構造の改善
- **アップグレード**: 依存関係やフレームワークの更新
- **マイグレーション**: 別の技術への移行
- **改善**: 既存機能の改善
- **新規プロジェクト**: ゼロから開始

#### 2.3 初期スコープ見積もり
- **単一ファイル**: 1 ファイルの変更
- **単一コンポーネント**: 1 コンポーネント/パッケージの変更
- **複数コンポーネント**: 複数コンポーネントにまたがる変更
- **システム全体**: システム全体に影響する変更
- **クロスシステム**: 複数システムに影響する変更

#### 2.4 初期複雑度見積もり
- **些細**: 単純で明快な変更
- **シンプル**: 実装の道筋が明確
- **中程度**: いくつかの複雑性と考慮点
- **複雑**: 大きな複雑性と多数の考慮点

### ステップ 3: 要件深度の決定

**要求分析に基づいて深度を決定:**

**最小深度** - 次の場合に使用:
- 要求が明確で単純
- 詳細な要件が不要
- 基本的な理解を文書化するだけでよい

**標準深度** - 次の場合に使用:
- 明確化が必要
- 機能/非機能要件が必要
- 通常の複雑度

**包括的深度** - 次の場合に使用:
- 複数ステークホルダーが関わる複雑プロジェクト
- 高リスクまたは重要システム
- トレーサビリティ付きの詳細要件が必要

### ステップ 4: 現在の要件の評価

ユーザーが提供した内容を分析:
   - 意図の記述（audit.md に記録済み）
   - 既存の要件ドキュメント（言及があればワークスペースを検索）
   - 貼り付けた内容やファイル参照
   - Markdown 以外の文書は Markdown に変換

### ステップ 5: 徹底した網羅性分析

**重要**: 包括的分析で要件の網羅性を評価する。あいまいさや欠落が少しでもあれば、質問することをデフォルトにする。

**必須**: 以下の領域をすべて評価し、不明確なものは必ず質問する:
- **機能要件**: コア機能、ユーザー操作、システム挙動
- **非機能要件**: パフォーマンス、セキュリティ、スケーラビリティ、ユーザビリティ
- **ユーザーシナリオ**: ユースケース、ユーザージャーニー、エッジケース、エラーシナリオ
- **ビジネス文脈**: 目標、制約、成功基準、ステークホルダー要件
- **技術文脈**: 統合ポイント、データ要件、システム境界
- **品質属性**: 信頼性、保守性、テスト容易性、アクセシビリティ

**迷ったら質問する** - 不完全な要件は不適切な実装につながる。

### ステップ 6: 確認質問の生成（プロアクティブ）
   - **常に** `aidlc-docs/inception/requirements/requirement-verification-questions.md` を作成（例外的に要件が極めて明確かつ完全な場合を除く）
   - 欠落/不明/あいまいな領域はすべて質問する
   - 機能要件、非機能要件、ユーザーシナリオ、ビジネス文脈に焦点を当てる
   - 質問文書内の [Answer]: タグをユーザーに直接記入してもらう
   - 複数選択形式を提示する場合:
     - 選択肢を A, B, C, D などで表記
     - 選択肢は相互排他的かつ重複しない
     - 必ずカスタム回答の選択肢を含める: "X) Other (please describe after [Answer]: tag below)"
   - ユーザー回答を待つ
   - **必須**: すべての回答のあいまいさを分析し、必要ならフォロー質問を作成
   - **必須**: あいまいさが解消されるまで、またはユーザーが明示的に進行を望むまで質問を続ける

### ステップ 7: 要件ドキュメントの生成
   - `aidlc-docs/inception/requirements/requirements.md` を作成
   - 先頭に意図分析の要約を含める:
     - ユーザー要求
     - 要求タイプ
     - スコープ見積もり
     - 複雑度見積もり
   - 機能要件と非機能要件を含める
   - 確認質問への回答を取り込む
   - 主要要件の簡潔な要約を提供

### ステップ 8: 状態追跡の更新

`aidlc-docs/aidlc-state.md` を更新:

```markdown
## Stage Progress
### 🔵 INCEPTION PHASE
- [x] Workspace Detection
- [x] Reverse Engineering (if applicable)
- [x] Requirements Analysis
```

### ステップ 9: ログと次の進行
   - 承認プロンプトをタイムスタンプ付きで `aidlc-docs/audit.md` に記録
   - 次の構造で完了メッセージを提示:
     1. **完了告知**（必須）: 必ずこれで開始

```markdown
# 🔍 Requirements Analysis Complete
```

     2. **AI 要約**（任意）: 構造化された箇条書きで要件を要約
        - 形式: "Requirements analysis has identified [project type/complexity]:"
        - 主要な機能要件を列挙
        - 主要な非機能要件を列挙
        - 該当する場合はアーキテクチャ上の考慮や技術判断に触れる
        - ワークフロー指示は含めない（"please review"、"let me know"、"proceed to next phase"、"before we proceed" など）
        - 事実ベースかつ内容中心にする
     3. **フォーマット済みワークフローメッセージ**（必須）: 必ず以下の形式で終了

```markdown
> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the requirements document at: `aidlc-docs/inception/requirements/requirements.md`



> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** -  Ask for modifications to the requirements if required based on your review 
> [IF User Stories will be skipped, add this option:]
> 📝 **Add User Stories** - Choose to Include **User Stories** stage (currently skipped based on project simplicity)  
> ✅ **Approve & Continue** - Approve requirements and proceed to **[User Stories/Workflow Planning]**

---
```

**注記**: User Stories をスキップする場合のみ "Add User Stories" を含める。[User Stories/Workflow Planning] は実際の次ステージ名に置き換える。

   - 明示的なユーザー承認を待つ
   - 承認回答をタイムスタンプ付きで記録
   - aidlc-state.md の Requirements Analysis を完了に更新
