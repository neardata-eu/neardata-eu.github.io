---
layout: page
title: Pathogen genomics
background: grey
permalink: /usecases/pathogen-genomics/
---

<div class="container">
    <div class="col-lg-12 text-center mb-4">
        <h2 class="section-heading text-uppercase">Pathogen genomics</h2>
    </div>

    <div class="row justify-content-center mb-5">
        <div class="col-lg-10">
            <div class="embed-responsive embed-responsive-16by9 shadow-lg rounded">
                <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/2Dze4TlSJNM" title="Pathogen genomics Use Case" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
            </div>
        </div>
    </div>

    <h3>Brief introduction</h3>
    <p class="text-justify">Public health agencies such as the UK Health Security Agency (UKHSA) rely on large-scale pathogen genomics to monitor outbreaks, track variants, and inform rapid response strategies. Modern sequencing technologies generate massive volumes of FASTQ data that must be ingested, processed, compared, and stored efficiently. In this use case, NEARDATA provides a stream-based architecture capable of managing large-scale genomic data while enabling real-time analytics and AI-driven pathogen surveillance across a federated public health ecosystem.</p>

    <div class="row mb-4">
        <div class="col-md-6 mb-3">
            <img src="/assets/img/usecases/NEARDATA_Variants-Interactions1.png" class="img-fluid rounded shadow" alt="Pathogen genomics">
        </div>
        <div class="col-md-6 mb-3">
            <img src="/assets/img/usecases/NEARDATA_Variants-Interactions2.png" class="img-fluid rounded shadow" alt="Pathogen genomics">
        </div>
    </div>

    <h3>Introduction of the problem</h3>
    <p class="text-justify">Pathogen genomics in public health presents three major challenges.</p>
    <ol>    
        <li>National surveillance programs must rapidly process, compare, and retrieve millions of pathogen genomes. Traditional workflows based on static batch processing and cluster-based analytics struggle to scale elastically during outbreak peaks.</li>
        <li>Genomic data must be accessible through both streaming and object storage interfaces. While streaming systems enable real-time ingestion and monitoring, many legacy genomics tools expect file-based object storage. Managing these dual interfaces efficiently, without data duplication or performance loss, is non-trivial.</li>
        <li>Deploying scalable analytics engines introduces operational overhead, including cluster provisioning, configuration, and maintenance. This complexity becomes a bottleneck in public health contexts where response to incidents and rapid deployment is crucial.</li>
    </ol>
    <p class="text-justify">Together, these challenges require a new architecture that combines high-throughput ingestion, elastic compute, efficient data reduction, and AI-ready representations.</p>

    <h3>How NEARDATA will address the challenge</h3>
    <p class="text-justify">NEARDATA addresses these challenges through a two-pronged strategy.</p>
    <p class="text-justify">On the architectural side, we integrate Pravega (streaming storage) and Nexus (tiered data management) to create a unified dual-access architecture. FaaStream (serverless orchestration) can also be optionally used. We developed specialised connectors, including the Nexus FASTQGzip streamlet, which compresses FASTQ data while preserving parallel access. This enables efficient ingestion, reduced storage footprint, and compatibility with both stream-based and object-based workflows.</p>
    <p class="text-justify">On the analytical side, we introduced and fully integrated KPop, a novel embedding-based comparative genomics method. Unlike sketch-based approaches, KPop computes the complete k-mer spectrum of genomes and transforms it into compact vector embeddings. These embeddings enable accurate pathogen classification, rapid nearest-neighbour retrieval, and direct integration with AI/ML pipelines.</p>
    <p class="text-justify">This combined architectural and methodological innovation reduces operational complexity, increases throughput, and prepares genomic data for scalable AI-driven analytics.</p>

    <h3>How it will work</h3>
    <p class="text-justify">Incoming FASTQ data streams are ingested via Pravega and processed through Nexus streamlets. The FASTQGzip streamlet applies windowed compression while annotating offsets, enabling efficient parallel batch access without disrupting real-time streaming reads.</p>

    <p class="text-justify">We also tested execution of genomic analytics workloads, such as KPop, using FaaStream, a serverless framework that orchestrates AWS Lambda functions. This allows dynamic scaling according to workload intensity. Stream-native primitives (e.g., shuffle and stateful coordination) support high-throughput distributed processing.</p>

    <p class="text-justify">KPop generates dataset-specific vector embeddings that can be used for classification, clustering, relatedness analysis, and AI-based downstream applications. Because the architecture supports both streaming and object interfaces, results can seamlessly feed legacy genomics pipelines or modern cloud-native AI frameworks.</p>

    <p class="text-justify">This design ensures elasticity during outbreak peaks, reduces idle infrastructure costs, and supports UKHSA’s federated operating model, where multiple institutions require controlled and timely access to genomic insights.</p>

    <h3>Summary of some results</h3>
    <p class="text-justify">The UKHSA use case achieved significant improvements in throughput, scalability, and cost efficiency.</p>

    <p class="text-justify">KPop demonstrated near-perfect classification performance, achieving over 98% accuracy on large real-world datasets, including one comprising more than 1.28 million SARS-CoV-2 genomes. Retrieval of related sequences from million-scale databases can be performed in seconds.</p>

    <p class="text-justify">The Nexus FASTQGzip streamlet achieved a 3.8× compression ratio while preserving parallel access, offering a strong trade-off between data reduction and processing speed compared to standard FASTQ or monolithic GZip files. The serverless FaaStream implementation of KPop achieved execution times comparable to Apache Flink while reducing end-to-end cost by up to 65% when cluster provisioning time is considered.  </p>

    <p class="text-justify">Although these results were demonstrated on a single, well-defined workflow, they validate proof-of-principle feasibility of AI-based, serverless, stream-based genomics analytics for national-scale pathogen surveillance. NEARDATA’s architecture can therefore be used to support the implementation of resilient, scalable, and cost-efficient genomics services for federated public health genomics.</p>
    
</div>
<div style="height: 50px;"></div>
