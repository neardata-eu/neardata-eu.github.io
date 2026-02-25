---
layout: page
title: Datasets
background: grey
permalink: /datasets/
---

<div class="col-lg-12 text-center mb-4">
	<h2 class="section-heading text-uppercase">Generated Datasets</h2>
</div>

<div class="col-lg-12">
	<table class="table table-striped table-bordered" style="text-align: left">
		<thead class="thead-dark">
			<tr>
				<th style="width: 25%">Name</th>
				<th style="width: 40%">Description</th>
				<th style="width: 15%">Volume</th>
				<th style="width: 10%">Access</th>
				<th style="width: 10%">DOI / Link</th>
			</tr>
		</thead>
		<tbody>
			{% for dataset in site.data.sitetext.datasets.list %}
			<tr>
				<td>{{ dataset.name }}</td>
				<td>{{ dataset.description }}</td>
				<td>{{ dataset.volume }}</td>
				<td>{{ dataset.access }}</td>
				<td>
					{% if dataset.doi != "NA" %}
					<a href="{{ dataset.doi }}" target="_blank"><i class="fas fa-external-link-alt"></i></a>
					{% else %}
					NA
					{% endif %}
				</td>
			</tr>
			{% endfor %}
		</tbody>
	</table>
</div>

<div style="height: 150px;"></div>