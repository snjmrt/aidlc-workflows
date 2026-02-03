# Units Generation - 詳細手順

## 概要
このステージは 2 部構成でシステムを作業単位へ分解する:
- **パート 1 - 計画**: 分解計画を作成し質問を収集、あいまいさを分析、承認を取得
- **パート 2 - 生成**: 承認済み計画を実行しユニット成果物を生成

**定義**: Unit of Work は開発のためのストーリー群の論理的まとまり。マイクロサービスの場合、各ユニットは独立デプロイ可能なサービスになる。モノリスの場合、単一ユニットがアプリ全体を表し、内部に論理モジュールを持つ。

**用語**: 独立デプロイ可能なコンポーネントは "Service"、サービス内の論理グループは "Module"、計画文脈では "Unit of Work" を使用。

## 前提条件
- Context Assessment が完了していること
- Requirements Assessment を推奨（機能スコープを提供）
- Story Development を推奨（ストーリーがユニットに対応）
- Application Design フェーズが必須（コンポーネント/メソッド/サービスを決定）
- 実行計画で Design フェーズが実行対象になっていること

---

# PART 1: PLANNING

## ステップ 1: Unit of Work 計画の作成
- システムを作業単位に分解するためのチェックボックス [] 付き計画を作成
- システムを管理可能な開発単位に分解することに集中
- 各ステップとサブステップにチェックボックス [] を付ける

## ステップ 2: 必須ユニット成果物を計画に含める
**必ず** 次の成果物を計画に含める:
- [ ] ユニット定義と責務を含む `aidlc-docs/inception/application-design/unit-of-work.md` を生成
- [ ] 依存関係マトリクスを含む `aidlc-docs/inception/application-design/unit-of-work-dependency.md` を生成
- [ ] ストーリーとユニットのマッピングを含む `aidlc-docs/inception/application-design/unit-of-work-story-map.md` を生成
- [ ] **グリーンフィールドのみ**: `unit-of-work.md` にコード構成戦略を記載（構造パターンは code-generation.md を参照）
- [ ] ユニット境界と依存関係を検証
- [ ] すべてのストーリーがユニットに割り当てられていることを確認

## ステップ 3: コンテキストに適した質問の生成
**指示**: 要件、ストーリー、アプリ設計を分析し、この分解問題に**関係する質問のみ**を作成する。以下カテゴリは参考であり必須チェックリストではない。該当しないカテゴリはスキップしてよい。

- [Answer]: タグ形式で質問を埋め込む
- この文脈特有のあいまいさや欠落情報に焦点
- 意思決定にユーザー入力が必要な場合のみ質問を作成

**質問カテゴリ例**（必要に応じて調整）:
- **ストーリーのグルーピング** - 複数ストーリーがあり戦略が不明な場合のみ
- **依存関係** - 複数ユニットが見込まれ、統合アプローチが不明な場合のみ
- **チーム整合** - チーム構造/責務が不明な場合のみ
- **技術的考慮** - ユニット間でスケール/デプロイ要件が異なる場合のみ
- **ビジネスドメイン** - ドメイン境界や境界づけられたコンテキストが不明な場合のみ
- **コード構成（グリーンフィールド複数ユニットのみ）** - デプロイモデルとディレクトリ構成の嗜好を質問

## ステップ 4: UOW 計画の保存
- `aidlc-docs/inception/plans/unit-of-work-plan.md` として保存
- ユーザー入力用に [Answer]: タグをすべて含める
- システム分解の全側面をカバーすることを確認

## ステップ 5: ユーザー入力の依頼
- 計画文書内の [Answer]: タグに回答してもらう
- 分解判断の重要性を強調
- [Answer]: タグの記入方法を明確に案内

## ステップ 6: 回答収集
- 文書内の [Answer]: タグでの回答を待つ
- **すべて**の [Answer]: タグが埋まるまで進めない
- 空欄がないことを確認

## ステップ 7: 回答分析（必須）
進行前に必ず以下を確認:
- **曖昧/あいまいな回答**: "mix of", "somewhere between", "not sure", "depends"
- **未定義の基準/用語**: 定義がない概念への参照
- **矛盾する回答**: 回答同士の衝突
- **生成詳細の欠落**: 具体的な指針がない
- **選択肢の混在**: 判断ルールなくアプローチを混合

