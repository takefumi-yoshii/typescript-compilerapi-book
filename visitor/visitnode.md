# visitNode

```typescript
function visitNode<T extends Node>(
  node: T | undefined,
  visitor: Visitor | undefined,
  test?: (node: Node) => boolean,
  lift?: (node: NodeArray<Node>) => T
): T
```

