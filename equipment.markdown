---
layout: page
title: Equipment
custom_css:
- https://cdn.datatables.net/2.0.8/css/dataTables.dataTables.css

custom_js:
- https://cdn.jsdelivr.net/npm/jquery/dist/jquery.min.js
- https://cdn.datatables.net/2.0.8/js/dataTables.js

---

<script>
	$(document).ready( function () {
		$('#equipment').DataTable({
			paging: false,
			order: [[1, 'asc']]
		});
	});
</script>

<table id="equipment" class="display">
    <thead>
        <tr>
            <th>Name</th>
            <th>Slot</th>
			<th>S</th>
            <th>E</th>
			<th>Affects</th>
			<th>Forge</th>
        </tr>
    </thead>
    <tbody>
		{% for eq in site.data.equipment %}
			<tr>
				<td>{{ eq.Name }}</td>
				<td>{{ eq.Slot }}</td>
				<td>{{ eq.Stats }}</td>
				<td>{{ eq.EnchantmentTier }}</td>
				<td>
					{% for affect in eq.Affects %}
						{{ affect }}<br/>
					{% endfor %}
				</td>
				<td>
					{% for component in eq.ForgeComponents %}
						{{ component }}<br/>
					{% endfor %}
				</td>			</tr>
		{% endfor %}
    </tbody>
</table>