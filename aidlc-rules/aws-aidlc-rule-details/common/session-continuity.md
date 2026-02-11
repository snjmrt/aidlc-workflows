# Session Continuity Templates
# セッション継続テンプレート

# セッション継続テンプレート

## Welcome Back Prompt Template
When a user returns to continue work on an existing AI-DLC project, present this prompt:
## おかえりプロンプトのテンプレート
既存の AI-DLC プロジェクトを続行するユーザーには、次のプロンプトを提示する:

## おかえりプロンプトのテンプレート
既存の AI-DLC プロジェクトを続行するユーザーには、次のプロンプトを提示する:

```markdown
**Welcome back! I can see you have an existing AI-DLC project in progress.**

Based on your aidlc-state.md, here's your current status:
- **Project**: [project-name]
- **Current Phase**: [INCEPTION/CONSTRUCTION/OPERATIONS]
- **Current Stage**: [Stage Name]
- **Last Completed**: [Last completed step]
- **Next Step**: [Next step to work on]

**What would you like to work on today?**

A) Continue where you left off ([Next step description])
B) Review a previous stage ([Show available stages])

[Answer]: 
```
```markdown
**Welcome back! I can see you have an existing AI-DLC project in progress.**

Based on your aidlc-state.md, here's your current status:
- **Project**: [project-name]
- **Current Phase**: [INCEPTION/CONSTRUCTION/OPERATIONS]
- **Current Stage**: [Stage Name]
- **Last Completed**: [Last completed step]
- **Next Step**: [Next step to work on]

**What would you like to work on today?**

A) Continue where you left off ([Next step description])
B) Review a previous stage ([Show available stages])

[Answer]: 
```

```markdown
**Welcome back! I can see you have an existing AI-DLC project in progress.**

Based on your aidlc-state.md, here's your current status:
- **Project**: [project-name]
- **Current Phase**: [INCEPTION/CONSTRUCTION/OPERATIONS]
- **Current Stage**: [Stage Name]
- **Last Completed**: [Last completed step]
- **Next Step**: [Next step to work on]

**What would you like to work on today?**

A) Continue where you left off ([Next step description])
B) Review a previous stage ([Show available stages])

[Answer]: 
```

## MANDATORY: Session Continuity Instructions
1. **Always read aidlc-state.md first** when detecting existing project
2. **Parse current status** from the workflow file to populate the prompt
3. **MANDATORY: Load Previous Stage Artifacts** - Before resuming any stage, automatically read all relevant artifacts from previous stages:
   - **Reverse Engineering**: Read architecture.md, code-structure.md, api-documentation.md
   - **Requirements Analysis**: Read requirements.md, requirement-verification-questions.md
   - **User Stories**: Read stories.md, personas.md, story-generation-plan.md
   - **Application Design**: Read application-design artifacts (components.md, component-methods.md, services.md)
   - **Design (Units)**: Read unit-of-work.md, unit-of-work-dependency.md, unit-of-work-story-map.md
   - **Per-Unit Design**: Read functional-design.md, nfr-requirements.md, nfr-design.md, infrastructure-design.md
   - **Code Stages**: Read all code files, plans, AND all previous artifacts
4. **Smart Context Loading by Stage**:
   - **Early Stages (Workspace Detection, Reverse Engineering)**: Load workspace analysis
   - **Requirements/Stories**: Load reverse engineering + requirements artifacts
   - **Design Stages**: Load requirements + stories + architecture + design artifacts
   - **Code Stages**: Load ALL artifacts + existing code files
