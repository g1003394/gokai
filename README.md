# 第5回課題
## URLとは
Uniform Resource Locatorの略、インターネット上のホームページやファイルの位置や情報を示すもの、アドレスとも呼ばれる。

アドレスバーに表示されているhttpもしくはhttpsから始まる半角英数の文字列。

## クエリ文字列とは
別名URLパラメーターとは、サーバーに情報を送るためにURLの末尾に付け足す文字列（変数）のこと。「？」をURLの末尾につけ、その次に「パラメーター＝値」をつけ、複数のパラメーターを付けたい場合は「＆」を使用する。この形式でサーバーに送信したいデータをURLに付け加えることが可能。

## パス変数とは
ファイル・システム上のロケーションを指定する。使用することによって、ディレクトリー構造をファイル・システムとまったく同じにすることなく、リンクされたリソースを含むプロジェクトをワークスペースおよびコンピューター間で移植可能な状態に保つことができる。

## クエリ文字列とパス変数の違いとは
**見え方の違い**

<img width="689" alt="スクリーンショット 2024-02-27 15 53 47" src="https://github.com/g1003394/gokai/assets/153340889/a52b9c01-2f8a-4abb-9a6e-027bdbfa052c">

①と②の見た目違いとして「search」の後に「?〜」が」あるかどうか

①のパスパラメータはsearchの部分になる
②の場合、パスパラメータは①と同じくsearch、クエリパラメータは?q=Laravel

_中身の違い_

例:株式会社アニメ（ドメイン：Anime.co.jp）に営業部（Sales）があり、チームが以下のように分かれているとする

<img width="146" alt="スクリーンショット 2024-02-27 15 58 55" src="https://github.com/g1003394/gokai/assets/153340889/8288f6f0-4791-4f58-818a-0e99953d26a0">

チームの中のユーザーは以下の通り

<img width="228" alt="スクリーンショット 2024-02-27 16 00 36" src="https://github.com/g1003394/gokai/assets/153340889/808fe79c-8534-4150-b3a1-e5d14473ed3e">

営業部のIsono（磯野）チームのページを表示するとなるとURIは以下のようになる.

https://Anime.co.jp/sales/{group_id}

パスパラメータは特定のもの（画面など）を表示したいときに必要になります。

// IsonoチームのSalesTableidは「１」

https://Anime.co.jp/sales/1

もし、メンバー一覧を画面表示にしたい場合は、下記のURIとする。

https://Anime.co.jp/sales/1/members

クエリパラメータは特定のもの（画面など）に条件を加える場合に必要になります。

例：上記のメンバー一覧から特定の人を検索したい場合（今回はID検索と想定）
今回はUsersTableのID:3（ワカメ）を検索（条件の追加）します。

https://Anime.co.jp/sales/1/members/3

参照：https://zenn.dev/eri_agri/articles/859a3362db8386

## httpメソッドとは
1. GET

リソース情報を取得する

2. POST

新しいリソース情報を送り込む

3. PUT

リソース情報を新しい情報で置き換える

4. PATCH

リソース情報の一部を新しい情報で書き換える

5. DELETE

リソース情報を削除する

## リクエストヘッダーとは

HTTPリクエストで使用されるHTTPヘッダーであり、メッセージの内容には関連しないもの。要求内容の詳細を記述する。

クライアントからサーバーへの要求であるHTTPリクエストの前半にある制御情報を記した領域のこと。

Accept,Accept-*,If-* などのリクエストヘッダーは、条件付きリクエストを行うことができる。

## HTTPステータスコードとは

HTTPにおいてWebサーバからのレスポンスの意味を表現する３桁の数字からなるコード。

### 200 OK

リクエストは成功し、レスポンスとともに要求に応じた情報が返される。

### 201 Created

リクエストは完了し、新たに作成されたリソースのURIが返される。

例：PUTメソッドでリソースを作成するリクエストを行ったとき、そのリクエストが完了した場合に返される。

### 400 Bad Request

リクエストが不正である。定義されていないメソッドを使うなど、クライアントのリクエストがおかしい場合に返される。

### 404 Not Found

未検出。リソース・ページが見つからなかった。

単にアクセス権がない場合などにも使用される。また、単に要求に答えられない理由を誤魔化すためにも使われる。

### 500 Internal Sever Error

サーバ内部エラー。サーバ内部にエラーが発生した場合に返される。

例として、CGIとして動作させているプログラムに文法エラーがあったり、設定に誤りがあった場合などに返される。

CGI：ウェブサーバ上でユーザプログラムを動作させるための仕組み。現存する多くのウェブサーバプログラムはCGIの機能を利用することができる。

## レスポンスヘッダーとは

レスポンスについての追加情報、例えば場所やサーバー自身についての情報（名前、バージョンなど）を含むヘッダー。

## レスポンスボディとは

Webサーバーからブラウザに返される実際のレスポンスデータのこと。HTML文書やCSS、JavaScriptなどのデータが含まれる。

## JSONとは

JavaScript Object Notationの略で、JavaScriptというプログラム言語におけるオブジェクトの書き方を参考に作られたデータフォーマット（データの記述形式）のこと。

人間とコンピューターの双方にとって可読性が高く、データが重くなりづらいという優れた特徴を持つため、Pythonなど多様な言語で用いられている。

記述形式「{“キー”、“値”}」

対応しているデータ型

1. 文字列型

ダブルクォーテーションで囲めばひらがなや漢字を扱うこともできる。

2. 数値型

数値はダブルクォーテーションで囲まない、囲むと文字列になってしまう。

3. bool

4. null

項目として用意されているものの該当する値が無い時に使う。囲まない。

## Jsonを使用したデータ表現

``` json
“IdolName”:[
 { “id” : 1 , “name” : “葛之葉雨彦” , “blood type” : “O” ,“age” : 30 },
 
 { “id” : 2 , “name” : “北村想楽” , “blood type” : “B” ,“age” : 19 },
 
 { “id” : 3 , “name” : “古論クリス” , “blood type” : “AB” ,“age” : 29 }
]
```
