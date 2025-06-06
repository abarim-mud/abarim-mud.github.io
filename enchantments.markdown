---
layout: page
title: Enchantments
custom_css:
- https://cdn.datatables.net/2.0.8/css/dataTables.dataTables.css

custom_js:
- https://cdn.jsdelivr.net/npm/jquery/dist/jquery.min.js
- https://cdn.datatables.net/2.0.8/js/dataTables.js

---

<script>
	$(document).ready( function () {
		$('#enchantments').DataTable({
			paging: false
		});
	});
</script>

<table id="enchantments" class="display">
    <thead>
        <tr>
            <th>Name</th>
            <th>Stones</th>
            <th>Slots</th>
			<th>Materials</th>
			<th>Price</th>
			<th>Affects</th>
        </tr>
    </thead>
    <tbody>
		{% for ench in site.data.enchantments %}
			<tr>
				<td>{{ ench.Name }}</td>
				<td>{{ ench.Stones }}</td>
				<td>{{ ench.Slots }}</td>
				<td>{{ ench.Materials }}</td>
				<td>{{ ench.Price }}</td>
				<td>
					{% for affect in ench.Affects %}
						{{ affect }}<br/>
					{% endfor %}
				</td>
			</tr>
		{% endfor %}
    </tbody>
</table>