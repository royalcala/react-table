---
title: Quick Start
---

TanStack Table is a headless table library. It manages your table's state and logic (sorting, filtering, pagination, selection, and more) while you keep 100% control over the markup and styles. This page gets you from install to a rendering Preact table, then shows how to layer on your first feature.

## Installation

TanStack Table v9 is currently published under the `beta` tag:

```bash
npm install @tanstack/preact-table@beta
```

## Your First Table

The component below is complete. Paste it into a Preact app and you will see a working table.

```tsx
import { tableFeatures, useTable } from '@tanstack/preact-table'
import type { ColumnDef } from '@tanstack/preact-table'

// 1. Define the shape of your data
type Person = {
  firstName: string
  lastName: string
  age: number
}

// 2. Give your data a stable reference (module scope, useState, a query cache, etc.)
const data: Array<Person> = [
  { firstName: 'tanner', lastName: 'linsley', age: 24 },
  { firstName: 'tandy', lastName: 'miller', age: 40 },
  { firstName: 'joe', lastName: 'dirte', age: 45 },
]

// 3. New in v9: declare which features this table uses (none yet)
const features = tableFeatures({})

// 4. Define your columns
const columns: Array<ColumnDef<typeof features, Person>> = [
  {
    accessorKey: 'firstName', // accessorKey shorthand
    header: 'First Name',
    cell: (info) => info.getValue(),
  },
  {
    accessorFn: (row) => row.lastName, // accessorFn alternative with a custom id
    id: 'lastName',
    header: () => <span>Last Name</span>,
    cell: (info) => <i>{info.getValue<string>()}</i>,
  },
  {
    accessorKey: 'age',
    header: () => 'Age',
  },
]

export function PersonTable() {
  // 5. Create the table instance
  const table = useTable({
    key: 'person-table', // registers this table with the devtools
    features,
    rowModels: {}, // the core row model is included by default
    columns,
    data,
  })

  // 6. Render markup from the table instance APIs
  return (
    <table>
      <thead>
        {table.getHeaderGroups().map((headerGroup) => (
          <tr key={headerGroup.id}>
            {headerGroup.headers.map((header) => (
              <th key={header.id}>
                {header.isPlaceholder ? null : (
                  <table.FlexRender header={header} />
                )}
              </th>
            ))}
          </tr>
        ))}
      </thead>
      <tbody>
        {table.getRowModel().rows.map((row) => (
          <tr key={row.id}>
            {row.getAllCells().map((cell) => (
              <td key={cell.id}>
                <table.FlexRender cell={cell} />
              </td>
            ))}
          </tr>
        ))}
      </tbody>
    </table>
  )
}
```

A few things to note:

- `tableFeatures({})` declares which optional features the table uses. Registering only what you need keeps bundles small and gives TypeScript accurate types for the table instance.
- `rowModels: {}` is fine for a basic table because the core row model is always included. Feature row models (sorting, filtering, pagination) are registered here when you need them.
- `table.FlexRender` renders the `header`, `cell`, and `footer` definitions from your columns, whether they are plain values or Preact components.
- The `key` option is optional unless you use the [TanStack Table Devtools](../../devtools). The devtools identify tables by `key`, and you register a table by calling `useTanStackTableDevtools(table)` from `@tanstack/preact-table-devtools`.

See the full [Basic useTable example](./examples/basic-use-table) for a runnable version with more columns, a footer, and the devtools wired up.

## Add a Feature: Sorting

Features are opt-in in v9. To make columns sortable, register `rowSortingFeature` in `tableFeatures`, register a sorted row model under `rowModels`, and wire the header click handler.

```tsx
import {
  createSortedRowModel,
  rowSortingFeature,
  sortFns,
  tableFeatures,
  useTable,
} from '@tanstack/preact-table'

const features = tableFeatures({
  rowSortingFeature, // enables sorting APIs and state
})

export function PersonTable() {
  const table = useTable({
    key: 'person-table',
    features,
    rowModels: {
      sortedRowModel: createSortedRowModel(sortFns), // client-side sorting
    },
    columns,
    data,
  })

  return (
    <table>
      <thead>
        {table.getHeaderGroups().map((headerGroup) => (
          <tr key={headerGroup.id}>
            {headerGroup.headers.map((header) => (
              <th key={header.id}>
                {header.isPlaceholder ? null : (
                  <div
                    style={{
                      cursor: header.column.getCanSort() ? 'pointer' : undefined,
                    }}
                    onClick={header.column.getToggleSortingHandler()}
                  >
                    <table.FlexRender header={header} />
                    {{
                      asc: ' 🔼',
                      desc: ' 🔽',
                    }[header.column.getIsSorted() as string] ?? null}
                  </div>
                )}
              </th>
            ))}
          </tr>
        ))}
      </thead>
      {/* tbody unchanged from above */}
    </table>
  )
}
```

Clicking a header now toggles between ascending, descending, and unsorted. Every other feature follows this same pattern: register the feature, register its row model if it has one, and use the APIs it adds to the table, columns, and rows. See the [Sorting Guide](./guide/sorting.md) and the [Sorting example](./examples/sorting) for custom sort functions, multi-sorting, and per-column options.

## Where to Go Next

**Table state.** In v9, table state is backed by TanStack Store atoms. You usually do not need to manage it yourself: set `initialState` for starting values and call feature APIs like `table.setSorting(...)` or `table.nextPage()`. When your app should own a state slice, or you want fine-grained subscriptions, read the [Table State Guide](./guide/table-state.md). It is the foundational guide for everything else.

**Feature guides.** Each feature has its own guide, such as [Column Filtering](./guide/column-filtering.md), [Pagination](./guide/pagination.md), [Row Selection](./guide/row-selection.md), and [Column Visibility](./guide/column-visibility.md).

**Composable tables.** When multiple tables in your app share features, row models, and component conventions, define them once with `createTableHook`:

```tsx
const features = tableFeatures({ rowSortingFeature })

const { useAppTable, createAppColumnHelper } = createTableHook({
  features,
  rowModels: { sortedRowModel: createSortedRowModel(sortFns) },
})
```

See the [Composable Tables Guide](./guide/composable-tables.md) for the full pattern, including pre-bound cell and header components.

**Examples.** Browse the runnable [Preact examples](./examples/basic-use-table), from basic tables to feature demos, to see intended usage end to end.
