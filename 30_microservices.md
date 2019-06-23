# マイクロサービスアーキテクチャーの構築

## JHipster Registry を起動
```
git clone https://github.com/jhipster/jhipster-registry.git
cd jhipster-registry
npm install
./mvnw -Pdev,webpack
```

http://localhost:8761 で JHipster Registry にアクセスできる。

## アプリケーションの作成
```
mkdir my-first-microservice-app
cd my-first-microservice-app
jhipster
./mvnw
```

[JDLによるモデル層の設計](/10_import_jdl.md) で使ったJDLをインポートしてみる。
これによってモデル層のクラスが自動的に生成される。

```
jhipster import-jdl ../book_author.jh
```

## ゲートウェイの作成
```
mkdir gateway
cd gateway
jhipster
```

アプリケーションのタイプとして Microservice gateway を選択。

こちらでも[JDLによるモデル層の設計](/10_import_jdl.md) で使ったJDLをインポートしてみる。
これによってモデル層に応じたAngularのUIが自動的に生成される。

```
jhipster import-jdl ../book_author.jh
```

## 別のマイクロサービスを登録してみる
```
mkdir review-app
cd review-app
jhipster
```
