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

## 別のマイクロサービスを登録してみる
```
mkdir review-app
cd review-app
jhipster
```

本のレビューを登録するエンティティを作成する
```
jhipster entity review
```

ゲートウェイ側にUIを作成する
```
cd ../gateway
jhipster entity review
```

このとき、review-app で作成したエンティティの定義を参照できる。
```
$ jhipster entity review
INFO! Using JHipster version installed locally in current project's node_modules
INFO! Executing jhipster:entity review
INFO! Options: from-cli: true

The entity review is being created.

? Do you want to generate this entity from an existing microservice? Yes
? Enter the path to the microservice root directory: ../review-app

Found the .jhipster/Review.json configuration file, entity can be automatically generated!

? Do you want to update the entity? This will replace the existing files for this entity, all your custom code will be overwri
tten (Use arrow keys)
❯ Yes, re generate the entity
  Yes, add more fields and relationships
  Yes, remove fields and relationships
  No, exit
```
