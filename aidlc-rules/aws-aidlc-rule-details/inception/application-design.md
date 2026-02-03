# Application Design - 詳細手順

## 目的
**高レベルのコンポーネント特定とサービス層設計**

Application Design の焦点:
- 主要な機能コンポーネントと責務の特定
- コンポーネントインターフェイスの定義（詳細なビジネスロジックは除外）
- オーケストレーションのためのサービス層設計
- コンポーネント依存関係と通信パターンの確立

**注記**: 詳細なビジネスロジック設計は後続の Functional Design（ユニットごと、CONSTRUCTION フェーズ）で行う

## 前提条件
- Context Assessment が完了していること
- Requirements Assessment を推奨（機能コンテキストを提供）
- Story Development を推奨（ユーザーストーリーが設計判断を導く）
- 実行計画で Application Design が実行対象となっていること

## 実行手順

### 1. コンテキスト分析
- `aidlc-docs/inception/requirements/requirements.md` と `aidlc-docs/inception/user-stories/stories.md` を読む
- 主要ビジネス能力と機能領域を特定
- 設計のスコープと複雑さを判断

### 2. Application Design 計画の作成
- アプリ設計用のチェックボックス [] 付き計画を作成
- コンポーネント、責務、メソッド、ビジネスルール、サービスに焦点
- 各ステップとサブステップにチェックボックス [] を付ける

### 3. 必須設計成果物を計画に含める
- **必ず** 次の成果物を計画に含める:
  - [ ] コンポーネント定義と高レベル責務を含む components.md を生成
  - [ ] メソッドシグネチャを含む component-methods.md を生成（詳細ルールは後の Functional Design）
  - [ ] サービス定義とオーケストレーションパターンを含む services.md を生成
  - [ ] 依存関係と通信パターンを含む component-dependency.md を生成
  - [ ] 設計の完全性と一貫性を検証

### 4. コンテキストに適した質問の生成
**指示**: 要件とストーリーを分析し、このアプリ設計に**関係する質問のみ**を作成する。以下カテゴリは参考であり、必須チェックリストではない。該当しないカテゴリはスキップしてよい。

- [Answer]: タグ形式で質問を埋め込む
- この文脈特有のあいまいさや欠落情報に焦点
- 設計判断にユーザー入力が必要な場合のみ質問を作成

**質問カテゴリ例**（必要に応じて調整）:
- **コンポーネント特定** - 境界や構成が不明な場合のみ
- **コンポーネントメソッド** - シグネチャの明確化が必要な場合のみ
- **サービス層設計** - オーケストレーションや境界が不明な場合のみ
- **コンポーネント依存** - 通信/依存管理が不明な場合のみ
- **設計パターン** - アーキテクチャ/パターン選択に入力が必要な場合のみ

### 5. Application Design 計画の保存
- `aidlc-docs/inception/plans/application-design-plan.md` として保存
- ユーザー入力用に [Answer]: タグをすべて含める
- 設計の全側面をカバーすることを確認

### 6. ユーザー入力の依頼
- 計画文書内の [Answer]: タグに回答してもらう
- 設計判断の重要性を強調
- [Answer]: タグの記入方法を明確に案内

### 7. 回答収集
- 文書内の [Answer]: タグでの回答を待つ
- **すべて**の [Answer]: タグが埋まるまで進めない
- 空欄がないことを確認

### 8. 回答分析（必須）
進行前に必ず以下を確認:
- **曖昧/あいまいな回答**: "mix of", "somewhere between", "not sure", "depends"
- **未定義の基準/用語**: 定義がない概念への参照
- **矛盾する回答**: 回答同士の衝突
- **設計詳細の欠落**: 具体的な指針がない
- **選択肢の混在**: 判断ルールなくアプローチを混合

### 9. フォロー質問（必須）
ステップ 8 であいまいさがあれば必ず:
- [Answer]: タグを使って計画文書に具体的なフォロー質問を追加
- すべてのあいまいさが解消されるまで承認に進まない
- フォロー例:
  - "'mix of A and B' とありましたが、A と B を使い分ける具体的基準は？"
  - "'somewhere between A and B' の中間案を具体化してください"
  - "'not sure' とありました。判断に必要な追加情報は？"
  - "'depends on complexity' とありました。複雑さの定義と閾値は？"

### 10. Application Design 成果物の生成
- 承認済み計画を実行して成果物を生成
- `aidlc-docs/inception/application-design/components.md` を作成:
  - コンポーネント名と目的
  - コンポーネント責務
  - コンポーネントインターフェイス
- `aidlc-docs/inception/application-design/component-methods.md` を作成:
  - 各コンポーネントのメソッドシグネチャ
  - 各メソッドの高レベル目的
  - 入出力型
  - 注記: 詳細ビジネスルールは Functional Design（ユニットごと、CONSTRUCTION フェーズ）で定義
- `aidlc-docs/inception/application-design/services.md` を作成:
  - サービス定義
  - サービス責務
  - サービスの相互作用とオーケストレーション
- `aidlc-docs/inception/application-design/component-dependency.md` を作成:
  - 関係を示す依存マトリクス
  - コンポーネント間の通信パターン
  - データフロー図

### 11. 承認ログ
- 承認プロンプト全文を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ISO 8601 形式を使用

### 12. 完了メッセージの提示

```markdown
# 🏗️ Application Design Complete

[AI-generated summary of application design artifacts created in bullet points]

> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the application design artifacts at: `aidlc-docs/inception/application-design/`

> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the application design if required
> [IF Units Generation is skipped:]
> 📝 **Add Units Generation** - Choose to include **Units Generation** stage (currently skipped)
> ✅ **Approve & Continue** - Approve design and proceed to **[Units Generation/CONSTRUCTION PHASE]**
```

### 13. 明示的承認待ち
- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があれば設計を更新し、承認プロセスを繰り返す

### 14. 承認応答の記録
- ユーザーの承認回答を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ユーザーの回答を正確に記録
- 承認状態を明確に記載

### 15. 進捗更新
- `aidlc-docs/aidlc-state.md` で Application Design を完了にする
- "Current Status" セクションを更新
- 次ステージへの移行準備
