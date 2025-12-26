# ragrs-lite

本プロジェクトは、RAG（Retrieval Augmented Generation）の仕組みを理解することを目的とした
学習・検証用途向けのサンプル実装です。

商用利用や本番環境での運用は想定していません。

## 構成

本プロジェクトでは、以下のような **最小構成の RAG パイプライン**を Rust で実装することを目指しています。

- FastEmbed によるデータのベクトル変換
- LanceDB を利用したデータの保存
- ベクトル検索によるデータの取得

## 依存関係

### Rust クレート

本プロジェクトでは以下のライブラリを使用しています。

- **fastembed**  
  文章をベクトルに変換する埋め込みエンジン

- **lancedb**  
  ベクトルの保存および近傍検索を行うファイルベースのデータベース

- **tokio**  
  非同期処理を行うためのランタイム

### システム依存関係

ビルド時にネイティブコードを使用するため、以下のパッケージが必要です。

#### Linux(RHEL系)

```bash
dnf install gcc gcc-c++
dnf install openssl-devel protobuf
dnf --enablerepo=crb install protobuf-devel
```
