# Diagnostic

`Diagnostic`は、コンパイラが検出したエラーを表すインスタンスです。 どのようなコンパイルエラーが得られるのか、次のような問題のある定義を用意します。

```typescript
const message: number = 'hello world'
message = 0
console.log(message)
```

このファイルを読み込む`Program`を用意し、`getPreEmitDiagnostics`で診断結果を取得します。

```typescript
import * as ts from 'typescript'

const file = '../src/type.ts'
const program = ts.createProgram([file], {})
const allDiagnostics = ts.getPreEmitDiagnostics(program)

allDiagnostics.forEach(diagnostic => {
  if (!diagnostic) return
  if (!diagnostic.file || !diagnostic.start) return
  // エラーを検出したファイル
  console.log(`ErrorFile: ${diagnostic.file.fileName}`)
  const position = diagnostic.file.getLineAndCharacterOfPosition(
    diagnostic.start
  )
  // エラーを検出した位置
  const line = position.line + 1
  const character = position.character + 1
  console.log(`ErrorPosition: ${line}, ${character}`)
  // 検出したエラー内容
  const message = ts.flattenDiagnosticMessageText(
    diagnostic.messageText,
    '\n'
  )
  console.log(`ErrorMessage: ${message}`)
})
```



