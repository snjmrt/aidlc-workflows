# Error Handling and Recovery Procedures
# エラーハンドリングと復旧手順

# エラーハンドリングと復旧手順

## General Error Handling Principles
## 一般的なエラーハンドリング原則

## 一般的なエラーハンドリング原則

### When Errors Occur
1. **Identify the error**: Clearly state what went wrong
2. **Assess impact**: Determine if the error is blocking or can be worked around
3. **Communicate**: Inform the user about the error and options
4. **Offer solutions**: Provide clear steps to resolve or work around the error
5. **Document**: Log the error and resolution in `audit.md`
### エラー発生時
1. **エラーを特定**: 何が起きたかを明確にする
2. **影響評価**: ブロッキングか回避可能かを判断
3. **通知**: エラーと選択肢をユーザーに伝える
4. **解決策提示**: 解決/回避の具体的手順を示す
5. **記録**: エラーと解決内容を `audit.md` に記録

### エラー発生時
1. **エラーを特定**: 何が起きたかを明確にする
2. **影響評価**: ブロッキングか回避可能かを判断
3. **通知**: エラーと選択肢をユーザーに伝える
4. **解決策提示**: 解決/回避の具体的手順を示す
5. **記録**: エラーと解決内容を `audit.md` に記録

### Error Severity Levels
### エラーの重大度

### エラーの重大度

**Critical**: Workflow cannot continue
- Missing required files or artifacts
- Invalid user input that cannot be processed
- System errors preventing file operations
**Critical**: ワークフローが継続できない
- 必須ファイル/成果物の欠落
- 処理不能な無効入力
- ファイル操作を妨げるシステムエラー

**Critical**: ワークフローが継続できない
- 必須ファイル/成果物の欠落
- 処理不能な無効入力
- ファイル操作を妨げるシステムエラー

**High**: Phase cannot complete as planned
- Incomplete answers to required questions
- Contradictory user responses
- Missing dependencies from prior phases
**High**: フェーズが計画通り完了できない
- 必須質問への回答不足
- 矛盾するユーザー回答
- 事前フェーズの依存関係の欠落

**High**: フェーズが計画通り完了できない
- 必須質問への回答不足
- 矛盾するユーザー回答
- 事前フェーズの依存関係の欠落

**Medium**: Phase can continue with workarounds
- Optional artifacts missing
- Non-critical validation failures
- Partial completion possible
**Medium**: 回避策で継続可能
- 任意成果物の欠落
- 重大でない検証失敗
- 部分的な完了が可能

**Medium**: 回避策で継続可能
- 任意成果物の欠落
- 重大でない検証失敗
- 部分的な完了が可能

**Low**: Minor issues that don't block progress
- Formatting inconsistencies
- Optional information missing
- Non-blocking warnings
**Low**: 進行を妨げない軽微な問題
- 書式の不整合
- 任意情報の欠落
- 非ブロッキングの警告

**Low**: 進行を妨げない軽微な問題
- 書式の不整合
- 任意情報の欠落
- 非ブロッキングの警告

## Phase-Specific Error Handling
## フェーズ別のエラーハンドリング

## フェーズ別のエラーハンドリング

### Context Assessment Errors
### コンテキスト評価エラー

### コンテキスト評価エラー

**Error**: Cannot read workspace files
- **Cause**: Permission issues, missing directories
- **Solution**: Ask user to verify workspace path and permissions
- **Workaround**: Proceed with user-provided information only
**エラー**: ワークスペースファイルを読み取れない
- **原因**: 権限問題、ディレクトリ欠如
- **解決**: ワークスペースのパスと権限の確認を依頼
- **回避**: ユーザー提供の情報のみで進める

**エラー**: ワークスペースファイルを読み取れない
- **原因**: 権限問題、ディレクトリ欠如
- **解決**: ワークスペースのパスと権限の確認を依頼
- **回避**: ユーザー提供の情報のみで進める

**Error**: Existing `aidlc-state.md` is corrupted
- **Cause**: Manual editing, incomplete previous run
- **Solution**: Ask user if they want to start fresh or attempt recovery
- **Recovery**: Create backup, start new state file
**エラー**: 既存の `aidlc-state.md` が破損
- **原因**: 手動編集、前回の不完全な実行
- **解決**: 新規開始か復旧を試すか確認
- **復旧**: バックアップを作成し、新しい状態ファイルを開始

**エラー**: 既存の `aidlc-state.md` が破損
- **原因**: 手動編集、前回の不完全な実行
- **解決**: 新規開始か復旧を試すか確認
- **復旧**: バックアップを作成し、新しい状態ファイルを開始

**Error**: Cannot determine required phases
- **Cause**: Insufficient information from user
- **Solution**: Ask clarifying questions about intent and scope
- **Workaround**: Default to comprehensive execution plan
**エラー**: 必要フェーズを判断できない
- **原因**: ユーザーからの情報不足
- **解決**: 意図とスコープについて確認質問
- **回避**: 包括的な実行計画をデフォルトにする

