# Mid-Workflow Changes and Phase Management(ワークフロー途中の変更とフェーズ管理)

## Overview(概要)

Users may request changes to the execution plan or phase execution during the workflow. This document provides guidance on handling these requests safely and effectively.

ワークフロー中に実行計画やフェーズ実行の変更を求められることがある。本書はそれらの要望を安全かつ効果的に扱うためのガイドである。

## Types of Mid-Workflow Changes(途中変更の種類)

### 1. Adding a Skipped Phase(1. スキップしたフェーズの追加)

**Scenario**: User wants to add a phase that was originally skipped

**シナリオ**: 当初スキップしたフェーズを追加したい

**Example**: "Actually, I want to add user stories even though we skipped that stage"

**例**: "実は User Stories を追加したい（スキップしていたけど）"

**Handling**:

**対応**:

1. **Confirm Request**: "You want to add User Stories stage. This will create user stories and personas. Confirm?"
2. **確認**: "User Stories ステージを追加したいということですね。ユーザーストーリーとペルソナを作成します。確認しますか？"
3. **Check Dependencies**: Verify all prerequisite phases are complete
4. **依存関係確認**: 必要な前提フェーズが完了しているか確認
5. **Update Execution Plan**: Add phase to `execution-plan.md` with rationale
6. **実行計画更新**: `execution-plan.md` に追加し理由を記載
7. **Update State**: Mark phase as "PENDING" in `aidlc-state.md`
8. **状態更新**: `aidlc-state.md` でフェーズを "PENDING" にする
9. **Execute Phase**: Follow normal phase execution process
10. **フェーズ実行**: 通常のフェーズ実行プロセスに従う
11. **Log Change**: Document in `audit.md` with timestamp and reason
12. **変更記録**: `audit.md` にタイムスタンプと理由を記録

**Considerations**:

**考慮点**:

- May need to update later phases that could benefit from new artifacts
- 新しい成果物により後続フェーズを更新する必要がある
- Existing artifacts may need revision to incorporate new information
- 既存成果物の修正が必要な場合がある
- Timeline will be extended
- タイムラインが延びる

### 2. Skipping a Planned Phase(2. 計画済みフェーズのスキップ)

**Scenario**: User wants to skip a phase that was planned to execute

**シナリオ**: 実行予定だったフェーズをスキップしたい

**Example**: "Let's skip the NFR Design stage for now"

**例**: "今は NFR Design をスキップしよう"

**Handling**:

**対応**:

1. **Confirm Request**: "You want to skip NFR Design. This means no NFR patterns or logical components will be incorporated. Confirm?"
2. **確認**: "NFR Design をスキップします。NFR パターンや論理コンポーネントは取り込まれません。確認しますか？"
3. **Warn About Impact**: Explain what will be missing and potential consequences
4. **影響警告**: 不足や影響を説明
5. **Get Explicit Confirmation**: User must explicitly confirm understanding of impact
6. **明示的確認**: 影響理解の明示的承認が必要
7. **Update Execution Plan**: Mark phase as "SKIPPED" with reason
8. **実行計画更新**: 理由と共に "SKIPPED" を記載
9. **Update State**: Mark phase as "SKIPPED" in `aidlc-state.md`
10. **状態更新**: `aidlc-state.md` でフェーズを "SKIPPED" に
11. **Adjust Later Phases**: Note that later phases may need manual setup
12. **後続調整**: 後続フェーズで手作業が必要な可能性を記載
13. **Log Change**: Document in `audit.md` with timestamp and reason
14. **変更記録**: `audit.md` にタイムスタンプと理由を記録

**Considerations**:

**考慮点**:

- Later phases may fail or require manual intervention
- 後続フェーズが失敗する/手作業が必要な可能性
- User accepts responsibility for missing artifacts
- 不足成果物はユーザーの責任であることを明確にする
- Can be added back later if needed
- 後から追加可能

### 3. Restarting Current Stage(3. 現在ステージのやり直し)

**Scenario**: User is unhappy with current stage results and wants to redo it

**シナリオ**: 現在ステージの結果に不満がありやり直したい

**Example**: "I don't like these user stories. Can we start over?"

**例**: "このユーザーストーリーは好みじゃない。やり直せる？"

**Handling**:

**対応**:

