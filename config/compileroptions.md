# CompilerOptions

```typescript
interface CompilerOptions {
  allowJs?: boolean
  allowSyntheticDefaultImports?: boolean
  allowUmdGlobalAccess?: boolean
  allowUnreachableCode?: boolean
  allowUnusedLabels?: boolean
  alwaysStrict?: boolean
  baseUrl?: string
  charset?: string
  checkJs?: boolean
  declaration?: boolean
  declarationMap?: boolean
  emitDeclarationOnly?: boolean
  declarationDir?: string
  disableSizeLimit?: boolean
  downlevelIteration?: boolean
  emitBOM?: boolean
  emitDecoratorMetadata?: boolean
  experimentalDecorators?: boolean
  forceConsistentCasingInFileNames?: boolean
  importHelpers?: boolean
  inlineSourceMap?: boolean
  inlineSources?: boolean
  isolatedModules?: boolean
  jsx?: JsxEmit
  keyofStringsOnly?: boolean
  lib?: string[]
  locale?: string
  mapRoot?: string
  maxNodeModuleJsDepth?: number
  module?: ModuleKind
  moduleResolution?: ModuleResolutionKind
  newLine?: NewLineKind
  noEmit?: boolean
  noEmitHelpers?: boolean
  noEmitOnError?: boolean
  noErrorTruncation?: boolean
  noFallthroughCasesInSwitch?: boolean
  noImplicitAny?: boolean
  noImplicitReturns?: boolean
  noImplicitThis?: boolean
  noStrictGenericChecks?: boolean
  noUnusedLocals?: boolean
  noUnusedParameters?: boolean
  noImplicitUseStrict?: boolean
  noLib?: boolean
  noResolve?: boolean
  out?: string
  outDir?: string
  outFile?: string
  paths?: MapLike<string[]>
  preserveConstEnums?: boolean
  preserveSymlinks?: boolean
  project?: string
  reactNamespace?: string
  jsxFactory?: string
  composite?: boolean
  incremental?: boolean
  tsBuildInfoFile?: string
  removeComments?: boolean
  rootDir?: string
  rootDirs?: string[]
  skipLibCheck?: boolean
  skipDefaultLibCheck?: boolean
  sourceMap?: boolean
  sourceRoot?: string
  strict?: boolean
  strictFunctionTypes?: boolean
  strictBindCallApply?: boolean
  strictNullChecks?: boolean
  strictPropertyInitialization?: boolean
  stripInternal?: boolean
  suppressExcessPropertyErrors?: boolean
  suppressImplicitAnyIndexErrors?: boolean
  target?: ScriptTarget
  traceResolution?: boolean
  resolveJsonModule?: boolean
  types?: string[]
  /** Paths used to compute primary types search locations */
  typeRoots?: string[]
  esModuleInterop?: boolean
  [option: string]: CompilerOptionsValue | TsConfigSourceFile | undefined
}
```

