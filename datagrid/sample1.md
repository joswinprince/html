HTML
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Sortable Data Grid</title>
  <link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/1.10.24/css/jquery.dataTables.min.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
</head>
<body>
  <table id="myTable" class="display">
    <thead>
      <tr>
        <th>ID</th>
        <th>Name</th>
        <th>Age</th>
        <th>Email</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>1</td>
        <td>John Smith</td>
        <td>35</td>
        <td>john@example.com</td>
      </tr>
      <tr>
        <td>2</td>
        <td>Jane Doe</td>
        <td>25</td>
        <td>jane@example.com</td>
      </tr>
      <tr>
        <td>3</td>
        <td>Bob Johnson</td>
        <td>42</td>
        <td>bob@example.com</td>
      </tr>
    </tbody>
  </table>
  <script>
  $(document).ready(function() {
    $('#myTable th').click(function() {
      var table = $(this).parents('table').eq(0)
      var rows = table.find('tr:gt(0)').toArray().sort(comparer($(this).index()))
      this.asc = !this.asc
      if (!this.asc){rows = rows.reverse()}
      for (var i = 0; i < rows.length; i++){table.append(rows[i])}
    })
    function comparer(index) {
      return function(a, b) {
        var valA = getCellValue(a, index), valB = getCellValue(b, index)
        return $.isNumeric(valA) && $.isNumeric(valB) ? valA - valB : valA.localeCompare(valB)
      }
    }
    function getCellValue(row, index){ return $(row).children('td').eq(index).text() }
  })
</script>


  <script type="text/javascript" src="https://code.jquery.com/jquery-3.5.1.min.js"></script>
  <script type="text/javascript" src="https://cdn.datatables.net/1.10.24/js/jquery.dataTables.min.js"></script>
  <script type="text/javascript">
    $(document).ready(function() {
      $('#myTable').DataTable();
    });
  </script>
</body>
</html>

```
