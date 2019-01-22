---
title: Flux aggregate functions
description: Flux aggregate functions take values from an input table and aggregate them in some way.
menu:
  v2_0_ref:
    parent: Transformations
    name: Aggregates
    weight: 1
---

Flux aggregate functions take values from an input table and aggregate them in some way.
The output table contains is a single row with the aggregated value.

Aggregate operations output a table for every input table they receive.
A list of columns to aggregate must be provided to the operation.
The aggregate function is applied to each column in isolation.
Any output table will have the following properties:

- It always contains a single record.
- It will have the same group key as the input table.
- It will contain a column for each provided aggregate column.
  The column label will be the same as the input table.
  The type of the column depends on the specific aggregate operation.
  The value of the column will be `null` if the input table is empty or the input column has only `null` values.
- It will not have a `_time` column.

### aggregateWindow helper function
The [`aggregateWindow()` function](/v2.0/reference/flux/functions/transformations/aggregates/aggregatewindow)
does most of the work needed when aggregating data.
It windows and aggregates the data, then combines windowed tables into a single output table.

### Aggregate functions
The following aggregate functions are available:

{{< function-list category="Aggregates" menu="v2_0_ref" >}}

### Aggregate selectors
The following functions are both aggregates and selectors.
Each returns `n` values after performing an aggregate operation.
They are categorized as selector functions in this documentation:

- [highestAverage](/v2.0/reference/flux/functions/transformations/selectors/highestaverage)
- [highestCurrent](/v2.0/reference/flux/functions/transformations/selectors/highestcurrent)
- [highestMax](/v2.0/reference/flux/functions/transformations/selectors/highestmax)
- [lowestAverage](/v2.0/reference/flux/functions/transformations/selectors/lowestaverage)
- [lowestCurrent](/v2.0/reference/flux/functions/transformations/selectors/lowestcurrent)
- [lowestMin](/v2.0/reference/flux/functions/transformations/selectors/lowestmin)