**エラー**: 必要フェーズを判断できない
- **原因**: ユーザーからの情報不足
- **解決**: 意図とスコープについて確認質問
- **回避**: 包括的な実行計画をデフォルトにする

### Requirements Assessment Errors
### 要件評価エラー

### 要件評価エラー

**Error**: User provides contradictory requirements
- **Cause**: Unclear understanding, changing needs
- **Solution**: Create follow-up questions to resolve contradictions
- **Do Not Proceed**: Until contradictions are resolved
**エラー**: 矛盾する要件
- **原因**: 理解不足、要件の変化
- **解決**: 矛盾を解消するフォロー質問を作成
- **進行不可**: 矛盾が解消されるまで進めない

**エラー**: 矛盾する要件
- **原因**: 理解不足、要件の変化
- **解決**: 矛盾を解消するフォロー質問を作成
- **進行不可**: 矛盾が解消されるまで進めない

**Error**: Requirements document cannot be converted
- **Cause**: Unsupported format, corrupted file
- **Solution**: Ask user to provide requirements in supported format
- **Workaround**: Work with user's verbal description
**エラー**: 要件ドキュメントを変換できない
- **原因**: 非対応形式、ファイル破損
- **解決**: 対応形式での提出を依頼
- **回避**: ユーザーの口頭説明で対応

**エラー**: 要件ドキュメントを変換できない
- **原因**: 非対応形式、ファイル破損
- **解決**: 対応形式での提出を依頼
- **回避**: ユーザーの口頭説明で対応

**Error**: Incomplete answers to verification questions
- **Cause**: User skipped questions, unclear what to answer
- **Solution**: Highlight unanswered questions, provide examples
- **Do Not Proceed**: Until all required questions are answered
**エラー**: 検証質問の回答不足
- **原因**: 質問のスキップ、回答方法の不明瞭さ
- **解決**: 未回答の質問を提示し、例を示す
- **進行不可**: 必須質問がすべて回答されるまで進めない

**エラー**: 検証質問の回答不足
- **原因**: 質問のスキップ、回答方法の不明瞭さ
- **解決**: 未回答の質問を提示し、例を示す
- **進行不可**: 必須質問がすべて回答されるまで進めない

### Story Development Errors
### ストーリー作成エラー

### ストーリー作成エラー

**Error**: Cannot map requirements to stories
- **Cause**: Requirements too vague, missing functional details
- **Solution**: Return to Requirements Assessment for clarification
- **Workaround**: Create stories based on available information, mark as incomplete
**エラー**: 要件をストーリーにマッピングできない
- **原因**: 要件が曖昧、機能詳細の欠如
- **解決**: 要件評価に戻って明確化
- **回避**: 利用可能情報でストーリーを作成し、不足を明記

**エラー**: 要件をストーリーにマッピングできない
- **原因**: 要件が曖昧、機能詳細の欠如
- **解決**: 要件評価に戻って明確化
- **回避**: 利用可能情報でストーリーを作成し、不足を明記

**Error**: User provides ambiguous story planning answers
- **Cause**: Unclear options, complex decision
- **Solution**: Add follow-up questions with specific examples
- **Do Not Proceed**: Until ambiguities are resolved
**エラー**: ストーリー計画の回答があいまい
- **原因**: 選択肢の不明瞭さ、意思決定の複雑さ
- **解決**: 具体例付きのフォロー質問を追加
- **進行不可**: あいまいさが解消されるまで進めない

**エラー**: ストーリー計画の回答があいまい
- **原因**: 選択肢の不明瞭さ、意思決定の複雑さ
- **解決**: 具体例付きのフォロー質問を追加
- **進行不可**: あいまいさが解消されるまで進めない

**Error**: Story generation plan has uncompleted steps
- **Cause**: Execution interrupted, steps skipped
- **Solution**: Resume from first uncompleted step
- **Recovery**: Review completed steps, continue from checkpoint
**エラー**: ストーリー生成計画のステップが未完了
- **原因**: 実行中断、ステップの欠落
- **解決**: 最初の未完了ステップから再開
- **復旧**: 完了済みステップを確認し、チェックポイントから続行

**エラー**: ストーリー生成計画のステップが未完了
- **原因**: 実行中断、ステップの欠落
- **解決**: 最初の未完了ステップから再開
- **復旧**: 完了済みステップを確認し、チェックポイントから続行

### Application Design Errors
### アプリケーション設計エラー

### アプリケーション設計エラー

**Error**: Architectural decision is unclear or contradictory
- **Cause**: Ambiguous answers, conflicting requirements
- **Solution**: Add follow-up questions to clarify decision
- **Do Not Proceed**: Until decision is clear and documented
**エラー**: アーキテクチャ判断が不明確/矛盾
- **原因**: あいまいな回答、相反する要件
- **解決**: 追加質問で判断を明確化
- **進行不可**: 判断が明確かつ文書化されるまで進めない

**エラー**: アーキテクチャ判断が不明確/矛盾
- **原因**: あいまいな回答、相反する要件
- **解決**: 追加質問で判断を明確化
- **進行不可**: 判断が明確かつ文書化されるまで進めない

