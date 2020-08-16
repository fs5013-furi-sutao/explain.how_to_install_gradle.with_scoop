# Gradle をインストールする（Scoop を使って）
Gradle をインストールする。

今回はインストールツールとして Scoop を利用する。Scoop が何か分からない、まだ導入していない場合は、以下のページを参照する。

[Scoop とは（メリットと使い方）](https://github.com/fs5013-furi-sutao/explain.scoop)

## アプリの場所を探す
Scoop でアプリのマニフェスト（対象アプリをインストールする手順書）のリポジトリ（マニフェストが置かれた場所）を探すには、以下のコマンドを実行する。

```console
scoop search gradle
```
実行結果例:
```
'main' bucket:
    gradle-bin (6.6)
    gradle (6.6)
```
上記の場合、実行結果例を見ると、`main` バケットにあると言っている。

## バケット一覧を表示する
ローカルのバケット一覧を表示してみる。
```console 
scoop bucket list
```
実行結果例:
```
main
```
上記の場合、ローカルには `main` バケットがあり、Gradle をインストールするためのマニフェストは手元にあることになるので、そのままインストールを進める。

## Gradle のインストール
準備が整ったので、次のコマンドで Java をインストールする。
```console
scoop install gradle
```
実行結果:
```
Updating Scoop...
Updating 'main' bucket...
Scoop was updated successfully!
Installing 'gradle' (6.6) [64bit]
Downloading https://services.gradle.org/distributions/gradle-6.6-all.zip (138.4 MB)...
Checking hash of gradle-6.6-all.zip ... ok.
Extracting gradle-6.6-all.zip ... done.
Linking ~\scoop\apps\gradle\current => ~\scoop\apps\gradle\6.6
Creating shim for 'gradle'.
'gradle' (6.6) was installed successfully!
```
Gradle のインストールが完了した。
