# openapi-work

## やりたいこと

prefixItemsが使えるOpenAPIの環境を整える

JSON schemaの [tupleValidation](https://json-schema.org/understanding-json-schema/reference/array#tupleValidation) がやりたい。

## 各種ツールの一覧

v3.1対応など書いてあるが、精査されていないのか間違いがほとんど？
あと新めのツールはなさげ。

https://openapi.tools/

## 状況

- ファイル分割での管理・結合ツール
  - openapi-generator-cli
    - 🙅‍♀️ prefixItems は利用できない
- viewer(API操作可能)
  - Swagger UI
    - 🙅‍♀️ prefixItems は利用できない
- viewer(ドキュメント表示特化)
  - ReDoc
    - 🙆‍♀️ prefixItems が表現できる
- mock
  - Prism
    - 🙅‍♀️ prefixItems は利用できない
  - openapi-mock
    - https://github.com/muonsoft/openapi-mock
    - 🙅‍♀️ prefixItems は利用できない(Unexpected errorとなる)
  - Mocks Server
    - https://github.com/mocks-server/main
    - https://www.mocks-server.org/docs/integrations/openapi/
    - https://www.mocks-server.org/docs/integrations/docker/

## 優先順位

- Prism
  - APIサーバの動作は work-around がない。最優先。
- openapi-generator-cli
  - prefixItemsの定義は generate できないが、その部分だけ手で上書きすればなんとか対応可能。対応自体は必須。
- Swagger UI
  - 定義の表示だけなら ReDoc で代用可能。API呼び出しは問題なく使える

## 環境構築

最新版で試したいので基本的にdocker hubのイメージは使わずに行う。
ただし、prefixItemsがすでに使えるサービスはimageでもOKとする

memo

- gen/openapi/openapi.yamlを更新すると...
  - Swagger UI
    - 🙆‍♀️ブラウザを更新すると最新の内容で更新される
  - ReDoc
    - ブラウザを更新しても最新の内容で更新されない。キャッシュを削除すると最新で表示
  - Prism
    - 更新後APIをcallするとコンテナが落ちる

## OpenAPIの生成

```
dc run openapi-generator generate -i /openapi/service1/main.yaml -g openapi-yaml -o /gen/service1/
```

