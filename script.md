# git/Github講座

# 流れ
1. はじめに
2. VScode,gitのインストール
3. git/GitHubについて
4. 実践
  - VScode
  - ターミナル
5. 発展
  - GitHubをより良く
  - GitHub Action
  - gitmoji


# 台本
## はじめに
みなさん、こんな経験ありませんか

> (要らないコードをコメントで残す)

> (ソースコードを消してしまう)

> (共同開発中に変更点が分からない) etc.

え、プログラミングした事ない？！
そんな時に`git``GitHub`があります  
`git, Githubとは` についての前に先にインストールを進めておきましょう

## VScode,gitのインストール
### VScodeのダウンロード
プログラミングをする上でエディタは必要ですが、
今回は王道の`VScode`を使用したいと思います。

ブラウザで`VScode ダウンロード`と調べて、
この[サイト](https://code.visualstudio.com/download)
からそれぞれの環境に合うものをダウンロードしてください

ダウンロード出来たら適当に押してインストールを完了してください

### gitインストール
#### Windows
はじめにWindowsです。
Mac,Linuxの人は待っててください。
出来そうなら右側を見ながら進めてください。

`TODO`

#### Mac
Macの人ははじめに `brew` というパッケージ管理システムをインストールします。  
これはMacで色んなものをインストールする時に使えるものです(適当)  

はじめにターミナルを開きます。  
ハッカーが使ってそうなこのターミナルはマウスカーソルを動かしてアイコンをクリックして使うGUIに対して、
コマンドでPCを操作するCLIと呼ばれるもので制御できるやつです。  
GUIとCUI、習いましたね？そういうことです

```zsh
brew --version
```
この[サイト](https://brew.sh)からコマンドをコピべしてください  
```zsh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
続いてbrewを使ってgitをインストールします
```zsh
brew install git
```
`git --version` と入れてバージョンが出てきたらOKです。
