# git/Github講座

# 流れ
1. はじめに
2. 説明 & 実践
   - 基本説明
   - GitHubアカウント
   - フォーク
   - ステージ ~ プッシュ
   - 追加説明
3. 発展
   - README
   - Issues
   - GitHub Action
4. おわりに


# 台本
## はじめに
みなさん、こんな経験ありませんか

> (要らないコードをコメントで残す)

> (ソースコードを消してしまう)

> (共同開発中に変更点が分からない) etc.

え、プログラミングした事ない？！
そんな時に`git` `GitHub`があります  

本当はPC開いて、VScodeやターミナルでやりたかったのですが、
デスクトップだったり、そもそも持っていないという人もいると思うので、
今回はブラウザ版のVScodeで実践していきます。  
もし、自分のPCを持っている人は `git インストール方法` と調べれば色々出てくるのでやりながら聞いてください。

## 説明 & 実践
### 基本説明
はじめに関連するファイルたちのまとまりを `リポジトリ` と言います。  
リポジトリはローカルリポジトリとグローバルリポジトリの2つがあります。  
ローカルリポジトリは自分のPC内にあり、
グローバルリポジトリはクラウド上、具体的にはGitHubにあります。

自分だけのローカルリポジトリで変更後にリモートに上げて他の人と共有するという流れですね。  
変更をgitに保存することをコミットと言います。  
コミット後にリモートリポジトリにあげることができます。このことをプッシュといいます。  

コミットは変更を確定するイメージで、何度コミットしても

ただし変更後にすぐコミットするわけではなく一段階あります。
それはステージです。  
小さな変更はコミットせずにステージに置いておき、まとめてコミットします。  

例えばword,excelなどで色々変更して、
もし間違えていた場合どうしますか？  
保存前まで飛びたい場合はソフトを終了させて
保存した時点に戻るという事をする人もいると思います。  
それと同様なことをするのがステージです。

コミットは変更を確定するもので、何度コミットしても履歴として残るので、
後々遡ることが出来ます。

リモートリポジトリにプッシュするのは、クラウドにアップロードするイメージです。
クラウドに置けば自分のPC上から消してしまっても問題ないですね。  
また、誰かと共有したい場合も一々USBなどで渡さずともネットワーク経由から
受け渡しが出来ますね。だから共同開発するのに向いてるんですね。

ここまでの流れをまとめると、
1. ファイルを変更
2. 問題なければステージにあげる
3. ある程度できたらコミットする
4. その後、リモートリポジトリにプッシュする

といった感じです。では実践していきましょう。

### GitHubアカウント
最初にGitHubアカウントを作成します。  
`github.com` を開き、`sign up` を押します。  
流れに沿って登録を進めてください。  

左上の検索欄から `misc-org` と入力し `Users` を押した後に `MISC` を選択してください。  
これは情報システム部のリポジトリ達があるところです。  
右上の `Follow` を押してくれれば後で招待を送ります。  
`Repositories` を押すといろんなリポジトリがありますね。  
この中には 出席確認システム や 情報システム部のサイト aiboard のリポジトリなどがあります。  
今回の講座の台本もありますね!  
その中から `sample` を選んで開いてください。

### フォーク
右上の `Fork` から `Create fork` を押してください。  
フォークというのは他人のリポジトリをコピーすることです。

フォークとは何かというと通常は自分のPC上でローカルリポジトリを作ってから、
リモートリポジトリにするのですが、ブラウザのVScodeだけではできないので、  
既にあるリモートリポジトリを複製して自分のリモートリポジトリとしているのです。

図で見てみると、私がローカル上で作ったリポジトリをリモートに上げて、  
皆さんはそれを複製している感じです。  
私のPC上からは消しましたが、リモートでは問題なく存在しています。
フォークせずともこのように同一のリモートを変更することが出来ますが、  
同じ所を変更するとコンフリクトと言って現在のファイルと変更後のファイル、  
どちらの変更を使用するかを指定する必要があり、今回はやりたくないので別々のリモートリポジトリ上でやっています。

### ステージ ~ プッシュ
現在 [UserName]/sample というリポジトリにいると思います。そこでキーボードの `.` を押してください。  
するとブラウザ版VScodeで開くことが出来ます。

