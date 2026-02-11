# Question Format Guide
# 質問フォーマットガイド

# 質問フォーマットガイド

## MANDATORY: All Questions Must Use This Format
## 必須: すべての質問はこの形式を使用する

## 必須: すべての質問はこの形式を使用する

### Rule: Never Ask Questions in Chat
**CRITICAL**: You must NEVER ask questions directly in the chat. ALL questions must be placed in dedicated question files.
### ルール: チャットで質問してはいけない
**重要**: チャットで直接質問してはならない。すべての質問は専用の質問ファイルに記載すること。

### ルール: チャットで質問してはいけない
**重要**: チャットで直接質問してはならない。すべての質問は専用の質問ファイルに記載すること。

### Question File Format
### 質問ファイル形式

### 質問ファイル形式

#### File Naming Convention
- Use descriptive names: `{phase-name}-questions.md`
- Examples:
  - `classification-questions.md`
  - `requirements-questions.md`
  - `story-planning-questions.md`
  - `design-questions.md`
#### ファイル命名規則
- 分かりやすい名前を使う: `{phase-name}-questions.md`
- 例:
  - `classification-questions.md`
  - `requirements-questions.md`
  - `story-planning-questions.md`
  - `design-questions.md`

#### ファイル命名規則
- 分かりやすい名前を使う: `{phase-name}-questions.md`
- 例:
  - `classification-questions.md`
  - `requirements-questions.md`
  - `story-planning-questions.md`
  - `design-questions.md`

#### Question Structure
Every question must include meaningful options plus "Other" as the last option:
#### 質問構造
すべての質問には意味のある選択肢と、最後に "Other" を含めること:

#### 質問構造
すべての質問には意味のある選択肢と、最後に "Other" を含めること:

```markdown
## Question [Number]
[Clear, specific question text]

A) [First meaningful option]
B) [Second meaningful option]
[...additional options as needed...]
X) Other (please describe after [Answer]: tag below)

[Answer]: 
```
```markdown
## Question [Number]
[明確で具体的な質問文]

A) [最初の意味ある選択肢]
B) [2 つ目の意味ある選択肢]
[...必要に応じて追加...]
X) Other (please describe after [Answer]: tag below)

[Answer]: 
```

```markdown
## Question [Number]
[明確で具体的な質問文]

A) [最初の意味ある選択肢]
B) [2 つ目の意味ある選択肢]
[...必要に応じて追加...]
X) Other (please describe after [Answer]: tag below)

[Answer]: 
```

**CRITICAL**: 
- "Other" is MANDATORY as the LAST option for every question
- Only include meaningful options - don't make up options to fill slots
- Use as many or as few options as make sense (minimum 2 + Other)
**重要**: 
- "Other" はすべての質問で**最後**に必ず含める
- 意味のある選択肢のみを含める（埋めるための選択肢は作らない）
- 適切な数の選択肢にする（最小 2 + Other）

**重要**: 
- "Other" はすべての質問で**最後**に必ず含める
- 意味のある選択肢のみを含める（埋めるための選択肢は作らない）
- 適切な数の選択肢にする（最小 2 + Other）

### Complete Example
### 完全な例

### 完全な例

```markdown
# Requirements Clarification Questions

Please answer the following questions to help clarify the requirements.

## Question 1
What is the primary user authentication method?

A) Username and password
B) Social media login (Google, Facebook)
C) Single Sign-On (SSO)
D) Multi-factor authentication
E) Other (please describe after [Answer]: tag below)

[Answer]: 

## Question 2
Will this be a web or mobile application?

A) Web application
B) Mobile application
C) Both web and mobile
D) Other (please describe after [Answer]: tag below)

[Answer]: 

## Question 3
Is this a new project or existing codebase?

A) New project (greenfield)
B) Existing codebase (brownfield)
C) Other (please describe after [Answer]: tag below)

[Answer]: 
```
```markdown
# Requirements Clarification Questions

Please answer the following questions to help clarify the requirements.

## Question 1
What is the primary user authentication method?

A) Username and password
B) Social media login (Google, Facebook)
C) Single Sign-On (SSO)
D) Multi-factor authentication
E) Other (please describe after [Answer]: tag below)

[Answer]: 

## Question 2
Will this be a web or mobile application?

A) Web application
B) Mobile application
C) Both web and mobile
D) Other (please describe after [Answer]: tag below)

[Answer]: 

## Question 3
Is this a new project or existing codebase?

A) New project (greenfield)
B) Existing codebase (brownfield)
C) Other (please describe after [Answer]: tag below)

[Answer]: 
```