**Error**: Cannot determine number of services/units
- **Cause**: Insufficient information about boundaries
- **Solution**: Ask specific questions about deployment, team structure, scaling
- **Workaround**: Default to monolith, allow change later
**エラー**: サービス/ユニット数を判断できない
- **原因**: 境界情報の不足
- **解決**: デプロイ、チーム構成、スケーリングについて質問
- **回避**: モノリスをデフォルトにし、後で変更可能にする

**エラー**: サービス/ユニット数を判断できない
- **原因**: 境界情報の不足
- **解決**: デプロイ、チーム構成、スケーリングについて質問
- **回避**: モノリスをデフォルトにし、後で変更可能にする

### Design Errors
### 設計エラー

### 設計エラー

**Error**: Unit dependencies are circular
- **Cause**: Poor boundary definition, tight coupling
- **Solution**: Identify circular dependencies, suggest refactoring
- **Recovery**: Revise unit boundaries to break cycles
**エラー**: ユニット依存が循環
- **原因**: 境界定義の不備、強結合
- **解決**: 循環依存を特定し、リファクタを提案
- **復旧**: ユニット境界を見直して循環を解消

**エラー**: ユニット依存が循環
- **原因**: 境界定義の不備、強結合
- **解決**: 循環依存を特定し、リファクタを提案
- **復旧**: ユニット境界を見直して循環を解消

**Error**: Unit design plan has missing steps
- **Cause**: Plan generation incomplete, template error
- **Solution**: Regenerate plan with all required steps
- **Recovery**: Add missing steps to existing plan
**エラー**: ユニット設計計画に欠落ステップ
- **原因**: 計画生成の不完全、テンプレートエラー
- **解決**: 必須ステップを含めて計画を再生成
- **復旧**: 既存計画に不足ステップを追加

**エラー**: ユニット設計計画に欠落ステップ
- **原因**: 計画生成の不完全、テンプレートエラー
- **解決**: 必須ステップを含めて計画を再生成
- **復旧**: 既存計画に不足ステップを追加

**Error**: Cannot generate design artifacts
- **Cause**: Missing unit information, unclear requirements
- **Solution**: Return to Units Planning to clarify unit definition
- **Workaround**: Generate partial design, mark gaps
**エラー**: 設計成果物を生成できない
- **原因**: ユニット情報不足、要件不明確
- **解決**: Units Planning に戻ってユニット定義を明確化
- **回避**: 部分的な設計を生成し、欠落を明記

**エラー**: 設計成果物を生成できない
- **原因**: ユニット情報不足、要件不明確
- **解決**: Units Planning に戻ってユニット定義を明確化
- **回避**: 部分的な設計を生成し、欠落を明記

### NFR Implementation Errors
### NFR 実装エラー

### NFR 実装エラー

**Error**: Technology stack choices are incompatible
- **Cause**: Conflicting requirements, platform limitations
- **Solution**: Highlight incompatibilities, ask user to choose
- **Do Not Proceed**: Until compatible choices are made
**エラー**: 技術スタック選定が非互換
- **原因**: 要件の衝突、プラットフォーム制約
- **解決**: 非互換を提示し、ユーザーに選択を依頼
- **進行不可**: 互換な選択が決まるまで進めない

**エラー**: 技術スタック選定が非互換
- **原因**: 要件の衝突、プラットフォーム制約
- **解決**: 非互換を提示し、ユーザーに選択を依頼
- **進行不可**: 互換な選択が決まるまで進めない

**Error**: Organizational constraints cannot be met
- **Cause**: Network restrictions, security policies
- **Solution**: Document constraints, ask user for workarounds
- **Escalation**: May require human intervention for setup
**エラー**: 組織制約を満たせない
- **原因**: ネットワーク制約、セキュリティポリシー
- **解決**: 制約を文書化し、回避策を相談
- **エスカレーション**: セットアップに人手が必要な場合がある

**エラー**: 組織制約を満たせない
- **原因**: ネットワーク制約、セキュリティポリシー
- **解決**: 制約を文書化し、回避策を相談
- **エスカレーション**: セットアップに人手が必要な場合がある

**Error**: NFR implementation step requires human action
- **Cause**: AI cannot perform certain tasks (network config, credentials)
- **Solution**: Clearly mark as **HUMAN TASK**, provide instructions
- **Wait**: For user confirmation before proceeding
**エラー**: NFR 実装ステップが人間の作業を要する
- **原因**: AI では実行できないタスク（ネットワーク設定、認証情報など）
- **解決**: **HUMAN TASK** と明確に表示し、手順を提供
- **待機**: ユーザー確認があるまで進めない

**エラー**: NFR 実装ステップが人間の作業を要する
- **原因**: AI では実行できないタスク（ネットワーク設定、認証情報など）
- **解決**: **HUMAN TASK** と明確に表示し、手順を提供
- **待機**: ユーザー確認があるまで進めない

### Code Planning Errors
### コード計画エラー

### コード計画エラー

