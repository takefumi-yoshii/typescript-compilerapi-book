# Node

```typescript
interface Node {
  getSourceFile(): SourceFile
  getChildCount(sourceFile?: SourceFile): number
  getChildAt(index: number, sourceFile?: SourceFile): Node
  getChildren(sourceFile?: SourceFile): Node[]
  getStart(sourceFile?: SourceFile, includeJsDocComment?: boolean): number
  getFullStart(): number
  getEnd(): number
  getWidth(sourceFile?: SourceFileLike): number
  getFullWidth(): number
  getLeadingTriviaWidth(sourceFile?: SourceFile): number
  getFullText(sourceFile?: SourceFile): string
  getText(sourceFile?: SourceFile): string
  getFirstToken(sourceFile?: SourceFile): Node | undefined
  getLastToken(sourceFile?: SourceFile): Node | undefined
  forEachChild<T>(
    cbNode: (node: Node) => T | undefined,
    cbNodeArray?: (nodes: NodeArray<Node>) => T | undefined
  ): T | undefined
}
```