1. **Understand Concern**: "What specifically would you like to change about the stories?"
2. **懸念の確認**: "具体的に何を変えたいですか？"
3. **Offer Options**:
4. **選択肢提示**:
   - **Option A**: Modify existing artifacts (faster, preserves some work)
   - **選択肢 A**: 既存成果物を修正（早い・一部作業を保持）
   - **Option B**: Complete restart (clean slate, more time)
   - **選択肢 B**: 完全にやり直す（クリーンスレート・時間がかかる）
5. **If Restart Chosen**:
6. **やり直しが選ばれたら**:
   - Archive existing artifacts: `{artifact}.backup.{timestamp}`
   - 既存成果物をアーカイブ: `{artifact}.backup.{timestamp}`
   - Reset stage checkboxes in plan file
   - 計画ファイルのチェックボックスをリセット
   - Mark stage as "IN PROGRESS" in `aidlc-state.md`
   - `aidlc-state.md` のステージを "IN PROGRESS" に
   - Clear stage completion status
   - ステージ完了状態をクリア
   - Re-execute from beginning
   - 最初から再実行
7. **Log Change**: Document reason for restart and what will change
8. **変更記録**: やり直し理由と変更内容を記録

**Considerations**:

**考慮点**:

- Existing work will be lost (but backed up)
- 既存作業は失われる（ただしバックアップあり）
- May need to redo dependent stages
- 依存ステージの再実行が必要になる場合がある
- Timeline will be extended
- タイムラインが延びる

### 4. Restarting Previous Stage(4. 以前のステージのやり直し)

**Scenario**: User wants to go back and redo a completed stage

**シナリオ**: 完了済みステージに戻ってやり直したい

**Example**: "I want to change the architectural decision we made earlier"

**例**: "以前のアーキテクチャ判断を変更したい"

**Handling**:

**対応**:

1. **Assess Impact**: Identify all stages that depend on the stage to be restarted
2. **影響評価**: やり直すステージに依存するステージを特定
3. **Warn User**: "Restarting Application Design will require redoing: Units Planning, Units Generation, per-unit design (all units), Code Planning, Code Generation. Confirm?"
4. **警告**: "Application Design をやり直す場合、Units Planning/Units Generation/全ユニットの per-unit design/Code Planning/Code Generation をやり直す必要があります。確認しますか？"
5. **Get Explicit Confirmation**: User must understand full impact
6. **明示的確認**: 影響を理解した承認が必要
7. **If Confirmed**:
8. **確認後**:
   - Archive all affected artifacts
   - 影響を受ける成果物をすべてアーカイブ
   - Reset all affected stages in `aidlc-state.md`
   - `aidlc-state.md` の影響ステージをリセット
   - Clear checkboxes in all affected plan files
   - 影響する計画ファイルのチェックボックスをクリア
   - Return to the stage to restart
   - やり直すステージへ戻る
   - Re-execute from that point forward
   - そこから再実行
9. **Log Change**: Document full impact and reason for restart
10. **変更記録**: 影響範囲と理由を記録

**Considerations**:

**考慮点**:

- Significant rework required
- 大きな手戻りが発生
- All dependent stages must be redone
- 依存ステージはすべてやり直し
- Timeline will be significantly extended
- タイムラインが大幅に延びる
- Consider if modification is better than restart
- 修正で済むなら再実行より修正を検討

### 5. Changing Stage Depth(5. ステージの深さ変更)

**Scenario**: User wants to change the depth level of current or upcoming stage

**シナリオ**: 現在/次のステージの詳細度を変更したい

**Example**: "Let's do a comprehensive requirements analysis instead of standard"

**例**: "要件分析を Standard ではなく Comprehensive にしよう"

**Handling**:

1. **Confirm Request**: "You want to change Requirements Analysis from Standard to Comprehensive depth. This will be more thorough but take longer. Confirm?"
2. **Update Execution Plan**: Change depth level in `workflow-planning.md`
3. **Adjust Approach**: Follow comprehensive depth guidelines for the stage
4. **Update Estimates**: Inform user of new timeline estimate
5. **Log Change**: Document depth change and reason
   **対応**:
6. **確認**: "Requirements Analysis を Standard から Comprehensive に変更します。より詳細になり時間がかかります。確認しますか？"
7. **実行計画更新**: `workflow-planning.md` の詳細度を変更
8. **アプローチ調整**: Comprehensive のガイドラインに従う
9. **見積更新**: 新しいタイムラインを通知
10. **変更記録**: 深さ変更と理由を記録

