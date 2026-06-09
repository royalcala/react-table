---
id: ColumnDef_FeatureMap
title: ColumnDef_FeatureMap
---

# Interface: ColumnDef\_FeatureMap\<TFeatures, TData, TValue\>

Defined in: [types/ColumnDef.ts:103](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/ColumnDef.ts#L103)

## Type Parameters

### TFeatures

`TFeatures` *extends* [`TableFeatures`](TableFeatures.md)

### TData

`TData` *extends* [`RowData`](../type-aliases/RowData.md)

### TValue

`TValue` *extends* [`CellData`](../type-aliases/CellData.md)

## Properties

### columnFilteringFeature

```ts
columnFilteringFeature: ColumnDef_ColumnFiltering<TFeatures, TData>;
```

Defined in: [types/ColumnDef.ts:110](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/ColumnDef.ts#L110)

***

### columnGroupingFeature

```ts
columnGroupingFeature: ColumnDef_ColumnGrouping<TFeatures, TData, TValue>;
```

Defined in: [types/ColumnDef.ts:113](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/ColumnDef.ts#L113)

***

### columnPinningFeature

```ts
columnPinningFeature: ColumnDef_ColumnPinning;
```

Defined in: [types/ColumnDef.ts:109](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/ColumnDef.ts#L109)

***

### columnResizingFeature

```ts
columnResizingFeature: ColumnDef_ColumnResizing;
```

Defined in: [types/ColumnDef.ts:115](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/ColumnDef.ts#L115)

***

### columnSizingFeature

```ts
columnSizingFeature: ColumnDef_ColumnSizing;
```

Defined in: [types/ColumnDef.ts:114](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/ColumnDef.ts#L114)

***

### columnVisibilityFeature

```ts
columnVisibilityFeature: ColumnDef_ColumnVisibility;
```

Defined in: [types/ColumnDef.ts:108](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/ColumnDef.ts#L108)

***

### globalFilteringFeature

```ts
globalFilteringFeature: ColumnDef_GlobalFiltering;
```

Defined in: [types/ColumnDef.ts:111](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/ColumnDef.ts#L111)

***

### rowSortingFeature

```ts
rowSortingFeature: ColumnDef_RowSorting<TFeatures, TData>;
```

Defined in: [types/ColumnDef.ts:112](https://github.com/TanStack/table/blob/main/packages/table-core/src/types/ColumnDef.ts#L112)
