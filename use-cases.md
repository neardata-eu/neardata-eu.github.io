---
layout: page
background: grey
---

<div class="col-lg-12 text-center mb-4">
	<h2 class="section-heading text-uppercase">Use cases</h2>
</div>

<br/>
<div class="col-lg-12 text-center mb-4">
<span class="fa-stack fa-4x">
    <i class="fas fa-circle fa-stack-2x text-primary"></i>
    <i class="fa fa-dna fa-stack-1x fa-inverse"></i>
</span>
<h3>Genomics</h3>
<h5>Creation of methods, fast storage, and communications infrastructures to communicate distributed computing power with scalable storage systems, allowing efficient distribution of datasets across the system.</h5>
</div>
<h6>USE CASE 1. Variants-Interactions Use Case</h6>
<p>Complex diseases, such as Type 2 Diabetes (T2D), are caused by the simultaneous effect of multiple
genomic variants and other environmental factors. During the last decades, the genomic study of T2D has been broadly approached with diverse methods. However, although hundreds of genomic variants are expected to contribute to disease development, the study of the relation between variants and T2D has been only analyzed in a single independent manner. There are different reasons to avoid this type of analysis. Among them, the analysis of variant interactions and their contribution to developing the disease is an extreme computational problem. Indeed, here we present two use cases where we tackle this type of analysis with different methods:</p>
<ul>
    <li>Genome-Wide discovery (GWD): use machine learning methods to find groups of variants that, simultaneously, are associated with T2D.</li>
    <li>Multi Dimensionality Reduction (MDR): use statistical methods to discover pairs of variants which, synergically, contribute to the development of T2D.</li>
</ul>


<h6>USE CASE 2. Transcriptomics Use Case</h6>
<p>This use case is divided into two main experiments, which can be seen as different use cases given each present different problems and uses different datasets. Such experiments are:</p>

<ol>
    <li>Transcriptomics Atlas</li>
    <li>Federated Learning for Human Genome Variation Analaysis</li>
</ol>


<h6>USE CASE 3. Genomics Use Case</h6>
<p>This use case is based on variant calling to identify variants from reference genome sequences. We discuss that this type of data is extreme due to the extreme volume of data and extensive pipelines that require. large computational resources to cope with the demands needed to process and analyze this data. The objective of this use case is to port a genomics Variant calling workflow from our HPC implementation to a serverless architecture that allows processing and analyzing extreme genomic data at large scales.</p>

<br/>
<div class="col-lg-12 text-center mb-4">
<span class="fa-stack fa-4x">
    <i class="fas fa-circle fa-stack-2x text-primary"></i>
    <i class="fa fa-flask fa-stack-1x fa-inverse"></i>
</span>
<h3>METABOLOMICS</h3>
<h5>Expand the analysis of metabolomics raw data and boost external access and efficient re-use of open data. Creation of federated and Hybrid distributed architecture and ensuring data privacy but also shared global computations.</h5>
</div>
<h6>USE CASE 1. Metabolomics Use Case</h6>
<p>In this use case, we contribute to improving <a href="https://metaspace2020.eu/" target="_blank">METASPACE</a>, a cloud platform for spatial metabolomics. Spatial metabolomics is a bioanalytical technology for spatially-resolved detection of metabolites, lipids, drugs and other molecules in tissue sections used in biology, medicine, and pharmacology. Spatial metabolomics generates large datasets because for each pixel it produces a mass spectrum
containing in the order of 104 dimensions representing abundances of different molecules. A key problem in spatial metabolomics is the metabolite identification or associating the spectral dimensions with specific metabolites they can represent. The individual spatial metabolomics datasets have large sizes, ranging from 1 to 100 GB per tissue section.</p>

<p>In this project, we aim to further improve the open METASPACE cloud platform and strengthen its position as a International Health Data Space.</p>

<br/>
<div class="col-lg-12 text-center mb-4">
<span class="fa-stack fa-4x">
    <i class="fas fa-circle fa-stack-2x text-primary"></i>
    <i class="fa fa-stethoscope fa-stack-1x fa-inverse"></i>
</span>
<h3>SURGERY</h3>
<h5>Create generalised machine-learning models that can aid surgeons during surgery and allow video data to be analysed in real-time and with low latency.</h5>
</div>
<h6>USE CASE 1. Surgery Use Case</h6>
<p>Our use case in surgery encompasses two distinct focal points. Firstly, we address the challenges inherent in Federated Learning, with a primary objective of improving its security protections. To achieve this, we leverage the Flower framework, enclosing its functionalities within a Docker container for streamlined deployment and management. Additionally, we integrate <a href="https://scontain.com/" target="_blank">Scone</a> to ensure security, ensuring the preservation of privacy throughout the Federated Learning processes.</p>

<p>Secondly, we embark on the development of a surgical video streaming application to handle multiple inference jobs. Our strategy revolves around the integration of <a href="https://cncf.pravega.io/" target="_blank">Pravega</a> and GStreamer into our existing pipelines. This integration empowers us to harness the advanced processing capabilities offered by GStreamer plugins, including our developed segmentation, phase detection, and tool detection plugins. Furthermore, by integrating both GStreamer and Pravega into our infrastructure, we establish a robust ecosystem that contributes to efficient data collection, processing, and storage within the context of surgical video streaming.</p>

<a href="/assets/deliverables/NEARDATA_D5.1_Public.pdf" target="_blank">Learn more about our use cases in D.5.1</a>

<br/>
<br/>