```markdown
# Requirements Clarification Questions

Please answer the following questions to help clarify the requirements.

## Question 1
What is the primary user authentication method?

A) Username and password
B) Social media login (Google, Facebook)
C) Single Sign-On (SSO)
D) Multi-factor authentication
E) Other (please describe after [Answer]: tag below)

[Answer]: 

## Question 2
Will this be a web or mobile application?

A) Web application
B) Mobile application
C) Both web and mobile
D) Other (please describe after [Answer]: tag below)

[Answer]: 

## Question 3
Is this a new project or existing codebase?

A) New project (greenfield)
B) Existing codebase (brownfield)
C) Other (please describe after [Answer]: tag below)

[Answer]: 
```

### User Response Format
Users will answer by filling in the letter choice after [Answer]: tag:
### ユーザー回答形式
ユーザーは [Answer]: タグの後に文字選択を記入する:

### ユーザー回答形式
ユーザーは [Answer]: タグの後に文字選択を記入する:

```markdown
## Question 1
What is the primary user authentication method?

A) Username and password
B) Social media login (Google, Facebook)
C) Single Sign-On (SSO)
D) Multi-factor authentication

[Answer]: C
```
```markdown
## Question 1
What is the primary user authentication method?

A) Username and password
B) Social media login (Google, Facebook)
C) Single Sign-On (SSO)
D) Multi-factor authentication

[Answer]: C
```

```markdown
## Question 1
What is the primary user authentication method?

A) Username and password
B) Social media login (Google, Facebook)
C) Single Sign-On (SSO)
D) Multi-factor authentication

[Answer]: C
```

### Reading User Responses
After user confirms completion:
1. Read the question file
2. Extract answers after [Answer]: tags
3. Validate all questions are answered
4. Proceed with analysis based on responses
### ユーザー回答の読み取り
ユーザーが完了を伝えた後:
1. 質問ファイルを読み込む
2. [Answer]: タグの後の回答を抽出
3. すべての質問が回答済みか検証
4. 回答に基づいて分析を進める

### ユーザー回答の読み取り
ユーザーが完了を伝えた後:
1. 質問ファイルを読み込む
2. [Answer]: タグの後の回答を抽出
3. すべての質問が回答済みか検証
4. 回答に基づいて分析を進める

### Multiple Choice Guidelines
### 多肢選択ガイドライン

### 多肢選択ガイドライン

#### Option Count
- Minimum: 2 meaningful options + "Other" (A, B, C)
- Typical: 3-4 meaningful options + "Other" (A, B, C, D, E)
- Maximum: 5 meaningful options + "Other" (A, B, C, D, E, F)
- **CRITICAL**: Don't make up options just to fill slots - only include meaningful choices
#### 選択肢数
- 最小: 意味のある 2 選択肢 + "Other"（A, B, C）
- 典型: 意味のある 3～4 選択肢 + "Other"（A, B, C, D, E）
- 最大: 意味のある 5 選択肢 + "Other"（A, B, C, D, E, F）
- **重要**: 枠を埋めるための選択肢を作らない

#### 選択肢数
- 最小: 意味のある 2 選択肢 + "Other"（A, B, C）
- 典型: 意味のある 3～4 選択肢 + "Other"（A, B, C, D, E）
- 最大: 意味のある 5 選択肢 + "Other"（A, B, C, D, E, F）
- **重要**: 枠を埋めるための選択肢を作らない