すると、左上のエクスプローラーを押すと `README.md` というファイルがあると思います。  
`新しいファイル` を押して `main.txt` というファイルを作成してください。  
開いたら適当に入力してください。  
すると `ソース管理` に `1` とバッジがついたと思います。

では `ソース管理` を開いてみてください。`変更` という欄に `main.txt` というのがあります。  
ファイル名をクリックすると変更点が確認できます。  

そしたらファイル名の横にある `プラス` マークを押してください。  
ファイルが `変更` から `ステージされている変更` に移動しました。  
これが `ステージ` というものです。

もう一回 `main.txt` を開いてさらに編集してください。  
なんとステージしていたのが `変更` に戻っています。
通常のVScodeでは、ステージにはステージした時点での変更が残るはずですがブラウザ版は残りません。
バグでしょうか...?

ではもう一回ステージに上げて、今回は `メッセージ` を入力して `コミットとプッシュ` を押してください。  
これで `コミット` と `プッシュ` ができました。  
通常のVScodeでは、コミットした後にプッシュするのですが、
ブラウザ版は直接リモートリポジトリを触っているせいで統合されているわけですね。

github を見てみるとちゃんと更新されていますね

### 追加説明
gitは簡単ですね!  
私は慣れるのに2ヶ月以上かかりました。

gitの基本的な使い方はわかったと思いますが、実際のVScode環境での手順を確認してもらいます。  

はじめにフォルダを作ります。  
VScodeを立ち上げて、このフォルダを開きます。  
`ソース管理` を開いて `リポジトリを初期化` を押します。  
エクスプローラーでファイルを生成し、編集します。  
ステージに上げます。  
さらに編集します。  
変更とステージ両方にありますね。  
`変更を破棄` を押すとステージした時点になります。  
もう一度編集し、ステージにあげるとステージが更新されました。  
コミットメッセージを入力し、コミットボタンを押します。  
VScodeの拡張機能でコミットの履歴を確認してみると、こうなっています。  
さらに変更し、コミットしてみます。  
するとこんな感じで履歴が積み重なっていますね。  
この繋がりを `ブランチ` と言います。  
ブランチを分岐させることもでき、共同作業をするときは機能ごとにブランチを分けて行って完成したらマージという分岐を繋げる作業をします。  

逆にGitHubにあるリポジトリを取得して更新するには  
VScodeを開き、`リポジトリの複製` からリポジトリを選択し、更新します。  
GitHubから持ってこれるのでリモートリポジトリにあげればパソコン上のフォルダーは削除しても問題ないんです!

これまでVScodeでのやり方を説明してきましたが、あくまでも拡張機能なんですね。  
本来は `git commit` みたいなコマンドをターミナルで実行し操作するものなので、
VScodeに慣れたらコマンドでもやってみるといいと思います。  
ということで基本的な使い方は以上です。

## 発展
### GitHubをよりよく
リポジトリには `README.md` というファイルがよくあります。  
ここにはリポジトリの説明や機能の説明などを書くファイルで GitHub でリポジトリを開くとトップで表示されます。  
なるべく書くようにしましょう。  

### Issues
そのリポジトリのプログラムに何か問題があったり、改善したい、新規追加したいものがあった場合どうしますか?  
そんなときどうしますか?  
一人ならメモ帳に書くとか、記憶頼りとかがありありますが、共同開発ではそういうわけにはいきません。  
そんな時に Issues というものがあります。  

実際に使っているものを見てみるとこんな感じですね。  
バグの報告や、欲しい新機能などがタグ付けされて保存されていますね。  
簡単に言うとメモ帳です。

### GitHubアクション
最初の方に情報システム部のサイトのリポジトリがあると言いました。  
なんとここにプッシュすると自動でサイトを更新してくれるんです。  
便利ですね!!これを実行しているのが `GitHub Action` というものです。  

## おわりに
今回ちょっと触ってみたりしましたが、どうでしょうか？  
本当に最低限しかやっていないので実際に触りながら調べながら慣れて行ってください。  
また、githubの練習したい場合は自分でリポジトリを作ってもいいし、  
`misc-org` には `daily-commit` というふざけたリポジトリがあり、  
Twitterのようにどうでもいい事を書きまくるリポジトリがあるのでそこで練習してもらっても大丈夫です。

以上でgit/GitHub講座を終わります。  
ありがとうございました。
