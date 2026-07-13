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
