# YC Startup School Application Answers

---

## Please tell us about things you've built before. For example apps you've built, websites, open source contributions. Include URLs if possible.

**Gigaflow vSwitch** (https://gigaflow-vswitch.github.io) — A new caching architecture for virtual switches on SmartNICs. The core insight: existing vSwitch caches (like Open vSwitch's Megaflow) cache entire pipeline traversals, wasting space and missing locality. Gigaflow caches sub-traversals in a multi-table pipeline, achieving up to 51% higher cache hit rates, 90% fewer cache misses, and 450x larger rule space coverage on real-world workloads. Published at ASPLOS 2025. Covered by P4.org, TechXplore, and UMich CSE news. Currently a Google Summer of Code 2025 project.

**SpliDT** (https://splidt-decision-trees.github.io) — A system for running decision tree ML models directly inside network hardware at line rate (terabits/sec), without a CPU in the critical path. Published at NSDI 2026. SpliDT partitions decision trees across the hardware pipeline and consistently dominates the accuracy-vs-resource Pareto frontier compared to prior art.

**AI-ForestWatch** (https://github.com/annusgit/ForestCoverChange) — An end-to-end deep learning pipeline using Landsat-8 satellite imagery to detect and quantify forest cover change across Pakistan's Billion Tree Tsunami afforestation regions (2014–2020). Used UNet for per-pixel semantic segmentation, Google Earth Engine for data preprocessing, and temporal inference to generate gain/loss maps. Published in Journal of Applied Remote Sensing (2021). 31 GitHub stars, 8 forks.

**aisuite contributor** (https://github.com/andrewyng/aisuite) — Contributed to Andrew Ng's open-source library providing a unified Python interface across all major LLM providers (OpenAI, Anthropic, Google, etc.). 13.7K GitHub stars, 1.4K forks.

**Smart Sensor Network / WiserMachines** — Designed hardware and wrote firmware for industrial IoT sensor nodes deployed at Pakistan Aeronautical Complex (PAC), Kamra — one of Pakistan's largest defense industrial facilities. The nodes performed waveform profiling and load current tracking on industrial machines to feed a shop floor digitization system, enabling job schedule tracking, power usage calculations, and predictive maintenance. Nodes extracted Class-0 Power over Ethernet and communicated over standard network protocols with on-chip and offloaded Ethernet controllers. This work won the National P@SHA ICT Award (Pakistan's premier tech industry award) and spun off into WiserMachines, a startup building smart sensor networks for industrial machine telemetry — providing critical monitoring infrastructure for expensive legacy industrial machines that were previously entirely dark.

**Stealth Startup (Founding Team)** — Currently a founding team member building a network transport layer purpose-built for AI inference and training workloads. This covers the full stack of AI communication primitives: inter-node transport, intra-node transport, KV-cache transfer, and the coordination fabric required for large-scale distributed inference and training. The core thesis is that existing network transports were designed for general-purpose workloads and are fundamentally mismatched to the communication patterns of modern AI systems at scale.

---

## Please tell us in one or two sentences about the most impressive thing that you have built or achieved.

I've consistently found non-traditional angles in systems research that others missed: Gigaflow rethought caching locality in virtual switches from first principles, got published at ASPLOS, was selected for Google Summer of Code and presented at Google Networking Summit, Intel, IBM, and ETH Zurich; Kairo then took incremental computation — a technique from database systems — and applied it to cache eviction in virtual switches, a connection nobody in networking had thought to make.

---

## Please tell us about a time you most successfully hacked some (non-computer) system to your advantage.

I grew up in Pakistan wanting to do systems research at top US institutions — but for someone coming from Pakistan, the standard path in simply doesn't exist without money, connections already inside the system, or a lucky break. So I reverse-engineered it.

First, I noticed my undergraduate advisor had active collaborators in Germany. I deliberately chose my thesis topic around their joint research area — not just because it was interesting, but because it gave me a legitimate reason to push for a DAAD-funded internship at TU Kaiserslautern. That internship produced a published paper, which was a credential I otherwise couldn't have built in Pakistan.

Then I applied to prestigious US master's programs I would have loved to attend but simply couldn't afford. Not just out of hope — but to collect admits. I used those offers as proof of credibility when applying to funded PhD programs, essentially borrowing the reputation of programs I couldn't pay for to unlock doors that required demonstrated selectivity to enter.

It worked. I converted those admits into a fully-funded PhD offer with a Ross Fellowship at Purdue, and when my advisor later moved to the University of Michigan, I transferred my PhD with him — eventually publishing at ASPLOS, NSDI, and SIGCOMM, the top venues in my field.

The system assumed you either had money, or already had institutional backing. I found the two pressure points where neither was strictly required — a collaborative research relationship and an admissions signal — and used each one to manufacture the next credential in the chain.
