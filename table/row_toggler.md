```
<table>
  <thead>
    <tr>
      <th onclick="toggleCollapse('row1')">Header 1</th>
      <th>Header 2</th>
      <th>Header 3</th>
    </tr>
  </thead>
  <tbody>
    <tr id="row1">
      <td>Row 1</td>
      <td>Data 1</td>
      <td>Data 2</td>
    </tr>
    <tr id="row2">
      <td>Row 2</td>
      <td>Data 3</td>
      <td>Data 4</td>
    </tr>
    <tr id="row3">
      <td>Row 3</td>
      <td>Data 5</td>
      <td>Data 6</td>
    </tr>
  </tbody>
</table>

<script>
  function toggleCollapse(rowId) {
    var row = document.getElementById(rowId);
    if (row.style.display === "none") {
      row.style.display = "";
    } else {
      row.style.display = "none";
    }
  }
</script>

```
