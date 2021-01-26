# TypeScript CompilerAPI Book

TypeScript Compiler API は、Node.js に向け公開された Compiler レイヤーの API です。tsc コマンドで実行される Transform・Build や、実行時に得られるエラーなどを取り扱うことができます。

Compiler API は、その namespace に全ての型定義とAPI（関数）を保持しています。Node.js アプリケーションから、`import * as ts from 'typescript'` と宣言し、パッケージを利用します。AST を解析するための便利な関数から、AST を生成するためのファクトリ関数まで、様々なものが用意されています。通常 Compiler API は、TypeScript AST を直接操作せずに抽象化された API として Node.js アプリケーションから利用されます。

## このドキュメントの目的

TypeScript Compiler API の公式ドキュメントは現在公開されていません（2021年1月現在）。わずかではありますが、[microsoft](https://github.com/microsoft)/[**TypeScript**](https://github.com/microsoft/TypeScript) ****のリポジトリで公開されているものもあります。

* \*\*\*\*[**Architectural Overview**](https://github.com/microsoft/TypeScript/wiki/Architectural-Overview)\*\*\*\*
* \*\*\*\*[**Using the Compiler API**](https://github.com/Microsoft/TypeScript/wiki/Using-the-Compiler-API)\*\*\*\*
* \*\*\*\*[**Using the Language Service API**](https://github.com/microsoft/TypeScript/wiki/Using-the-Language-Service-API)\*\*\*\*

型定義を出力する code generator であったり、language service ホストのプラグインなどは、TypeScript Compiler API の知識が必要になることがあります。しかし、確立された Document は存在せず、TypeScript Compiler API の振る舞いは、型定義から読み解く他ありませんでした。ツールメンテナの一助となるべく、このドキュメントを発足するに至りました。この他にまとまった情報として [**TypeScript Deep Dive**](https://basarat.gitbooks.io/typescript/docs/compiler/overview.html) ****にも情報がありますので、そちらも参考にしてみてください。

## Node

ts.Node は、AST を構築する基底オブジェクトです。

```typescript
interface Node extends TextRange {
  kind: SyntaxKind
  flags: NodeFlags
  decorators?: NodeArray<Decorator>
  modifiers?: ModifiersArray
  parent: Node
}
```

