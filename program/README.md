# Program

```typescript
interface Program extends ScriptReferenceHost {
  getRootFileNames(): ReadonlyArray<string>
  getSourceFiles(): ReadonlyArray<SourceFile>
  emit(
    targetSourceFile?: SourceFile,
    writeFile?: WriteFileCallback,
    cancellationToken?: CancellationToken,
    emitOnlyDtsFiles?: boolean,
    customTransformers?: CustomTransformers
  ): EmitResult
  getOptionsDiagnostics(
    cancellationToken?: CancellationToken
  ): ReadonlyArray<Diagnostic>
  getGlobalDiagnostics(
    cancellationToken?: CancellationToken
  ): ReadonlyArray<Diagnostic>
  getSyntacticDiagnostics(
    sourceFile?: SourceFile,
    cancellationToken?: CancellationToken
  ): ReadonlyArray<DiagnosticWithLocation>
  getSemanticDiagnostics(
    sourceFile?: SourceFile,
    cancellationToken?: CancellationToken
  ): ReadonlyArray<Diagnostic>
  getDeclarationDiagnostics(
    sourceFile?: SourceFile,
    cancellationToken?: CancellationToken
  ): ReadonlyArray<DiagnosticWithLocation>
  getConfigFileParsingDiagnostics(): ReadonlyArray<Diagnostic>
  getTypeChecker(): TypeChecker
  isSourceFileFromExternalLibrary(file: SourceFile): boolean
  isSourceFileDefaultLibrary(file: SourceFile): boolean
  getProjectReferences(): ReadonlyArray<ProjectReference> | undefined
  getResolvedProjectReferences():
    | ReadonlyArray<ResolvedProjectReference | undefined>
    | undefined
}
```

