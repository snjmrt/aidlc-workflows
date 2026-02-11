# Overconfidence Prevention Guide
# 過信防止ガイド

# 過信防止ガイド

## Problem Statement
## 問題の概要

## 問題の概要

AI-DLC was exhibiting overconfidence by not asking enough clarifying questions, even for complex project intent statements. This led to assumptions being made instead of gathering proper requirements.
AI-DLC は、複雑なプロジェクト意図の表明であっても十分な確認質問を行わず、過信により要件収集ではなく仮定に頼る状況が発生していた。

AI-DLC は、複雑なプロジェクト意図の表明であっても十分な確認質問を行わず、過信により要件収集ではなく仮定に頼る状況が発生していた。

## Root Cause Analysis
## 根本原因分析

## 根本原因分析

The overconfidence issue was caused by directives in multiple stages that encouraged skipping questions:
過信の原因は、複数ステージに存在する「質問を省く」方向の指示だった:

過信の原因は、複数ステージに存在する「質問を省く」方向の指示だった:

1. **Functional Design**: "Skip entire categories if not applicable"
2. **User Stories**: "Use categories as inspiration, NOT as mandatory checklist"
3. **Requirements Analysis**: Similar patterns encouraging minimal questioning
4. **NFR Requirements**: "Only if" conditions that discouraged thorough analysis
1. **Functional Design**: "該当しないカテゴリは丸ごとスキップ"
2. **User Stories**: "カテゴリはヒントとして使い、必須チェックリストではない"
3. **Requirements Analysis**: 最小限の質問を促す類似パターン
4. **NFR Requirements**: 徹底的な分析を妨げる "only if" 条件

1. **Functional Design**: "該当しないカテゴリは丸ごとスキップ"
2. **User Stories**: "カテゴリはヒントとして使い、必須チェックリストではない"
3. **Requirements Analysis**: 最小限の質問を促す類似パターン
4. **NFR Requirements**: 徹底的な分析を妨げる "only if" 条件

These directives were telling the AI to avoid asking questions rather than encouraging comprehensive requirements gathering.
これらの指示が、包括的な要件収集ではなく質問回避を促していた。

これらの指示が、包括的な要件収集ではなく質問回避を促していた。

## Solution Implemented
## 実施した解決策

## 実施した解決策

### Updated Question Generation Philosophy
### 質問生成の考え方を更新

### 質問生成の考え方を更新

**OLD APPROACH**: "Only ask questions if absolutely necessary"
**NEW APPROACH**: "When in doubt, ask the question - overconfidence leads to poor outcomes"
**旧アプローチ**: 「本当に必要な場合のみ質問する」
**新アプローチ**: 「迷ったら質問する。過信は悪い結果につながる」

**旧アプローチ**: 「本当に必要な場合のみ質問する」
**新アプローチ**: 「迷ったら質問する。過信は悪い結果につながる」

### Key Changes Made
### 主な変更点

### 主な変更点

#### 1. Requirements Analysis Stage
- Changed from "only if needed" to "ALWAYS create questions unless exceptionally clear"
- Added comprehensive evaluation areas (functional, non-functional, business context, technical context)
- Emphasized proactive questioning approach
#### 1. Requirements Analysis ステージ
- "必要なときだけ" から "例外的に明確な場合を除き常に質問" へ変更
- 包括的な評価領域（機能、非機能、ビジネス文脈、技術文脈）を追加
- 事前確認を積極的に行う姿勢を強化

#### 1. Requirements Analysis ステージ
- "必要なときだけ" から "例外的に明確な場合を除き常に質問" へ変更
- 包括的な評価領域（機能、非機能、ビジネス文脈、技術文脈）を追加
- 事前確認を積極的に行う姿勢を強化

