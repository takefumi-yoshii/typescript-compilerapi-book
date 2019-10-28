# ScriptReferenceHost

```typescript
interface ScriptReferenceHost {
  getCompilerOptions(): CompilerOptions
  getSourceFile(fileName: string): SourceFile | undefined
  getSourceFileByPath(path: Path): SourceFile | undefined
  getCurrentDirectory(): string
}
```

## getCompilerOptions

