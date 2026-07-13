# Sitefinity Responsive Table

This snippet creates a compact, reusable table for Sitefinity content blocks. It uses Sofia Sans, supports dynamic rows from systems like JDE, and keeps most styling tied to CSS variables for easy maintenance.

## Preview Content

| Column One | Column Two |
|---|---|
| Row Label | Row Value |
| Row Label | Row Value |
| Row Label | Row Value |
| Row Label | Row Value |

## Features

- Uses Sofia Sans.
- Scoped styling under `.sf-content-table`.
- Expands automatically when more rows are added.
- Alternates row colors automatically.
- Uses CSS variables for most visual settings.
- Can be pasted into Sitefinity or split into separate HTML/CSS files.

## HTML

```html
<div class="sf-content-table">
  <table>
    <thead>
      <tr>
        <th>Column One</th>
        <th>Column Two</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Row Label</td>
        <td>Row Value</td>
      </tr>
      <tr>
        <td>Row Label</td>
        <td>Row Value</td>
      </tr>
      <tr>
        <td>Row Label</td>
        <td>Row Value</td>
      </tr>
      <tr>
        <td>Row Label</td>
        <td>Row Value</td>
      </tr>
    </tbody>
  </table>
</div>
```

## CSS

```css
@import url("https://fonts.googleapis.com/css2?family=Sofia+Sans:wght@400;600;700&display=swap");

.sf-content-table {
  --sf-table-width: 365px;
  --sf-table-font-family: "Sofia Sans", Arial, sans-serif;
  --sf-table-font-size: 14px;
  --sf-table-line-height: 1.35;

  --sf-table-text-color: #222222;
  --sf-table-muted-text-color: #555555;
  --sf-table-border-color: #d1d1d1;
  --sf-table-header-bg: #f8f8f8;
  --sf-table-row-odd-bg: #fafafa;
  --sf-table-row-even-bg: #f6f6f5;

  --sf-table-border-radius: 7px;
  --sf-table-cell-padding-y: 12px;
  --sf-table-cell-padding-x: 11px;
  --sf-table-header-weight: 700;
  --sf-table-first-column-weight: 700;
  --sf-table-cell-weight: 400;

  max-width: var(--sf-table-width);
  font-family: var(--sf-table-font-family);
}

.sf-content-table table {
  width: 100%;
  border-collapse: separate;
  border-spacing: 0;
  border: 1px solid var(--sf-table-border-color);
  border-radius: var(--sf-table-border-radius);
  overflow: hidden;
  color: var(--sf-table-text-color);
  font-size: var(--sf-table-font-size);
  line-height: var(--sf-table-line-height);
}

.sf-content-table th,
.sf-content-table td {
  padding: var(--sf-table-cell-padding-y) var(--sf-table-cell-padding-x);
  text-align: left;
  font-weight: var(--sf-table-cell-weight);
}

.sf-content-table thead th {
  font-weight: var(--sf-table-header-weight);
  background: var(--sf-table-header-bg);
  border-bottom: 1px solid var(--sf-table-border-color);
}

.sf-content-table tbody td:first-child {
  font-weight: var(--sf-table-first-column-weight);
}

.sf-content-table tbody tr:nth-child(odd) {
  background: var(--sf-table-row-odd-bg);
}

.sf-content-table tbody tr:nth-child(even) {
  background: var(--sf-table-row-even-bg);
}
```

## Dynamic Rows

The table will expand automatically as more rows are added.

The alternating row colors are controlled by this CSS:

```css
.sf-content-table tbody tr:nth-child(odd) {
  background: var(--sf-table-row-odd-bg);
}

.sf-content-table tbody tr:nth-child(even) {
  background: var(--sf-table-row-even-bg);
}
```

As long as your data source outputs each item as a table row inside `<tbody>`, the striping will continue automatically.

Example:

```html
<tbody>
  <tr>
    <td>Row Label</td>
    <td>Row Value</td>
  </tr>
  <tr>
    <td>Row Label</td>
    <td>Row Value</td>
  </tr>
  <!-- Additional rows can be inserted here -->
</tbody>
```

## Sitefinity Notes

If Sitefinity strips out `<style>` tags inside content blocks, place the CSS in the site theme or global stylesheet instead.

If Sofia Sans is already loaded globally on the site, remove this line to avoid loading the font twice:

```css
@import url("https://fonts.googleapis.com/css2?family=Sofia+Sans:wght@400;600;700&display=swap");
```

Keep the `.sf-content-table` wrapper around the table so the styles stay scoped and do not affect other tables on the page.

## Suggested GitHub File Structure

```text
sitefinity-responsive-table/
├── README.md
├── example.html
└── sitefinity-responsive-table.css
```
