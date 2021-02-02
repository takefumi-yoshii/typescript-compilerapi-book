---
description: AST 解析のエントリーポイントと呼べるルートノード
---

# SrouceFile

SrouceFile は AST 解析のエントリーポイントと呼べるルートノードです。 `SourceFile`はそれ自体が`Node`です。生テキスト・ファイル内参照・識別子リスト、 ファイル内の位置から行番号と文字番号へのマッピングにアクセスするためのインタフェースセットを提供します。

コンパイル単位である`Program`インスタンスを作成し、そこから対象ファイルの AST ルートノード、である `SourceFile` を取得する最小コードは次のとおりです。

```typescript
const filePath = './test.ts'
const program: ts.Program = ts.createProgram([filePath], {})
const sourceFile: ts.SourceFile = program.getSourceFile(filePath)
```



