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
Updating 'java' bucket...
Updating 'main' bucket...
Scoop was updated successfully!
Installing 'openjdk11' (11.0.2-9) [64bit]
Loading openjdk-11.0.2_windows-x64_bin.zip from cache
Checking hash of openjdk-11.0.2_windows-x64_bin.zip ... ok.
Extracting openjdk-11.0.2_windows-x64_bin.zip ... done.
Linking ~\scoop\apps\openjdk11\current => ~\scoop\apps\openjdk11\11.0.2-9
'openjdk11' (11.0.2-9) was installed successfully!
```
Java のインストールが完了した。

## Java のバージョン確認
Java がインストールできていることを、次のコマンドで確認する。
```console
java --version
```
実行結果:
```
openjdk 11.0.2 2019-01-15
OpenJDK Runtime Environment 18.9 (build 11.0.2+9)
OpenJDK 64-Bit Server VM 18.9 (build 11.0.2+9, mixed mode)
```

## はじめての Java ファイル作成
次のコマンドを実行して「Hello world.」を出力する毎度おなじみの Java ファイルを作成する。
```console
echo 'public class App {
    public static void main(String[] args) {
        System.out.println("Hello world.");
    }
}' > ./App.java
```
コードが書き込まれたか、確認する。
```console
cat ./App.java
```

## はじめての Java 実行
次のコマンドで作成した `App.java` ファイルをコンパイルする。
```console
javac ./App.java
```
これでカレントディレクトリに、コンパイルされた `App.class` ファイルが生成される。

`java` コマンドでこのクラスファイルを実行する。

```console
java App
```
実行結果: 
```
Hello world.
```

インストールした Java で、Java ファイルのコンパイルと実行までできることが、確認できた。
