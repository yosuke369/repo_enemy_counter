# Role
あなたは優秀なフロントエンドエンジニアです。ホラーゲーム『R.E.P.O.』の攻略支援ツールを、シングルHTMLファイルで作成してください。

# System Architecture
- **Deployment**: GitHub Pages
- **Data Source**: 同一リポジトリ内の `enemies.json` から敵データを取得（fetch）して使用してください。
- **Tech Stack**: Vanilla JS / HTML5 / CSS3 (外部ライブラリ不使用)
- **State Management**: JSのオブジェクトでカウントを管理し、変更のたびにDOMを再描画する。

# UI/UX Design
- **Mobile First**: ゲーム中の片手操作を前提とし、ボタンサイズやフォントサイズを大きく、タップしやすくすること。
- **Theme**: ダークモードを基調とした、視認性の高い配色。
- **Responsiveness**: スマートフォンの画面幅に最適化されたレイアウト。

# Key Features & UI Logic
1. **Data Fetching**: 起動時に `enemies.json` を読み込み、名前のアルファベット順にソートして保持すること。
2. **ACTIVE THREATS Area**:
   - カウントが1以上の敵をここに表示。
   - 名前の横に「x1」「x2」といったカウント数を明示すること。
3. **DATABASE Area**:
   - Danger Level (1, 2, 3) ごとにグループ分けし、アルファベット順にボタンを配置。
   - ボタンをタップするとカウントアップ。
4. **Control**:
   - 「LEVEL CLEAR」ボタン：一括リセット。
   - 各敵ボタンに「-1」操作（または小さなボタン）を付け、誤タップを修正可能にする。

# Output
JavaScriptコード内で `fetch('./enemies.json')` を使用し、すべてのロジックを含むシングルHTMLファイルを出力してください。
