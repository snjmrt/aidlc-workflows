# コンテンツ検証ルール

## 必須: ファイル作成前のコンテンツ検証

**重要**: 生成コンテンツはパースエラーを防ぐため、ファイルに書き込む前に必ず検証すること。

## ASCII 図の基準

**重要**: ASCII 図を含むファイルを作成する前に:

1. **読み込み**: `common/ascii-diagram-standards.md`
2. **検証**: 各図を確認
   - 行ごとの文字数を数える（全行同一幅であること）
   - 使用文字は `+` `-` `|` `^` `v` `<` `>` と空白のみ
   - Unicode の罫線文字は禁止
   - 空白はスペースのみ（タブ禁止）
3. **テスト**: 罫線の角が縦に揃うことを確認

**パターンと検証チェックリストは `common/ascii-diagram-standards.md` を参照。**

## Mermaid 図の検証

### 必須の検証手順

1. **構文チェック**: ファイル作成前に Mermaid 構文を検証
2. **文字エスケープ**: 特殊文字が正しくエスケープされていることを確認
3. **フォールバック**: Mermaid が失敗した場合のテキスト代替を用意

### Mermaid 検証ルール

```markdown
## BEFORE creating any file with Mermaid diagrams:

1. Check for invalid characters in node IDs (use alphanumeric + underscore only)
2. Escape special characters in labels: " → \" and ' → \
3. Validate flowchart syntax: node connections must be valid
4. Test diagram parsing with simple validation

## FALLBACK: If Mermaid validation fails, use text-based workflow representation
```

### 実装パターン

````markdown
## Workflow Visualization

### Mermaid Diagram (if syntax valid)

```mermaid
[validated diagram content]
```
````

### Text Alternative (always include)

```
Phase 1: INCEPTION
- Stage 1: Workspace Detection (COMPLETED)
- Stage 2: Requirements Analysis (COMPLETED)
[continue with text representation]
```

```

## 一般的なコンテンツ検証

### 作成前検証チェックリスト
- [ ] 埋め込みコードブロック（Mermaid、JSON、YAML）を検証
- [ ] 特殊文字のエスケープを確認
- [ ] Markdown 構文の正しさを確認
- [ ] コンテンツのパース互換性をテスト
- [ ] 複雑な要素にテキスト代替を含める

### エラー防止ルール
1. **ツール/コマンドでファイルを書き込む前に必ず検証**: 未検証の内容は書き込まない
2. **特殊文字をエスケープ**: 特に図やコードブロック内
3. **代替を用意**: 視覚的コンテンツにはテキスト版を含める
4. **構文をテスト**: 複雑な構造は必ず検証

## 検証失敗時の対応

### 検証に失敗した場合
1. **エラーを記録**: 何が失敗したかを記録
2. **フォールバックを使用**: テキストベースの代替に切り替え
3. **ワークフロー継続**: 検証失敗で停止しない
4. **ユーザーに通知**: パース制約により簡略化したことを伝える
```