5. **Adapt options** based on architectural choice and current phase
6. **Show specific next steps** rather than generic descriptions
7. **Log the continuity prompt** in audit.md with timestamp
8. **Context Summary**: After loading artifacts, provide brief summary of what was loaded for user awareness
9. **Asking questions**: ALWAYS ask clarification or user feedback questions by placing them in .md files. DO NOT place the multiple-choice questions in-line in the chat session.
## 必須: セッション継続の指示
1. 既存プロジェクトを検出したら **必ず最初に aidlc-state.md を読む**
2. ワークフローファイルから現在の状態を解析してプロンプトに反映
3. **必須: 以前のステージ成果物を読み込む** - どのステージを再開する場合でも、以前の関連成果物を自動で読み込む:
   - **Reverse Engineering**: architecture.md, code-structure.md, api-documentation.md
   - **Requirements Analysis**: requirements.md, requirement-verification-questions.md
   - **User Stories**: stories.md, personas.md, story-generation-plan.md
   - **Application Design**: アプリ設計成果物（components.md, component-methods.md, services.md）
   - **Design (Units)**: unit-of-work.md, unit-of-work-dependency.md, unit-of-work-story-map.md
   - **Per-Unit Design**: functional-design.md, nfr-requirements.md, nfr-design.md, infrastructure-design.md
   - **Code Stages**: すべてのコードファイル、計画、そしてすべての過去成果物
4. **ステージ別のスマートなコンテキスト読み込み**:
   - **初期ステージ（Workspace Detection, Reverse Engineering）**: ワークスペース分析を読み込む
   - **Requirements/Stories**: リバースエンジニアリング + 要件成果物を読み込む
   - **Design ステージ**: 要件 + ストーリー + アーキテクチャ + 設計成果物を読み込む
   - **Code ステージ**: すべての成果物 + 既存コードファイルを読み込む
5. アーキテクチャ選択と現在フェーズに合わせて選択肢を調整
6. 一般的な説明ではなく具体的な次のステップを表示
7. 継続プロンプトをタイムスタンプ付きで audit.md に記録
8. **コンテキスト要約**: 成果物読み込み後、ユーザー向けに簡潔な読み込み内容を要約
9. **質問の方法**: 確認質問やフィードバック質問は必ず .md ファイルに記載する。多肢選択をチャット内に直接書かない。

## 必須: セッション継続の指示
1. 既存プロジェクトを検出したら **必ず最初に aidlc-state.md を読む**
2. ワークフローファイルから現在の状態を解析してプロンプトに反映
3. **必須: 以前のステージ成果物を読み込む** - どのステージを再開する場合でも、以前の関連成果物を自動で読み込む:
   - **Reverse Engineering**: architecture.md, code-structure.md, api-documentation.md
   - **Requirements Analysis**: requirements.md, requirement-verification-questions.md
   - **User Stories**: stories.md, personas.md, story-generation-plan.md
   - **Application Design**: アプリ設計成果物（components.md, component-methods.md, services.md）
   - **Design (Units)**: unit-of-work.md, unit-of-work-dependency.md, unit-of-work-story-map.md
   - **Per-Unit Design**: functional-design.md, nfr-requirements.md, nfr-design.md, infrastructure-design.md
   - **Code Stages**: すべてのコードファイル、計画、そしてすべての過去成果物
4. **ステージ別のスマートなコンテキスト読み込み**:
   - **初期ステージ（Workspace Detection, Reverse Engineering）**: ワークスペース分析を読み込む
   - **Requirements/Stories**: リバースエンジニアリング + 要件成果物を読み込む
   - **Design ステージ**: 要件 + ストーリー + アーキテクチャ + 設計成果物を読み込む
   - **Code ステージ**: すべての成果物 + 既存コードファイルを読み込む
5. アーキテクチャ選択と現在フェーズに合わせて選択肢を調整
6. 一般的な説明ではなく具体的な次のステップを表示
7. 継続プロンプトをタイムスタンプ付きで audit.md に記録
8. **コンテキスト要約**: 成果物読み込み後、ユーザー向けに簡潔な読み込み内容を要約
9. **質問の方法**: 確認質問やフィードバック質問は必ず .md ファイルに記載する。多肢選択をチャット内に直接書かない。

## Error Handling
If artifacts are missing or corrupted during session resumption, see [error-handling.md](error-handling.md) for guidance on recovery procedures.
## エラーハンドリング
セッション再開時に成果物が欠落または破損している場合は、復旧手順として [error-handling.md](error-handling.md) を参照する。

## エラーハンドリング
セッション再開時に成果物が欠落または破損している場合は、復旧手順として [error-handling.md](error-handling.md) を参照する。
