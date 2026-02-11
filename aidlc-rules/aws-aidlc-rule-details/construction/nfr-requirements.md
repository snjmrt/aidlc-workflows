# NFR Requirements
# NFR Requirements

# NFR Requirements

## Prerequisites
- Functional Design must be complete for the unit
- Unit functional design artifacts must be available
- Execution plan must indicate NFR Requirements stage should execute
## 前提条件
- ユニットの Functional Design が完了していること
- ユニットの Functional Design 成果物が利用可能であること
- 実行計画で NFR Requirements ステージが実行対象であること

## 前提条件
- ユニットの Functional Design が完了していること
- ユニットの Functional Design 成果物が利用可能であること
- 実行計画で NFR Requirements ステージが実行対象であること

## Overview
Determine non-functional requirements for the unit and make tech stack choices.
## 概要
ユニットの非機能要件を決定し、技術スタックを選定する。

## 概要
ユニットの非機能要件を決定し、技術スタックを選定する。

## Steps to Execute
## 実行手順

## 実行手順

### Step 1: Analyze Functional Design
- Read functional design artifacts from `aidlc-docs/construction/{unit-name}/functional-design/`
- Understand business logic complexity and requirements
### ステップ 1: Functional Design の分析
- `aidlc-docs/construction/{unit-name}/functional-design/` から成果物を読み込む
- ビジネスロジックの複雑さと要件を理解

### ステップ 1: Functional Design の分析
- `aidlc-docs/construction/{unit-name}/functional-design/` から成果物を読み込む
- ビジネスロジックの複雑さと要件を理解

### Step 2: Create NFR Requirements Plan
- Generate plan with checkboxes [] for NFR assessment
- Focus on scalability, performance, availability, security
- Each step should have a checkbox []
### ステップ 2: NFR Requirements 計画の作成
- NFR 評価用のチェックボックス [] 付き計画を作成
- スケーラビリティ、性能、可用性、セキュリティに焦点
- 各ステップにチェックボックス [] を付ける

### ステップ 2: NFR Requirements 計画の作成
- NFR 評価用のチェックボックス [] 付き計画を作成
- スケーラビリティ、性能、可用性、セキュリティに焦点
- 各ステップにチェックボックス [] を付ける

### Step 3: Generate Context-Appropriate Questions
**DIRECTIVE**: Thoroughly analyze the functional design to identify ALL areas where NFR clarification would improve system quality and architecture decisions. Be proactive in asking questions to ensure comprehensive NFR coverage.
### ステップ 3: コンテキストに適した質問の生成
**指示**: Functional Design を徹底分析し、NFR の明確化が品質やアーキテクチャ判断を改善する領域をすべて特定する。積極的に質問する。

### ステップ 3: コンテキストに適した質問の生成
**指示**: Functional Design を徹底分析し、NFR の明確化が品質やアーキテクチャ判断を改善する領域をすべて特定する。積極的に質問する。

**CRITICAL**: Default to asking questions when there is ANY ambiguity or missing detail that could affect system quality. It's better to ask too many questions than to make incorrect NFR assumptions.
**重要**: あいまいさや欠落が少しでもあれば質問することをデフォルトにする。誤った NFR 仮定をするより、質問しすぎる方がよい。

**重要**: あいまいさや欠落が少しでもあれば質問することをデフォルトにする。誤った NFR 仮定をするより、質問しすぎる方がよい。

- EMBED questions using [Answer]: tag format
- Focus on ANY ambiguities, missing information, or areas needing clarification
- Generate questions wherever user input would improve NFR and tech stack decisions
- **When in doubt, ask the question** - overconfidence leads to poor system quality
- [Answer]: タグ形式で質問を埋め込む
- あいまい/欠落/確認が必要な領域に焦点
- NFR/技術スタック判断にユーザー入力が有益なら質問を作成
- **迷ったら質問する** - 過信は品質低下につながる

- [Answer]: タグ形式で質問を埋め込む
- あいまい/欠落/確認が必要な領域に焦点
- NFR/技術スタック判断にユーザー入力が有益なら質問を作成
- **迷ったら質問する** - 過信は品質低下につながる

