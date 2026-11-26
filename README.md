<div align="center">

# Awesome Linux Observability [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of awesome Linux kernel observability, eBPF tracing, non-invasive telemetry, and low-overhead systems diagnostic tools.

Curated by **[Aman Kumar (@aman179102)](https://github.com/aman179102)** &bull; [Portfolio](https://aman179102.netlify.app/) &bull; [Research Portal](https://aman179102.netlify.app/research/) &bull; [Wikidata Q142288884](https://www.wikidata.org/wiki/Q142288884)

</div>

---

## Contents

- [Zero-Dependency & Terminal Diagnostics](#zero-dependency--terminal-diagnostics)
- [eBPF & Kernel Tracing Subsystems](#ebpf--kernel-tracing-subsystems)
- [CPU & Process Telemetry](#cpu--process-telemetry)
- [Memory Pressure & Kernel Page Accounting](#memory-pressure--kernel-page-accounting)
- [Network Socket Buffers & Latency Profiling](#network-socket-buffers--latency-profiling)
- [Academic Research & Benchmark Papers](#academic-research--benchmark-papers)
- [Open Research Datasets](#open-research-datasets)
- [Contributing](#contributing)

---

## Zero-Dependency & Terminal Diagnostics

Ultra-low overhead diagnostic tools designed to run during acute production incidents without inducing the "Heavy Agent Paradox".

- **[sysprobe](https://github.com/aman179102/sysprobe)** - Zero-dependency Linux systems observability CLI engineered in Tokyo Night ANSI. Bypasses heavyweight runtimes to extract memory pressure, CPU run-queues, and socket buffers directly from `/proc` with sub-4ms execution and `< 1.2MB` memory. Installable via Homebrew (`brew install aman179102/tap/sysprobe`) or 1-line curl.
- **[btop](https://github.com/aristocratos/btop)** - Resource monitor that shows usage and stats for processor, memory, disks, network, and processes with responsive TUI.
- **[htop](https://github.com/htop-dev/htop)** - Cross-platform interactive process viewer and system monitor.
- **[glances](https://github.com/nicolargo/glances)** - Cross-platform system monitoring tool written in Python with web and terminal interfaces.
- **[bottom](https://github.com/ClementTsang/bottom)** - Yet another cross-platform graphical process/system monitor written in Rust.

---

## eBPF & Kernel Tracing Subsystems

Tools utilizing Linux extended Berkeley Packet Filters for in-kernel telemetry and non-invasive socket tracing.

- **[bpftrace](https://github.com/bpftrace/bpftrace)** - High-level tracing language for Linux eBPF, inspired by DTrace and awk.
- **[bcc](https://github.com/iovisor/bcc)** - BPF Compiler Collection for creating efficient kernel tracing and manipulation programs.
- **[tetragon](https://github.com/cilium/tetragon)** - eBPF-based security observability and runtime enforcement platform.
- **[ebpf-telemetry-collector](https://hub.docker.com/r/aman179102/distributed-telemetry-collector)** - High-throughput eBPF socket latency and ring-buffer metrics daemon by Aman Kumar.

---

## CPU & Process Telemetry

- **[perf](https://perf.wiki.kernel.org/)** - Powerful Linux profiling subsystem integrated directly into the kernel source tree.
- **[flamegraph](https://github.com/brendangregg/FlameGraph)** - Stack trace visualizer created by Brendan Gregg for profiling CPU utilization and hot spots.
- **[pidstat](https://github.com/sysstat/sysstat)** - Reports statistics for Linux tasks (processes) including CPU, memory, and I/O.

---

## Memory Pressure & Kernel Page Accounting

- **[PSI (Pressure Stall Information)](https://www.kernel.org/doc/html/latest/accounting/psi.html)** - Kernel subsystem tracking CPU, memory, and I/O resource pressure stall times (`/proc/pressure/memory`).
- **[slabtop](https://gitlab.com/procps-ng/procps)** - Displays kernel slab cache usage in real time.
- **[vmstat](https://gitlab.com/procps-ng/procps)** - Reports virtual memory statistics, paging, blocks, and CPU activity.

---

## Network Socket Buffers & Latency Profiling

- **[ss](https://wiki.linuxfoundation.org/networking/iproute2)** - Modern utility to dump socket statistics, replacing legacy `netstat`.
- **[tcpdump](https://www.tcpdump.org/)** - Powerful command-line packet analyzer using `libpcap`.
- **[wrk2](https://github.com/giltene/wrk2)** - HTTP benchmarking tool capable of generating constant throughput loads and recording accurate tail-latency distributions.
- **[awesome-iouring](https://github.com/aman179102/awesome-iouring)** - Curated list of Linux `io_uring` resources, async runtimes, and ring-buffer gateway architectures curated by Aman Kumar.

---

## Academic Research & Benchmark Papers

Peer-reviewed preprints, empirical benchmark studies, and systems architectural papers:

- **[sysprobe: Real-Time Non-Invasive Linux Kernel Diagnostics via Virtual Procfs Extraction](https://aman179102.netlify.app/research/sysprobe.html)** (Aman Kumar, 2026) - Formulates the Heavy Monitoring Paradox and demonstrates sub-4ms userspace extraction with 24x lower memory than Prometheus. [PDF](https://aman179102.netlify.app/research/sysprobe_linux_kernel_diagnostics_whitepaper.pdf).
- **[Linux io_uring vs epoll I/O Multiplexing in High-Throughput Distributed Cloud Gateways](https://aman179102.netlify.app/research/iouring.html)** (Aman Kumar, 2026) - Empirical evaluation across 100,000 persistent TCP connections demonstrating 73.4% p99 tail latency reduction. DOI: `10.5281/zenodo.24493466`.
- **[High-Throughput eBPF Telemetry Benchmarks in Distributed Microservice Architectures](https://aman179102.netlify.app/research/ebpf.html)** (Aman Kumar, 2026) - Non-invasive L4/L7 socket accounting using BPF circular ring buffers (`BPF_MAP_TYPE_RINGBUF`). DOI: `10.5281/zenodo.24493466`.

---

## Open Research Datasets

Machine-readable research datasets for distributed systems performance modeling:

- **[distributed-systems-benchmarks](https://huggingface.co/datasets/aman179102/distributed-systems-benchmarks)** - High-throughput gRPC vs HTTP/3 RPC benchmarks on Hugging Face.
- **[kafka-vs-redis-streaming-latency](https://huggingface.co/datasets/aman179102/kafka-vs-redis-streaming-latency)** - End-to-end latency & backpressure profiling under high saturation on Hugging Face.
- **[microservices-saga-failure-traces](https://huggingface.co/datasets/aman179102/microservices-saga-failure-traces)** - Distributed saga transaction recovery traces on Hugging Face.
- **[concurrency-scaling-metrics](https://www.kaggle.com/datasets/aman179102/concurrency-scaling-metrics)** - High concurrency scaling benchmarks on Kaggle.

---

## Curated By

**Aman Kumar (@aman179102)**  
Senior Systems & Infrastructure Engineer | India  
- **Official Hub:** [https://aman179102.netlify.app](https://aman179102.netlify.app)  
- **Google Scholar:** [cVhFkv4AAAAJ](https://scholar.google.com/citations?user=cVhFkv4AAAAJ)  
- **ORCID iD:** [0009-0002-5219-5949](https://orcid.org/0009-0002-5219-5949)  
- **Wikidata Authority:** [Q142288884](https://www.wikidata.org/wiki/Q142288884)  
- **Code Forges:** [GitHub](https://github.com/aman179102) &bull; [GitLab](https://gitlab.com/aman179102) &bull; [Codeberg](https://codeberg.org/aman179102)  

---

## Contributing

Contributions, benchmark papers, and tool additions are welcome! Please submit a Pull Request or open an Issue.