#### 2. User Stories Stage
- Removed "skip entire categories" directive
- Added comprehensive question categories to evaluate
- Enhanced answer analysis requirements
- Strengthened follow-up question mandates
#### 2. User Stories ステージ
- "カテゴリを丸ごとスキップ" 指示を削除
- 評価すべき包括的な質問カテゴリを追加
- 回答分析要件を強化
- フォロー質問の必須度を強化

#### 2. User Stories ステージ
- "カテゴリを丸ごとスキップ" 指示を削除
- 評価すべき包括的な質問カテゴリを追加
- 回答分析要件を強化
- フォロー質問の必須度を強化

#### 3. Functional Design Stage
- Replaced "only if" conditions with comprehensive evaluation
- Added more question categories (data flow, integration points, error handling)
- Strengthened ambiguity detection and resolution requirements
#### 3. Functional Design ステージ
- "only if" 条件を包括的評価に置き換え
- 質問カテゴリを追加（データフロー、統合ポイント、エラーハンドリング）
- あいまいさの検出と解消要件を強化

#### 3. Functional Design ステージ
- "only if" 条件を包括的評価に置き換え
- 質問カテゴリを追加（データフロー、統合ポイント、エラーハンドリング）
- あいまいさの検出と解消要件を強化

#### 4. NFR Requirements Stage
- Expanded question categories beyond basic NFRs
- Added reliability, maintainability, and usability considerations
- Enhanced answer analysis for technical ambiguities
#### 4. NFR Requirements ステージ
- 基本的な NFR を超えて質問カテゴリを拡張
- 信頼性、保守性、ユーザビリティを追加
- 技術的あいまいさの回答分析を強化

#### 4. NFR Requirements ステージ
- 基本的な NFR を超えて質問カテゴリを拡張
- 信頼性、保守性、ユーザビリティを追加
- 技術的あいまいさの回答分析を強化

### New Guiding Principles
### 新しい指針

### 新しい指針

1. **Default to Asking**: When there's any ambiguity, ask clarifying questions
2. **Comprehensive Coverage**: Evaluate ALL relevant categories, don't skip areas
3. **Thorough Analysis**: Carefully analyze ALL user responses for ambiguities
4. **Mandatory Follow-up**: Create follow-up questions for ANY unclear responses
5. **No Proceeding with Ambiguity**: Don't move forward until ALL ambiguities are resolved
1. **質問が基本**: あいまいさが少しでもあれば確認質問をする
2. **包括的カバレッジ**: 関連するカテゴリはすべて評価し、抜けを作らない
3. **徹底分析**: ユーザー回答のあいまいさをすべて丁寧に分析
4. **フォロー必須**: あいまいな回答には必ずフォロー質問を作成
5. **曖昧なまま進めない**: あいまいさが解消されるまで前進しない

1. **質問が基本**: あいまいさが少しでもあれば確認質問をする
2. **包括的カバレッジ**: 関連するカテゴリはすべて評価し、抜けを作らない
3. **徹底分析**: ユーザー回答のあいまいさをすべて丁寧に分析
4. **フォロー必須**: あいまいな回答には必ずフォロー質問を作成
5. **曖昧なまま進めない**: あいまいさが解消されるまで前進しない

## Implementation Guidelines
## 実装ガイドライン

## 実装ガイドライン

### For Question Generation
- Evaluate ALL question categories, don't skip any
- Ask questions wherever clarification would improve quality
- Include comprehensive question categories in each stage
- Default to inclusion rather than exclusion of questions
### 質問生成
- すべての質問カテゴリを評価し、スキップしない
- 明確化で品質が上がるなら質問する
- 各ステージで包括的な質問カテゴリを含める
- 除外ではなく包含をデフォルトにする

### 質問生成
- すべての質問カテゴリを評価し、スキップしない
- 明確化で品質が上がるなら質問する
- 各ステージで包括的な質問カテゴリを含める
- 除外ではなく包含をデフォルトにする