## ステップ 8: フォロー質問（必須）
ステップ 7 であいまいさがあれば必ず:
- [Answer]: タグで計画文書に具体的なフォロー質問を追加
- すべてのあいまいさが解消されるまで承認に進まない
- フォロー例:
  - "'mix of A and B' とありましたが、A と B を使い分ける具体的基準は？"
  - "'somewhere between A and B' の中間案を具体化してください"
  - "'not sure' とありました。判断に必要な追加情報は？"
  - "'depends on complexity' とありました。複雑さの定義と閾値は？"

## ステップ 9: 承認依頼
- 質問: "**Unit of work plan complete. Review the plan in aidlc-docs/inception/plans/unit-of-work-plan.md. Ready to proceed to generation?**"
- ユーザー確認があるまで進めない

## ステップ 10: 承認ログ
- audit.md にプロンプトと応答をタイムスタンプ付きで記録
- ISO 8601 形式を使用
- 承認プロンプト全文を含める

## ステップ 11: 進捗更新
- aidlc-state.md で Units Planning を完了にする
- "Current Status" セクションを更新
- Units Generation への移行準備

---

# PART 2: GENERATION

## ステップ 12: Unit of Work 計画の読み込み
- [ ] `aidlc-docs/inception/plans/unit-of-work-plan.md` から完全な計画を読み込む
- [ ] 次の未完了ステップ（最初の [ ]）を特定
- [ ] 該当ステップのコンテキストと要件を読み込む

## ステップ 13: 現在ステップの実行
- [ ] 計画に記載された内容を正確に実行
- [ ] 計画で指定されたユニット成果物を生成
- [ ] Planning で承認済みの分解アプローチに従う
- [ ] 計画で指定された基準と境界を使用

## ステップ 14: 進捗更新
- [ ] 完了ステップを Unit of Work 計画で [x] にする
- [ ] `aidlc-docs/aidlc-state.md` の現在状況を更新
- [ ] 生成成果物を保存

## ステップ 15: 継続または完了
- [ ] 残りがあればステップ 12 に戻る
- [ ] すべて完了なら設計ステージに進める状態を確認
- [ ] Units Generation ステージを完了にする

## ステップ 16: 完了メッセージの提示

```markdown
# 🔧 Units Generation Complete

[AI-generated summary of units and decomposition created in bullet points]

> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the units generation artifacts at: `aidlc-docs/inception/application-design/`

> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the units generation if required
> ✅ **Approve & Continue** - Approve units and proceed to **CONSTRUCTION PHASE**
```

## ステップ 17: 明示的承認待ち
- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があればユニットを更新し、承認プロセスを繰り返す

## ステップ 18: 承認応答の記録
- ユーザーの承認回答を `aidlc-docs/audit.md` にタイムスタンプ付きで記録
- ユーザーの回答を正確に記録
- 承認状態を明確に記載

## ステップ 19: 進捗更新
- `aidlc-docs/aidlc-state.md` で Units Generation を完了にする
- "Current Status" セクションを更新
- CONSTRUCTION フェーズへの移行準備

---

## 重要ルール

### Planning フェーズのルール
- コンテキストに関係する質問のみ生成
- すべての質問は [Answer]: タグ形式
- 進行前に回答のあいまいさを分析
- すべてのあいまいさをフォロー質問で解消
- 生成前にユーザーの明示的承認を得る

### Generation フェーズのルール
- **ハードコード禁止**: Unit of Work 計画に書かれた内容のみ実行
- **計画に厳密に従う**: ステップ順序から逸脱しない
- **チェックボックス更新**: 完了直後に [x] を付ける
- **承認済みアプローチの使用**: Planning の分解方法に従う
- **完了検証**: 次へ進む前に成果物が完了しているか確認

## 完了条件
- 計画質問がすべて回答され、あいまいさが解消されている
- 計画へのユーザー承認が取得済み
- Unit of Work 計画の全ステップが [x]
- 計画どおりに成果物が生成されている:
  - `unit-of-work.md`（ユニット定義）
  - `unit-of-work-dependency.md`（依存マトリクス）
  - `unit-of-work-story-map.md`（ストーリーマッピング）
- ユニットが検証され、ユニットごとの設計ステージに進める状態
