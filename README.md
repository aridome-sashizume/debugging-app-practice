# debugging-app-practice

## 概要
COACHTECH 教材 Tutorial 10-4「デバッグ ハンズオン演習」で作成した成果物です。
ユーザ登録フォームからユーザ登録するプログラム
ユーザ登録時に当初のプログラムがエラーが派生していたため、デバッグツールを利用して、原因を確認し修正した。

## 使用技術
- PHP 8.x
- Laravel 10.x
- デバッグツール（`dd()`, `dump()`, `Log` ファサード）
（**他に使ったものがあれば追記してください**）

## 学んだこと
- Laravelエラー時のエラー原因および確認方法
    - 今回は'Add [title] to fillable property to allow mass assignment on [App\Models\Post].'のエラーが発生
    - モデルに$fillable（Eloquent ORMのマスアサインメントを定義）が足りていないことが原因だった
- ddやLogの挙動を確認した
    - dd()　Dump and Die：変数の内容を表示して処理を停止
    - Log：\Log::info() でログを出六
    - tail -5 storage/logs/laravel.logで5行分のログを出力

## 動作確認
1. Githubからリポジトリをクローン
```
git clone git@github.com:aridome-sashizume/debugging-app-practice.git
```
2. sailを起動
```
./vendor/bin/sail up -d
```
3. http://localhost/users/create にアクセス