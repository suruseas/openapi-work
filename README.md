# openapi-work

## やりたいこと

prefixItemsが使えるOpenAPIの環境を整える

## 欲しい機能

must

- OpenAPI Viewer(UI)
  - Swagger UI
  - https://github.com/swagger-api/swagger-ui
- OpenAPI のAPI Mockサーバ
  - ReDoc


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

## 優先順位

- Prism
- openapi-generator-cli
- Swagger UI

## 環境構築

最新版で試したいので基本的にdocker hubのイメージは使わずに行う。
ただし、prefixItemsがすでに使えるサービスはimageでもOKとする

## OpenAPIの生成

```
dc run openapi-generator generate -i /openapi/service1/main.yaml -g openapi-yaml -o /gen/service1/
```