**Error**: Code generation plan is incomplete
- **Cause**: Missing design artifacts, unclear requirements
- **Solution**: Return to Design phase to complete artifacts
- **Recovery**: Generate plan with available information, mark gaps
**エラー**: コード生成計画が不完全
- **原因**: 設計成果物の欠落、要件の不明確さ
- **解決**: 設計フェーズに戻って成果物を完成
- **復旧**: 利用可能情報で計画を生成し、欠落を明記

**エラー**: コード生成計画が不完全
- **原因**: 設計成果物の欠落、要件の不明確さ
- **解決**: 設計フェーズに戻って成果物を完成
- **復旧**: 利用可能情報で計画を生成し、欠落を明記

**Error**: Unit dependencies not satisfied
- **Cause**: Dependent units not yet generated
- **Solution**: Reorder generation sequence to respect dependencies
- **Workaround**: Generate with stub dependencies, integrate later
**エラー**: ユニット依存が満たされていない
- **原因**: 依存ユニットが未生成
- **解決**: 依存を考慮した生成順に並べ替え
- **回避**: スタブ依存で生成し、後で統合

**エラー**: ユニット依存が満たされていない
- **原因**: 依存ユニットが未生成
- **解決**: 依存を考慮した生成順に並べ替え
- **回避**: スタブ依存で生成し、後で統合

### Code Generation Errors
### コード生成エラー

### コード生成エラー

**Error**: Cannot generate code for a step
- **Cause**: Insufficient design information, unclear requirements
- **Solution**: Skip step, document as incomplete, continue
- **Recovery**: Return to step after gathering more information
**エラー**: ステップのコードを生成できない
- **原因**: 設計情報不足、要件不明瞭
- **解決**: ステップをスキップし、不完全として記録して続行
- **復旧**: 追加情報を得た後にそのステップへ戻る

**エラー**: ステップのコードを生成できない
- **原因**: 設計情報不足、要件不明瞭
- **解決**: ステップをスキップし、不完全として記録して続行
- **復旧**: 追加情報を得た後にそのステップへ戻る

**Error**: Generated code has syntax errors
- **Cause**: Template issues, language-specific problems
- **Solution**: Fix syntax errors, regenerate if needed
- **Validation**: Verify code compiles before proceeding
**エラー**: 生成コードに構文エラー
- **原因**: テンプレート問題、言語固有の問題
- **解決**: 構文エラーを修正し、必要なら再生成
- **検証**: 次に進む前にコンパイルを確認

**エラー**: 生成コードに構文エラー
- **原因**: テンプレート問題、言語固有の問題
- **解決**: 構文エラーを修正し、必要なら再生成
- **検証**: 次に進む前にコンパイルを確認

**Error**: Test generation fails
- **Cause**: Complex logic, missing test framework setup
- **Solution**: Generate basic test structure, mark for manual completion
- **Workaround**: Proceed without tests, add in Operations phase
**エラー**: テスト生成に失敗
- **原因**: 複雑なロジック、テスト基盤未整備
- **解決**: 基本的なテスト構造を生成し、手作業での補完を明記
- **回避**: テストなしで進め、Operations フェーズで追加

**エラー**: テスト生成に失敗
- **原因**: 複雑なロジック、テスト基盤未整備
- **解決**: 基本的なテスト構造を生成し、手作業での補完を明記
- **回避**: テストなしで進め、Operations フェーズで追加

### Operations Errors
### 運用（Operations）エラー

### 運用（Operations）エラー

**Error**: Cannot determine build tool
- **Cause**: Unusual project structure, multiple build systems
- **Solution**: Ask user to specify build tool and commands
- **Workaround**: Provide generic instructions, user adapts
**エラー**: ビルドツールを特定できない
- **原因**: 特殊な構造、複数のビルドシステム
- **解決**: ユーザーにビルドツールとコマンドを指定してもらう
- **回避**: 一般的な手順を提示し、ユーザーに適用してもらう

**エラー**: ビルドツールを特定できない
- **原因**: 特殊な構造、複数のビルドシステム
- **解決**: ユーザーにビルドツールとコマンドを指定してもらう
- **回避**: 一般的な手順を提示し、ユーザーに適用してもらう

**Error**: Deployment target is unclear
- **Cause**: Multiple environments, complex infrastructure
- **Solution**: Ask user to specify deployment targets and methods
- **Workaround**: Provide instructions for common platforms
**エラー**: デプロイ先が不明確
- **原因**: 複数環境、複雑なインフラ
- **解決**: デプロイ先と手法を明確にしてもらう
- **回避**: 代表的なプラットフォームの手順を提示

**エラー**: デプロイ先が不明確
- **原因**: 複数環境、複雑なインフラ
- **解決**: デプロイ先と手法を明確にしてもらう
- **回避**: 代表的なプラットフォームの手順を提示

## Recovery Procedures
## 復旧手順

## 復旧手順

### Partial Phase Completion
### フェーズの部分完了

### フェーズの部分完了

**Scenario**: Phase was interrupted mid-execution
**シナリオ**: フェーズが途中で中断

