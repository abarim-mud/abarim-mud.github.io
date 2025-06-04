---
layout: page
title: Items
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
		
		$('#consumables').DataTable({
			paging: false
		});
	});
</script>

<ul>
	<li><a href="#EQUIPMENT">Equipment</a></li>
	<li><a href="#CONSUMABLES">Consumables</a></li>
</ul>

<h3><a name="EQUIPMENT">Equipment</a></h3>
<table id="equipment" class="display">
    <thead>
        <tr>
            <th>Name</th>
            <th>Slot</th>
            <th>Price</th>
            <th>Enchantment Tier</th>
			<th>Stats</th>
			<th>Affects</th>
        </tr>
    </thead>
    <tbody>
		{% for eq in site.data.equipment %}
			<tr>
				<td>{{ eq.Name }}</td>
				<td>{{ eq.Slot }}</td>
				<td>{{ eq.Price }}</td>
				<td>{{ eq.EnchantmentTier }}</td>
				<td>{{ eq.Stats }}</td>
				<td>
					{% for pair in eq.Affects %}
						{{ pair[0] }}: {{ pair[1] }}<br/>
					{% endfor %}
				</td>
			</tr>
		{% endfor %}
    </tbody>
</table>

<br/>
<h3><a name="CONSUMABLES">Consumables</a></h3>
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
		{% for eq in site.data.consumables %}
			<tr>
				<td>{{ eq.Name }}</td>
				<td>{{ eq.Type }}</td>
				<td>{{ eq.Price }}</td>
				<td>
					{% for affect in eq.Affects %}
						{{ affect }}<br/>
					{% endfor %}
				</td>
			</tr>
		{% endfor %}
    </tbody>
</table>