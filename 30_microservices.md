# マイクロサービスアーキテクチャーの構築

## JHipster Registry を起動
```
git clone https://github.com/jhipster/jhipster-registry.git
cd jhipster-registry
npm install
./mvnw -Pdev,webpack
```

http://localhost:8761 で JHipster Registry にアクセスできる。

## アプリケーション(book)の作成
```
mkdir book-app
cd book-app
jhipster
./mvnw
```

アプリケーションのタイプとして Microservice application を選択。

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

## 別のマイクロサービス(review)を登録してみる
```
mkdir review-app
cd review-app
jhipster
```

アプリケーションのタイプとして Microservice application を選択。
同一ホストで動かすのでポート番号を8081から8082とかに変更する。

```
jhipster entity review
```

Book に対してのレビューを登録できるようなエンティティを作成する。
このとき、マイクロサービスをまたがって Book へのリレーションシップは作れない。そういうユースケースが必要になる場合はマイクロサービスの切り方の単位がよろしくない。

gateway の側で、
```
jhipster entity review
```

とすると、新しいエンティティ用のフロントエンドのコードも自動的に生成される。
