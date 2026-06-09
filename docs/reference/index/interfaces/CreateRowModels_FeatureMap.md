---
id: CreateRowModels_FeatureMap
title: CreateRowModels_FeatureMap
---

# Interface: CreateRowModels\_FeatureMap\<TFeatures, TData\>

Defined in: [types/RowModel.ts:33](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/RowModel.ts#L33)

## Type Parameters

### TFeatures

`TFeatures` *extends* [`TableFeatures`](TableFeatures.md)

### TData

`TData` *extends* [`RowData`](../type-aliases/RowData.md)

## Properties

### columnFacetingFeature

```ts
columnFacetingFeature: CreateRowModel_Faceted<TFeatures, TData>;
```

Defined in: [types/RowModel.ts:37](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/RowModel.ts#L37)

***

### columnFilteringFeature

```ts
columnFilteringFeature: CreateRowModel_Filtered<TFeatures, TData>;
```

Defined in: [types/RowModel.ts:38](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/RowModel.ts#L38)

***

### columnGroupingFeature

```ts
columnGroupingFeature: CreateRowModel_Grouped<TFeatures, TData>;
```

Defined in: [types/RowModel.ts:40](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/RowModel.ts#L40)

***

### rowExpandingFeature

```ts
rowExpandingFeature: CreateRowModel_Expanded<TFeatures, TData>;
```

Defined in: [types/RowModel.ts:39](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/RowModel.ts#L39)

***

### rowPaginationFeature

```ts
rowPaginationFeature: CreateRowModel_Paginated<TFeatures, TData>;
```

Defined in: [types/RowModel.ts:41](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/RowModel.ts#L41)

***

### rowSortingFeature

```ts
rowSortingFeature: CreateRowModel_Sorted<TFeatures, TData>;
```

Defined in: [types/RowModel.ts:42](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/RowModel.ts#L42)