**Question categories to evaluate** (consider ALL categories):
- **Scalability Requirements** - Ask about expected load, growth patterns, scaling triggers, and capacity planning
- **Performance Requirements** - Ask about response times, throughput, latency, and performance benchmarks
- **Availability Requirements** - Ask about uptime expectations, disaster recovery, failover, and business continuity
- **Security Requirements** - Ask about data protection, compliance, authentication, authorization, and threat models
- **Tech Stack Selection** - Ask about technology preferences, constraints, existing systems, and integration requirements
- **Reliability Requirements** - Ask about error handling, fault tolerance, monitoring, and alerting needs
- **Maintainability Requirements** - Ask about code quality, documentation, testing, and operational requirements
- **Usability Requirements** - Ask about user experience, accessibility, and interface requirements
**評価すべき質問カテゴリ**（すべて考慮）:
- **スケーラビリティ要件** - 予想負荷、成長パターン、スケール条件、容量計画
- **性能要件** - 応答時間、スループット、レイテンシ、性能指標
- **可用性要件** - 稼働率、災害復旧、フェイルオーバー、事業継続
- **セキュリティ要件** - データ保護、コンプライアンス、認証/認可、脅威モデル
- **技術スタック選定** - 技術嗜好、制約、既存システム、統合要件
- **信頼性要件** - エラーハンドリング、耐障害性、監視、アラート
- **保守性要件** - コード品質、ドキュメント、テスト、運用要件
- **ユーザビリティ要件** - ユーザー体験、アクセシビリティ、UI 要件

**評価すべき質問カテゴリ**（すべて考慮）:
- **スケーラビリティ要件** - 予想負荷、成長パターン、スケール条件、容量計画
- **性能要件** - 応答時間、スループット、レイテンシ、性能指標
- **可用性要件** - 稼働率、災害復旧、フェイルオーバー、事業継続
- **セキュリティ要件** - データ保護、コンプライアンス、認証/認可、脅威モデル
- **技術スタック選定** - 技術嗜好、制約、既存システム、統合要件
- **信頼性要件** - エラーハンドリング、耐障害性、監視、アラート
- **保守性要件** - コード品質、ドキュメント、テスト、運用要件
- **ユーザビリティ要件** - ユーザー体験、アクセシビリティ、UI 要件

### Step 4: Store Plan
- Save as `aidlc-docs/construction/plans/{unit-name}-nfr-requirements-plan.md`
- Include all [Answer]: tags for user input
### ステップ 4: 計画の保存
- `aidlc-docs/construction/plans/{unit-name}-nfr-requirements-plan.md` として保存
- ユーザー入力用に [Answer]: タグをすべて含める

### ステップ 4: 計画の保存
- `aidlc-docs/construction/plans/{unit-name}-nfr-requirements-plan.md` として保存
- ユーザー入力用に [Answer]: タグをすべて含める

### Step 5: Collect and Analyze Answers
- Wait for user to complete all [Answer]: tags
- **MANDATORY**: Carefully review ALL responses for vague or ambiguous answers
- **CRITICAL**: Add follow-up questions for ANY unclear responses - do not proceed with ambiguity
- Look for responses like "depends", "maybe", "not sure", "mix of", "somewhere between", "standard", "typical"
- Create clarification questions file if ANY ambiguities are detected
- **Do not proceed until ALL ambiguities are resolved**
### ステップ 5: 回答収集と分析
- ユーザーがすべての [Answer]: タグを埋めるまで待つ
- **必須**: すべての回答のあいまいさを丁寧に確認
- **重要**: 不明瞭な回答には必ずフォロー質問を追加し、曖昧なまま進めない
- "depends", "maybe", "not sure", "mix of", "somewhere between", "standard", "typical" に注意
- あいまいさがあれば確認質問ファイルを作成
- **すべての曖昧さが解消されるまで進めない**

