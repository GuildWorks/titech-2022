---
marp: true
theme: gaia
size: 16:9
header: '　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　Copyright Ryo Imahashi'

page_number: true
paginate: true
---

**Programming Boot Camp**

# Adaloの基本

**東京工業大学 2022/11/5**
　
　
　
　
　
　　　　　　　　　　　　　　　　　　　　　　　　**Ryo Imahashi**

---
## 目次
  - Adaloとは
  - Adaloに登録しよう
  - テンプレートアプリを操作してみよう
  - Adaloでのアプリ開発の概要説明
  - アプリを作ってみよう
  - 演習
  - まとめ

---
## Adaloとは
- [Adalo](https://www.adalo.com/)は、アメリカ発のノーコードツールです。プログラミング不要でアプリを開発することができます。
- 用意されているパーツから使用したいものを選び、それを画面にドラッグ＆ドロップしていくことで、アプリを作ることが可能です。
- ブラウザで表示するWebアプリだけでなく、AndroidやiOS向けのスマートフォンアプリも開発できます。開発したアプリのGooglePlayやAppStoreでの公開も可能です。


---
#### Adaloで作られたアプリの例
- Union: https://union-jp.site/
  - 大学生が開発した、大学生・大学院生・大学教員・大学職員限定のSNS
  - 2021年に1,000万円の資金調達を実施している
    - https://prtimes.jp/main/html/rd/p/000000001.000076669.html
- その他にも、 #MadeInAdalo でたくさん紹介されています
  - https://www.adalo.com/made-in-adalo
---
## Adaloに登録しよう
- AdaloのSignUp画面にアクセスしてください
  - https://app.adalo.com/signup
![w:800px](images/signup.png)

---
- 無料で登録できます
- ご自身のEメールアドレス、パスワード、フルネームを入力してください
- 利用規約への同意のチェックを入れてください
- LET'S DO THIS! ボタンを押して、次の画面に進んでください

---

#### 参考: [無料プラン](https://www.adalo.com/pricing)の制限
<!-- ![w:900px](images/pricing.png) -->
- 外部アプリケーションとの連携ができない
  - ただし、14日間はトライアル利用が可能
<!-- - ドメインを変更できない(Adaloのドメインになる)
- ロゴの変更ができない(Adaloのロゴが表示される)
- GooglePlayやAppStoreへの申請ができない -->
- 1アプリで登録できるデータベースのレコード数の上限が200件
- 月間アクション(ボタンクリック時等に行われる処理)回数の上限が1000回

:white_check_mark: 実際にサービスを運用していく際は、有料プランへの移行を検討してください

---
#### プラットフォームの選択
- Native Mobile AppとDesktop Web Appが選べます
- 今回は、Native Mobile Appを選択しましょう
![bg 90% right](images/select-native-mobile-app.png)
---
#### テンプレートの選択
- 完成されたアプリがテンプレートとして提供されています
- 今回は、Chatを選択しましょう
![bg 90% right](images/2022-11-04-23-15-25.png)

---
#### ブランディング

- App Name、Primary Color、Secondary Colorを自由に入力してください
  - Primary Colorは、アプリで最も使われるベースになる色です
  - Secondary Colorは、目立たせたい時に使う色です。重要なボタンなどに使われます。
![bg 90% right](images/branding-chat-app.png)
<!-- - ADVANCED OPTIONSは変更せず、そのままで大丈夫です -->
---
- このようなAdaloの管理画面が表示されたらOKです
- 今後はこの管理画面を使って、アプリを開発していきます
![w:900px](images/dev-tool-of-chat-app.png)

---
## テンプレートアプリを操作してみよう
- まずはAdaloで作ったアプリがどのように動作するかを確認するために、先ほど選択したChatアプリを操作してみましょう
- 画面右上のPreviewボタンをクリックしてください

![w:1100px](images/preview-button.png)

---
- プレビュー画面が起動します
- 一緒にChatアプリを操作してみましょう
![w:800px](images/chat-app-preview.png)

---
- Signupしましょう
  - EmailとPasswordはメモしておいてください(後で使います)
![bg 50% right](images/chat-app-signup.png)

---
- プロフィール写真を追加しましょう
![bg 50% right](images/2022-11-02-07-48-39.png)

---
- まだ会話が行われていないため、リストが空の状態です
- 画面右下の + ボタンを押してみましょう
![bg 50% right](images/chat-app-no-conversation.png)

---
- サンプルユーザーのリストが表示されます
- 一人を選んでクリックしてください
![bg 50% right](images/2022-11-02-07-51-03.png)

---
- メッセージを送信できます
![bg 50% right](images/2022-11-02-07-54-34.png)

---
- 作ったアプリを他の人にシェアして会話してみましょう
- Previewモードを左上の×ボタンで閉じて、メニューにあるSHAREをクリックしてください

![w:1100px](images/share-button.png)

---
- SHARE APPボタンをクリックして、COPY LINKを選択してください
- コピーしたリンクを、参加者全員が見られるようにSlackに投稿しましょう
  <!-- - TODO: 時間がかからないようにペアを作るなどの工夫が必要 -->
![w:800px](images/share-chat-app.png)

---
- 他の人の投稿したリンクをクリックしてその人のアプリにSignupし、メッセージを送りましょう
  - ユーザーのリストにアプリの作成者(と他の登録者)が表示されると思います
![bg 50% right](images/start-conversation.png)

---
- (みんなのアプリにメッセージが送られたであろう頃に、)
自分のアプリのPreview画面をもう一度表示してください
  - メッセージが届いているはずなので、クリックして表示してみましょう
![bg 50% right](images/2022-11-02-07-58-19.png)

---
- メッセージが受信できました :tada:
![bg 50% right](images/2022-11-02-07-59-15.png)

---
- 今回試したChat以外にも、いくつかのテンプレートが提供されています。
- 自分たちが作りたいアプリに近いものがあれば、そのテンプレートを流用して開発スピードをアップさせられるかもしれません。時間がある時に、他のテンプレートも試してみましょう。

---
## Adaloでのアプリ開発の概要説明
次に、Adaloでのアプリ開発の概要を説明していきます。

---
### 3つの基本コンセプト
- 基本となる以下3つのコンセプトについて紹介します
  - Components
  - Database
  - Actions

--- 
#### Components
- ユーザーインターフェースを作るために画面上に配置される要素。
- 例:
  - リスト
  - ボタン
  - テキスト
  - 画像
![bg 35% right](images/components.png)

---
#### Database
- 整理されたデータの集合。
- データの登録、読込(表示)、更新、削除が行われる。
- 例: Chatアプリの場合
![w:400px](images/2021-10-19-23-49-03.png)
<!-- ![w:570px](images/2021-10-19-23-39-29.png) -->
![bg 35% right](images/2021-10-19-23-13-47.png)

---
#### Actions
- 特定のコンポーネントをクリックした時に何を行うかを指定するために使われる。
<!-- - コンポーネントとそこで表示するデータベース内のデータを紐付けたり、ユーザー体験をカスタマイズする。 -->
- 例:
  - 別の画面に遷移させる
  - データベースのデータを登録、更新、削除する
![bg 35% right](images/2021-10-19-23-12-42.png)

---
### Adaloの機能説明
次に、Adaloの管理画面で利用できる機能を紹介していきます
![w:900px](images/dev-tool-of-chat-app.png)

---
#### Canvas
- 画面を作る作業領域
- 要素を選択したり、ドラッグアンドドロップで動かしたりできる
![w:680px](images/canvas.png)
<!-- - スクロール、拡大、縮小ができる -->
<!-- ![w:650px](images/2021-10-19-23-57-52.png) -->

---

#### Left Toolbar
左側のツールバーの各機能を紹介します。

![w:60px](images/2022-11-02-08-00-18.png)

---
###### ![w:60px](images/add-panel.png) Add Panel
- コンポーネントや画面を選択してアプリに追加できる
![bg right 95%](images/2021-10-20-00-37-54.png)
![bg right 93%](images/2021-10-20-00-44-42.png)
<!-- 画面とコンポーネントの追加を実演する -->
---
###### ![w:60px](images/2021-10-20-00-52-07.png) Branding
- 色やフォントを変えられる
![bg right 100%](images/2021-10-20-00-50-02.png)
![bg right 92%](images/2021-10-20-00-50-42.png)
<!-- 色とフォントの変更を実演する -->
---
###### ![w:60px](images/2021-10-20-00-54-44.png) Screens
- 画面の一覧や、その画面の構成を表示できる
![bg right 100%](images/2021-10-20-01-18-20.png)
![bg right 93%](images/2021-10-20-01-14-53.png)

---
###### ![w:60px](images/2021-10-20-01-20-56.png) Database
- データベースの構成や保存されているデータを表示できる
- Collection: 同じ属性(プロパティ)を持ったデータの集まり
![w:214px](images/2021-10-20-01-38-57.png) ![w:878px](images/2021-10-20-01-30-09.png)

---
###### ![w:60px](images/2021-10-20-01-45-09.png) Settings 
- アプリの名前やアイコンを設定できる
- キャンバスに関する表示設定ができる
- アプリへのアクセス権限の設定ができる
- アプリの複製や削除ができる
- 位置情報機能を使うためのAPIキーの設定ができる
![bg right 90%](images/2022-11-04-23-24-28.png)

---
###### ![w:60px](images/2021-10-20-01-56-00.png)Publish
- 作ったアプリを公開できる(有料プランのみ)
![bg right 90%](images/2021-10-20-01-59-11.png)

---
###### ![w:60px](images/2021-10-20-02-06-34.png) Analytics
- 利用状況を分析したレポートを見ることができる
![bg right 90%](images/2021-10-20-02-07-44.png)


---
###### ![w:60px](images/2022-11-02-08-01-35.png) Version History
- バージョン履歴を作成したり、アプリをバージョン履歴作成時と同じ状態に戻すことができる(有料プランのみ)
![bg right 80%](images/2022-11-04-23-29-30.png)

---
#### Top Bar
上部のツールバーの各機能を紹介します。

![w:1150px](images/2021-10-20-02-11-14.png)

---
###### App Switcher
- 開いているアプリの名前が表示される
- アプリを切り替えられる
- 新しいアプリを追加できる

![bg right 90%](images/2021-10-20-02-27-22.png)


---
######  Preview
- アプリを実行して試すことができる
- 画面サイズの異なるデバイスに切り替えて表示の確認ができる
![w:830px](images/2021-10-20-02-42-08.png)

---
###### Share
- アプリをシェアして他の人に使ってもらうことができる。
  Adaloのアカウントを持っていない人でも利用可能。
![w:830px](images/2021-10-20-02-44-28.png)

---
###### Account Menu
- 各種設定ができる
- ヘルプやドキュメントを開ける
- ログアウトできる
![bg right 90%](images/2021-10-20-02-56-33.png)
---
#### 開発に役立つTipsを覚えておこう
- 間違って編集してしまった時は、Windowsなら`Ctrl + Z`、Macなら `Command + Z ` で元に戻せます
- Adaloの開発ツールでは、日本語の直接入力がうまくいかないことがあります。日本語のテキスト入力はコピー＆ペーストで行ってください。

---
## アプリを作ってみよう
次に、新しくアプリを作ってみましょう。

<!-- 
データベースにはあまり触れずに作るには？
  - 静的サイトとして作る？
  - データベースは作成済みのテンプレートをクローンしてもらう？ -->

- 今回のレクチャーでは、データベースを使わない静的な(いつどのユーザーがアクセスしても表示される内容が変わらない)画面を作成します。
- 次回のレクチャーで、データベースを使った動的な(ユーザー毎に表示される内容が変わる)画面に仕上げていきます。
<!-- 例: https://kt-life.net/seitekisite-doutekisite/# -->

---
#### 作りたいアプリのUI
ペットの健康管理アプリを作ってみましょう。
まずはUIを確認していきます。

![h:383px](images/2021-10-20-06-09-56.png)![h:383px](images/2021-10-20-06-16-03.png)![h:383px](images/2021-10-22-02-23-09.png)![h:384px](images/2021-10-22-02-40-24.png)![h:383px](images/2021-10-22-04-07-06.png)![h:383px](images/2021-10-22-16-42-42.png)
<!-- ![h:385px](images/2021-10-20-05-02-23.png)![h:385px](images/2021-10-20-05-06-03.png)![h:385px](images/2021-10-20-04-40-45.png)![h:385px](images/2021-10-20-04-35-13.png)![h:385px](images/2021-10-20-04-36-11.png)![h:385px](images/2021-10-20-04-36-37.png) -->
<!-- ![h:380px](images/2021-10-20-04-37-19.png) -->


---
###### 会員登録画面
- 以下の項目を入力して会員登録できる
  - Email
  - Password
  - Full Name
- 会員登録済の人向けに、ログイン画面へのリンクがある
![bg right h:700px](images/2021-10-20-06-09-56.png)

---
###### ログイン画面
- 以下の項目を入力してログインできる
  - Email
  - Password
- パスワードを忘れた人向けのリンクがある
- 会員登録画面へのリンクがある
![bg right h:700px](images/2021-10-20-06-16-03.png)

---
###### ペット登録画面
- 名前を入力できる
- 写真を選択できる
- 誕生日を入力できる
- 登録ボタンで確定し、ペット一覧画面に遷移できる
![bg right h:700px](images/2021-10-22-02-23-09.png)

---
###### ペット一覧画面
- 登録したペットが一覧で表示できる
- ペットをクリックすると、そのペットのペット詳細画面に遷移できる
- 右下のアイコンを押すと、ペット登録画面に遷移できる
![bg right h:700px](images/2021-10-22-02-40-24.png)

---
###### ペット詳細画面
- 体重記録画面へのリンクがある
(Link2は演習用)
- 誕生日が表示される
- 最新の体重が表示される
![bg right h:700px](images/2021-10-22-04-07-06.png)

---
###### 体重記録画面
- 体重の遷移を示すグラフが表示される
- 現在の体重を入力できる
- ボタンを押して体重を追加できる
![bg right h:700px](images/2021-10-22-16-42-42.png)

<!-- ---
###### 活動記録画面
- 
![bg right h:700px](images/2021-10-20-04-37-19.png) -->


---
#### アプリ作成
それでは、実際にアプリを作っていきます。

- CREATE NEW APPを選択してください
![bg right 90%](images/2021-10-20-05-31-12.png)

---
- Native Mobile Appを選択してください
![bg right 90%](images/select-native-mobile-app.png)

---
- テンプレート: Blankを選択してください
![bg right 90%](images/2021-10-20-05-35-47.png)

---
- App Name、Colorを自由に決めてください
![bg right 90%](images/2022-11-04-23-51-03.png)

---
- アプリができました
![h:550px](images/2021-10-20-05-45-06.png)

---
###### 会員登録画面、ログイン画面

:white_check_mark: 会員登録画面、ログイン画面はデフォルトで生成されるようになっています。
![h:400px](images/2021-10-20-05-53-24.png)

---
プレビュー機能で動作を確認してみましょう。

- 会員登録画面
  - 会員登録をすると、Home画面に遷移します
  - Home画面右上のアイコンからログアウトしましょう
![bg right h:600px](images/2021-10-20-06-09-56.png)
![bg right h:600px](images/2021-10-20-06-11-03.png)

---
- ログイン画面
  - 先程会員登録したのと同じEmail、Passwordでログインすると、Home画面に遷移します

![bg right h:600px](images/2021-10-20-06-16-03.png)
![bg right h:600px](images/2021-10-20-06-11-03.png)

---
会員登録画面、ログイン画面はそのままで問題ないことがわかりました。
その他の4画面を作成していきましょう。

---
###### ペット登録画面
- 名前を入力できる
- 写真を選択できる
- 誕生日を入力できる
- 登録ボタンで確定し、ペット一覧画面に遷移できる

こちらの画面を作りましょう
![bg right h:700px](images/2021-10-22-02-23-09.png)

---
- ADD SCREENからApp Barを選択します
![bg right h:700px](images/2021-10-20-06-26-12.png)

---
- Screen Nameを入力します
![w:900px](images/2021-10-20-06-28-11.png)


---
Screenが追加されました。

この上に必要なコンポーネントを追加していきます。

![bg right h:700px](images/2021-10-20-06-37-56.png)

---
- ADD COMPONENTからTextを選択します
![bg right h:500px](images/2021-10-20-06-47-19.png)

---
- 画面上に配置します
![bg right h:500px](images/2021-10-20-06-49-18.png)

---
- Textの値をNameに変えます
![bg right h:500px](images/2021-10-20-06-52-11.png)

---
- 同様に、ImageとBirthdayというTextも追加します。
![bg right h:500px](images/2021-10-20-07-02-04.png)

---
- ADD COMPONENTからText Inputを選択します
![bg right h:500px](images/2021-10-20-06-53-05.png)

---
- 画面上に配置し、Placeholderの値をEnter Nameに変更します
![bg right h:480px](images/2021-10-20-07-03-27.png)

---
- ADD COMPONENTからImage Pickerを選択します
![bg right h:480px](images/2021-10-20-07-05-23.png)

---
- 画面上に配置します
![bg right h:480px](images/2021-10-20-07-06-54.png)

---
- ADD COMPONENTからDate Pickerを選択します
![bg right h:480px](images/2021-10-20-07-08-35.png)

---
- 画面上に配置し、StyleをDate Pickerに変更します
![bg right h:480px](images/2021-10-20-07-10-35.png)

---
- ADD COMPONENTからButtonを選択します
![bg right h:480px](images/2021-10-20-07-12-13.png)

---
- 画面上に配置します
- Textの値をRegisterに変更します
- Button ColorをSecondaryに変更します
- Icon & Text ColorをDefault Background(White)に変更します
![bg right h:530px](images/2021-10-22-02-19-14.png)

---
ペット登録画面の見た目を確認してみましょう。
- まだ導線がなく、画面遷移をして表示することができないので、ログイン後の遷移先であるHome Screenに設定します
- Screensからペット登録画面を選び、Screen Navigation TypeをHome Screenに変更しましょう
![bg right h:400px](images/2021-10-20-07-28-52.png)
---
- プレビュー機能でログインをすると、ペット登録画面が表示できます。
- 名前の入力、画像の選択、誕生日の選択ができます。
- まだRegisterボタンを押しても何も起きません

これで、ペット登録画面のUIは完成です。
![bg right h:700px](images/2021-10-22-02-23-09.png)

---
###### ペット一覧画面
- 登録したペットが一覧で表示できる
- ペットをクリックすると、そのペットのペット詳細画面に遷移できる
- 右下のアイコンを押すと、ペット登録画面に遷移できる
![bg right h:700px](images/2021-10-22-02-40-24.png)

次は、こちらの画面を作りましょう

---
- ADD SCREENからApp Barを選択して、Screen Nameを入力してください
![bg right h:700px](images/2021-10-20-06-26-12.png)

---
- ADD COMPONENTからImageを選択してください
![bg right h:700px](images/2021-10-21-23-24-54.png)

---
- 画面上に配置してください
- Image Source -> Uploadから、ペットの写真をアップロードしてください
![bg right h:540px](images/2021-10-22-01-08-36.png)

---
- ADD COMPONENTからTextを選択してください
![bg right h:500px](images/2021-10-22-00-07-29.png)

---
- Textにペットの名前を入力し、文字色をWhiteに変更しましょう
- 選んだ写真によっては白い文字が見えづらくなりますので、次は文字を見やすくします
![bg right h:450px](images/2021-10-22-01-10-24.png)

---
- ADD COMPONENTからRectagleを選択してください
![bg right h:500px](images/2021-10-22-01-13-13.png)

---
- ペットの名前の上に重ねて配置してください
- Backgroundの色でBlackを選択した後、RGBAのAの値を10に変更してください
  - RGBAは色を表す形式のひとつで、色をRed、Green、Blueの三原色のそれぞれの強度と、透明度(Alpha)の組み合わせで表現します
![bg right h:500px](images/2021-10-22-01-23-50.png)

---
- Screensからペット一覧画面を選択し、Componentsの並び順でRectangleがTextよりも上になっていることを確認してください
  - 上にあるものが手前に表示されるため、今はRectangleがTextを隠してしまっています
<!-- ![bg right h:500px](images/2021-10-22-01-33-23.png) -->
![bg right h:500px](images/2021-10-22-01-38-45.png)

---
- 順番を入れ替えて、Textを一番上に、Rectangleを2番目にしましょう
  -  Textが手前に表示され、Rectangleのおかげで白い文字が見やすくなりました
![bg right h:500px](images/2021-10-22-01-41-54.png)

---
次に、ペットをもう一匹表示しましょう
- 追加した3つのコンポーネント(Image, Rectangle, Text)をCanvas上で選択し、MAKE GROUPをクリックします
![bg right h:500px](images/2021-10-22-01-53-38.png)

---
- 作成したGroupを選択した状態でコピー&ペースト(Windowsなら`Ctrl + C`と`Ctrl + V`、Macなら`Command + C`と`Command + V`)をして、複製されたGroupを下に配置します
![bg right h:700px](images/2021-10-22-02-01-32.png)

---
- 2つ目のImage、Textを別のペットのものに変更しましょう
![bg right h:700px](images/2021-10-22-02-06-16.png)

---
次に、ペット登録画面への導線を追加します
- ADD COMPONENTからAction Buttonを選択してください
![bg right h:370px](images/2021-10-22-02-11-11.png)

---
- 画面右下に配置してください
- Icon and Text ColorをDefault Background(White)に変更してください
![bg right h:500px](images/2021-10-22-02-26-03.png)

---
- ADD ACTION -> Link -> [ペット登録画面名] を選択してください
![bg right h:500px](images/2021-10-22-02-28-24.png)

---
ペット登録画面からペット一覧画面への導線も追加しておきましょう
- ペット登録画面のRegisterボタンを選択してください
- ADD ACTION -> Link -> [ペット一覧画面名] を選択してください
※ 導線を追加しただけなので、まだペットの登録はできません(データの登録は次回のレクチャーでやります)
![bg right h:500px](images/2021-10-22-02-33-55.png)

---
- SignUp画面のSIGNUPボタンとLogin画面のLOGINボタンの遷移先も、Homeからペット一覧画面に変更しておきましょう
<!-- ![](images/2021-10-22-03-50-48.png) -->
![bg right h:340px](images/2021-10-22-03-52-31.png)

---
- デフォルトで作成されていたHome画面は不要になったので、削除しましょう
![bg right h:480px](images/2021-10-22-03-57-57.png)
---
ペット一覧画面の見た目を確認してみましょう。
- ペット登録画面のプレビューをした時と同様に、ペット一覧画面のScreen Navigation TypeをHome Screenに変更してください
- プレビュー機能でログインをすると、ペット一覧画面が表示できます。

これで、ペット一覧画面のUIは完成です。
![bg right h:700px](images/2021-10-22-02-40-24.png)

---
###### ペット詳細画面
- 体重記録画面へのリンクがある
(Link2は演習用)
- 誕生日が表示される
- 最新の体重が表示される

次は、こちらの画面を作りましょう
![bg right h:700px](images/2021-10-22-04-07-06.png)

---
- ADD SCREENからInfo with Linksを選択して、Screen Nameを入力してください
![bg right h:650px](images/2021-10-22-02-58-46.png)

---
- Image Sourceでペット一覧画面で使用した写真をUploadしてください
![bg right h:500px](images/2021-10-22-03-05-37.png)


---
- TextをBirthdayというラベルとその値、Latest Weightというラベルとその値に書き換えましょう
![bg right h:700px](images/2021-10-22-03-18-32.png)

---
- Link 1というTextをWeihgt Logに変更しましょう
- Link 2はそのまま残しておきます
(最後の演習時間で作成した画面への導線として使ってください)

![bg right h:700px](images/2021-10-22-03-28-26.png)

---
ペット一覧画面からペット詳細画面に遷移できるようにしましょう
- ペット一覧画面の1匹目のペットに関するコンポーネントをまとめたGroupを選択し、ADD ACTION -> Link -> PetDetail とクリックしてください
  <!-- - この設定を2匹目のペットに関するコンポーネントをまとめたGroupにも設定しても良いです。ただし、ペット詳細画面はどちらのペットをクリックして遷移しても、同じ表示になります。 -->
![bg right h:450px](images/2021-10-22-03-31-30.png)

---
- プレビュー画面で表示を確認しておきましょう

ペット詳細画面のUIはこれでOKです。
![bg right h:700px](images/2021-10-22-04-07-06.png)

---
###### 体重記録画面
- 体重の遷移を示すグラフが表示される
- 現在の体重を入力できる
- ボタンを押して体重を追加できる

最後に、こちらの画面を作りましょう
![bg right h:700px](images/2021-10-22-16-42-42.png)


<!-- Chartコンポーネントは次回に回すので却下 -->
---
- ADD SCREENからApp Barを選択して、Screen Nameを入力してください
![bg right h:700px](images/2021-10-20-06-26-12.png)
<!-- ---
- ADD COMPONENTから、EXPLORE MARKETPLACEを選択してください
![bg right h:500px](images/2021-10-22-04-15-57.png) -->
<!-- ![](images/2021-10-22-04-18-00.png) -->
<!-- ---
- Chart KitをINSTALLしてください
![bg right h:500px](images/2021-10-22-04-19-03.png) -->
<!-- ---
- ADD COMPONENTのInstalled欄にChartのコンポーネントが追加されました
- Line Chartを選んで、画面上に配置してください
![bg right h:500px](images/2021-10-22-04-20-12.png) -->

---
- Chartの作成にはデータベースの準備が必要なので、これは次回のレクチャーで説明します
- 今回は、Chartの画像を貼り付けましょう
  - 画像は私からみなさんにSlackで共有します
  (右の画像のスクリーンショットを撮影してそれを使ってもOKです)
![bg right h:350px](images/pet-weight-log-chart.png)

---
- ADD COMPONENTからImageを追加して、Chartの画像をアップロードしてください
![bg right h:500px](images/2021-10-22-16-33-13.png)

---
- ADD COMPONENTから、Text Inputを追加してください
- TypeをNumberに変更してください
- PlaceholderをEnter current weightに変更してください
![bg right h:500px](images/2021-10-22-16-35-03.png)
---
- ADD COMPONENTからTextを追加してください
- 値をWeight(kg)に変更してください
![bg right h:500px](images/2021-10-22-16-35-39.png)

---
- ADD COMPONENTからButtonを追加してください
- TextをAddに変更してください
![bg right h:500px](images/2021-10-22-16-36-06.png)

---
ペット詳細画面から体重記録画面への導線を設定しましょう
- ペット詳細画面のText:'Weight Log'を含むGroupに対して、Click Actionで体重記録画面へのLinkを設定します
![bg right h:500px](images/2021-10-22-12-40-18.png)

---
- プレビュー画面で表示を確認しておきましょう

体重記録画面のUIはこれでOKです。
![bg right h:700px](images/2021-10-22-16-42-42.png)

---
アプリのUIを一通り作成することができました :tada:

![h:383px](images/2021-10-20-06-09-56.png)![h:383px](images/2021-10-20-06-16-03.png)![h:383px](images/2021-10-22-02-23-09.png)![h:384px](images/2021-10-22-02-40-24.png)![h:383px](images/2021-10-22-04-07-06.png)![h:383px](images/2021-10-22-16-42-42.png)

---
#### クローン用URL
- 以下のURLからアプリをクローンできますので、答え合わせに使ってください
https://previewer.adalo.com/014fd9d1-80c6-4325-899a-d943e778c865

![bg right h:400px](images/2021-10-22-17-31-06.png)

---
## 演習
- ペット詳細画面のLink 2の遷移先となる画面を自由に作成してみてください
- あるいは、好きなアプリを新しく作成してもOKです

できたらSlackでURLを共有して、みなさんに見てもらいましょう

![bg right h:500px](images/2021-10-22-18-37-12.png)

---
#### 演習における注意事項
- 名前に「List」とつくComponentやScreenは、次回のレクチャーでお伝えするデータベースとの紐付けが必要なので、使うのが難しいかもしれません。
  - 自分で解決できなければ、今日はそれ以外のもので代用することをお勧めします。
- NoCodeツールでは、簡単にアプリを作れる反面、複雑なUIや機能を実現できない場合があります
  - 行き詰まった時は、どうすれば自分がやりたいことをシンプルなUI、機能で実現できるか考えてみてください
    - 例: 1画面に多くのコンポーネントを含めず、画面を分ける 等

---
#### 演習結果の発表
(時間があれば)

演習で作った画面を紹介してみませんか？

---
## まとめ
- 今回のレクチャーでは、Adaloについて紹介し、ペットの健康管理アプリを題材にアプリのUIを作成しました。
  - データベースを必要としない、シンプルなコンポーネントだけを使っています。
- 次回のレクチャーでは、引き続きAdaloを使って、今回作ったUIに合わせたデータベースを構築し、アプリからデータを操作できるようにしていきましょう。 
  - データベースを使うことで様々な機能が実現できますし、UIを簡単に作ることも可能になります。お楽しみに！

---
# 以上です！
# お疲れさまでした！

