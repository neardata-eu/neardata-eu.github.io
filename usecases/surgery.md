---
layout: page
title: Surgery
background: grey
permalink: /usecases/surgery/
---

<div class="container">
    <div class="col-lg-12 text-center mb-4">
        <h2 class="section-heading text-uppercase">Surgery</h2>
    </div>

    <div class="row justify-content-center mb-5">
        <div class="col-lg-10">
            <div class="embed-responsive embed-responsive-16by9 shadow-lg rounded">
                <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/_qlivJXrH8c" title="Surgery Use Case" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
            </div>
        </div>
    </div>

    <h3>Brief introduction</h3>
    <p class="text-justify">Healthcare systems currently confront an aging demographic alongside a reduction in the surgical workforce. Consequently, the necessity for operational efficiency within the operating room is critical. Surgical Data Science enhances the quality and value of interventional healthcare through the systematic capture, organization, analysis, and modeling of data. This research domain facilitates surgery assisted by computers and robots. It thereby improves patient outcomes, including superior cosmetic results, reduced infection risks, and lower morbidity rates. Furthermore, it enhances the surgical experience through tremor filtration, improved visualization, and greater freedom of movement for surgical instruments. Nevertheless, the full potential of these systems depends on the availability of surgical data, which requires secure handling and rigorous model training.</p>

    <div class="row mb-4 mt-4">
        <div class="col-md-6 mb-3">
            <img src="/assets/img/usecases/neardata_surgery1.png" class="img-fluid rounded shadow" alt="Surgery Interface 1">
        </div>
        <div class="col-md-6 mb-3">
            <img src="/assets/img/usecases/neardata_surgery2.png" class="img-fluid rounded shadow" alt="Surgery Interface 2">
        </div>
    </div>

    <h3>Introduction of the problem</h3>
    <p class="text-justify">The primary impediment to advancing AI driven surgery is the limited accessibility of training data. Artificial intelligence models require extensive datasets for effective learning. However, hospitals must adhere to strict data protection regulations. Examples include the General Data Protection Regulation in Europe or the Health Insurance Portability and Accountability Act in the US. These laws restrict the sharing of sensitive patient records. Traditional Federated Learning attempts to address this by training models across decentralized devices. Yet, this approach often presents issues regarding strict security requirements and the processing of heterogeneous data types. Consequently, medical institutions face difficulties when attempting to combine knowledge or extract reliable insights across different facilities without compromising patient privacy or compliance protocols.</p>
    <p class="text-justify">A secondary challenge involves the issue of data silos. Large hospitals accumulate vast quantities of patient data and surgical video streams. Researchers seeking specific data points for experiments often struggle to locate relevant information within these massive repositories. As a result, significant amounts of data frequently remain unutilized.</p>

    <h3>How NEARDATA will address the challenge</h3>
    <p class="text-justify">NEARDATA addresses both of these significant challenges. The consortium has previously validated the efficacy of distributed training algorithms by organizing a Federated Learning Challenge. This initiative specifically targeted the critical balance between generalization and adaptation. Furthermore, the team has contributed to the field through research on foundation model training utilizing Federated Learning. Building upon this algorithmic groundwork, NEARDATA introduces hardware based security layers.</p>
    <p class="text-justify">This architecture ensures that only verified and trusted hospitals participate in the workflow. The incorporation of SCONE into the federated workflow prevents unauthorized entities from accessing the learning loop.</p>
    <p class="text-justify">Additionally, NEARDATA mitigates the data silo issue through the establishment of a secure data querying framework. This system renders complex surgical data queryable via the StreamSense workflow.</p>

    <h3>How it will work</h3>
    <p class="text-justify">The NEARDATA solution functions through a combination of rigorous data security and high speed semantic search.</p>
    <ul>
        <li><strong>Federated Learning and Trusted Execution Environments (TEEs)</strong> ensure confidentiality by utilizing Intel SGX technology. This architecture allows data processing to take place within an isolated and hardware protected enclave. The platform employs SCONE to ensure comprehensive protection. This includes shielding data at rest within the file system, in transit over the network, and during actual processing.</li>
        <li><strong>StreamSense</strong> manages the substantial influx of surgical video through a semantic search engine constructed on tiered streaming storage. Rather than relying on manual video tagging, AI models generate embeddings from video frames to create a two level index. This capability enables researchers to execute complex queries both between and within videos instantly. Consequently, users can identify specific surgical moments without the need to download hours of footage.</li>
    </ul>

    <h3>Summary of some results</h3>
    <p class="text-justify">The NEARDATA consortium has successfully validated the technical infrastructure required for secure and efficient surgical data science. Regarding the security framework, the implementation of TEEs provided verifiable proof of isolation for sensitive computation. This validation confirms that the system maintains rigorous confidentiality standards during the execution of complex federated workflows.</p>
    <p class="text-justify">On the performance front, the semantic video search solution yielded substantial efficiency gains. Benchmarking of the tiered streaming storage architecture revealed that users can retrieve relevant video fragments in less than 30 milliseconds. Furthermore, the system significantly optimizes the pipeline for artificial intelligence model development. By enabling targeted dataset creation, the platform reduced the necessary data transfer overhead by more than 80 percent compared to conventional bulk retrieval methods.</p>
</div>
<div style="height: 50px;"></div>