### ステップ 5: 回答収集と分析
- ユーザーがすべての [Answer]: タグを埋めるまで待つ
- **必須**: すべての回答のあいまいさを丁寧に確認
- **重要**: 不明瞭な回答には必ずフォロー質問を追加し、曖昧なまま進めない
- "depends", "maybe", "not sure", "mix of", "somewhere between", "standard", "typical" に注意
- あいまいさがあれば確認質問ファイルを作成
- **すべての曖昧さが解消されるまで進めない**

### Step 6: Generate NFR Requirements Artifacts
- Create `aidlc-docs/construction/{unit-name}/nfr-requirements/nfr-requirements.md`
- Create `aidlc-docs/construction/{unit-name}/nfr-requirements/tech-stack-decisions.md`
### ステップ 6: NFR Requirements 成果物の生成
- `aidlc-docs/construction/{unit-name}/nfr-requirements/nfr-requirements.md` を作成
- `aidlc-docs/construction/{unit-name}/nfr-requirements/tech-stack-decisions.md` を作成

### ステップ 6: NFR Requirements 成果物の生成
- `aidlc-docs/construction/{unit-name}/nfr-requirements/nfr-requirements.md` を作成
- `aidlc-docs/construction/{unit-name}/nfr-requirements/tech-stack-decisions.md` を作成

### Step 7: Present Completion Message
- Present completion message in this structure:
     1. **Completion Announcement** (mandatory): Always start with this:
### ステップ 7: 完了メッセージの提示
- 次の構造で完了メッセージを提示:
     1. **完了告知**（必須）: 必ずこれで開始

### ステップ 7: 完了メッセージの提示
- 次の構造で完了メッセージを提示:
     1. **完了告知**（必須）: 必ずこれで開始

```markdown
# 📊 NFR Requirements Complete - [unit-name]
```
```markdown
# 📊 NFR Requirements Complete - [unit-name]
```

```markdown
# 📊 NFR Requirements Complete - [unit-name]
```

     2. **AI Summary** (optional): Provide structured bullet-point summary of NFR requirements
        - Format: "NFR requirements assessment has identified [description]:"
        - List key scalability, performance, availability requirements (bullet points)
        - List security and compliance requirements identified
        - Mention tech stack decisions and rationale
        - DO NOT include workflow instructions ("please review", "let me know", "proceed to next phase", "before we proceed")
        - Keep factual and content-focused
     3. **Formatted Workflow Message** (mandatory): Always end with this exact format:
     2. **AI 要約**（任意）: NFR 要件の構造化要約
        - 形式: "NFR requirements assessment has identified [description]:"
        - 主要なスケーラビリティ/性能/可用性要件を列挙
        - セキュリティ/コンプライアンス要件に言及
        - 技術スタック判断と理由に言及
        - ワークフロー指示は含めない（"please review"、"let me know"、"proceed to next phase"、"before we proceed" など）
        - 事実ベースかつ内容中心にする
     3. **フォーマット済みワークフローメッセージ**（必須）: 必ず以下の形式で終了

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

### Step 8: Wait for Explicit Approval
- Do not proceed until the user explicitly approves the NFR requirements
- Approval must be clear and unambiguous
- If user requests changes, update the requirements and repeat the approval process
### ステップ 8: 明示的承認待ち
- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があれば要件を更新し、承認プロセスを繰り返す

### ステップ 8: 明示的承認待ち
- ユーザーが明示的に承認するまで進めない
- 承認は明確で曖昧でないこと
- 変更依頼があれば要件を更新し、承認プロセスを繰り返す

### Step 9: Record Approval and Update Progress
- Log approval in audit.md with timestamp
- Record the user's approval response with timestamp
- Mark NFR Requirements stage complete in aidlc-state.md
### ステップ 9: 承認記録と進捗更新
- audit.md に承認をタイムスタンプ付きで記録
- ユーザーの承認回答をタイムスタンプ付きで記録
- aidlc-state.md で NFR Requirements を完了にする

### ステップ 9: 承認記録と進捗更新
- audit.md に承認をタイムスタンプ付きで記録
- ユーザーの承認回答をタイムスタンプ付きで記録
- aidlc-state.md で NFR Requirements を完了にする