#### Option Quality
- Make options mutually exclusive
- Cover the most common scenarios
- Only include meaningful, realistic options
- **ALWAYS include "Other" as the LAST option** (MANDATORY)
- Be specific and clear
- **Don't make up options to fill A, B, C, D slots**
#### 選択肢の質
- 選択肢は相互排他的にする
- もっとも一般的なシナリオをカバーする
- 意味のある現実的な選択肢のみを含める
- **"Other" を必ず最後に含める**（必須）
- 具体的で明確にする
- **A, B, C, D の枠埋めのために選択肢を作らない**

#### 選択肢の質
- 選択肢は相互排他的にする
- もっとも一般的なシナリオをカバーする
- 意味のある現実的な選択肢のみを含める
- **"Other" を必ず最後に含める**（必須）
- 具体的で明確にする
- **A, B, C, D の枠埋めのために選択肢を作らない**

#### Good Example:
```markdown
## Question 5
What database technology will be used?

A) Relational (PostgreSQL, MySQL)
B) NoSQL Document (MongoDB, DynamoDB)
C) NoSQL Key-Value (Redis, Memcached)
D) Graph Database (Neo4j, Neptune)
E) Other (please describe after [Answer]: tag below)

[Answer]: 
```
#### 良い例:
```markdown
## Question 5
What database technology will be used?

A) Relational (PostgreSQL, MySQL)
B) NoSQL Document (MongoDB, DynamoDB)
C) NoSQL Key-Value (Redis, Memcached)
D) Graph Database (Neo4j, Neptune)
E) Other (please describe after [Answer]: tag below)

[Answer]: 
```

#### 良い例:
```markdown
## Question 5
What database technology will be used?

A) Relational (PostgreSQL, MySQL)
B) NoSQL Document (MongoDB, DynamoDB)
C) NoSQL Key-Value (Redis, Memcached)
D) Graph Database (Neo4j, Neptune)
E) Other (please describe after [Answer]: tag below)

[Answer]: 
```

#### Bad Example (Avoid):
```markdown
## Question 5
What database will you use?

A) Yes
B) No
C) Maybe

[Answer]: 
```
#### 悪い例（避ける）:
```markdown
## Question 5
What database will you use?

A) Yes
B) No
C) Maybe

[Answer]: 
```

#### 悪い例（避ける）:
```markdown
## Question 5
What database will you use?

A) Yes
B) No
C) Maybe

[Answer]: 
```

### Workflow Integration
### ワークフロー統合

### ワークフロー統合

#### Step 1: Create Question File
```markdown
Create aidlc-docs/{phase-name}-questions.md with all questions
```
#### ステップ 1: 質問ファイルの作成
```markdown
Create aidlc-docs/{phase-name}-questions.md with all questions
```

#### ステップ 1: 質問ファイルの作成
```markdown
Create aidlc-docs/{phase-name}-questions.md with all questions
```

#### Step 2: Inform User
```
"I've created {phase-name}-questions.md with [X] questions. 
Please answer each question by filling in the letter choice after the [Answer]: tag. 
If none of the options match your needs, choose the last option (Other) and describe your preference. Let me know when you're done."
```
#### ステップ 2: ユーザーへの通知
```
"I've created {phase-name}-questions.md with [X] questions. 
Please answer each question by filling in the letter choice after the [Answer]: tag. 
If none of the options match your needs, choose the last option (Other) and describe your preference. Let me know when you're done."
```

#### ステップ 2: ユーザーへの通知
```
"I've created {phase-name}-questions.md with [X] questions. 
Please answer each question by filling in the letter choice after the [Answer]: tag. 
If none of the options match your needs, choose the last option (Other) and describe your preference. Let me know when you're done."
```

#### Step 3: Wait for Confirmation
Wait for user to say "done", "completed", "finished", or similar.
#### ステップ 3: 完了の確認を待つ
ユーザーが "done"、"completed"、"finished" などと伝えるまで待つ。

#### ステップ 3: 完了の確認を待つ
ユーザーが "done"、"completed"、"finished" などと伝えるまで待つ。