**シナリオ**: フェーズが途中で中断

**Recovery Steps**:
1. Load the phase plan file
2. Identify last completed step (last [x] checkbox)
3. Resume from next uncompleted step
4. Verify all prior steps are actually complete
5. Continue execution normally
**復旧手順**:
1. フェーズ計画ファイルを読み込む
2. 最後に完了したステップ（最後の [x]）を特定
3. 次の未完了ステップから再開
4. 以前のステップが実際に完了していることを確認
5. 通常どおり実行を継続

**復旧手順**:
1. フェーズ計画ファイルを読み込む
2. 最後に完了したステップ（最後の [x]）を特定
3. 次の未完了ステップから再開
4. 以前のステップが実際に完了していることを確認
5. 通常どおり実行を継続

### Corrupted State File
### 状態ファイルの破損

### 状態ファイルの破損

**Scenario**: `aidlc-state.md` is corrupted or inconsistent
**シナリオ**: `aidlc-state.md` が破損または不整合

**シナリオ**: `aidlc-state.md` が破損または不整合

**Recovery Steps**:
1. Create backup: `aidlc-state.md.backup`
2. Ask user which phase they're actually on
3. Regenerate state file from scratch
4. Mark completed phases based on existing artifacts
5. Resume from current phase
**復旧手順**:
1. バックアップ作成: `aidlc-state.md.backup`
2. ユーザーに現在のフェーズを確認
3. 状態ファイルを最初から再生成
4. 既存成果物に基づき完了済みフェーズを反映
5. 現在フェーズから再開

**復旧手順**:
1. バックアップ作成: `aidlc-state.md.backup`
2. ユーザーに現在のフェーズを確認
3. 状態ファイルを最初から再生成
4. 既存成果物に基づき完了済みフェーズを反映
5. 現在フェーズから再開

### Missing Artifacts
### 成果物の欠落

### 成果物の欠落

**Scenario**: Required artifacts from prior phase are missing
**シナリオ**: 前フェーズの必須成果物が欠落

**シナリオ**: 前フェーズの必須成果物が欠落

**Recovery Steps**:
1. Identify which artifacts are missing
2. Determine if they can be regenerated
3. If yes: Return to that phase, regenerate artifacts
4. If no: Ask user to provide information manually
5. Document the gap in `audit.md`
**復旧手順**:
1. 欠落している成果物を特定
2. 再生成可能か判断
3. 可能なら: 該当フェーズに戻り再生成
4. 不可能なら: ユーザーから手動で情報提供を依頼
5. `audit.md` にギャップを記録

**復旧手順**:
1. 欠落している成果物を特定
2. 再生成可能か判断
3. 可能なら: 該当フェーズに戻り再生成
4. 不可能なら: ユーザーから手動で情報提供を依頼
5. `audit.md` にギャップを記録

### User Wants to Restart Phase
### ユーザーがフェーズをやり直したい

### ユーザーがフェーズをやり直したい

**Scenario**: User is unhappy with phase results and wants to redo
**シナリオ**: 結果に不満がありやり直しを希望

**シナリオ**: 結果に不満がありやり直しを希望

**Recovery Steps**:
1. Confirm user wants to restart (data will be lost)
2. Archive existing artifacts: `{artifact}.backup`
3. Reset phase status in `aidlc-state.md`
4. Clear phase checkboxes in plan files
5. Re-execute phase from beginning
**復旧手順**:
1. やり直し意思を確認（データが失われる旨を伝える）
2. 既存成果物をアーカイブ: `{artifact}.backup`
3. `aidlc-state.md` のフェーズ状態をリセット
4. 計画ファイルのチェックボックスをクリア
5. フェーズを最初から再実行

**復旧手順**:
1. やり直し意思を確認（データが失われる旨を伝える）
2. 既存成果物をアーカイブ: `{artifact}.backup`
3. `aidlc-state.md` のフェーズ状態をリセット
4. 計画ファイルのチェックボックスをクリア
5. フェーズを最初から再実行

### User Wants to Skip Phase
### ユーザーがフェーズをスキップしたい

### ユーザーがフェーズをスキップしたい

**Scenario**: User wants to skip a phase that was planned
**シナリオ**: 計画されていたフェーズをスキップしたい

**シナリオ**: 計画されていたフェーズをスキップしたい

**Recovery Steps**:
1. Confirm user understands implications
2. Document skip reason in `audit.md`
3. Mark phase as "SKIPPED" in `aidlc-state.md`
4. Proceed to next phase
5. Note: May cause issues in later phases if dependencies missing
**復旧手順**:
1. 影響を理解していることを確認
2. スキップ理由を `audit.md` に記録
3. `aidlc-state.md` でフェーズを "SKIPPED" としてマーク
4. 次のフェーズに進む
5. 注記: 依存が欠落すると後続フェーズで問題が起きる可能性あり

**復旧手順**:
1. 影響を理解していることを確認
2. スキップ理由を `audit.md` に記録
3. `aidlc-state.md` でフェーズを "SKIPPED" としてマーク
4. 次のフェーズに進む
5. 注記: 依存が欠落すると後続フェーズで問題が起きる可能性あり

