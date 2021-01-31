# createProgram

新しい`Program`インスタンスを作成する関数。`Program`は、「SourceFile」と「CompilerOptions」のコレクションであり、コンパイル単位を表します。

```typescript
function createProgram(createProgramOptions: CreateProgramOptions): Program;
```

引数の `CreateProgramOptions` 内訳です。`Program` インスタンスの生成は高コストであり時間を要しますが、生成済みの `Program` インスタンスを oldProgram として与えることで、再生成コストを抑える効果があります。

```typescript
export interface CreateProgramOptions {
  rootNames: readonly string[];
  options: CompilerOptions;
  projectReferences?: readonly ProjectReference[];
  host?: CompilerHost;
  oldProgram?: Program;
  configFileParsingDiagnostics?: readonly Diagnostic[];
}
```

CreateProgramOptions 以外に、第二引数以降に指定を与えることもできます。

```typescript
function createProgram(
  rootNames: readonly string[],
  options: CompilerOptions,
  host?: CompilerHost,
  oldProgram?: Program,
  configFileParsingDiagnostics?: readonly Diagnostic[]
): Program;
```



