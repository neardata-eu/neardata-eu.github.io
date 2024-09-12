---
layout: page
background: grey
---

<div class="col-lg-12 text-center mb-4">
	<h2 class="section-heading text-uppercase">List of software results</h2>
</div>

<div class="col-lg-12 text-center">
	<table class="table table-striped" style="text-align: left">
		<thead>
			<tr>
				<th>Name</th>
                <th>Description</th>
				<th>Link</th>
			</tr>
		</thead>
		<tbody>
			{% for artifact in site.data.sitetext.review.artifacts %}
			<tr>
				<td>{{ artifact.title }}</td>
                <td>{{ artifact.description }}</td>
				<td><a href="{{ artifact.link }}"><i class="fas fa-external-link-alt"></i></a></td>
			</tr>
			{% endfor %}
		</tbody>
	</table>
</div>

<div style="height: 150px;"></div>