## Escalation Guidelines
## エスカレーション指針

## エスカレーション指針

### When to Ask for User Help
### ユーザー支援を求めるタイミング

### ユーザー支援を求めるタイミング

**Immediately**:
- Contradictory or ambiguous user input
- Missing required information
- Technical constraints AI cannot resolve
- Decisions requiring business judgment
**すぐに**:
- 矛盾またはあいまいな入力
- 必須情報の欠落
- AI が解決できない技術的制約
- ビジネス判断を要する決定

**すぐに**:
- 矛盾またはあいまいな入力
- 必須情報の欠落
- AI が解決できない技術的制約
- ビジネス判断を要する決定

**After Attempting Resolution**:
- Repeated errors in same step
- Complex technical issues
- Unusual project structures
- Integration with external systems
**解決を試みた後**:
- 同一ステップでの繰り返しエラー
- 複雑な技術問題
- 例外的なプロジェクト構造
- 外部システムとの統合

**解決を試みた後**:
- 同一ステップでの繰り返しエラー
- 複雑な技術問題
- 例外的なプロジェクト構造
- 外部システムとの統合

### When to Suggest Starting Over
### やり直しを提案するタイミング

### やり直しを提案するタイミング

**Consider Fresh Start If**:
- Multiple phases have errors
- State file is severely corrupted
- User cannot provide missing information
- Artifacts are inconsistent across phases
**以下の場合は新規開始を検討**:
- 複数フェーズでエラー
- 状態ファイルが深刻に破損
- ユーザーが欠落情報を提供できない
- フェーズ間で成果物が不整合

**以下の場合は新規開始を検討**:
- 複数フェーズでエラー
- 状態ファイルが深刻に破損
- ユーザーが欠落情報を提供できない
- フェーズ間で成果物が不整合

## Session Resumption Errors
## セッション再開時のエラー

## セッション再開時のエラー

### Missing Artifacts During Resumption
### 再開時の成果物欠落

### 再開時の成果物欠落

**Error**: Required artifacts from previous stages are missing
- **Cause**: Files deleted, moved, or never created
- **Solution**: 
  1. Identify which stage created the missing artifacts
  2. Check if stage was marked complete in aidlc-state.md
  3. If marked complete but artifacts missing: Regenerate that stage
  4. If not marked complete: Resume from that stage
- **Recovery**: Return to the stage that creates missing artifacts and re-execute
**エラー**: 前ステージの必須成果物が欠落
- **原因**: ファイル削除、移動、未作成
- **解決**: 
  1. 欠落成果物を作成したステージを特定
  2. aidlc-state.md で完了とマークされているか確認
  3. 完了だが成果物がない場合: 該当ステージを再生成
  4. 未完了の場合: 該当ステージから再開
- **復旧**: 欠落成果物を作成するステージに戻って再実行

**エラー**: 前ステージの必須成果物が欠落
- **原因**: ファイル削除、移動、未作成
- **解決**: 
  1. 欠落成果物を作成したステージを特定
  2. aidlc-state.md で完了とマークされているか確認
  3. 完了だが成果物がない場合: 該当ステージを再生成
  4. 未完了の場合: 該当ステージから再開
- **復旧**: 欠落成果物を作成するステージに戻って再実行

**Error**: Artifact file exists but is empty or corrupted
- **Cause**: Interrupted write, manual editing, file system issues
- **Solution**:
  1. Create backup of corrupted file
  2. Attempt to regenerate from stage that creates it
  3. If cannot regenerate: Ask user for information to recreate
- **Recovery**: Re-execute the stage that creates the artifact
**エラー**: 成果物ファイルが空/破損
- **原因**: 書き込み中断、手動編集、ファイルシステム問題
- **解決**:
  1. 破損ファイルをバックアップ
  2. 作成ステージから再生成を試みる
  3. 再生成できない場合は、再作成のための情報提供を依頼
- **復旧**: 成果物を作成するステージを再実行

**エラー**: 成果物ファイルが空/破損
- **原因**: 書き込み中断、手動編集、ファイルシステム問題
- **解決**:
  1. 破損ファイルをバックアップ
  2. 作成ステージから再生成を試みる
  3. 再生成できない場合は、再作成のための情報提供を依頼
- **復旧**: 成果物を作成するステージを再実行

### Inconsistent State During Resumption
### 再開時の状態不整合

### 再開時の状態不整合

**Error**: aidlc-state.md shows stage complete but artifacts don't exist
- **Cause**: State file updated but artifact generation failed
- **Solution**:
  1. Mark stage as incomplete in aidlc-state.md
  2. Re-execute the stage to generate artifacts
  3. Verify artifacts exist before marking complete
- **Recovery**: Reset stage status and re-execute
**エラー**: aidlc-state.md は完了だが成果物が存在しない
- **原因**: 状態更新は成功したが成果物生成が失敗
- **解決**:
  1. aidlc-state.md でステージを未完了に変更
  2. ステージを再実行して成果物を生成
  3. 成果物の存在を確認してから完了にマーク
