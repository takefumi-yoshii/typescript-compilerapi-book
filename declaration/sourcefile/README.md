# SourceFile

```typescript
interface SourceFile extends Declaration {
  kind: SyntaxKind.SourceFile
  statements: NodeArray<Statement>
  endOfFileToken: Token<SyntaxKind.EndOfFileToken>
  fileName: string
  text: string
  amdDependencies: ReadonlyArray<AmdDependency>
  moduleName?: string
  referencedFiles: ReadonlyArray<FileReference>
  typeReferenceDirectives: ReadonlyArray<FileReference>
  libReferenceDirectives: ReadonlyArray<FileReference>
  languageVariant: LanguageVariant
  isDeclarationFile: boolean
  hasNoDefaultLib: boolean
  languageVersion: ScriptTarget
}
```

