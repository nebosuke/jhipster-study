# e2e (end-to-end) テスト
アプリ構成時にe2eテストフレームワークとして protractor を利用するように設定した場合には、```src/test/javascript/e2e```に、protractorのシナリオが自動生成されます。

## protractor(http://www.protractortest.org)とは
Angularをe2eでテストするためのフレームワーク。Angular CLIでプロジェクトを生成すると標準のe2eテストとして protractor が定義されます。内部で Selenium WebDriver が利用されており、e2eテストはChromeを起動して実行されます。

## 実行方法
```
$ npm run e2e
```
