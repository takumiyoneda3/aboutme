# Takumi Yoneda — Personal Website

ビルド不要の6ページ静的サイト。HTML / CSS / JavaScriptのみで動作します。

## はじめに

`index.html` をブラウザーで開けます。外部ライブラリ・アクセス解析・サーバー処理はありません。写真はユーザー提供の24枚のみをローカルに同梱し、外部画像への通信はありません。

## GitHub Pagesで無料公開

1. GitHubにログインし、Publicリポジトリを作成します。
2. `takumi-yoneda` **フォルダーの中身**をリポジトリのルートへアップロードします。`index.html` が最上位になるようにします。`.nojekyll` も含めてください。
3. リポジトリの **Settings → Pages → Build and deployment** を開きます。
4. Sourceを **Deploy from a branch**、Branchを **main**、フォルダーを **/(root)** に設定し、Saveします。
5. デプロイ完了後、Pagesに表示されるURLを開きます。

アカウント名が `TakumiYoneda` で取得できれば、リポジトリ名を `TakumiYoneda.github.io` にすると `https://takumiyoneda.github.io/` で公開できます。通常のリポジトリなら `https://ユーザー名.github.io/リポジトリ名/` です。アカウント名の空き状況は未確認です。独自ドメインの取得費用は含まれません。

公式手順: https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site

## 写真を差し替える

- `assets/photo-0.jpg` から `photo-23.jpg` を自分の写真で置き換えます。横幅1400px程度、JPEGまたはWebPで200〜400KB程度を目安に圧縮します。
- `assets/content.js` の `photos` にある `src`、`alt`、`title`、`caption`、`category` は詳細シート・カルーセル用のデータです。
- 各HTMLにも初期表示用の画像・作品名・代替テキストがあります。**両方を変更**してください。拡張子を変える場合も両方のパスを変更します。
- 作品名は元ファイル名です。説明文は写真の内容を基に付けています。元画像は変更せず、最長辺1800pxの掲載用JPEGを作成しています。

掲載写真: © Takumi Yoneda。ユーザー提供ファイルの対応は `assets/content.js` の `source` を参照してください。元画像のメタデータは掲載用JPEGには引き継いでいません。

## 文章・連絡先

- 各HTMLを直接編集します。Aboutの経歴は未記入、Journalはサンプル、Favoritesは選定待ちです。実在する経歴やおすすめを捏造していません。
- `assets/content.js` の `email: ""` に本人の公開メールアドレスを設定すると、Contactにメール送信リンクとコピー操作が表示されます。空欄では準備中となります。
- 問い合わせフォームの送信機能はありません。メールアプリを開く方式です。メールアドレスは公開情報になる点をご確認ください。
- ナビゲーション・フッターは各HTMLにあります。構成を変える場合は6ページを揃えて更新してください。

## デザイン・操作

Material Design 3の色ロール、tonal surface、丸み、状態表示、44〜56pxの操作領域、easingに基づいたカスタム実装です。公式コンポーネントライブラリや適合認証ではありません。仕様参考: https://m3.material.io/ 、https://m3.material.io/styles/motion

- スケルトンは実際の画像読み込み中のみ表示。読込失敗時は説明を表示します。
- カルーセルは手動操作。自動再生はありません。
- モバイルメニュー、ボトムシート、写真拡大はネイティブ `dialog`。Escapeで閉じ、閉じた後は起点へフォーカスを戻します。
- FAQはネイティブ `details` / `summary`。
- スクロール登場、キネティック文字、制作プロセス図、hover/focusフィードバックを実装。
- OSの `prefers-reduced-motion` とフッターの手動設定に対応。OS設定を優先します。
- JavaScript無効時も各ページ・画像・FAQ・PC用ナビは閲覧可能。モバイルでJSを無効にする場合もフッター手前の下記案内から各HTMLを直接開けます。写真絞り込み・詳細などにはJavaScriptが必要です。

## 確認の目安

公開前にPCとスマートフォンで、メニュー、Tabキー、Escape、カルーセル両方向、フィルター、モーダル、FAQ、OSの動きを減らす設定、画像読込失敗、実際のメールリンクを確認してください。相対パスのためプロジェクト型GitHub Pagesにも対応します。

公開操作は未実施です。

## Portfolio

`portfolio.html` と `photography.html` は写真24枚のポートフォリオです。トップも写真一覧を中心に変更しました。白主体のニュートラルなM3色ロール、最小限の文字、元の縦横比を保つレイアウトです。画像の代替テキストはアクセシビリティのため保持しています。

## 最新版の構成

Homeは手動カルーセルと6枚の選抜、Photography / Portfolioは提供写真24枚すべてを掲載。Aboutは氏名と実際の収録写真のカテゴリー別件数を表示します。JournalとMusic & Favoritesは本人コンテンツが未提供のため準備中とし、以前のサンプル記事を取り除きました。Contactはメール未設定時に準備中と表示します。

動き: キネティック文字、画像の切り替え、スクロール登場、実データの棒グラフ、ボタンの状態変化。画像スケルトン・読込エラー表示、モバイルメニュー、パンくず、ボトムシート、拡大モーダル、手動カルーセル、アコーディオンを実装しています。自動再生・スクロールの乗っ取りはありません。OSと手動の動きを減らす設定に対応しています。

デザイン判断の参考:
- https://research.google/pubs/the-role-of-visual-complexity-and-prototypicality-regarding-first-impression-of-websites-working-towards-understanding-aesthetic-judgments/
- https://business.google.com/en-all/think/consumer-insights/navigating-purchase-behavior-and-decision-making/

低い視覚的複雑さと見慣れた操作体系を優先。探索・絞り込み・詳細閲覧の行き来に応用した設計であり、個人サイトへの効果を実測したものではありません。Material Design 3に基づくカスタム実装で、公式認証はありません。

## 感情デザインの調整

写真は1タップで拡大。情報は拡大画面のiボタンからボトムシートへ。Escapeで一段ずつ戻り、元の作品へフォーカスを戻します。拡大画面は左右キー・左右ボタン・横スワイプに対応。拡大画像の読み込みと失敗にも状態表示があります。トップ画像は全体を表示し、最後は縦写真を一枚置いて静かに終えます。

設計参考（心理効果を実測・保証したものではありません）:
- Don Norman: https://jnd.org/emotional-design-people-and-things/
- Fitts: https://lawsofux.com/fittss-law/
- Jakob: https://lawsofux.com/jakobs-law/
- Peak–End: https://lawsofux.com/peak-end-rule/
- Apple HIG: https://developer.apple.com/design/human-interface-guidelines/
- 視覚表現の参考: https://www.awwwards.com/

Material Design 3を基本に、Appleのガイドラインは操作性の補助参考としています。Awwwardsの作品画像・コードは転用していません。

Aboutのプロフィールは本人提供情報: 19歳、2007年5月生まれ、he/him、Japan。年齢19は2026年10月22日時点の固定表示です。誕生日の日は未提供なので自動更新していません。更新時はabout.htmlのAgeを変更してください。

Music欄だけに外部写真5点を追加しました。出典とライセンスはMUSIC-CREDITS.mdおよびページ内Photo creditsに掲載。写真ファイルは変更せず、ソロ写真の表示範囲はCSSで調整しています。外部画像はポートフォリオの24枚には含まれません。