#### Step 4: Read and Analyze
```
Read aidlc-docs/{phase-name}-questions.md
Extract all answers
Validate completeness
Proceed with analysis
```
#### ステップ 4: 読み取りと分析
```
Read aidlc-docs/{phase-name}-questions.md
Extract all answers
Validate completeness
Proceed with analysis
```

#### ステップ 4: 読み取りと分析
```
Read aidlc-docs/{phase-name}-questions.md
Extract all answers
Validate completeness
Proceed with analysis
```

### Error Handling
### エラーハンドリング

### エラーハンドリング

#### Missing Answers
If any [Answer]: tag is empty:
```
"I noticed Question [X] is not answered. Please provide an answer using one of the letter choices 
for all questions before proceeding."
```
#### 未回答
[Answer]: タグが空の場合:
```
"I noticed Question [X] is not answered. Please provide an answer using one of the letter choices 
for all questions before proceeding."
```

#### 未回答
[Answer]: タグが空の場合:
```
"I noticed Question [X] is not answered. Please provide an answer using one of the letter choices 
for all questions before proceeding."
```

#### Invalid Answers
If answer is not a valid letter choice:
```
"Question [X] has an invalid answer '[answer]'. 
Please use only the letter choices provided in the question."
```
#### 無効な回答
回答が無効な文字の場合:
```
"Question [X] has an invalid answer '[answer]'. 
Please use only the letter choices provided in the question."
```

#### 無効な回答
回答が無効な文字の場合:
```
"Question [X] has an invalid answer '[answer]'. 
Please use only the letter choices provided in the question."
```

#### Ambiguous Answers
If user provides explanation instead of letter:
```
"For Question [X], please provide the letter choice that best matches your answer. 
If none match, choose 'Other' and add your description after the [Answer]: tag."
```
#### あいまいな回答
ユーザーが文字ではなく説明を記入した場合:
```
"For Question [X], please provide the letter choice that best matches your answer. 
If none match, choose 'Other' and add your description after the [Answer]: tag."
```

#### あいまいな回答
ユーザーが文字ではなく説明を記入した場合:
```
"For Question [X], please provide the letter choice that best matches your answer. 
If none match, choose 'Other' and add your description after the [Answer]: tag."
```

### Contradiction and Ambiguity Detection
### 矛盾とあいまいさの検出

### 矛盾とあいまいさの検出

**MANDATORY**: After reading user responses, you MUST check for contradictions and ambiguities.
**必須**: ユーザー回答を読み取ったら、矛盾とあいまいさを必ず確認する。

**必須**: ユーザー回答を読み取ったら、矛盾とあいまいさを必ず確認する。

#### Detecting Contradictions
Look for logically inconsistent answers:
- Scope mismatch: "Bug fix" but "Entire codebase affected"
- Risk mismatch: "Low risk" but "Breaking changes"
- Timeline mismatch: "Quick fix" but "Multiple subsystems"
- Impact mismatch: "Single component" but "Significant architecture changes"
#### 矛盾の検出
論理的に整合しない回答を探す:
- スコープ不一致: "バグ修正" だが "コードベース全体に影響"
- リスク不一致: "低リスク" だが "破壊的変更"
- 期限不一致: "素早い修正" だが "複数サブシステム"
- 影響不一致: "単一コンポーネント" だが "大きなアーキテクチャ変更"

#### 矛盾の検出
論理的に整合しない回答を探す:
- スコープ不一致: "バグ修正" だが "コードベース全体に影響"
- リスク不一致: "低リスク" だが "破壊的変更"
- 期限不一致: "素早い修正" だが "複数サブシステム"
- 影響不一致: "単一コンポーネント" だが "大きなアーキテクチャ変更"

#### Detecting Ambiguities
Look for unclear or borderline responses:
- Answers that could fit multiple classifications
- Responses that lack specificity
- Conflicting indicators across multiple questions
#### あいまいさの検出
不明確または境界的な回答を探す:
- 複数分類に当てはまり得る回答
- 具体性に欠ける回答
- 複数質問にまたがる相反する兆候

