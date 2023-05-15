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

最新版で試したいのでdocker hubのイメージは使わずに行う。ただ、基本はdocker hubのDockerfileを参考にする

## OpenAPIの生成

```
openapi-generator generate -i ./openapi/service1/main.yaml -g openapi -o ./gen/service1/
```