**対応**:

1. **確認**: "Requirements Analysis を Standard から Comprehensive に変更します。より詳細になり時間がかかります。確認しますか？"
2. **実行計画更新**: `workflow-planning.md` の詳細度を変更
3. **アプローチ調整**: Comprehensive のガイドラインに従う
4. **見積更新**: 新しいタイムラインを通知
5. **変更記録**: 深さ変更と理由を記録

**Considerations**:

**考慮点**:

- More depth = more time but better quality
- 詳細度が増えるほど時間は増えるが品質は向上
- Less depth = faster but may miss details
- 詳細度を下げると早いが漏れのリスク
- Can only change before or during stage, not after completion
- 変更はステージ前/中のみ（完了後は不可）

### 6. Pausing Workflow

### 6. ワークフローの一時停止

### 6. ワークフローの一時停止

**Scenario**: User needs to pause and resume later
**シナリオ**: 一時停止して後で再開したい

**シナリオ**: 一時停止して後で再開したい

**Example**: "I need to stop for now and continue tomorrow"
**例**: "今日はここまでで、明日続けたい"

**例**: "今日はここまでで、明日続けたい"

**Handling**:

1. **Complete Current Step**: Finish the current step in progress if possible
2. **Update Checkboxes**: Mark all completed steps with [x]
3. **Update State**: Ensure `aidlc-state.md` reflects current status
4. **Log Pause**: Document pause point in `audit.md`
5. **Provide Resume Instructions**: "When you return, I'll detect your existing project and offer to continue from: [current phase, current step]"
   **対応**:
6. **現在のステップを完了**: 可能であれば進行中のステップを完了
7. **チェックボックス更新**: 完了ステップを [x] に
8. **状態更新**: `aidlc-state.md` に現状を反映
9. **停止ログ**: `audit.md` に停止地点を記録
10. **再開手順の案内**: "再開時は既存プロジェクトを検出し、[現在フェーズ、現在ステップ] から続ける提案をします"

**対応**:

1. **現在のステップを完了**: 可能であれば進行中のステップを完了
2. **チェックボックス更新**: 完了ステップを [x] に
3. **状態更新**: `aidlc-state.md` に現状を反映
4. **停止ログ**: `audit.md` に停止地点を記録
5. **再開手順の案内**: "再開時は既存プロジェクトを検出し、[現在フェーズ、現在ステップ] から続ける提案をします"

**On Resume**:

1. **Detect Existing Project**: Check for `aidlc-state.md`
2. **Load Context**: Read all artifacts from completed stages
3. **Show Status**: Display current stage and next step
4. **Offer Options**: Continue where left off or review previous work
5. **Log Resume**: Document resume point in `audit.md`
   **再開時**:
6. **既存プロジェクトの検出**: `aidlc-state.md` を確認
7. **コンテキスト読み込み**: 完了済みステージの成果物を読み込む
8. **状態表示**: 現在ステージと次ステップを表示
9. **選択肢提示**: 続行 or 以前の作業の確認
10. **再開ログ**: `audit.md` に再開地点を記録

**再開時**:

1. **既存プロジェクトの検出**: `aidlc-state.md` を確認
2. **コンテキスト読み込み**: 完了済みステージの成果物を読み込む
3. **状態表示**: 現在ステージと次ステップを表示
4. **選択肢提示**: 続行 or 以前の作業の確認
5. **再開ログ**: `audit.md` に再開地点を記録

---

---

---

### 7. Changing Architectural Decision

### 7. アーキテクチャ判断の変更

### 7. アーキテクチャ判断の変更

**Scenario**: User wants to change from monolith to microservices (or vice versa)
**シナリオ**: モノリスからマイクロサービスへの変更（または逆）

**シナリオ**: モノリスからマイクロサービスへの変更（または逆）

**Example**: "Actually, let's do microservices instead of a monolith"
**例**: "やっぱりモノリスではなくマイクロサービスにしよう"

**例**: "やっぱりモノリスではなくマイクロサービスにしよう"

**Handling**:

1. **Assess Current Progress**: Determine how far into workflow
2. **Explain Impact**:
   - If before Units Planning: Minimal impact, just update decision
   - If after Units Planning: Must redo Units Planning, Units Generation, all per-unit design
   - If after Code Generation: Significant rework required
3. **Recommend Approach**:
   - Early in workflow: Restart from Application Design stage
   - Late in workflow: Consider if modification is feasible vs. restart