#### あいまいさの検出
不明確または境界的な回答を探す:
- 複数分類に当てはまり得る回答
- 具体性に欠ける回答
- 複数質問にまたがる相反する兆候

#### Creating Clarification Questions
If contradictions or ambiguities detected:
#### 確認質問の作成
矛盾またはあいまいさが検出された場合:

#### 確認質問の作成
矛盾またはあいまいさが検出された場合:

1. **Create clarification file**: `{phase-name}-clarification-questions.md`
2. **Explain the issue**: Clearly state what contradiction/ambiguity was detected
3. **Ask targeted questions**: Use multiple choice format to resolve the issue
4. **Reference original questions**: Show which questions had conflicting answers
1. **確認ファイルを作成**: `{phase-name}-clarification-questions.md`
2. **問題点を説明**: どの矛盾/あいまいさが検出されたかを明確に記載
3. **的を絞った質問をする**: 多肢選択形式で解消
4. **元の質問を参照**: どの質問で矛盾したかを示す

1. **確認ファイルを作成**: `{phase-name}-clarification-questions.md`
2. **問題点を説明**: どの矛盾/あいまいさが検出されたかを明確に記載
3. **的を絞った質問をする**: 多肢選択形式で解消
4. **元の質問を参照**: どの質問で矛盾したかを示す

**Example**:
```markdown
# [Phase Name] Clarification Questions

I detected contradictions in your responses that need clarification:

## Contradiction 1: [Brief Description]
You indicated "[Answer A]" (Q[X]:[Letter]) but also "[Answer B]" (Q[Y]:[Letter]).
These responses are contradictory because [explanation].

### Clarification Question 1
[Specific question to resolve contradiction]

A) [Option that resolves toward first answer]
B) [Option that resolves toward second answer]
C) [Option that provides middle ground]
D) [Option that reframes the question]

[Answer]: 

## Ambiguity 1: [Brief Description]
Your response to Q[X] ("[Answer]") is ambiguous because [explanation].

### Clarification Question 2
[Specific question to clarify ambiguity]

A) [Clear option 1]
B) [Clear option 2]
C) [Clear option 3]
D) [Clear option 4]

[Answer]: 
```
**例**:
```markdown
# [Phase Name] Clarification Questions

I detected contradictions in your responses that need clarification:

## Contradiction 1: [Brief Description]
You indicated "[Answer A]" (Q[X]:[Letter]) but also "[Answer B]" (Q[Y]:[Letter]).
These responses are contradictory because [explanation].

### Clarification Question 1
[Specific question to resolve contradiction]

A) [Option that resolves toward first answer]
B) [Option that resolves toward second answer]
C) [Option that provides middle ground]
D) [Option that reframes the question]

[Answer]: 

## Ambiguity 1: [Brief Description]
Your response to Q[X] ("[Answer]") is ambiguous because [explanation].

### Clarification Question 2
[Specific question to clarify ambiguity]

A) [Clear option 1]
B) [Clear option 2]
C) [Clear option 3]
D) [Clear option 4]

[Answer]: 
```

**例**:
```markdown
# [Phase Name] Clarification Questions

I detected contradictions in your responses that need clarification:

## Contradiction 1: [Brief Description]
You indicated "[Answer A]" (Q[X]:[Letter]) but also "[Answer B]" (Q[Y]:[Letter]).
These responses are contradictory because [explanation].

### Clarification Question 1
[Specific question to resolve contradiction]

A) [Option that resolves toward first answer]
B) [Option that resolves toward second answer]
C) [Option that provides middle ground]
D) [Option that reframes the question]

[Answer]: 

## Ambiguity 1: [Brief Description]
Your response to Q[X] ("[Answer]") is ambiguous because [explanation].

### Clarification Question 2
[Specific question to clarify ambiguity]

A) [Clear option 1]
B) [Clear option 2]
C) [Clear option 3]
D) [Clear option 4]

[Answer]: 
```

#### Workflow for Clarifications
#### 確認のワークフロー

#### 確認のワークフロー

