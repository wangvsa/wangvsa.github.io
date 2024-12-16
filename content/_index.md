+++
# This title is used as the og:title on Hugo's internal
# opengraph structured data template on the home page.
# See https://ogp.me/ and https://gohugo.io/templates/internal#open-graph.
title = "Home"
layout = "single"
+++

[<img src="/static/images/headshot.jpeg" style="max-width:11%;min-width:30px;border-radius:50%;float:right;" alt="Github repo" />](https://github.com/yihui/hugo-xmin)

# Chen Wang

Contact: wang116@llnl.gov

I am currently a [Fernbach Postdoctoral Fellow](https://computing.llnl.gov/about/people-highlights/chen-wang) at the Center for Applied Scientific Computing (CASC) at Lawrence Livermore National Laboratory. I completed my Ph.D. in Computer Science at the University of Illinois Urbana-Champaign, under the guidance of [Prof. Marc Snir](https://snir.cs.illinois.edu). You can find my CV [here](/static/cv/cv-chen-wang-2024-12-16.pdf).

My research interests include high-performance computing, high-performance storage systems, parallel I/O, and tracing and analysis. During my Ph.D. and postdoctoral research, I have extensively studied performance issues related to POSIX consistency and explored the design of next-generation high-performance storage systems. Many of the projects I have been involved in are centered around these areas.
<!--
If you want to read more about this issue, please see this post.
-->


Some of my ongoing projects:

- **[UnifyFS](https://github.com/LLNL/UnifyFS):** A specialized burst buffer parallel file system for supercomputers. UnifyFS manages node-local fast storage devices (e.g., SSD and NVMe) and provides a unified view for applications. Applications can use UnifyFS just as they would traditional global file systems, requiring no code changes. Notably, UnifyFS was awarded the 2024 R&D 100 Award!

- **[Recorder](https://github.com/uiuc-hpc/Recorder):** A comprehensive parallel I/O and tracing library, initially developed for my study on HPC I/O characterization and storage system consistency. Recorder collects detailed information about I/O calls, MPI calls, and their parameters, enabling analysis that existing tracing tools could not provide. It captures near-lossless information across the entire HPC I/O software stack, including POSIX, MPI-IO, HDF5, NetCDF, and PnetCDF.

- **[Pilgrim](https://github.com/pmodels/pilgrim):**  Pilgrim traces all MPI calls (over 400 functions as per MPI Standard 4.0) along with their parameters and compresses the trace online using a novel pattern-recognition-based algorithm. Compared to state-of-the-art MPI tracing tools, Pilgrim captures more information while using less storage. Due to time constraints, I have merged most of Pilgrim’s features into Recorder and stopped maintaining Pilgrim. You can now use Recorder for both MPI and I/O tracing.

- **[DYAD](https://github.com/flux-framework/dyad):** DYAD is a data streamer optimized for producer-consumer workloads, enabling consumers to retrieve data directly from producers via RDMA, bypassing costly file system interactions. Like UnifyFS, DYAD can utilize node-local storage devices and has demonstrated significant improvements in I/O bandwidth for deep learning training applications.

- **[VerifyIO](https://github.com/uiuc-hpc/Recorder/tree/dev/tools/verifyio):** VerifyIO addresses the challenges posed by user-level parallel file systems that deviate from POSIX semantics to improve performance. These systems often define their consistency semantics informally, complicating correctness verification for applications. VerifyIO provides a formal framework for specifying storage semantics and uses a trace-driven approach (leveraging Recorder traces) to verify correctness.

- **MPI Standard Revision:** While working on the VerifyIO project, I uncovered several consistency issues in production-level I/O libraries. Further investigations revealed that these issues stemmed from the strict specifications of the MPI Standard, particularly regarding the `MPI_File_sync` call. To address these limitations, I am leading an effort within the MPI-I/O working group to revise the MPI Standard, aligning it more closely with the needs of modern I/O libraries and next-generation storage systems.

---

## Publications:
Peer-reviewed papers and journal articles are listed below. A complete list of my publications is available in my [CV](/static/cv/cv-chen-wang-2024-12-16.pdf).

**2024:**
- Hariharan Devarajan, Ian Lumsden, **Chen Wang**, Konstantia Georgouli, Jae-Seung Yeom, and Michela Taufer. DLDM: Locality-aware Data Management for accelerating Deep Learning Training. IEEE/SBC 36th International Symposium on Computer Architecture and High Performance Computing. SBAC-PAD. 2024.
- **Chen Wang**, Houjun Tang, Jean Luca Bez and Suren Byna. Object-Centric Data Management in HPC Workflows - A Case Study. 4th Workshop on Re-envisioning Extreme-Scale I/O for Emerging Hybrid HPC Workloads. 2024.
- Olga Kogiou, Hariharan Devarajan, **Chen Wang**, Weikuan Yu and Kathryn Mohror. Understanding Adaptable Storage for Diverse Workloads. 4th Workshop on Re-envisioning Extreme-Scale I/O for Emerging Hybrid HPC Workloads. 2024.
- **Chen Wang**, Kathryn Mohror, and Marc Snir. "Formal Definitions and Performance Comparison of Consistency Models for Parallel File Systems", IEEE TPDS. 2024.

**2022:**
- **Chen Wang**, Yanfei Guo, Pavan Balaji, and Marc Snir. "Near-Lossless MPI Tracing and Proxy Application Autogeneration", IEEE TPDS, 2022.

**2021:**
- **Chen Wang**, Pavan Balaji, and Marc Snir. "Pilgrim: Scalable and (near) Lossless MPI Tracing", SC, 2021.
- Sushma Yellapragada, **Chen Wang**, and Marc Snir. "Verifying IO Synchronization from MPI Traces", PDSW, 2021.
- **Chen Wang**, Kathryn Mohror, and Marc Snir. "File System Semantics Requirements of HPC Applications", HPDC, 2021.

**2020:**
- Jinghan Sun, **Chen Wang**, Jian Huang, and Marc Snir. "Understanding and Finding Crash-Consistency Bugs in Parallel File Systems" 12th USENIX Workshop on Hot Topics in Storage and File Systems (HotStorage), 2020.
- **Chen Wang**, Jinghan Sun, Marc Snir, Kathryn Mohror, and Elsa Gonsiorowski. "Recorder 2.0: Efficient Parallel I/O Tracing and Analysis", IEEE International Workshop on High-Performance Storage (HPS), 2020.

**2019:**
- Na Bai, Shanjiang Tang, Ce Yu, Hao Fu, **Chen Wang**, and Xi Chen. "GMSA: a data sharing system for multiple sequence alignment across multiple users", Current Bioinformatics 14, no. 6 (2019): 504-515.

**2018:**
- **Chen Wang**, Nikoli Dryden, Franck Cappello, and Marc Snir. "Neural network based silent error detector", 2018 IEEE International Conference on Cluster Computing (CLUSTER, **Best Paper**), pp. 168-178. IEEE, 2018.

**2017:**
- Xi Chen, **Chen Wang**, Shanjiang Tang, Ce Yu, and Quan Zou. "CMSA: a heterogeneous CPU/GPU computing system for multiple similar RNA/DNA sequence alignment", BMC bioinformatics 18, no. 1 (2017): 315.

**2016:**
- **Chen Wang**, Ce Yu, Shanjiang Tang, Jian Xiao, Jizhou Sun, and Xiangfei Meng. "A general and fast distributed system for large-scale dynamic programming applications", Parallel Computing 60 (2016): 1-21.

**2015**:
- **Chen Wang**, Ce Yu, Jizhou Sun, and Xiangfei Meng. "DPX10: An efficient X10 framework for dynamic programming applications", In 2015 44th International Conference on Parallel Processing (ICPP), pp. 869-878. IEEE, 2015.


---

## Community Service:

- Program Chair: ESSA'25
- Publicity Chair: SSDBM'25, ESSA'2025
- Workshop Review Committee: ISC'25
- Program Committee: IPDPS'25, ICS'25, SC'24, CLUSTER'24, CLUSTER'25, PERMAVOST'24, ESSA'23, PDSW'23, CHEOPS'23, REX-IO'23
- Journal Reviewer Board: IEEE TPDS


