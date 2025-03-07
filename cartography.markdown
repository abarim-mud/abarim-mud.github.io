---
layout: page
title: Cartography
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

Name | Credits | Min Level | Max Level
-----| ------- | --------- | ---------
[Arachnos](/maps/png/Arachnos.png) | Mahatma | 5 | 20
[Astoria](/maps/png/Astoria.png) | | ALL | ALL
[Haon Dor](/maps/png/Haon Dor.png) | Diku | 1 | 20
[Sewers](/maps/png/Sewers.png) | Poohb | 5 | 35
{: .datatable}