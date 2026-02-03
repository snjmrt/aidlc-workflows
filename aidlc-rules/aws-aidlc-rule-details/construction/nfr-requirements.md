# NFR Requirements

## 前提条件
- ユニットの Functional Design が完了していること
- ユニットの Functional Design 成果物が利用可能であること
- 実行計画で NFR Requirements ステージが実行対象であること

## 概要
ユニットの非機能要件を決定し、技術スタックを選定する。

## 実行手順

### ステップ 1: Functional Design の分析
- `aidlc-docs/construction/{unit-name}/functional-design/` から成果物を読み込む
- ビジネスロジックの複雑さと要件を理解

### ステップ 2: NFR Requirements 計画の作成
- NFR 評価用のチェックボックス [] 付き計画を作成
- スケーラビリティ、性能、可用性、セキュリティに焦点
- 各ステップにチェックボックス [] を付ける

### ステップ 3: コンテキストに適した質問の生成
**指示**: Functional Design を徹底分析し、NFR の明確化が品質やアーキテクチャ判断を改善する領域をすべて特定する。積極的に質問する。

**重要**: あいまいさや欠落が少しでもあれば質問することをデフォルトにする。誤った NFR 仮定をするより、質問しすぎる方がよい。

- [Answer]: タグ形式で質問を埋め込む
- あいまい/欠落/確認が必要な領域に焦点
- NFR/技術スタック判断にユーザー入力が有益なら質問を作成
- **迷ったら質問する** - 過信は品質低下につながる

**評価すべき質問カテゴリ**（すべて考慮）:
- **スケーラビリティ要件** - 予想負荷、成長パターン、スケール条件、容量計画
- **性能要件** - 応答時間、スループット、レイテンシ、性能指標
- **可用性要件** - 稼働率、災害復旧、フェイルオーバー、事業継続
- **セキュリティ要件** - データ保護、コンプライアンス、認証/認可、脅威モデル
- **技術スタック選定** - 技術嗜好、制約、既存システム、統合要件
- **信頼性要件** - エラーハンドリング、耐障害性、監視、アラート
- **保守性要件** - コード品質、ドキュメント、テスト、運用要件
- **ユーザビリティ要件** - ユーザー体験、アクセシビリティ、UI 要件

### ステップ 4: 計画の保存
- `aidlc-docs/construction/plans/{unit-name}-nfr-requirements-plan.md` として保存
- ユーザー入力用に [Answer]: タグをすべて含める

### ステップ 5: 回答収集と分析
- ユーザーがすべての [Answer]: タグを埋めるまで待つ
- **必須**: すべての回答のあいまいさを丁寧に確認
- **重要**: 不明瞭な回答には必ずフォロー質問を追加し、曖昧なまま進めない
- "depends", "maybe", "not sure", "mix of", "somewhere between", "standard", "typical" に注意
- あいまいさがあれば確認質問ファイルを作成
- **すべての曖昧さが解消されるまで進めない**

### ステップ 6: NFR Requirements 成果物の生成
- `aidlc-docs/construction/{unit-name}/nfr-requirements/nfr-requirements.md` を作成
- `aidlc-docs/construction/{unit-name}/nfr-requirements/tech-stack-decisions.md` を作成

### ステップ 7: 完了メッセージの提示
- 次の構造で完了メッセージを提示:
     1. **完了告知**（必須）: 必ずこれで開始

```markdown
# 📊 NFR Requirements Complete - [unit-name]
```

     2. **AI 要約**（任意）: NFR 要件の構造化要約
        - 形式: "NFR requirements assessment has identified [description]:"
        - 主要なスケーラビリティ/性能/可用性要件を列挙
        - セキュリティ/コンプライアンス要件に言及
        - 技術スタック判断と理由に言及
        - ワークフロー指示は含めない（"please review"、"let me know"、"proceed to next phase"、"before we proceed" など）
        - 事実ベースかつ内容中心にする
     3. **フォーマット済みワークフローメッセージ**（必須）: 必ず以下の形式で終了

```markdown
> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the NFR requirements at: `aidlc-docs/construction/[unit-name]/nfr-requirements/`



> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the NFR requirements based on your review  
> ✅ **Continue to Next Stage** - Approve NFR requirements and proceed to **[next-stage-name]**

---
```

### ステップ 8: 明示的承認待ち
- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があれば要件を更新し、承認プロセスを繰り返す

### ステップ 9: 承認記録と進捗更新
- audit.md に承認をタイムスタンプ付きで記録
- ユーザーの承認回答をタイムスタンプ付きで記録
- aidlc-state.md で NFR Requirements を完了にする
