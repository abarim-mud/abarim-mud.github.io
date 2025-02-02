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
[Newbie Zone.png](/maps/png/Newbie Zone.png) | Maynard | 1 | 10
[Northern Midgaard.png](/maps/png/Northern Midgaard.png) | DikuMUD | 1 | 100
{: .datatable}