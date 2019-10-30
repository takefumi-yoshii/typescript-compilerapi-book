# ReadBuildProgramHost

```typescript
interface ReadBuildProgramHost {
  useCaseSensitiveFileNames(): boolean
  getCurrentDirectory(): string
  readFile(fileName: string): string | undefined
}
```

