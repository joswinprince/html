java script
```

		// Sorting functionality
		$("th").click(function() {
			var column = $(this).index();
			var rows = $("#myTable tbody tr").get();
			rows.sort(function(a, b) {
				var A = $(a).children("td").eq(column).text().toUpperCase();
				var B = $(b).children("td").eq(column).text().toUpperCase();
				if ($.isNumeric(A) && $.isNumeric(B)) {
					return parseFloat(A) - parseFloat(B);
				} else {
					return A.localeCompare(B);
				}
			});
			$.each(rows, function(index, row) {
				$("#myTable").children("tbody").append(row);
			});
		});

		// Search functionality
		function searchTable() {
			var input = $("#searchInput").val().toUpperCase();
			var rows = $("#myTable tbody tr").get();
			$.each(rows, function(index, row) {
				var values = $(row).children("td").map(function() {
					return $(this).text().toUpperCase();
				}).get();
				if (values.indexOf(input) > -1) {
					$(row).show();
				} else {
					$(row).hide();
				}
			});
		}

```

Css
```
table {
			border-collapse: collapse;
			width: 100%;
			text-align: left;
		}
		th, td {
			padding: 8px;
			text-align: left;
			border: 1px solid #ddd;
		}
		th {
			background-color: #f2f2f2;
			cursor: pointer;
		}
		input[type=text] {
			padding: 6px;
			border: 1px solid #ccc;
			border-radius: 4px;
			box-sizing: border-box;
		}
```

html

```
<!DOCTYPE html>
<html>
<head>
	<title>Data Grid with Sorting and Search</title>
	<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>

</head>
<body>
	<h2>Data Grid with Sorting and Search</h2>
	<p>Click on a column header to sort by that column.</p>
	<input type="text" id="searchInput" onkeyup="searchTable()" placeholder="Search...">
	<table id="myTable">
		<thead>
			<tr>
				<th>ID</th>
				<th>Name</th>
				<th>Email</th>
				<th>Age</th>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td>1</td>
				<td>John Doe</td>
				<td>john.doe@example.com</td>
				<td>30</td>
			</tr>
			<tr>
				<td>2</td>
				<td>Jane Smith</td>
				<td>jane.smith@example.com</td>
				<td>25</td>
			</tr>
			<tr>
				<td>3</td>
				<td>Bob Johnson</td>
				<td>bob.johnson@example.com</td>
				<td>35</td>
			</tr>
			<tr>
				<td>4</td>
				<td>Sarah Lee</td>
				<td>sarah.lee@example.com</td>
				<td>27</td>
			</tr>
		</tbody>
	</table>

```
