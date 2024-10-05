---
layout: page
background: grey
---

<div class="col-lg-12 text-center mb-4">
	<h2 class="section-heading text-uppercase">Dissemination materials</h2>
</div>

<div class="col-lg-12 text-center">
	<table class="table table-striped" style="text-align: left">
		<thead>
			<tr>
				<th>Material</th>
				<th></th>
			</tr>
		</thead>
		<tbody>
			{% for material in site.data.sitetext.materials.material %}
			<tr>
				<td width="60%"><a href="{{ material.link }}" target="_blank"><img class="img-fluid" src="{{ material.image }}" alt="" width="35%"></a> </td>
				<td width="40%"> {{ material.title }} </td>
			</tr>
			{% endfor %}
		</tbody>
	</table>
</div>

<div style="height: 150px;"></div>
