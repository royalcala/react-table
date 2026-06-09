---
id: CreateRowModels
title: CreateRowModels
---

# Type Alias: CreateRowModels\<TFeatures, TData\>

```ts
type CreateRowModels<TFeatures, TData> = CreateRowModel_Core<TFeatures, TData> & ExtractFeatureMapTypes<TFeatures, CreateRowModels_FeatureMap<TFeatures, TData>>;
```

Defined in: [types/RowModel.ts:45](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/RowModel.ts#L45)

## Type Parameters

### TFeatures

`TFeatures` *extends* [`TableFeatures`](../interfaces/TableFeatures.md)

### TData

`TData` *extends* [`RowData`](RowData.md)
