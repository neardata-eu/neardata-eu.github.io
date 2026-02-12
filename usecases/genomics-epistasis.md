---
layout: page
title: Genomics Epistasis
background: grey
permalink: /usecases/genomics-epistasis/
---

<div class="container">
    <div class="col-lg-12 text-center mb-4">
        <h2 class="section-heading text-uppercase">Genomics Epistasis</h2>
    </div>

    <div class="row justify-content-center mb-5">
        <div class="col-lg-10">
            <div class="embed-responsive embed-responsive-16by9 shadow-lg rounded">
                <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/bQfzeTAXsFU" title="Genomics Epistasis Use Case" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
            </div>
        </div>
    </div>

    <h3>Brief introduction</h3>
    <p class="text-justify">Current state of the art devoted their efforts to determining how single genome variants could be associated with complex diseases. However, recent studies have shown that while a specific couple of variants may not be associated with the disease, the combination of both of them within a single genome may be. Thus, it is necessary to devote our efforts to studying the impact of variant interactions with such diseases. In this section, we present a use case for the identification of such interactions with two different but complementary methodologies, which we define as separate use cases and experiments.</p>

    <!-- Images intercalated here -->
    <div class="row mb-4 mt-4">
        <div class="col-md-6 mb-3">
            <img src="/assets/img/usecases/neardata_genomics1.png" class="img-fluid rounded shadow" alt="Genomics Interface 1">
        </div>
        <div class="col-md-6 mb-3">
            <img src="/assets/img/usecases/neardata_genomics2.png" class="img-fluid rounded shadow" alt="Genomics Interface 2">
        </div>
    </div>

    <h3>Introduction of the problem</h3>
    <p class="text-justify">The discovery of variant groups associated with the disease involves the analysis of over 15 million variants. Studying all the possible combinations of pairs of variants represents more than 6*10<sup>13</sup> tests. Using the Mare Nostrum 4 (MN4) architecture (165,888 CPU - 1.880 GB/core and 208 GPU - 16GB/each), this process is estimated to take approximately 9 days. This exemplifies how this use case represents an extreme data problem. On the other hand, the combinatorial analysis based on machine learning approaches requires the execution of over 112 million tests, which represents 3 days of continuous analysis using the whole MN4 architecture. Moreover, this calculus is done by computing only pairs of variants. However, the ideal scenario would be computing all the possibilities with the 23 chromosomes. Thus, sets of 23 rather than just pairs. Consequently, the problem would take months of computations using the whole supercomputer.</p>

    <h3>How NEARDATA will address the challenge</h3>
    <p class="text-justify">Traditional association testing methods often overlook the combined contribution of multiple genomic variants to disease development. Machine learning (ML) approaches have emerged as promising tools for identifying variant groups and assessing their impact on disease risk. However, the structure of genomic datasets, characterized by millions of features across a relatively limited number of individuals, poses significant challenges for the effective application of ML techniques. To address this, we implement a combinatorial strategy that aligns with the statistical constraints of ML methodologies. The genomic data is first partitioned into manageable chunks that conform to the computational limitations of ML tools, ensuring robust analytical performance. These chunks are then paired and analysed for their association with the disease. This approach enables scalable, genome-wide analysis and contributes to enhanced understanding of disease mechanisms, with potential implications for early detection and precision medicine.</p>
    <p class="text-justify">The substantial volume of data stored in genomic datasets, often encompassing tens of millions of variants across hundreds of thousands of individuals, presents a significant challenge for efficient data ingestion. To ensure optimal performance and avoid computational bottlenecks, it is critical to minimize redundant read operations from the same file. This is particularly relevant when working with formats such as Variant Call Format (VCF), Binary Call Format (BCF), or scalable alternatives like Apache Parquet, which support columnar storage and compression. To address these challenges, the ingestion process is designed to partition the data into discrete chunks that can be processed in parallel. This approach reduces I/O overhead and enables distributed execution using Lithops in combination with DataPlug, facilitating efficient data access and transfer and, thus, allowing the scalable ingestion and processing of large genomic datasets.</p>

    <h3>How it will work</h3>
    <p class="text-justify">To enable such solutions, we implemented four main connectors:</p>
    <ul>
        <li><strong>Data shuffle and partitioning connector:</strong> this connector reads the input data, shuffles its contents, mixing the variants, and splits it into several partitions. This provides partitions that are already disordered and can be later used by the data analytics engine that has been implemented.</li>
        <li><strong>Auto-scaling connector:</strong> this component leverages a time-series-based forecasting model, predicting resources available in supercomputers, to later auto-scale the amount of resources allocated to the Lithops-HPC backends. This achieves dynamic resource handling of the infrastructure transparently and efficiently. With this connector, the users no longer need to decide on resources for themselves.</li>
        <li><strong>ML accelerator connector:</strong> this component allows running the required random forest analytics based on XGBoost on multiple GPUs, splitting the data. For this, the Dask library has been merged together with the Data Plug partitioner.</li>
        <li><strong>HPC connector:</strong> this connector is the main component of Lithops-HPC. It connects the Lithops architecture with HPC platforms, enabling not only the usage of HPC computing resources but also handling heterogeneous supercomputing systems. This allows us to dynamically run on GPUs and CPU partitions, as well as enabling running on other devices (i.e., FPGAs) when available.</li>
    </ul>

    <h3>Summary of some results</h3>
    <p class="text-justify">The development of the HPC extreme data connector and its integration within Lithops has allowed for speed-up improvements of up to 36x in the data ingestion of the GWD use-case, solving its main bottleneck. Moreover, further improvements on the hyperparameter tuning and selection improved its performance by another 5x. On the other hand, the Lithops-HPC data connector not only has improved performance but also the user experience by providing a much easier handling of the supercomputing resources. This enhancement allows non-technical users to manage the supercomputer and launch the GWD use-case without dealing with the hurdles of HPC resource management. Such efficiency has been further boosted by integrating the auto-scaler connectors that allow Lithops-HPC to dynamically adapt resources to foreseen demands.</p>
</div>
<div style="height: 50px;"></div>