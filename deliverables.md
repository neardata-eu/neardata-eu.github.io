---
layout: page
title: Deliverables
background: grey
permalink: /deliverables/
---

<div class="col-lg-12 text-center mb-4">
	<h2 class="section-heading text-uppercase">Deliverables</h2>
</div>

<div class="container">
    <div class="d-flex align-content-around flex-wrap justify-content-center">
        {% for deliverable in site.data.sitetext.results.deliverables %}
        <div class="m-2">
            <div class="card" style="width: 18rem;">
                <div class="card-body">
                    <h5 class="card-title">{{ deliverable.title }}</h5>
                    <h6 class="card-subtitle mb-2 text-muted">{{ deliverable.subtitle }}</h6>
                    <a href="{{ deliverable.file }}" class="card-link"><i class="fas fa-file-pdf"></i> PDF</a>
                </div>
            </div>
        </div>
        {% endfor %}
    </div>
    <div class="col-lg-12 text-center mt-4">
        <i>* Deliverables pending approval</i>
    </div>
</div>

<div style="height: 100px;"></div>

<!-- Additional Previous Information -->
<div class="col-lg-12 text-center mb-4">
	<h2 class="section-heading text-uppercase">Other Results</h2>
</div>

<div class="container">
    <div class="row">
        <div class="col-lg-6 text-center mb-5">
            <span class="fa-stack fa-4x mb-4">
                <i class="fas fa-circle fa-stack-2x text-primary"></i>
                <i class="fas fa-book fa-stack-1x fa-inverse"></i>
            </span>
            <h4 class="service-heading">Publications</h4>
            <p class="text-muted">Explore our scientific publications and conference proceedings.</p>
            <a href="/publication/" class="btn btn-primary">View Publications</a>
        </div>
        <div class="col-lg-6 text-center mb-5">
            <span class="fa-stack fa-4x mb-4">
                <i class="fas fa-circle fa-stack-2x text-primary"></i>
                <i class="fas fa-code fa-stack-1x fa-inverse"></i>
            </span>
            <h4 class="service-heading">Software Results</h4>
            <p class="text-muted">Access our open-source software, repositories, and technical artifacts.</p>
            <a href="/software-results/" class="btn btn-primary">View Software</a>
        </div>
    </div>
</div>