1. **Detect**: Analyze all responses for contradictions/ambiguities
2. **Create**: Generate clarification question file if issues found
3. **Inform**: Tell user about the issues and clarification file
4. **Wait**: Do not proceed until user provides clarifications
5. **Re-validate**: After clarifications, check again for consistency
6. **Proceed**: Only move forward when all contradictions are resolved
1. **検出**: すべての回答を分析し、矛盾/あいまいさを確認
2. **作成**: 問題があれば確認質問ファイルを生成
3. **通知**: 問題点と確認ファイルをユーザーに伝える
4. **待機**: ユーザーの確認回答があるまで進めない
5. **再検証**: 回答後に再度整合性を確認
6. **続行**: すべての矛盾が解消されたら前進

1. **検出**: すべての回答を分析し、矛盾/あいまいさを確認
2. **作成**: 問題があれば確認質問ファイルを生成
3. **通知**: 問題点と確認ファイルをユーザーに伝える
4. **待機**: ユーザーの確認回答があるまで進めない
5. **再検証**: 回答後に再度整合性を確認
6. **続行**: すべての矛盾が解消されたら前進

#### Example User Message
```
"I detected 2 contradictions in your responses:

1. Bug fix scope vs. codebase impact (Q1 vs Q2)
2. Low risk vs. breaking changes (Q7 vs Q4)

I've created classification-clarification-questions.md with 2 questions to resolve these.
Please answer these clarifying questions before I can proceed with classification."
```
#### ユーザーへの例メッセージ
```
"I detected 2 contradictions in your responses:

1. Bug fix scope vs. codebase impact (Q1 vs Q2)
2. Low risk vs. breaking changes (Q7 vs Q4)

I've created classification-clarification-questions.md with 2 questions to resolve these.
Please answer these clarifying questions before I can proceed with classification."
```

#### ユーザーへの例メッセージ
```
"I detected 2 contradictions in your responses:

1. Bug fix scope vs. codebase impact (Q1 vs Q2)
2. Low risk vs. breaking changes (Q7 vs Q4)

I've created classification-clarification-questions.md with 2 questions to resolve these.
Please answer these clarifying questions before I can proceed with classification."
```

### Best Practices
### ベストプラクティス

### ベストプラクティス

1. **Be Specific**: Questions should be clear and unambiguous
2. **Be Comprehensive**: Cover all necessary information
3. **Be Concise**: Keep questions focused on one topic
4. **Be Practical**: Options should be realistic and actionable
5. **Be Consistent**: Use same format throughout all question files
1. **具体的に**: 質問は明確であいまいさのない内容にする
2. **網羅的に**: 必要情報をすべてカバーする
3. **簡潔に**: 質問は 1 トピックに絞る
4. **実用的に**: 選択肢は現実的で行動可能にする
5. **一貫性**: すべての質問ファイルで同じ形式を使う

1. **具体的に**: 質問は明確であいまいさのない内容にする
2. **網羅的に**: 必要情報をすべてカバーする
3. **簡潔に**: 質問は 1 トピックに絞る
4. **実用的に**: 選択肢は現実的で行動可能にする
5. **一貫性**: すべての質問ファイルで同じ形式を使う

### Phase-Specific Examples
### フェーズ別の例

### フェーズ別の例

#### Example with 2 meaningful options:
```markdown
## Question 1
Is this a new project or existing codebase?

A) New project (greenfield)
B) Existing codebase (brownfield)
C) Other (please describe after [Answer]: tag below)

[Answer]: 
```
#### 意味のある選択肢が 2 つの例:
```markdown
## Question 1
Is this a new project or existing codebase?

A) New project (greenfield)
B) Existing codebase (brownfield)
C) Other (please describe after [Answer]: tag below)

[Answer]: 
```

#### 意味のある選択肢が 2 つの例:
```markdown
## Question 1
Is this a new project or existing codebase?

A) New project (greenfield)
B) Existing codebase (brownfield)
C) Other (please describe after [Answer]: tag below)

[Answer]: 
```

