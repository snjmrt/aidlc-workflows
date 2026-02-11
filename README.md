# AI-DLC (AI-Driven Development Life Cycle)

AI-DLC is an intelligent software development workflow that adapts to your needs, maintains quality standards, and keeps you in control of the process. For learning more about AI-DLC Methodology, read this [blog](https://aws.amazon.com/blogs/devops/ai-driven-development-life-cycle/) and the [Method Definition Paper](https://prod.d13rzhkk8cj2z0.amplifyapp.com/) referred in it.

AI-DLC は、ニーズに合わせて適応し、品質基準を維持し、プロセスの主導権をあなたに保つインテリジェントなソフトウェア開発ワークフローです。AI-DLC の方法論について詳しくは、こちらの[ブログ](https://aws.amazon.com/blogs/devops/ai-driven-development-life-cycle/)と、そこで参照されている[Method Definition Paper](https://prod.d13rzhkk8cj2z0.amplifyapp.com/)を参照してください。

## Quick Start(クイックスタート)

1. Download the latest release zip from the [Releases page](../../releases/latest) to a folder **outside** your project directory (e.g., `~/Downloads`).
2. [Releases ページ](../../releases/latest) から最新リリースの zip を、プロジェクトディレクトリの**外**にあるフォルダ（例: `~/Downloads`）へダウンロードします。
3. Extract the zip. It contains an `aidlc-rules/` folder with two subdirectories:
4. zip を展開します。中には `aidlc-rules/` フォルダがあり、次の 2 つのサブディレクトリが含まれます:
   - `aws-aidlc-rules/` — the core AI-DLC workflow rules
   - `aws-aidlc-rules/` — AI-DLC の中核ワークフロールール
   - `aws-aidlc-rule-details/` — supporting documents referenced by the rules
   - `aws-aidlc-rule-details/` — ルールから参照される補助ドキュメント
5. Copy both folders into your project, following the setup for your platform below.
6. 以下のプラットフォーム別手順に従い、両方のフォルダをプロジェクトへコピーします。

> **Note**: The extracted folder may contain a top-level directory (e.g., `aidlc-workflows-0.1.0/`). Navigate into it first so that `aidlc-rules/` is directly accessible.

> **Note**: 展開したフォルダにトップレベルのディレクトリ（例: `aidlc-workflows-0.1.0/`）が含まれる場合があります。その中に移動し、`aidlc-rules/` に直接アクセスできる状態にしてください。

## Kiro

AI-DLC uses [Kiro Steering Files](https://kiro.dev/docs/cli/steering/) within your project workspace. Copy the rules into your project's `.kiro` folder:

AI-DLC は、プロジェクトワークスペース内で [Kiro Steering Files](https://kiro.dev/docs/cli/steering/) を使用します。ルールをプロジェクトの `.kiro` フォルダへコピーしてください:

1. Create the directories `.kiro/steering` and `.kiro/aws-aidlc-rule-details` in your project root.
2. プロジェクトルートに `.kiro/steering` と `.kiro/aws-aidlc-rule-details` を作成します。
3. Copy `aws-aidlc-rules/` into `.kiro/steering/`.
4. `aws-aidlc-rules/` を `.kiro/steering/` にコピーします。
5. Copy `aws-aidlc-rule-details/` into `.kiro/`.
6. `aws-aidlc-rule-details/` を `.kiro/` にコピーします。

The commands below assume you extracted the zip to your `Downloads` folder. If you used a different location, replace `Downloads` with your actual folder path.

以下のコマンドは zip を `Downloads` フォルダに展開した前提です。別の場所に展開した場合は、`Downloads` を実際のパスに置き換えてください。

macOS/Linux の場合:

```bash
mkdir -p .kiro/steering
cp -R ~/Downloads/aidlc-rules/aws-aidlc-rules .kiro/steering/
cp -R ~/Downloads/aidlc-rules/aws-aidlc-rule-details .kiro/
```

Windows (CMD) の場合:

```cmd
mkdir .kiro\steering
xcopy %USERPROFILE%\Downloads\aidlc-rules\aws-aidlc-rules .kiro\steering\aws-aidlc-rules\ /E /I
xcopy %USERPROFILE%\Downloads\aidlc-rules\aws-aidlc-rule-details .kiro\aws-aidlc-rule-details\ /E /I
```

Your project should look like:

プロジェクトは次のような構成になります:

```
<project-root>/
    ├── .kiro/
    │     ├── steering/
    │     │      ├── aws-aidlc-rules/
    │     ├── aws-aidlc-rule-details/
```

To verify the rules are loaded:

ルールが読み込まれていることを確認するには:

### Kiro IDE

Open the steering files panel and confirm you see an entry for `core-workflow` under `Workspace` as shown in the screenshot below.

ステアリングファイルのパネルを開き、以下のスクリーンショットのように `Workspace` 配下に `core-workflow` が表示されていることを確認してください。

<img src="./assets/images/kiro-ide-aidlc-rules-loaded.png?raw=true" alt="AI-DLC Rules in Kiro IDE" width="700" height="450">

We use Kiro IDE in Vibe mode to run the AI-DLC workflow. This ensures that AI-DLC workflow guides the development workflow in Kiro. At times, Kiro may nudge you to switch to spec mode. Select `No` to such prompts to stay in Vibe mode.

AI-DLC ワークフローは Kiro IDE の Vibe モードで実行します。これにより AI-DLC が Kiro の開発ワークフローをガイドします。場合によっては Kiro が spec モードへの切り替えを促すことがありますが、その際は `No` を選択して Vibe モードを維持してください。

<img src="./assets/images/kiro-sdd-nudge.png" alt="Staying in Kiro Vibe mode" width="500" height="175">

### Kiro CLI

Run `kiro-cli`, then `/context show`, and confirm entries for `.kiro/steering/aws-aidlc-rules`.

`kiro-cli` を起動し、`/context show` を実行して `.kiro/steering/aws-aidlc-rules` のエントリが表示されることを確認してください。

<img src="./assets/images/kiro-cli-aidlc-rules-loaded.png?raw=true" alt="AI-DLC Rules in Kiro CLI" width="700" height="660">

## Amazon Q Developer IDE Plugin/Extension(Amazon Q Developer IDE プラグイン/拡張)

AI-DLC uses [Amazon Q Rules](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/context-project-rules.html) within your project workspace. Copy the rules into your project's `.amazonq` folder:

AI-DLC は、プロジェクトワークスペース内で [Amazon Q Rules](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/context-project-rules.html) を使用します。ルールをプロジェクトの `.amazonq` フォルダへコピーしてください:

1. Create the directories `.amazonq/rules` and `.amazonq/aws-aidlc-rule-details` in your project root.
2. プロジェクトルートに `.amazonq/rules` と `.amazonq/aws-aidlc-rule-details` を作成します。
3. Copy `aws-aidlc-rules/` into `.amazonq/rules/`.
4. `aws-aidlc-rules/` を `.amazonq/rules/` にコピーします。
5. Copy `aws-aidlc-rule-details/` into `.amazonq/`.
6. `aws-aidlc-rule-details/` を `.amazonq/` にコピーします。

The commands below assume you extracted the zip to your `Downloads` folder. If you used a different location, replace `Downloads` with your actual folder path.

以下のコマンドは zip を `Downloads` フォルダに展開した前提です。別の場所に展開した場合は、`Downloads` を実際のパスに置き換えてください。

macOS/Linux の場合:

```bash
mkdir -p .amazonq/rules
cp -R ~/Downloads/aidlc-rules/aws-aidlc-rules .amazonq/rules/
cp -R ~/Downloads/aidlc-rules/aws-aidlc-rule-details .amazonq/
```

Windows（CMD）の場合:

```cmd
mkdir .amazonq\rules
xcopy %USERPROFILE%\Downloads\aidlc-rules\aws-aidlc-rules .amazonq\rules\aws-aidlc-rules\ /E /I
xcopy %USERPROFILE%\Downloads\aidlc-rules\aws-aidlc-rule-details .amazonq\aws-aidlc-rule-details\ /E /I
```

Your project should look like:

プロジェクトは次のような構成になります:

```
<project-root>/
    ├── .amazonq/
    │     ├── rules/
    │     │     ├── aws-aidlc-rules/
    │     ├── aws-aidlc-rule-details/
```

To verify the rules are loaded:

ルールが読み込まれていることを確認するには:

1. In the Amazon Q Chat window, click the `Rules` button in the lower right corner.
2. Amazon Q のチャットウィンドウ右下にある `Rules` ボタンをクリックします。
3. Confirm you see entries for `.amazonq/rules/aws-aidlc-rules`.
4. `.amazonq/rules/aws-aidlc-rules` のエントリが表示されることを確認します。

<img src="./assets/images/q-ide-aidlc-rules-loaded.png?raw=true" alt="AI-DLC Rules in Q Developer IDE plugin" width="700" height="400">

### Other Agents(他のエージェント)

AI-DLC works with any coding agent that supports project-level rules or steering files. The general approach:

AI-DLC は、プロジェクトレベルのルールやステアリングファイルに対応している任意のコーディングエージェントで動作します。一般的な手順は次のとおりです:

1. Place `aws-aidlc-rules/` wherever your agent reads project rules from (consult your agent's documentation).
2. `aws-aidlc-rules/` を、エージェントがプロジェクトルールを読み込む場所へ配置します（詳細はエージェントのドキュメントを参照）。
3. Place `aws-aidlc-rule-details/` at a sibling level so the rules can reference it.
4. `aws-aidlc-rule-details/` はルールが参照できるように同じ階層に配置します。

If your agent has no convention for rules files, place both folders at your project root and point the agent to `aws-aidlc-rules/` as its rules directory.

ルールファイルの配置規約がないエージェントの場合は、両フォルダをプロジェクトルートに配置し、`aws-aidlc-rules/` をルールディレクトリとして指定してください。

### Usage(使い方)

1. Start any software development project by stating your intent starting with the phrase "Using AI-DLC, ..." in the chat.
2. チャットで「Using AI-DLC, ...」というフレーズで意図を述べて、任意のソフトウェア開発プロジェクトを開始します。
3. AI-DLC workflow automatically activates and guides you from there.
4. AI-DLC ワークフローが自動的に有効化され、以降の手順をガイドします。
5. Answer structured questions that AI-DLC asks you
6. AI-DLC が提示する構造化された質問に回答します。
7. Carefully review every plan that AI generates. Provide your oversight and validation.
8. AI が生成する計画は必ず確認し、監督と検証を行ってください。
9. Review the execution plan to see which stages will run
10. 実行計画を確認し、どのステージが実行されるかを把握します。
11. Carefully review the artifacts and approve each stage to maintain control
12. 成果物を慎重にレビューし、各ステージを承認して主導権を維持します。
13. All the artifacts will be generated in the `aidlc-docs/` directory
14. すべての成果物は `aidlc-docs/` ディレクトリに生成されます。

## Three-Phase Adaptive Workflow(3 フェーズの適応型ワークフロー)

AI-DLC follows a structured three-phase approach that adapts to your project's complexity:

AI-DLC はプロジェクトの複雑さに応じて適応する、構造化された 3 フェーズのアプローチに従います:

- **🔵 INCEPTION PHASE**: Determines **WHAT** to build and **WHY**
- **🔵 開始フェーズ**: **何を**、そして **なぜ** 作るかを決定
  - Requirements analysis and validation
  - 要件分析と検証
  - User story creation (when applicable)
  - ユーザーストーリー作成（該当する場合）
  - Application Design and creating units of work for parallel development
  - アプリケーション設計と並列開発のための作業単位作成
  - Risk assessment and complexity evaluation
  - リスク評価と複雑性評価

- **🟢 CONSTRUCTION PHASE**: Determines **HOW** to build it
- **🟢 構築フェーズ**: **どのように** 作るかを決定
  - Detailed component design
  - 詳細なコンポーネント設計
  - Code generation and implementation
  - コード生成と実装
  - Build configuration and testing strategies
  - ビルド設定とテスト戦略
  - Quality assurance and validation
  - 品質保証と検証

- **🟡 OPERATIONS PHASE**: Deployment and monitoring (future)
- **🟡 運用フェーズ**: デプロイと監視（将来）
  - Deployment automation and infrastructure
  - デプロイ自動化とインフラ
  - Monitoring and observability setup
  - 監視と可観測性のセットアップ
  - Production readiness validation
  - 本番準備の検証

## Key Features(主な特徴)

- **Adaptive Intelligence**: Only executes stages that add value to your specific request
- **適応型インテリジェンス**: 特定の要求に価値を与えるステージのみを実行
- **Context-Aware**: Analyzes existing codebase and complexity requirements
- **コンテキスト認識**: 既存コードベースと複雑性要件を分析
- **リスクベース**: 複雑な変更は包括的に扱い、単純な変更は効率的に
- **Risk-Based**: Complex changes get comprehensive treatment, simple changes stay efficient
- **Question-Driven**: Structured multiple-choice questions in files, not chat
- **質問駆動**: チャットではなくファイル内の構造化された選択式質問
- **Always in Control**: Review execution plans and approve each phase
- **常に主導権は人に**: 実行計画をレビューし、各フェーズを承認

## Prerequisites(前提条件)

Have one of our supported platforms/tools for Assisted AI Coding installed:

支援型 AI コーディングのために、以下の対応プラットフォーム/ツールのいずれかをインストールしてください:

### Kiro

- [Kiro IDE](https://kiro.dev/)
- [Kiro CLI](https://kiro.dev/cli/)
- [Amazon Q Developer IDE plugin](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/q-in-IDE.html)

## Tenets(基本理念)

These are our core principles to guide our decision making.

意思決定を導く中核原則です。

- **No duplication**. The source of truth lives in one place. If we add support for new tools or formats that require specific files, we generate them from the source rather than maintaining separate copies.
- **重複なし**。真のソースは一箇所に置く。新しいツールや形式に対応するために特定ファイルが必要になった場合でも、ソースから生成し、別コピーを維持しない。
- **Methodology first**. AI-DLC is fundamentally a methodology, not a tool. Users shouldn't need to install anything to get started. That said, we're open to convenience tooling (scripts, CLIs) down the road if it helps users adopt or extend the methodology.
- **方法論優先**。AI-DLC は本質的に方法論であり、ツールではない。ユーザーは開始にインストールを必要としないべき。ただし、採用や拡張に役立つなら、利便性のためのツール（スクリプト、CLI）を将来的に検討する。
- **Reproducible**. Rules should be clear enough that different models produce similar outcomes. We know models behave differently, but the methodology should minimize variance through explicit guidance.
- **再現可能**。異なるモデルでも類似の成果が出るように、ルールは十分に明確であるべき。モデルの差異は認識した上で、明示的なガイダンスによりばらつきを最小化する。
- **Agnostic**. The methodology works with any IDE, agent, or model. We don't tie ourselves to specific tools or vendors.
- **中立性**。方法論はどの IDE、エージェント、モデルでも機能する。特定ツールやベンダーに依存しない。
- **Human in the loop**. Critical decisions require explicit user confirmation. The agent proposes, the human approves.
- **人間が最終判断**。重要な意思決定は明示的なユーザー承認を要する。エージェントが提案し、人間が承認する。

## Security(セキュリティ)

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

詳細は [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) を参照してください。

## License(ライセンス)

This library is licensed under the MIT-0 License. See the LICENSE file.

本ライブラリは MIT-0 License の下で提供されています。詳細は LICENSE を参照してください。
