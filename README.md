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
- viewer(API操作可能)
  - Swagger UI
- viewer(ドキュメント表示特化)
  - ReDoc
- mock
  - Prism

## 環境構築

最新版で試したいので基本的にdocker hubのイメージは使わずに行う。
ただし、prefixItemsがすでに使えるサービスはimageでもOKとする

## OpenAPIの生成

```
dc run openapi-generator generate -i /openapi/service1/main.yaml -g openapi-yaml -o /gen/service1/
```