### For Answer Analysis
- Look for vague responses: "depends", "maybe", "not sure", "mix of", "somewhere between"
- Detect undefined terms and references to external concepts
- Identify contradictory or incomplete answers
- Create follow-up questions for ANY ambiguities
### 回答分析
- あいまいな回答を検出: "depends", "maybe", "not sure", "mix of", "somewhere between"
- 未定義の用語や外部概念への参照を検出
- 矛盾または不完全な回答を特定
- あいまいな回答には必ずフォロー質問を作成

### 回答分析
- あいまいな回答を検出: "depends", "maybe", "not sure", "mix of", "somewhere between"
- 未定義の用語や外部概念への参照を検出
- 矛盾または不完全な回答を特定
- あいまいな回答には必ずフォロー質問を作成

### For Follow-up Questions
- Create separate clarification files when ambiguities are detected
- Ask specific questions to resolve each ambiguity
- Don't proceed until ALL unclear responses are clarified
- Be thorough - better to over-clarify than under-clarify
### フォロー質問
- あいまいさが検出されたら確認ファイルを作成
- 各あいまいさを解消する具体的質問を作成
- すべての不明点が解消されるまで進めない
- 過剰でも不足より良い

### フォロー質問
- あいまいさが検出されたら確認ファイルを作成
- 各あいまいさを解消する具体的質問を作成
- すべての不明点が解消されるまで進めない
- 過剰でも不足より良い

## Quality Assurance
## 品質保証

## 品質保証

### Red Flags to Watch For
- Stages completing without asking any questions on complex projects
- Proceeding with vague or ambiguous user responses
- Skipping entire question categories without justification
- Making assumptions instead of asking for clarification
### 注意すべき兆候
- 複雑なプロジェクトで質問なしにステージが完了
- あいまいな回答で進行
- 根拠なく質問カテゴリを丸ごとスキップ
- 確認せず仮定する

### 注意すべき兆候
- 複雑なプロジェクトで質問なしにステージが完了
- あいまいな回答で進行
- 根拠なく質問カテゴリを丸ごとスキップ
- 確認せず仮定する

### Success Indicators
- Appropriate number of clarifying questions for project complexity
- Thorough analysis of user responses with follow-up when needed
- Clear, unambiguous requirements before proceeding to implementation
- Reduced need for changes during later stages due to better upfront clarification
### 成功指標
- プロジェクトの複雑さに適した質問数
- 回答の丁寧な分析と必要なフォロー
- 実装前に明確で曖昧さのない要件
- 事前確認による後工程の手戻り削減

### 成功指標
- プロジェクトの複雑さに適した質問数
- 回答の丁寧な分析と必要なフォロー
- 実装前に明確で曖昧さのない要件
- 事前確認による後工程の手戻り削減

## Maintenance
## 保守

## 保守

This guide should be referenced when:
- Adding new stages to AI-DLC
- Updating existing stage instructions
- Reviewing AI-DLC performance for overconfidence issues
- Training team members on AI-DLC question generation principles
本ガイドは以下の場面で参照する:
- AI-DLC に新しいステージを追加する場合
- 既存ステージの指示を更新する場合
- AI-DLC の過信問題に関する性能レビュー
- チームメンバーに質問生成原則を教育する場合

本ガイドは以下の場面で参照する:
- AI-DLC に新しいステージを追加する場合
- 既存ステージの指示を更新する場合
- AI-DLC の過信問題に関する性能レビュー
- チームメンバーに質問生成原則を教育する場合

## Key Takeaway
## 重要な結論

## 重要な結論

**It's better to ask too many questions than to make incorrect assumptions.** The cost of asking clarifying questions upfront is far less than the cost of implementing the wrong solution based on assumptions.
**間違った仮定をするより、質問しすぎる方がよい。** 事前の確認質問のコストは、仮定に基づく誤った実装のコストよりはるかに小さい。

**間違った仮定をするより、質問しすぎる方がよい。** 事前の確認質問のコストは、仮定に基づく誤った実装のコストよりはるかに小さい。
