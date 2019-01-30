# SonarQube (https://www.sonarqube.org) によるコードの静的解析
SonarQubeは、コードの重複やサイクロマティック数をチェックしてくれる静的解析ツール。

JHipsterで生成したプロジェクトには SonarQube の Dockerfile が含まれているので簡単にコードの静的解析を実行することができる。

## SonarQubeの起動
```
$ docker-compose -f src/main/docker/sonar.yml up -d
```

## 静的解析の実行
```
$ ./mvnw sonar:sonar
```

## 解析結果の確認
http://localhost:9001

## SonarQubeの停止
```
$ docker-compose -f src/main/docker/sonar.yml down
```

## 注意点
- SonarQube は Java8 でないと動かない。https://docs.sonarqube.org/latest/requirements/requirements/
- mvnw sonar:sonar でエラーが出力されるときは、```java -version```をチェック
