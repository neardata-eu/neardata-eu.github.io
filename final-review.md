---
layout: page
background: grey
permalink: /final-review/
---

<div class="col-lg-12 text-center mb-4">
	<h2 class="section-heading text-uppercase">Neardata final review</h2>
</div>

#### Review Agenda

__Meeting Subject__: NEARDATA review

__Venue__: Teams meeting

__Date__: February 26, 2026

__Chair__: Pedro García López (Coordinator)


<div class="col-lg-12 text-center mt-4 mb-4">
	<table class="table table-striped" style="text-align: left; white-space: pre;">
		<thead>
			<tr>
				<th>Time</th>
				<th>Subject</th>
				<th>Time (mins)</th>
				<th>Lead partner</th>
			</tr>
		</thead>
		<tbody>
			{% for event in site.data.sitetext.final_review.events %}
			<tr>
				<td>{{ event.time }}</td>
				<td>{{ event.subject }}</td>
				<td>{{ event.duration }}</td>
				<td>{{ event.lead }}</td>
			</tr>
			{% endfor %}
		</tbody>
	</table>
</div>

#### Review Slides
<div class="col-lg-12 text-center mt-4 mb-4">
	<table class="table table-striped" style="text-align: left">
		<thead>
			<tr>
				<th>Document</th>
				<th>File</th>
				<!-- <th>KPI</th> -->
			</tr>
		</thead>
		<tbody>
			{% for item in site.data.sitetext.final_review.slides %}
			<tr>
				<td>{{ item.title }}</td>
				<td><a href="{{ item.link }}"><i class="fas fa-external-link-alt"></i></a></td>
				<!-- <td> {% if item.kpi != "#" %} <a href="{{ item.kpi }}"><i class="fas fa-external-link-alt"></i></a> {% endif %} </td> -->
			</tr>
			{% endfor %}
		</tbody>
	</table>
</div>


#### Project Deliverables
<div class="col-lg-12 text-center mt-4 mb-4">
	<table class="table table-striped" style="text-align: left">
		<thead>
			<tr>
				<th>Title</th>
				<th>PDF</th>
			</tr>
		</thead>
		<tbody>
			{% for deliverable in site.data.sitetext.final_review.deliverables %}
			<tr>
				<td>
                    {{ deliverable.title }} - {{ deliverable.subtitle }}
                </td>
				<td><a href="{{ deliverable.file }}"><i class="fas fa-external-link-alt"></i></a></td>
			</tr>
			{% endfor %}
		</tbody>
	</table>
    <p class="text-muted" style="font-size: 0.9em; text-align: left;">* Marked deliverables are pending approval.</p>
</div>


#### Publications
<div class="col-lg-12 text-center mt-4 mb-4">
	<table class="table table-striped" style="text-align: left">
		<thead>
			<tr>
				<th>Name</th>
				<th>Link</th>
				<th>DOI</th>
			</tr>
		</thead>
		<tbody>
			{% for publication in site.data.sitetext.publications %}
			<tr>
				<td>{{ publication.title }}</td>
				<td><a href="{{ publication.url }}"><i class="fas fa-external-link-alt"></i></a></td>
				<td> {% if publication.doi != "" %} <a href="https://doi.org/{{ publication.doi }}">{{ publication.doi }}</a> {% endif %} </td>
			</tr>
			{% endfor %}
		</tbody>
	</table>
</div>

<!--
#### Summary reports
<div class="col-lg-12 text-center mt-4 mb-4">
	<table class="table table-striped" style="text-align: left">
		<thead>
			<tr>
				<th>Partner short name</th>
				<th>Partner</th>
				<th>PDF</th>
			</tr>
		</thead>
		<tbody>
			{% for summary in site.data.sitetext.final_review.summaries %}
			<tr>
				<td>{{ summary.shortname }}</td>
				<td>{{ summary.partner }}</td>
				<td><a href="{{ summary.link }}"><i class="fas fa-external-link-alt"></i></a></td>
			</tr>
			{% endfor %}
		</tbody>
	</table>
</div> -->



#### Software results
<div class="col-lg-12 text-center mt-4 mb-4">
	<table class="table table-striped" style="text-align: left">
		<thead>
			<tr>
				<th>Title</th>
				<th>Description</th>
				<th>Repository</th>
			</tr>
		</thead>
		<tbody>
			{% for artifact in site.data.sitetext.final_review.artifacts %}
			<tr>
				<td>{{ artifact.title }}</td>
				<td>{{ artifact.description }}</td>
				<td><a href="{{ artifact.link }}"><i class="fas fa-external-link-alt"></i></a></td>
			</tr>
			{% endfor %}
		</tbody>
	</table>
</div>


#### Videos
<div class="col-lg-12 text-center mt-4 mb-4">
	<table class="table table-striped" style="text-align: left">
		<thead>
			<tr>
				<th>Title</th>
				<th>Video</th>
			</tr>
		</thead>
		<tbody>
			{% for video in site.data.sitetext.final_review.videos %}
			<tr>
				<td>{{ video.title }}</td>
				<td><a href="{{ video.video }}"><i class="fas fa-external-link-alt"></i></a></td>
			</tr>
			{% endfor %}
		</tbody>
	</table>
</div>
