---
layout: page
background: grey
---
<!-- Portfolio Grid -->
<section class="page-section bg-light" id="portfolio">
  <div class="container">
    <div class="row">
      <div class="col-lg-12 text-center">
        <h2 class="section-heading">{{ site.data.sitetext.news.title | markdownify }}</h2>
      </div>
    </div>
    <hr class="light pb-5">
    <div class="row">
      {% for project in site.news reversed %}
      {% assign length = forloop.length %}
      <div class="col-md-4 col-sm-6 portfolio-item">
        <a class="portfolio-link" data-toggle="modal" href="#p{{ length | minus: forloop.index0 }}">
          <div class="portfolio-hover">
            <div class="portfolio-hover-content">
              <i class="{{ site.data.style.portfolio-icon | default: " fas fa-plus fa-3x" }}"></i>
            </div>
          </div>
          <img class="img-fluid" src="{{ project.caption.thumbnail }}" alt="">
        </a>
        <div class="portfolio-caption">
          <h4>{{ project.caption.title }}</h4>
          <p class="text-muted">{{ project.caption.subtitle }}</p>
        </div>
      </div>
      {% endfor %}
    </div>
  </div>

  <div class="col-lg-12 text-center mb-4">
	<h2 class="section-heading text-uppercase">List of press releases</h2>
</div>

<div class="col-lg-12 text-center">
	<table class="table table-striped" style="text-align: left">
		<thead>
			<tr>
				<th>Title</th>
				<th>Link</th>
			</tr>
		</thead>
		<tbody>
			{% for press in site.data.sitetext.press %}
			<tr>
				<td>{{ press.title }}</td>
				<td><a href="{{ press.url }}"><i class="fas fa-external-link-alt"></i></a></td>
			</tr>
			{% endfor %}
		</tbody>
	</table>
</div>

</section>

{% include modals.html %}