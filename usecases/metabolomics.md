---
layout: page
title: Metabolomics
background: grey
permalink: /usecases/metabolomics/
---

<div class="container">
    <div class="col-lg-12 text-center mb-4">
        <h2 class="section-heading text-uppercase">Metabolomics</h2>
    </div>

    <div class="row justify-content-center mb-5">
        <div class="col-lg-10">
            <div class="embed-responsive embed-responsive-16by9 shadow-lg rounded">
                <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/lH7EuAj5M2I" title="Metabolomics Use Case" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
            </div>
        </div>
    </div>

    <h3>Brief introduction</h3>
    <p class="text-justify">Metabolomics is the study of small molecules, or metabolites, that keep our cells and tissues alive. By measuring these molecules, we can understand how diseases develop, how drugs work, and how organisms respond to their environment.</p>
    <p class="text-justify">In spatial metabolomics, scientists need to map these molecules across tissue slides pixel by pixel into detailed images of biology. The starting point for this use case is the METASPACE platform, which provides an open ecosystem for processing and sharing metabolomics datasets. METASPACE offers end-to-end functionality, from raw imzML/ibd files to annotated molecular features and visualization-ready outputs. However, when deploying this workflow at scale within NEARDATA, we encountered three main challenges that required methodological and architectural innovations.</p>

    <div class="row mb-4 mt-4">
        <div class="col-md-6 mb-3">
            <img src="/assets/img/usecases/neardata_metabolomics1.png" class="img-fluid rounded shadow" alt="Metabolomics Interface 1">
        </div>
        <div class="col-md-6 mb-3">
            <img src="/assets/img/usecases/neardata_metabolomics2.png" class="img-fluid rounded shadow" alt="Metabolomics Interface 2">
        </div>
    </div>

    <h3>Introduction of the problem</h3>
    <p class="text-justify">First, the challenge of scalability and flexibility. The metabolomics pipeline mixes stages with heterogeneous compute and I/O profiles, making fixed clusters either underutilized or overloaded. The metabolomics workflow has irregular stages with different execution requirements. This variability makes the system difficult to manage, especially for scientists who are not familiar with cloud development. They would have to adjust the execution setup to stay efficient, which is hard to achieve in practice, and many resources end up being wasted.</p>
    <p class="text-justify">Second, the challenge of data fragmentation. Public metabolomics data are distributed across multiple repositories, each with its own access mechanisms, metadata standards, and usage constraints. Furthermore, it is very complex to process metabolomic data in parallel due to format complexity and resource provisioning.</p>
    <p class="text-justify">Finally, the challenge of confidential computing. Metabolomics data often involve sensitive biomedical information, requiring protection not only at rest and in transit but also in use. Health sensitive data may require secure hardware protection to ensure that the entire life cycle is protected.</p>

    <h3>How NEARDATA will address the challenge</h3>
    <p class="text-justify">We addressed the first challenge, scalability, by adopting a fully serverless execution model, allowing concurrency to scale elastically per stage. we re-implemented the pipeline using PyRun: our platform for pipeline execution that makes cloud development easier. It automatically scales each step to the right level of parallelism, optimizing computing power without manual tuning. Also, researchers can easily see how resources are being used through our intuitive interface.</p>
    <p class="text-justify">We addressed the second challenge, data fragmentation, implementing novel data management tools in Pyrun: Data cockpit and Dataplug. The Data Cockpit tool helps us split large imaging files, explore datasets, and test the best ways to process them. Data cockpit provides unified access to four key repositories: Metaspace, AWS Open Registry, MetaboLights, and Metabolomics Workbench. Dataplug is an extensible data connector architecture capable of providing dynamic partitions for a variety of scientific formats. Together, these components mitigate fragmentation and ensure datasets are delivered in a standardized, partitioned form, ready for large-scale analysis.</p>
    <p class="text-justify">Finally, to address the confidential challenge, we have executed the metabolomics pipeline inside Trusted Execution Environments (TEEs) to execute unmodified code securely, thereby extending Metaspace execution model into a privacy-preserving domain. In particular, we leveraged SCONE secure execution technologies to run in a confidential way the entire metabolomics pipeline in an edge cloud provider (KIO Networks). We demonstrated how it is possible to offload computations in a secure way thanks to confidential technologies that cover the entire data and compute life cycle.</p>

    <h3>How it will work</h3>
    <p class="text-justify">We outline two major software outcomes of the metabolomics use case:</p>
    <p class="text-justify"><strong>METASPACE platform</strong>, a popular international repository with hundreds of users around the world is directly benefiting from NEARDATA developments. In particular, the metabolomics pipeline and the offsample machine learning pipeline are built on top of an elastic serverless architecture (Lithops) that ensures automated and efficient resource scaling and provisioning. We are demonstrating that research technologies can be used in production with highly demanding workloads.</p>
    <p class="text-justify"><strong>PyRun platform</strong>, an advanced serverless platform developed in the context of the project, is offering advanced tools (Data Cockpit, Data plug connectors, Data pipelines, AI pipelines) for scientific researchers in bioinformatics and metabolomics. With a few clicks, practitioners can import metabolomics datasets from different open repositories, ingest them efficiently with custom data connectors, and finally execute their pipelines efficiently at scale thanks to data-driven and AI-assisted tools.</p>

    <h3>Summary of some results</h3>
    <p class="text-justify">We covered key KPIS in the metabolomics use case. First of all, resource auto-scaling was demonstrated thanks to data-driven orchestration on Lithops, where concurrency elastically adapts to each pipeline stage, with compute-intensive steps fanning out to hundreds of workers while lighter stages run sequentially, avoiding over-provisioning. Secondly, ETL performance was improved by replacing sequential data load with the distributed parallel ingestion, enabling scalable parsing and partitioning; tuning ingestion with DataPlug and DataCockpit identified 50 MB partitions as a robust point, significantly reducing ingestion time versus a 130 MB baseline. We also achieved simplicity and productivity thanks to PyRun and Lithops, which eliminate infrastructure setup, accelerate iterative experimentation, and provide fine-grained telemetry, allowing developers to focus on pipeline logic rather than cluster management. Finally, we also demonstrated Security and confidential computing, validating execution within Trusted Execution Environments, and extending the pipeline with strong data-in-use protection and privacy guarantees.</p>
</div>
<div style="height: 50px;"></div>