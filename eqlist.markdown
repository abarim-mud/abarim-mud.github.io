---
layout: page
title: Eqlist
custom_css:
- https://cdn.datatables.net/2.0.8/css/dataTables.dataTables.css

custom_js:
- https://cdn.jsdelivr.net/npm/jquery/dist/jquery.min.js
- https://cdn.datatables.net/2.0.8/js/dataTables.js

---

<script>
	$(document).ready( function () {
		$('table.datatable').DataTable({
			paging: false		
		});
	});
</script> 

Food    | Quantity sold | Time sold         | Cashier
------- | ------------- | ----------------- | -----------
Apples  |   5           | 8-25-2022 9:00:01 | Bearbear
Bananas |   10          | 8-25-2022 9:03:55 | Racc
Kiwis   |   3           | 8-25-2022 9:06:37 | Mickey
Oranges |   5           | 8-25-2022 9:07:24 | Bearbear
{: .datatable}