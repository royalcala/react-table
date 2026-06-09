---
id: CachedRowModels_FeatureMap
title: CachedRowModels_FeatureMap
---

# Interface: CachedRowModels\_FeatureMap\<TFeatures, TData\>

Defined in: [types/RowModel.ts:65](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/RowModel.ts#L65)

## Type Parameters

### TFeatures

`TFeatures` *extends* [`TableFeatures`](TableFeatures.md)

### TData

`TData` *extends* [`RowData`](../type-aliases/RowData.md)

## Properties

### columnFacetingFeature

```ts
columnFacetingFeature: CachedRowModel_Faceted<TFeatures, TData>;
```

Defined in: [types/RowModel.ts:69](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/RowModel.ts#L69)

***

### columnFilteringFeature

```ts
columnFilteringFeature: CachedRowModel_Filtered<TFeatures, TData>;
```

Defined in: [types/RowModel.ts:70](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/RowModel.ts#L70)

***

### columnGroupingFeature

```ts
columnGroupingFeature: CachedRowModel_Grouped<TFeatures, TData>;
```

Defined in: [types/RowModel.ts:72](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/RowModel.ts#L72)

***

### rowExpandingFeature

```ts
rowExpandingFeature: CachedRowModel_Expanded<TFeatures, TData>;
```

Defined in: [types/RowModel.ts:71](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/RowModel.ts#L71)

***

### rowPaginationFeature

```ts
rowPaginationFeature: CachedRowModel_Paginated<TFeatures, TData>;
```

Defined in: [types/RowModel.ts:73](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/RowModel.ts#L73)

***

### rowSortingFeature

```ts
rowSortingFeature: CachedRowModel_Sorted<TFeatures, TData>;
```

Defined in: [types/RowModel.ts:74](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/RowModel.ts#L74)
