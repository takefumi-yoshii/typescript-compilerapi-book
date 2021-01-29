---
description: ファクトリ関数
---

# factory

CompilerAPI には、任意の ts.Node を生成するファクトリ関数があります。生成された ts.Node をもって抽象構文木を構築することで、SRC コードを生成することができます。JavaScript の構文木に加え、TypeScript 特有のリテラル・型情報なども、ts.Node で表現することができます。