- **復旧**: ステージ状態をリセットして再実行

**エラー**: aidlc-state.md は完了だが成果物が存在しない
- **原因**: 状態更新は成功したが成果物生成が失敗
- **解決**:
  1. aidlc-state.md でステージを未完了に変更
  2. ステージを再実行して成果物を生成
  3. 成果物の存在を確認してから完了にマーク
- **復旧**: ステージ状態をリセットして再実行

**Error**: Artifacts exist but aidlc-state.md shows stage incomplete
- **Cause**: Artifact generation succeeded but state update failed
- **Solution**:
  1. Verify artifacts are complete and valid
  2. Update aidlc-state.md to mark stage complete
  3. Proceed to next stage
- **Recovery**: Update state file to reflect actual completion
**エラー**: 成果物はあるが aidlc-state.md が未完了
- **原因**: 成果物生成は成功したが状態更新に失敗
- **解決**:
  1. 成果物が完全・有効であることを確認
  2. aidlc-state.md を更新してステージ完了を反映
  3. 次のステージへ進む
- **復旧**: 状態ファイルを実際の完了状態に更新

**エラー**: 成果物はあるが aidlc-state.md が未完了
- **原因**: 成果物生成は成功したが状態更新に失敗
- **解決**:
  1. 成果物が完全・有効であることを確認
  2. aidlc-state.md を更新してステージ完了を反映
  3. 次のステージへ進む
- **復旧**: 状態ファイルを実際の完了状態に更新

**Error**: Multiple stages marked as "current" in aidlc-state.md
- **Cause**: State file corruption, manual editing
- **Solution**:
  1. Review artifacts to determine actual progress
  2. Ask user which stage they're actually on
  3. Correct aidlc-state.md to show single current stage
- **Recovery**: Rebuild state file based on existing artifacts
**エラー**: aidlc-state.md で複数ステージが "current" とマーク
- **原因**: 状態ファイル破損、手動編集
- **解決**:
  1. 成果物を確認して実際の進捗を判断
  2. ユーザーに現在のステージを確認
  3. aidlc-state.md を修正し current を 1 つにする
- **復旧**: 既存成果物に基づき状態ファイルを再構築

**エラー**: aidlc-state.md で複数ステージが "current" とマーク
- **原因**: 状態ファイル破損、手動編集
- **解決**:
  1. 成果物を確認して実際の進捗を判断
  2. ユーザーに現在のステージを確認
  3. aidlc-state.md を修正し current を 1 つにする
- **復旧**: 既存成果物に基づき状態ファイルを再構築

### Context Loading Errors
### コンテキスト読み込みエラー

### コンテキスト読み込みエラー

**Error**: Cannot load required context from previous stages
- **Cause**: Missing files, corrupted content, wrong file paths
- **Solution**:
  1. List which artifacts are needed for current stage
  2. Check which ones are missing or corrupted
  3. Regenerate missing artifacts or ask user for information
- **Recovery**: Complete prerequisite stages before resuming current stage
**エラー**: 前ステージの必要コンテキストを読み込めない
- **原因**: ファイル欠落、内容破損、誤ったパス
- **解決**:
  1. 現在ステージに必要な成果物を列挙
  2. 欠落/破損しているものを特定
  3. 欠落成果物を再生成、またはユーザーに情報提供を依頼
- **復旧**: 現在ステージの前提を満たすまで準備

**エラー**: 前ステージの必要コンテキストを読み込めない
- **原因**: ファイル欠落、内容破損、誤ったパス
- **解決**:
  1. 現在ステージに必要な成果物を列挙
  2. 欠落/破損しているものを特定
  3. 欠落成果物を再生成、またはユーザーに情報提供を依頼
- **復旧**: 現在ステージの前提を満たすまで準備

**Error**: Loaded artifacts contain contradictory information
- **Cause**: Manual editing, multiple people working, incomplete updates
- **Solution**:
  1. Identify contradictions and present to user
  2. Ask user which information is correct
  3. Update artifacts to resolve contradictions
- **Recovery**: Reconcile contradictions before proceeding
**エラー**: 読み込んだ成果物に矛盾がある
- **原因**: 手動編集、複数人作業、更新の不完全
- **解決**:
  1. 矛盾点を特定しユーザーに提示
  2. 正しい情報をユーザーに確認
  3. 成果物を更新して矛盾を解消
- **復旧**: 進行前に矛盾を解消

**エラー**: 読み込んだ成果物に矛盾がある
- **原因**: 手動編集、複数人作業、更新の不完全
- **解決**:
  1. 矛盾点を特定しユーザーに提示
  2. 正しい情報をユーザーに確認
  3. 成果物を更新して矛盾を解消
- **復旧**: 進行前に矛盾を解消

### Resumption Best Practices
### 再開時のベストプラクティス

### 再開時のベストプラクティス

