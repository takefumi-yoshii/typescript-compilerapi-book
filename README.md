# TypeScript CompilerAPI Book

TypeScript Compiler API は、Node.js に向け公開された Compiler レイヤーの API です。tsc コマンドで実行される Transform・Build や、実行時に得られるエラーなどを取り扱うことができます。

Compiler API は、その namespace に全ての型定義とAPI（関数）を保持しています。Node.js アプリケーションから、`import * as ts from 'typescript'` と宣言し、パッケージを利用します。AST を解析するための便利な関数から、AST を生成するためのファクトリ関数まで、様々なものが用意されています。通常 Compiler API は、TypeScript AST を直接操作せずに抽象化された API として Node.js アプリケーションから利用されます。

## このドキュメントの目的

TypeScript Compiler API の公式ドキュメントは、公開されていません（2019年11月現在）。わずかではありますが、[microsoft](https://github.com/microsoft)/[**TypeScript**](https://github.com/microsoft/TypeScript) ****のリポジトリで公開されているものもあります。

* \*\*\*\*[**Architectural Overview**](https://github.com/microsoft/TypeScript/wiki/Architectural-Overview)\*\*\*\*
* \*\*\*\*[**Using the Compiler API**](https://github.com/Microsoft/TypeScript/wiki/Using-the-Compiler-API)\*\*\*\*
* \*\*\*\*[**Using the Language Service API**](https://github.com/microsoft/TypeScript/wiki/Using-the-Language-Service-API)\*\*\*\*

この他にまとまった情報として [**TypeScript Deep Dive**](https://basarat.gitbooks.io/typescript/docs/compiler/overview.html) ****にも情報がありますが、やはり情報量としては不十分です。API Documentとして確立されたものは存在せず、TypeScript Compiler API を利用するユーザーは、型定義から読み解く他ありませんでした。

Compiler API は、TypeScript + ライブラリを用いたアプリケーション開発などでは、直接触れる機会はないでしょう。しかしながら、TypeScript の需要は日に日に増し「その開発環境が整備されているか否か」が技術選定のひとつの基準となっています。TypeScript アプリケーションであっても、最終的には JavaScript アプリケーションとしてトランスパイルされるので、本質的価値は型システムに帰属しません。

どんな環境であっても、型システムの恩恵を受けるためには、TypeScript Compiler API に対する知識の共有が必須です。この様な背景からドキュメントの必要性を感じ、発足するに至りました。

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

