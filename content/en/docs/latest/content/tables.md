---
title: Tables
description: Enhance out-of-the-box Markdown tables with Bootstrap styling.
date: 2023-04-28
layout: docs
---

Hugo supports out-of-the box Markdown tables. Hinode enhances the basic tables with optional styling features provided by Bootstrap. The following paragraphs illustrate how to use basic tables, how to accent them, how to adjust the borders, and how to make the table more compact.

## Basic tables

Hugo supports tables out-of-the-box with extended Markdown. Use an optional shortcode as wrapper to align the table cells.

### Default alignment

Hugo supports tables out-of-the-box by using the `|` and `-` characters. Add `{.table}` at the bottom of the block to apply the correct styling. You can mix the content with inline Markdown.

{{< example lang="markdown" >}}
| Italics   | Bold     | Code   |
| --------- | -------- | ------ |
| _italics_ | **bold** | `code` |
{.table}
{{< /example >}}

### Aligned cells and headers

Hugo's Markdown processor applies inline styles to align cells in a table, which is blocked by Hinode's [Content Security Policy]({{< relref "server-headers" >}}). Use the `table` shortcode to wrap your Markdown input instead. You can then align header and cell data to the left, center, or right of a column using the `:` character. Pass additional class attributes between double quotes, e.g. `"table-striped"`. See the [next section](#accented-tables) for more options.

<!-- markdownlint-disable MD037 -->
{{< example lang="hugo" >}}
{{</* table "table-striped" */>}}
| #  | Item        | Left aligned | Center aligned |   Right aligned|
| -- | ----------- |:-------------|:--------------:| --------------:|
| 1. | First item  | some text    | more text      | even more text |
| 2. | Second item | some text    | more text      | even more text |
| 3. | Third item  | some text    | more text      | even more text |
{{</* /table */>}}
{{< /example >}}
<!-- markdownlint-enable MD037 -->

## Accented tables

Add optional class attributes to style the table using Bootstrap.

### Striped rows

Use `.table-striped` to add zebra-striping to any table row.

{{< example lang="markdown" >}}
| #  | Item        |
| -- | ----------- |
| 1. | First item  |
| 2. | Second item |
| 3. | Third item  |
{.table .table-striped}
{{< /example >}}

### Striped columns

Use `.table-striped-columns` to add zebra-striping to any table column.

{{< example lang="markdown" >}}
| #  | Item        | Description            |
| -- | ----------- | ---------------------- |
| 1. | First item  | This is the first row  |
| 2. | Second item | This is the second row |
| 3. | Third item  | This is the third row  |
{.table .table-striped-columns}
{{< /example >}}

### Hoverable rows

Add `.table-hover` to enable a hover state on the table rows.

{{< example lang="markdown" >}}
| #  | Item        |
| -- | ----------- |
| 1. | First item  |
| 2. | Second item |
| 3. | Third item  |
{.table .table-hover}
{{< /example >}}

### Colored tables

Add `table-<theme>` to apply [theme colors]({{< ref "colors" >}}) to your table. You can mix them with other classes, such as `.table-striped`.

{{< example lang="markdown" >}}
| #  | Item        |
| -- | ----------- |
| 1. | First item  |
| 2. | Second item |
| 3. | Third item  |
{.table .table-success .table-striped}
{{< /example>}}

## Table borders

Adjust the borders of a table to match your style preferences.

### Bordered tables

Add `.table-bordered` for borders on all sides of the table and cells. Add an optional `border-<theme>` class to apply [theme colors]({{< ref "colors" >}}) to the table borders.

{{< example lang="markdown" >}}
| #  | Item        |
| -- | ----------- |
| 1. | First item  |
| 2. | Second item |
| 3. | Third item  |
{.table .table-bordered .border-primary}
{{< /example >}}

### Tables without borders

Add `.table-borderless` for a table without borders.

{{< example lang="markdown" >}}
| #  | Item        |
| -- | ----------- |
| 1. | First item  |
| 2. | Second item |
| 3. | Third item  |
{.table .table-borderless}
{{< /example >}}

## Small tables

Add `.table-sm` to make any table more compact by cutting all cell padding in half.

{{< example lang="markdown" >}}
| #  | Item        |
| -- | ----------- |
| 1. | First item  |
| 2. | Second item |
| 3. | Third item  |
{.table .table-sm}
{{< /example >}}

## Responsive tables

{{< release version="v0.8.0" >}}

Embed the markdown table within the `table` shortcode to make the table responsive. Responsive tables scroll horizontally to improve the layout on smaller screens.

### Always responsive

By default, the `table` shortcode is responsive for all viewports.

<!-- markdownlint-disable MD037 -->
{{< example lang="markdown" >}}
{{</* table */>}}
| #  | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading |
|----|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 1. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
| 2. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
| 3. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
{{</* /table */>}}
{{< /example >}}
<!-- markdownlint-enable MD037 -->

Use `.table-responsive-none` to disable this behavior.

<!-- markdownlint-disable MD037 -->
{{< example lang="markdown" >}}
{{</* table table-responsive-none */>}}
| #  | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading |
|----|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 1. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
| 2. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
| 3. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
{{</* /table */>}}
{{< /example >}}
<!-- markdownlint-enable MD037 -->

### Breakpoint specific

Use `.table-responsive{-sm|-md|-lg|-xl|-xxl}` to create responsive tables up to a particular breakpoint. From that breakpoint and up, the table will behave normally and not scroll horizontally.

<!-- markdownlint-disable MD037 -->
{{< example lang="markdown" >}}
{{</* table table-responsive-sm */>}}
| #  | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading |
|----|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 1. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
| 2. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
| 3. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
{{</* /table */>}}

{{</* table table-responsive-md */>}}
| #  | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading |
|----|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 1. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
| 2. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
| 3. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
{{</* /table */>}}

{{</* table table-responsive-lg */>}}
| #  | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading |
|----|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 1. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
| 2. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
| 3. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
{{</* /table */>}}

{{</* table table-responsive-xl */>}}
| #  | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading |
|----|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 1. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
| 2. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
| 3. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
{{</* /table */>}}

{{</* table table-responsive-xxl */>}}
| #  | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading | Heading |
|----|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 1. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
| 2. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
| 3. | cell    | cel     | cel     | cel     | cel     | cel     | cel     | cel     | cel     |
{{</* /table */>}}
{{< /example >}}
<!-- markdownlint-enable MD037 -->