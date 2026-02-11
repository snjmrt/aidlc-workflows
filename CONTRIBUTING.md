# Contributing Guidelines(コントリビューションガイドライン)

Thank you for your interest in contributing to AI-DLC. Whether it's a bug report, new rule, correction, or documentation improvement, we value feedback and contributions from the community.

AI-DLC への貢献に関心をお寄せいただきありがとうございます。バグ報告、新しいルール、修正、ドキュメント改善など、コミュニティからのフィードバックと貢献を歓迎します。

Please read through this document before submitting any issues or pull requests.

課題やプルリクエストを提出する前に、本ドキュメントをお読みください。

## Tenets(基本理念)

Before contributing, familiarize yourself with our [tenets](README.md#tenets).

貢献前に [基本理念](README.md#tenets) を確認してください。

## Contributing Rules(コントリビューションルール)

AI-DLC rules live in `aidlc-rules/aws-aidlc-rule-details/`. When contributing:

AI-DLC のルールは `aidlc-rules/aws-aidlc-rule-details/` にあります。貢献時の注意事項:

- **Be reproducible**: Changes should be consistently reproducible either via test case or a series of step
- **再現可能であること**: 変更はテストケースまたは一連の手順で一貫して再現できる必要があります。
- **Single source of truth**: Don't duplicate content. If guidance applies to multiple stages, put it in `common/` and reference it.
- **単一の真実のソース**: 内容を重複させないでください。複数ステージに適用されるガイダンスは `common/` に置き、参照してください。
- **Keep it agnostic**: The core methodology shouldn't assume specific IDEs, agents, or models. Tool-specific files are generated from the source.
- **中立性を保つ**: 中核の方法論は特定の IDE、エージェント、モデルを前提にしないでください。ツール固有のファイルはソースから生成されます。

### Rule Structure(ルール構成)

Rules are organized by phase:

ルールはフェーズごとに整理されています:

- `common/` - Shared guidance across all phases
- `common/` - 全フェーズ共通のガイダンス
- `inception/` - Planning and architecture rules
- `inception/` - 計画とアーキテクチャのルール
- `construction/` - Design and implementation rules
- `construction/` - 設計と実装のルール
- `operations/` - Deployment and monitoring rules
- `operations/` - デプロイと監視のルール

### Testing Changes(変更のテスト)

Test your rule changes with at least one supported platform (Amazon Q Developer, Kiro, or other tools) before submitting. Describe what you tested in your PR.

変更したルールは、少なくとも 1 つの対応プラットフォーム（Amazon Q Developer, Kiro など）でテストしてから提出してください。PR にはテスト内容を記載してください。

## Reporting Bugs/Feature Requests(バグ報告/機能要望)

Use GitHub issues to report bugs or suggest features. Before filing, check existing issues to avoid duplicates.

バグ報告や機能提案は GitHub Issues を使用してください。提出前に既存の Issue を確認し、重複を避けてください。

含める内容:

- Which rule or stage is affected
- 影響を受けるルールまたはステージ
- Expected vs actual behavior
- 期待される動作と実際の動作
- The platform/model you tested with
- テストしたプラットフォーム/モデル

## Contributing via Pull Requests(プルリクエストによる貢献)

Before sending a pull request:

プルリクエストを送る前に:

1. Work against the latest `main` branch
2. 最新の `main` ブランチで作業する
3. Check existing open and recently merged PRs
4. 既存のオープン/最近マージされた PR を確認する
5. Open an issue first for significant changes
6. 大きな変更は先に Issue を立てる

提出手順:

1. Fork the repository
2. リポジトリをフォーク
3. Make your changes (keep them focused)
4. 変更を加える（焦点を絞る）
5. Use clear commit messages following [conventional commits](https://www.conventionalcommits.org/) (e.g., `feat:`, `fix:`, `docs:`)
6. [conventional commits](https://www.conventionalcommits.org/) に従った明確なコミットメッセージを使用（例: `feat:`, `fix:`, `docs:`）
7. Submit the PR and respond to feedback
8. PR を提出し、フィードバックに対応

## Code of Conduct

## 行動規範

## 行動規範

This project has adopted the [Amazon Open Source Code of Conduct](https://aws.github.io/code-of-conduct).
このプロジェクトは [Amazon Open Source Code of Conduct](https://aws.github.io/code-of-conduct) を採用しています。

For more information see the [Code of Conduct FAQ](https://aws.github.io/code-of-conduct-faq) or contact opensource-codeofconduct@amazon.com with any additional questions or comments.

詳細は [Code of Conduct FAQ](https://aws.github.io/code-of-conduct-faq) を参照するか、追加の質問やコメントは opensource-codeofconduct@amazon.com までご連絡ください。

## Security Issue Notifications(セキュリティ問題の通知)

If you discover a potential security issue, notify AWS/Amazon Security via the [vulnerability reporting page](http://aws.amazon.com/security/vulnerability-reporting/). Please do not create a public GitHub issue.

潜在的なセキュリティ問題を発見した場合は、[脆弱性報告ページ](http://aws.amazon.com/security/vulnerability-reporting/) から AWS/Amazon Security に通知してください。公開の GitHub Issue は作成しないでください。

## Licensing(ライセンス)

See the [LICENSE](LICENSE) file for our project's licensing. We will ask you to confirm the licensing of your contribution.

プロジェクトのライセンスは [LICENSE](LICENSE) を参照してください。貢献内容のライセンス確認をお願いする場合があります。