1. **Always validate state**: Check aidlc-state.md matches actual artifacts
2. **Load incrementally**: Load artifacts stage-by-stage, validate each
3. **Fail fast**: Stop immediately if critical artifacts are missing
4. **Communicate clearly**: Tell user exactly what's missing and why it's needed
5. **Offer options**: Regenerate, provide manually, or start fresh
6. **Document recovery**: Log all recovery actions in audit.md State file is severely corrupted
- User requirements have changed significantly
- Architectural decision needs to be reversed
1. **状態を必ず検証**: aidlc-state.md が実際の成果物と一致しているか
2. **段階的に読み込む**: ステージごとに読み込み、各段階で検証
3. **早期停止**: 重要な成果物が欠落していれば直ちに停止
4. **明確に伝える**: 何が欠落しているか、なぜ必要かを明示
5. **選択肢を提示**: 再生成/手動提供/新規開始
6. **復旧を記録**: すべての復旧措置を audit.md に記録 State file is severely corrupted
- User requirements have changed significantly
- Architectural decision needs to be reversed

1. **状態を必ず検証**: aidlc-state.md が実際の成果物と一致しているか
2. **段階的に読み込む**: ステージごとに読み込み、各段階で検証
3. **早期停止**: 重要な成果物が欠落していれば直ちに停止
4. **明確に伝える**: 何が欠落しているか、なぜ必要かを明示
5. **選択肢を提示**: 再生成/手動提供/新規開始
6. **復旧を記録**: すべての復旧措置を audit.md に記録 State file is severely corrupted
- User requirements have changed significantly
- Architectural decision needs to be reversed

**Before Starting Over**:
1. Archive all existing work
2. Document lessons learned
3. Identify what to preserve
4. Get user confirmation
5. Create new execution plan
**新規開始前に**:
1. 既存作業をすべてアーカイブ
2. 学びを記録
3. 保持すべき内容を特定
4. ユーザーの確認を得る
5. 新しい実行計画を作成

**新規開始前に**:
1. 既存作業をすべてアーカイブ
2. 学びを記録
3. 保持すべき内容を特定
4. ユーザーの確認を得る
5. 新しい実行計画を作成

## Logging Requirements
## ログ要件

## ログ要件

### Error Logging Format
### エラーログ形式

### エラーログ形式

```markdown
## Error - [Phase Name]
**Timestamp**: [ISO timestamp]
**Error Type**: [Critical/High/Medium/Low]
**Description**: [What went wrong]
**Cause**: [Why it happened]
**Resolution**: [How it was resolved]
**Impact**: [Effect on workflow]

---
```
```markdown
## Error - [Phase Name]
**Timestamp**: [ISO timestamp]
**Error Type**: [Critical/High/Medium/Low]
**Description**: [What went wrong]
**Cause**: [Why it happened]
**Resolution**: [How it was resolved]
**Impact**: [Effect on workflow]

---
```

```markdown
## Error - [Phase Name]
**Timestamp**: [ISO timestamp]
**Error Type**: [Critical/High/Medium/Low]
**Description**: [What went wrong]
**Cause**: [Why it happened]
**Resolution**: [How it was resolved]
**Impact**: [Effect on workflow]

---
```

### Recovery Logging Format
### 復旧ログ形式

### 復旧ログ形式

```markdown
## Recovery - [Phase Name]
**Timestamp**: [ISO timestamp]
**Issue**: [What needed recovery]
**Recovery Steps**: [What was done]
**Outcome**: [Result of recovery]
**Artifacts Affected**: [List of files]

---
```
```markdown
## Recovery - [Phase Name]
**Timestamp**: [ISO timestamp]
**Issue**: [What needed recovery]
**Recovery Steps**: [What was done]
**Outcome**: [Result of recovery]
**Artifacts Affected**: [List of files]

---
```

```markdown
## Recovery - [Phase Name]
**Timestamp**: [ISO timestamp]
**Issue**: [What needed recovery]
**Recovery Steps**: [What was done]
**Outcome**: [Result of recovery]
**Artifacts Affected**: [List of files]

---
```

## Prevention Best Practices
## 予防のベストプラクティス

## 予防のベストプラクティス

1. **Validate Early**: Check inputs and dependencies before starting work
2. **Checkpoint Often**: Update checkboxes immediately after completing steps
3. **Communicate Clearly**: Explain what you're doing and why
4. **Ask Questions**: Don't assume - clarify ambiguities immediately
5. **Document Everything**: Log all decisions and changes in `audit.md`
1. **早期検証**: 作業開始前に入力と依存関係を確認
2. **頻繁にチェックポイント**: ステップ完了ごとにチェックを更新
3. **明確なコミュニケーション**: 何を/なぜ行うかを説明
4. **質問する**: 推測せず、あいまいさは即確認
5. **すべて記録**: すべての判断と変更を `audit.md` に記録

1. **早期検証**: 作業開始前に入力と依存関係を確認
2. **頻繁にチェックポイント**: ステップ完了ごとにチェックを更新
3. **明確なコミュニケーション**: 何を/なぜ行うかを説明
4. **質問する**: 推測せず、あいまいさは即確認
5. **すべて記録**: すべての判断と変更を `audit.md` に記録