#### Example with 3 meaningful options:
```markdown
## Question 2
What is the deployment target?

A) Cloud (AWS, Azure, GCP)
B) On-premises servers
C) Hybrid (both cloud and on-premises)
D) Other (please describe after [Answer]: tag below)

[Answer]: 
```
#### 意味のある選択肢が 3 つの例:
```markdown
## Question 2
What is the deployment target?

A) Cloud (AWS, Azure, GCP)
B) On-premises servers
C) Hybrid (both cloud and on-premises)
D) Other (please describe after [Answer]: tag below)

[Answer]: 
```

#### 意味のある選択肢が 3 つの例:
```markdown
## Question 2
What is the deployment target?

A) Cloud (AWS, Azure, GCP)
B) On-premises servers
C) Hybrid (both cloud and on-premises)
D) Other (please describe after [Answer]: tag below)

[Answer]: 
```

#### Example with 4 meaningful options:
```markdown
## Question 3
What architectural pattern should be used?

A) Monolithic architecture
B) Microservices architecture
C) Serverless architecture
D) Event-driven architecture
E) Other (please describe after [Answer]: tag below)

[Answer]: 
```
#### 意味のある選択肢が 4 つの例:
```markdown
## Question 3
What architectural pattern should be used?

A) Monolithic architecture
B) Microservices architecture
C) Serverless architecture
D) Event-driven architecture
E) Other (please describe after [Answer]: tag below)

[Answer]: 
```

#### 意味のある選択肢が 4 つの例:
```markdown
## Question 3
What architectural pattern should be used?

A) Monolithic architecture
B) Microservices architecture
C) Serverless architecture
D) Event-driven architecture
E) Other (please describe after [Answer]: tag below)

[Answer]: 
```

## Summary
## まとめ

## まとめ

**Remember**: 
- ✅ Always create question files
- ✅ Always use multiple choice format
- ✅ **Always include "Other" as the LAST option (MANDATORY)**
- ✅ Only include meaningful options - don't make up options to fill slots
- ✅ Always use [Answer]: tags
- ✅ Always wait for user completion
- ✅ Always validate responses for contradictions
- ✅ Always create clarification files if needed
- ✅ Always resolve contradictions before proceeding
- ❌ Never ask questions in chat
- ❌ Never make up options just to have A, B, C, D
- ❌ Never proceed without answers
- ❌ Never proceed with unresolved contradictions
- ❌ Never make assumptions about ambiguous responses
**忘れないこと**: 
- ✅ 質問ファイルを必ず作成する
- ✅ 常に多肢選択形式を使用する
- ✅ **"Other" を必ず最後の選択肢に含める（必須）**
- ✅ 意味のある選択肢のみを含め、枠埋め用の選択肢は作らない
- ✅ 必ず [Answer]: タグを使う
- ✅ ユーザーの完了を必ず待つ
- ✅ 回答の矛盾を必ず検証する
- ✅ 必要なら確認ファイルを必ず作成する
- ✅ 矛盾が解消されるまで進めない
- ❌ チャットで質問しない
- ❌ A, B, C, D を埋めるための選択肢を作らない
- ❌ 回答なしで進めない
- ❌ 矛盾を解消せずに進めない
- ❌ あいまいな回答を前提として進めない

**忘れないこと**: 
- ✅ 質問ファイルを必ず作成する
- ✅ 常に多肢選択形式を使用する
- ✅ **"Other" を必ず最後の選択肢に含める（必須）**
- ✅ 意味のある選択肢のみを含め、枠埋め用の選択肢は作らない
- ✅ 必ず [Answer]: タグを使う
- ✅ ユーザーの完了を必ず待つ
- ✅ 回答の矛盾を必ず検証する
- ✅ 必要なら確認ファイルを必ず作成する
- ✅ 矛盾が解消されるまで進めない
- ❌ チャットで質問しない
- ❌ A, B, C, D を埋めるための選択肢を作らない
- ❌ 回答なしで進めない
- ❌ 矛盾を解消せずに進めない
- ❌ あいまいな回答を前提として進めない
