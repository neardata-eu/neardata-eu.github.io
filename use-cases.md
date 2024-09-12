---
layout: page
background: grey
---

<div class="col-lg-12 text-center mb-4">
	<h2 class="section-heading text-uppercase">Use cases</h2>
</div>
<h3>Genomics</h3>
<p>Creation of methods, fast storage, and communications infrastructures to communicate distributed computing power with scalable storage systems, allowing efficient distribution of datasets across the system.</p>

<h4>Variants-Interactions Use Case</h4>
<p>Complex diseases, such as Type 2 Diabetes (T2D), are caused by the simultaneous effect of multiple
genomic variants and other environmental factors. During the last decades, the genomic study of T2D has been broadly approached with diverse methods. However, although hundreds of genomic variants are expected to contribute to disease development, the study of the relation between variants and T2D has been only analyzed in a single independent manner. There are different reasons to avoid this type of analysis. Among them, the analysis of variant interactions and their contribution to developing the disease is an extreme computational problem. Indeed, here we present two use cases where we tackle this type of analysis with different methods:</p>
<ul>
    <li>Genome-Wide discovery (GWD): use machine learning methods to find groups of variants that, simultaneously, are associated with T2D.</li>
    <li>Multi Dimensionality Reduction (MDR): use statistical methods to discover pairs of variants which, synergically, contribute to the development of T2D.</li>
</ul>


<h4>Transcriptomics Use Case</h4>
<p>Original pipeline was created for HPC execution by a domain specialist. It consists of four steps listed below:</p>

<ol>
    <li>Downloading .sra file using prefetch tool.</li>
    <li>Converting into .fastq files using fasterq-dump tool.</li>
    <li>Alignement and quantification of reads using Salmon or STAR.</li>
    <li>Count normalization using DESeq2.</li>
</ol>


<h4>Genomics Use Case</h4>
<p>ariant calling in genomics involves “alignment” (i.e., a string similarity search) of sequencing reads,
stored as FASTQ files, to a reference genome, stored as a FASTA file. Alignment mismatches are filtered and form the basis for establishing (“calling”) any mutations (“variants”) in the samples
analyzed. Alignment requires loading large data structures (“indices”) into memory allowing for fast similarity searches in the reference genome. With indices ranging up to 50 GB for large datasets,
loading a full index in a lambda function is not feasible due to resource constraints. Alternatively, the reference genome can be split into smaller chunks and align reads to all of them. Consequently,a reduce step is required to collect and score all alignments for each read later on. FASTQ reads can also be chunked to trivially increase parallelism, as each sequencing read is aligned to the genome
independently.</p>

<p>The original HPC implementation involved bash scripts and CLI tools that utilized the local file system and pipe commands to pass data between processes. To transition this pipeline into a serverless architecture, we employed Python code to wrap the genomic CLI tools and introduce new logicfor data partitioning and load distribution across fine-grained serverless tasks.</p>

<p>Porting this pipeline to a serverless architecture for scalability poses several technical challenges, including the need for effective and efficient FASTA and FASTQ file partitioning with appropriate
partition sizes, dealing with blocking code due to data dependencies, and managing stateful data shuffling.</p>

<p>NEARDATA’s serverless data analytics platform Lithops provides facilities for massively invoking functions across different cloud providers. Also, the existence of parallelization in the HPC im-
plementation allows Lithops to fit perfectly to port this implementation to a serverless architecture.</p>


<h3>Metabolomics</h3>
<p>Expand the analysis of metabolomics raw data and boost external access and efficient re-use of open data. Creation of federated and Hybrid distributed architecture and ensuring data privacy but also shared global computations.</p>

<h4>Metabolomics Use Case</h4>
<p>METASPACE was developed in the EU Horizon2020 project METASPACE in 2015-2018 (grant ID 634402). Furthermore, in the EU Horizon 2020 project CloudButton 2019-2022 (grant ID 825184), we have developed a novel version of METASPACE underlying metabolite identification engine by
employing the serverless framework Lithops. The serverless version of METASPACE helped providing better service to the users and was recognized as a notable Deep Tech innovation by the EU Innovation Radar.</p>

<p>METASPACE became a leading software in the emerging field of spatial metabolomics; It can be used for data from various samples and technologies with various applications in multiple fields of biology, medicine, and pharmacology. METASPACE provides capacities for big data analysis, results sharing, and can be used in conjunction with other software through API. It is used by more than 2600 users from over 160 groups from multiple contributing institutions world-
wide. We have processed more than 45.000 datasets submitted, with more than 10.000 of them made public under the CC-BY 4.0 license. Most users access METASPACE through our web app; however we also provide headless access through API which is used in particular by major users.</p>

<p>METASPACE is open-source 18 and free supported by the funding from the EC, National Institutes of Health (NIH) from USA, as well as from a number of other grants. Importantly for the field
and for this project, a large number ( 30%) of the datasets are made public by their submitters (under the CC-BY 4.0 license) that created the largest data space in this field.</p>

<p>For processing large numbers of diverse datasets, we have implemented METASPACE as a scalable data processing platform using the serverless framework Lithops, depicted in Figure 52. More over, the data storage infrastructure on METASPACE allows to store all the incoming files together
with the processing results (identified metabolites) and other metadata. Overall, accumulated data on METASPACE amounts to over 45 TB as of April 2024.</p>

<p>Altogether, the scientific position and reputation, a worldwide community of users, the large number and size of datasets, and cloud architecture of data storage position METASPACE as an International Health Data Space in the field of spatial metabolomics.</p>

<p>In this project, we aim to further improve the open METASPACE cloud platform and strengthen its position as a International Health Data Space.</p>


<h3>Surgery</h3>
<p>Create generalised machine-learning models that can aid surgeons during surgery and allow video data to be analysed in real-time and with low latency.</p>

<h4>Use Case Surgery</h4>
<p>Our use-case in surgery encompasses two distinct focal points. Firstly, we address the challenges inherent in Federated Learning, with a primary objective of improving its security protections. To
achieve this, we leverage the Flower framework, enclosing its functionalities within a Docker container for streamlined deployment and management. Additionally, we integrate Scone to ensure security, ensuring the preservation of privacy throughout the Federated Learning processes.</p>
<p>Secondly, we embark on the development of a surgical video streaming application to handle multiple inference jobs. Our current testbed on Dell’s Cork lab can be found in Figure 17. Our strat-
egy revolves around the integration of Pravega and GStreamer into our existing pipelines. This integration empowers us to harness the advanced processing capabilities offered by GStreamer plugins,
including our developed segmentation, phase detection, and tool detection plugins. Furthermore, by integrating both GStreamer and Pravega into our infrastructure, we establish a robust ecosystem that
contributes to efficient data collection, processing, and storage within the context of surgical video streaming.</p>