4. **Get Confirmation**: User must understand full scope of change
5. **Execute Change**: Follow restart procedures for affected stages
   **対応**:
6. **現在進捗の把握**: ワークフローの進行度を確認
7. **影響説明**:
   - Units Planning 前: 影響は小さく決定更新のみ
   - Units Planning 後: Units Planning/Units Generation/全ユニットの設計をやり直し
   - Code Generation 後: 大幅な手戻り
8. **推奨**:
   - 早期: Application Design から再開
   - 後半: 修正で対応可能か再実行かを検討
9. **確認取得**: 変更範囲の理解を得る
10. **変更実行**: 影響ステージの再実行手順に従う

**対応**:

1. **現在進捗の把握**: ワークフローの進行度を確認
2. **影響説明**:
   - Units Planning 前: 影響は小さく決定更新のみ
   - Units Planning 後: Units Planning/Units Generation/全ユニットの設計をやり直し
   - Code Generation 後: 大幅な手戻り
3. **推奨**:
   - 早期: Application Design から再開
   - 後半: 修正で対応可能か再実行かを検討
4. **確認取得**: 変更範囲の理解を得る
5. **変更実行**: 影響ステージの再実行手順に従う

**Considerations**:

- Architectural changes have cascading effects
- Earlier in workflow = easier to change
- Later in workflow = consider cost vs. benefit
  **考慮点**:
- アーキテクチャ変更は連鎖的に影響
- 早いほど変更しやすい
- 遅いほどコスト/効果を検討

**考慮点**:

- アーキテクチャ変更は連鎖的に影響
- 早いほど変更しやすい
- 遅いほどコスト/効果を検討

---

---

---

### 8. Adding/Removing Units

### 8. ユニットの追加/削除

### 8. ユニットの追加/削除

**Scenario**: User wants to add or remove units after Units Generation
**シナリオ**: Units Generation 後にユニットを追加/削除したい

**シナリオ**: Units Generation 後にユニットを追加/削除したい

**Example**: "We need to split the Payment unit into Payment and Billing"
**例**: "Payment ユニットを Payment と Billing に分けたい"

**例**: "Payment ユニットを Payment と Billing に分けたい"

**Handling**:

1. **Assess Impact**: Determine which units have completed design/code
2. **Explain Consequences**:
   - Adding unit: Need to do full design and code for new unit
   - Removing unit: Need to redistribute functionality to other units
   - Splitting unit: Need to redo design and code for both resulting units
3. **Update Unit Artifacts**:
   - Modify `unit-of-work.md`
   - Update `unit-of-work-dependency.md`
   - Revise `unit-of-work-story-map.md`
4. **Reset Affected Units**: Mark affected units as needing redesign
5. **Execute Changes**: Follow normal unit design and code process for affected units
   **対応**:
6. **影響評価**: どのユニットが設計/コード完了済みか確認
7. **結果説明**:
   - 追加: 新ユニットの設計とコードが必要
   - 削除: 機能を他ユニットへ再配分
   - 分割: 両ユニットの設計/コードをやり直し
8. **ユニット成果物更新**:
   - `unit-of-work.md` を修正
   - `unit-of-work-dependency.md` を更新
   - `unit-of-work-story-map.md` を修正
9. **影響ユニットをリセット**: 再設計が必要とマーク
10. **変更実行**: 影響ユニットに通常の設計/コードプロセスを適用

**対応**:

1. **影響評価**: どのユニットが設計/コード完了済みか確認
2. **結果説明**:
   - 追加: 新ユニットの設計とコードが必要
   - 削除: 機能を他ユニットへ再配分
   - 分割: 両ユニットの設計/コードをやり直し
3. **ユニット成果物更新**:
   - `unit-of-work.md` を修正
   - `unit-of-work-dependency.md` を更新
   - `unit-of-work-story-map.md` を修正
4. **影響ユニットをリセット**: 再設計が必要とマーク
5. **変更実行**: 影響ユニットに通常の設計/コードプロセスを適用

**Considerations**:

- Affects all downstream stages for those units
- May affect other units if dependencies change
- Timeline impact depends on how many units affected
  **考慮点**:
- 該当ユニットの下流ステージ全体に影響
- 依存関係が変わると他ユニットにも影響
- 影響ユニット数に応じてタイムラインが変動

**考慮点**:

- 該当ユニットの下流ステージ全体に影響
- 依存関係が変わると他ユニットにも影響
- 影響ユニット数に応じてタイムラインが変動

---

---

---

## General Guidelines for Handling Changes

## 変更対応の一般ガイドライン

## 変更対応の一般ガイドライン

### Before Making Changes

### 変更前

### 変更前

1. **Understand the Request**: Ask clarifying questions about what user wants to change and why
2. **Assess Impact**: Identify all affected stages, artifacts, and dependencies
3. **Explain Consequences**: Clearly communicate what will need to be redone and timeline impact
4. **Offer Alternatives**: Sometimes modification is better than restart
5. **Get Explicit Confirmation**: User must understand and accept the impact
6. **要求の理解**: 何をどう変えたいかを確認質問
7. **影響評価**: 影響するステージ、成果物、依存関係を特定
8. **結果説明**: やり直し範囲とタイムラインへの影響を明確に伝える
9. **代替案提示**: 修正で済む場合は再実行より修正を提案
10. **明示的確認**: 影響を理解し受け入れることを確認

11. **要求の理解**: 何をどう変えたいかを確認質問
12. **影響評価**: 影響するステージ、成果物、依存関係を特定
13. **結果説明**: やり直し範囲とタイムラインへの影響を明確に伝える
14. **代替案提示**: 修正で済む場合は再実行より修正を提案
15. **明示的確認**: 影響を理解し受け入れることを確認

### During Changes

### 変更中

### 変更中

1. **Archive Existing Work**: Always backup before making destructive changes
2. **Update All Tracking**: Keep `aidlc-state.md`, plan files, and `audit.md` in sync
3. **Communicate Progress**: Keep user informed about what's happening
4. **Validate Changes**: Ensure changes are consistent across all artifacts
5. **Test Continuity**: Verify workflow can continue smoothly after changes
6. **既存作業のアーカイブ**: 破壊的変更前に必ずバックアップ
7. **追跡ファイル更新**: `aidlc-state.md`、計画ファイル、`audit.md` を整合させる
8. **進捗共有**: 何が起きているかをユーザーに伝える
9. **変更の検証**: すべての成果物で整合性を確認
10. **継続性テスト**: 変更後にワークフローがスムーズに継続できるか確認

11. **既存作業のアーカイブ**: 破壊的変更前に必ずバックアップ
12. **追跡ファイル更新**: `aidlc-state.md`、計画ファイル、`audit.md` を整合させる
13. **進捗共有**: 何が起きているかをユーザーに伝える
14. **変更の検証**: すべての成果物で整合性を確認
15. **継続性テスト**: 変更後にワークフローがスムーズに継続できるか確認

### After Changes

### 変更後

### 変更後

1. **Verify Consistency**: Check that all artifacts are aligned with changes
2. **Update Documentation**: Ensure all references are updated
3. **Log Completely**: Document full change history in `audit.md`
4. **Confirm with User**: Verify changes meet user's expectations
5. **Resume Workflow**: Continue with normal execution from new state
6. **整合性検証**: すべての成果物が変更内容と整合しているか確認
7. **ドキュメント更新**: 参照をすべて更新
8. **完全なログ**: 変更履歴を `audit.md` に記録
9. **ユーザー確認**: 期待に合致しているか確認
10. **ワークフロー再開**: 新しい状態で通常実行に戻る

11. **整合性検証**: すべての成果物が変更内容と整合しているか確認
12. **ドキュメント更新**: 参照をすべて更新
13. **完全なログ**: 変更履歴を `audit.md` に記録
14. **ユーザー確認**: 期待に合致しているか確認
15. **ワークフロー再開**: 新しい状態で通常実行に戻る

---

---

---

## Change Request Decision Tree

## 変更要求の判断ツリー

## 変更要求の判断ツリー

```
User requests change
    |
    ├─ Is it current phase?
    |   ├─ Yes: Can modify or restart current phase
    |   └─ No: Go to next question
    |
    ├─ Is it a completed phase?
    |   ├─ Yes: Assess impact on dependent phases
    |   |   ├─ Low impact: Modify and update dependents
    |   |   └─ High impact: Recommend restart from that phase
    |   └─ No: Go to next question
    |
    ├─ Is it adding a skipped phase?
    |   ├─ Yes: Check prerequisites, add to plan, execute
    |   └─ No: Go to next question
    |
    ├─ Is it skipping a planned phase?
    |   ├─ Yes: Warn about impact, get confirmation, skip
    |   └─ No: Go to next question
    |
    └─ Is it changing depth level?
        ├─ Yes: Update plan, adjust approach
        └─ No: Clarify request with user
```

