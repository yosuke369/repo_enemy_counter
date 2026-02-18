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
- **Tab Navigation**: DATABASE Areaは、画面の限られたスペースを有効活用するため、脅威度別のタブ切り替え方式を採用する。
- **Responsiveness**: スマートフォンの画面幅に最適化されたレイアウト。
- **Screen Management**: ゲーム中の利便性を高めるため、**ブラウザが起動している間は端末のスリープ（画面消灯）を抑制する機能**を実装すること。

# Key Features & UI Logic
1. **Data Fetching**: 
   - 起動時に `enemies.json` を読み込み、名前のアルファベット順にソートして保持すること。
2. **ACTIVE THREATS Area (出現中リスト)**:
   - カウントが1以上の敵をここに表示。
   - **分類表示**: このエリア内でも Danger Level (1, 2, 3) ごとにセクションを分けて表示すること。
   - **操作ボタン**: 各敵の横に「+」および「-1」ボタンを設け、出現中リスト内ですばやくカウントを調整可能にする。
3. **DATABASE Area (敵図鑑リスト)**:
   - **タブ表示**: 「Level 1」「Level 2」「Level 3」のタブを設け、タップで表示する脅威度を切り替える。
   - タブ内では敵をアルファベット順に配置。
   - ボタンをタップするとカウントアップ（出現中リストへ追加）。
4. **Sleep Prevention (Wake Lock API) with Toggle**:
   - **UI Control**: 画面下部に「Screen Always On（画面常時点灯）」のON/OFFを切り替えるトグルスイッチを配置する。
   - **Default State**: 初期状態は OFF（ユーザーの利便性を考慮して任意に設定）。
   - **Logic**:
     - スイッチが ON の場合：ユーザーの最初のタップ操作をトリガーに Wake Lock を有効化し、ページが前面にある限り維持する。
     - スイッチを OFF にした場合：即座に Wake Lock を解除（release）し、通常の端末設定に従ってスリープするように戻す。
   - **Feedback**: スイッチの色の変化を用いて、現在スリープ抑制が効いているかを明示すること。
   - **Error Handling**: 未対応ブラウザやエラー時にはスイッチを無効化（グレーアウト）し、ユーザーに機能が利用不可であることを伝える。
   - エラーが発生した場合や未対応ブラウザでもアプリ自体は動作するようにフォールバック（例外処理）を記述すること。
5. **Control**:
   - 「LEVEL CLEAR」ボタン：画面下部に固定配置。一括ですべてのカウントをリセットする。

# Output
JavaScriptコード内で `fetch('./enemies.json')` を使用し、すべてのロジックを含むシングルHTMLファイルを出力してください。
