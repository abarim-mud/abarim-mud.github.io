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
		$('#areas').DataTable({
			paging: false
		});
	});
</script> 

<table id="areas" class="display">
    <thead>
        <tr>
            <th>Name</th>
            <th>Credits</th>
            <th>Min Level</th>
            <th>Max Level</th>
        </tr>
    </thead>
    <tbody>
		{% for area in site.data.areas %}
			<tr>
				<td><a href="/maps/png/{{ area.Name }}.png">{{ area.Name }}</a></td>
				<td>{{ area.Credits }}</td>
				<td>{{ area.MinLevel }}</td>
				<td>{{ area.MaxLevel }}</td>
			</tr>
		{% endfor %}
    </tbody>
</table>