---
id: ExtractFeatureMapTypes
title: ExtractFeatureMapTypes
---

# Type Alias: ExtractFeatureMapTypes\<TFeatures, TFeatureMap\>

```ts
type ExtractFeatureMapTypes<TFeatures, TFeatureMap> = IsAny<TFeatures> extends true ? UnionToIntersection<TFeatureMap[keyof TFeatureMap]> : UnionToIntersectionOrEmpty<TFeatureMap[Extract<keyof TFeatures, keyof TFeatureMap>]>;
```

Defined in: [types/TableFeatures.ts:15](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/TableFeatures.ts#L15)

## Type Parameters

### TFeatures

`TFeatures` *extends* [`TableFeatures`](../interfaces/TableFeatures.md)

### TFeatureMap

`TFeatureMap` *extends* `object`
