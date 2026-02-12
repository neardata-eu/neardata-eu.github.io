---
layout: page
title: Transcriptomics
background: grey
permalink: /usecases/transcriptomics/
---

<div class="container">
    <div class="col-lg-12 text-center mb-4">
        <h2 class="section-heading text-uppercase">Transcriptomics</h2>
    </div>

    <div class="row justify-content-center mb-5">
        <div class="col-lg-10">
            <div class="embed-responsive embed-responsive-16by9 shadow-lg rounded">
                <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/WL9qs1feKgU" title="Transcriptomics Use Case" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
            </div>
        </div>
    </div>

    <h3>Brief introduction</h3>
    <p class="text-justify">Transcriptomics Atlas groups the uniformly processed data from a representative set of human tissues. This resource can be of use in a wide range of scientific applications, including pharmacogenomics and biomarker discovery, where transcriptomic analyses are often performed in a comparative framework, examining different health states, diseases, or stimuli relative to baseline conditions. The use of the Transcriptomics Atlas should result in reduced monetary and operational costs of transcriptomics and wet lab experiments. Transcriptomic Atlas can be used as a reference database for future clinical practice when gene expression profiles will be used in disease diagnosis and treatments. Moreover, faster results in the processing of RNA-sequences with the STAR aligner can improve medical services if STAR is used for diagnosis by medical specialists. This, in turn, has impact on the more accurate and timely diagnosis and treatments, which is key for development of healthcare systems in modern society.</p>

    <div class="row mb-4 mt-4">
        <div class="col-md-6 mb-3">
            <img src="/assets/img/usecases/neardata_transcriptomics1.png" class="img-fluid rounded shadow" alt="Transcriptomics Interface 1">
        </div>
        <div class="col-md-6 mb-3">
            <img src="/assets/img/usecases/neardata_transcriptomics2.png" class="img-fluid rounded shadow" alt="Transcriptomics Interface 2">
        </div>
    </div>

    <h3>Introduction of the problem</h3>
    <p class="text-justify">The efficient processing of large-scale RNA sequences presents significant challenges. Bioinformatics tools, such as the STAR aligner, consume substantial resources in terms of both CPU and memory. For example, processing of over 7000 FASTQ files requires procesing 130TB of data. Moreover, the Transcriptomics Atlas pipeline requires a high-throughput solution for data access and index distribution to the worker nodes. While cloud services provide a plethora of options, identifying the optimal architecture and configuration remains a complex undertaking.</p>

    <h3>How NEARDATA will address the challenge</h3>
    <p class="text-justify">To attain high computational efficiency, within NearData project we implemented numerous optimizations, encompassing both application-specific and cloud-related improvements. For instance, the early stopping functionality integrated into the STAR aligner enhances system throughput by 20% through the termination of alignment process for low-quality files. Moreover, the Transcriptomics Atlas pipeline itself has been tailored for the cloud environment:</p>
    <ul>
        <li>The solution effectively utilizes spot instances, reducing the computational costs by 50%-60%.</li>
        <li>It efficiently distributes the STAR index to worker nodes.</li>
        <li>It leverages the most cost-effective instance types, which is 25% cheaper and faster with the newest processors on EC2 (r7a.2xlarge) compared to the older generation.</li>
    </ul>
    <p class="text-justify">The optimizations implemented for the Transcriptomics Atlas pipeline can be applied to other bioinformatics pipelines and compute environments.</p>

    <h3>How it will work</h3>
    <p class="text-justify">In the serverless version of the pipeline, we could use NearData tools and connectors which enable efficient parallelization of workflow in cloud and HPC environments while keeping data movement intact:</p>
    <ul>
        <li><strong>DataPlug connector</strong>, which we extended to support new backend for SRA data format by introducing new system-level data-slicing techniques,</li>
        <li><strong>Lithops HPC</strong>, which we ported to the Ares cluster at Cyfronet Academic Computer Centre in Krakow so that allowed us to parallelize the pseudoalignment part of pipeline using Salmon tool,</li>
        <li><strong>PyRun</strong>, an advanced serverless platform which allows for simple automated deployment and parallelization of relevant applications within the pipeline.</li>
    </ul>

    <h3>Summary of some results</h3>
    <p class="text-justify">The optimizations we introduced within NearData into the Transctiptomics Atlas pipeline can me summarized as contributing to the following key performance indicators:</p>
    <ul>
        <li>Significant performance improvements (data throughput, data transfer reduction).</li>
        <li>Early stopping which enhances the system throughput by ~20%.</li>
        <li>Execution time reduction of up to ~12x due to usage of newer release of human genome.</li>
        <li>Spot instances reduce the cost by factor of ~2.</li>
        <li>Cost-efficient instance type for STAR reduces the monetary cost by ~25%.</li>
        <li>Demonstrated resource auto-scaling for batch and stream data processing.</li>
        <li>Scalability of the solution and underlying tools in the experiments showing speedups of up to 100x due to efficient parallel processing.</li>
        <li>Adaptation of the pipeline to dynamic spot instances.</li>
    </ul>
</div>
<div style="height: 50px;"></div>