```
User requests change
    |
    ├─ Is it current phase?
    |   ├─ Yes: Can modify or restart current phase
    |   └─ No: Go to next question
    |
    ├─ Is it a completed phase?
    |   ├─ Yes: Assess impact on dependent phases
    |   |   ├─ Low impact: Modify and update dependents
    |   |   └─ High impact: Recommend restart from that phase
    |   └─ No: Go to next question
    |
    ├─ Is it adding a skipped phase?
    |   ├─ Yes: Check prerequisites, add to plan, execute
    |   └─ No: Go to next question
    |
    ├─ Is it skipping a planned phase?
    |   ├─ Yes: Warn about impact, get confirmation, skip
    |   └─ No: Go to next question
    |
    └─ Is it changing depth level?
        ├─ Yes: Update plan, adjust approach
        └─ No: Clarify request with user
```

```
User requests change
    |
    ├─ Is it current phase?
    |   ├─ Yes: Can modify or restart current phase
    |   └─ No: Go to next question
    |
    ├─ Is it a completed phase?
    |   ├─ Yes: Assess impact on dependent phases
    |   |   ├─ Low impact: Modify and update dependents
    |   |   └─ High impact: Recommend restart from that phase
    |   └─ No: Go to next question
    |
    ├─ Is it adding a skipped phase?
    |   ├─ Yes: Check prerequisites, add to plan, execute
    |   └─ No: Go to next question
    |
    ├─ Is it skipping a planned phase?
    |   ├─ Yes: Warn about impact, get confirmation, skip
    |   └─ No: Go to next question
    |
    └─ Is it changing depth level?
        ├─ Yes: Update plan, adjust approach
        └─ No: Clarify request with user
```

---

---

---

## Logging Requirements

## ログ要件

## ログ要件

### Change Request Log Format

### 変更要求ログ形式

### 変更要求ログ形式

```markdown
## Change Request - [Phase Name]

**Timestamp**: [ISO timestamp]
**Request**: [What user wants to change]
**Current State**: [Where we are in workflow]
**Impact Assessment**: [What will be affected]
**User Confirmation**: [User's explicit confirmation]
**Action Taken**: [What was done]
**Artifacts Affected**: [List of files changed/reset]

---
```

```markdown
## Change Request - [Phase Name]

**Timestamp**: [ISO timestamp]
**Request**: [What user wants to change]
**Current State**: [Where we are in workflow]
**Impact Assessment**: [What will be affected]
**User Confirmation**: [User's explicit confirmation]
**Action Taken**: [What was done]
**Artifacts Affected**: [List of files changed/reset]

---
```

```markdown
## Change Request - [Phase Name]

**Timestamp**: [ISO timestamp]
**Request**: [What user wants to change]
**Current State**: [Where we are in workflow]
**Impact Assessment**: [What will be affected]
**User Confirmation**: [User's explicit confirmation]
**Action Taken**: [What was done]
**Artifacts Affected**: [List of files changed/reset]

---
```

---

---

---

## Best Practices

## ベストプラクティス

## ベストプラクティス

1. **Always Confirm**: Never make destructive changes without explicit user confirmation
2. **Explain Impact**: Users need to understand consequences before deciding
3. **Offer Options**: Sometimes there are multiple ways to handle a change
4. **Archive First**: Always backup before making destructive changes
5. **Update Everything**: Keep all tracking files in sync
6. **Log Thoroughly**: Document all changes for audit trail
7. **Validate After**: Ensure workflow can continue smoothly
8. **Be Flexible**: Workflow should adapt to user needs, not force rigid process
9. **必ず確認**: 明示的承認なしに破壊的変更は行わない
10. **影響を説明**: 決定前に結果を理解してもらう
11. **選択肢を提示**: 変更の扱い方は複数あることがある
12. **先にアーカイブ**: 破壊的変更の前に必ずバックアップ
13. **全更新**: 追跡ファイルの整合を保つ
14. **詳細ログ**: 変更は監査ログにすべて記録
15. **変更後検証**: ワークフローが継続可能か確認
16. **柔軟性**: ワークフローはユーザーのニーズに合わせる
