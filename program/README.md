# Program

`Program`は型システムとコード生成へのエントリーポイントと呼べます。 `SourceFiles`の集合とコンパイル単位を表す一連のコンパイルオプションを含みます。典型的な Program インスタンス作成コードは以下の様なものです。`ts.findConfigFile`関数で、パーサーの tsconfig.json を特定します。

```typescript
import * as ts from 'typescript'
import { createConfigFileHost } from './createConfigFileHost'
import { Config } from './types'
// ______________________________________________________
//
export function createProgram(searchPath: string, config: Config) {
  const configPath = ts.findConfigFile(
    searchPath,
    ts.sys.fileExists,
    config.tsconfigFileName
  )
  if (!configPath) {
    throw new Error("Could not find 'tsconfig.json'.")
  }
  const parsedCommandLine = ts.getParsedCommandLineOfConfigFile(
    configPath,
    {},
    createConfigFileHost()
  )
  if (!parsedCommandLine) {
    throw new Error('invalid parsedCommandLine.')
  }
  if (parsedCommandLine.errors.length) {
    throw new Error('parsedCommandLine has errors.')
  }
  return ts.createProgram({
    rootNames: parsedCommandLine.fileNames,
    options: parsedCommandLine.options
  })
}
```

