---
layout: page
title: Consumables
custom_css:
- https://cdn.datatables.net/2.0.8/css/dataTables.dataTables.css

custom_js:
- https://cdn.jsdelivr.net/npm/jquery/dist/jquery.min.js
- https://cdn.datatables.net/2.0.8/js/dataTables.js

---

<script>
	$(document).ready( function () {
		$('#consumables').DataTable({
			paging: false
		});
	});
</script>

<table id="consumables" class="display">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Price</th>
			<th>Affects</th>
        </tr>
    </thead>
    <tbody>
		{% for cons in site.data.consumables %}
			<tr>
				<td>{{ cons.Name }}</td>
				<td>{{ cons.Type }}</td>
				<td>{{ cons.Price }}</td>
				<td>
					{% for affect in cons.Affects %}
						{{ affect }}<br/>
					{% endfor %}
				</td>
			</tr>
		{% endfor %}
    </tbody>
</table>