# AffectedFileResult

```typescript
type AffectedFileResult<T> =
  | {
      result: T
      affected: SourceFile | Program
    }
  | undefined
```

