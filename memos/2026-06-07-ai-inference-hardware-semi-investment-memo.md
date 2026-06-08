- tags:: [[semiconductor]], [[inference]], [[AI infrastructure]], [[data-center]], [[HBM]], [[HBF]], [[DRAM]], [[NAND]], [[packaging]], [[$NVDA]], [[$TSM]], [[$MU]], [[$MRVL]]

- **Source**: user-provided PDF, "Challenges and Research Directions for Large Language Model Inference Hardware," Xiaoyu Ma and David Patterson (Google), PDF dated 2026-02-06

- ## Bottom line
	- The paper's core investment message is that **LLM inference bottlenecks are shifting away from raw FLOPS and toward memory capacity, memory bandwidth, and interconnect latency**.
	- That is bullish for the parts of the semi stack that solve the **decode-phase memory wall**: HBM, advanced packaging, low-latency networking, and potentially a new on-package NAND tier via **High-Bandwidth Flash (HBF)**.
	- It is also a warning that the current "more giant reticle dies + more FLOPS" framing is incomplete. Future AI hardware spend may tilt further toward **memory architecture, 3D integration, and communication fabrics**, not just accelerator compute silicon.

- ## Main arguments from the paper
	- **Inference, not training, is the economic problem**:
		- The authors argue the cost of inference determines economic viability as model usage scales.
		- They cite forecasts for **AI inference chip annual sales to grow 4x-6x over the next 5-8 years**.
	- **Decode is fundamentally memory-bound**:
		- Transformer inference has two phases:
			- **Prefill**: parallel and often compute-bound
			- **Decode**: sequential/autoregressive and therefore memory-bound
		- The practical implication is that scaling compute alone does not fix the hardest part of serving large models.
	- **The workload is getting harder in exactly the wrong way for current hardware**:
		- **MoE** increases memory and communication demands
		- **Reasoning models** increase latency and memory strain through long "thinking" token sequences
		- **Long context** and **RAG** expand KV-cache and retrieval requirements
		- **Multimodal** inference raises data movement requirements
	- **Current AI hardware is mismatched to decode inference**:
		- The paper explicitly argues that the current hardware philosophy of **full-reticle die + many HBM stacks + bandwidth-optimized interconnect** is a poor fit for decode-heavy inference.
		- Their proposed focus areas are:
			- **HBF** for much more memory capacity
			- **PNM / 3D memory-logic stacking** for higher effective memory bandwidth
			- **Low-latency interconnect** for multi-chip inference systems

- ## Key data points worth carrying into semi work
	- **Performance and cost trends**
	
	  | Topic | Data point | Why it matters |
	  |---|---|---|
	  | Compute vs memory scaling | NVIDIA GPU FP64 FLOPS rose **80x** from 2012 to 2022; memory bandwidth rose only **17x** | The inference bottleneck shifts toward memory bandwidth rather than raw compute |
	  | HBM bandwidth progression | HBM stack bandwidth rose from **128 GB/s** in 2013 to **2,048 GB/s** for HBM4 in 2026 | HBM is still improving aggressively, but not enough to close the memory-wall gap |
	  | HBM capacity progression | Max HBM stack capacity rose from **4 GiB** to **64 GiB** | Capacity growth exists, but remains small relative to the needs of giant inference models |
	  | HBM economics | Normalized HBM **$/GB** and **$/GBps** both increased **1.35x from 2023 to 2025** | Supports pricing power for HBM suppliers, but also creates incentive for substitution |
	  | DDR economics | DDR4 normalized capacity cost fell to **0.54x** and bandwidth cost fell to **0.45x** from 2022 to 2025 | Commodity DRAM keeps getting cheaper, widening the economic gap vs HBM |
	  | DRAM density scaling | A **4x** gain from 8Gb DRAM dies introduced in 2014 will take **more than 10 years** vs historical **3-6 years** for prior 4x gains | Reinforces that memory scaling is slowing structurally |
	- **HBF vs incumbent memory tiers**
	
	  | Memory type | Capacity | Bandwidth | Power | Read latency | Notes |
	  |---|---:|---:|---:|---|---|
	  | **1 HBF stack** | **512 GB** | **1,638 GB/s** read | **<80W** | **1,000s of ns** | Low write endurance; much higher capacity than HBM |
	  | **1 HBM4 stack** | **48 GB** | **1,638 GB/s** | **40W** | **10-100 ns** | Much lower capacity, but far better latency/endurance |
	  | **1 DDR5-6400 64GB module** | **64 GB** | **51 GB/s** | **12W** | **10-100 ns** | Cheap and standard, but far lower bandwidth |
	  | **1 flash card** | **4,096 GB** | **4 GB/s** read | **50W** | **10,000s of ns** | Huge capacity, but nowhere near accelerator-grade bandwidth |
	- **Read-through**: HBF is presented as roughly **10x the capacity of HBM at similar bandwidth**, but with materially worse latency and endurance, so it is a **bridge tier**, not a replacement.
	- **PNM vs PIM matters commercially**
	
	  | Dimension | PIM | PNM | Investment read-through |
	  |---|---|---|---|
	  | Bandwidth-per-watt | **5x-10x** of standard | **2x-5x** of standard | PIM wins on raw efficiency |
	  | Memory pricing | Loses commodity-memory economics | Preserves commodity-memory economics | PNM is more commercially scalable |
	  | Process optimization | Logic constrained by memory process | Separate logic and memory process nodes | PNM is easier to optimize and iterate |
	  | Software sharding | Often **32-64 MB** bank-sized shards | **16-32 GB** shards | PNM is far easier to program for datacenter LLMs |
	- **3D memory-logic stacking**
	
	  | Claim | Data point | Why it matters |
	  |---|---|---|
	  | Bandwidth | Compute-on-HBM-base-die can keep **HBM-level bandwidth** | Memory-adjacent compute does not require sacrificing bandwidth |
	  | Power | Power can be **2-3x lower** because of shorter data paths | Important for inference TCO, rack density, and thermals |

- ## What matters for semi investors
	- **Memory remains the first-order bottleneck**:
		- This paper reinforces the existing bullish case for HBM and server DRAM: inference scaling pushes memory harder than consensus still appreciates.
		- It also strengthens the case that **NAND/flash becomes more strategic**, not just cheaper bulk storage, if HBF or related near-flash architectures become real.
	- **HBM scarcity should persist, but HBM may not capture every dollar of future memory growth**:
		- Bullish: the paper is explicit that HBM is capacity-constrained and increasingly expensive.
		- Nuance: if HBF emerges, some future inference memory spend could shift from incremental HBM content toward **on-package or near-package flash tiers**.
	- **Advanced packaging value increases**:
		- The proposed solutions all depend on tighter integration between logic and memory:
			- HBM-style stacking
			- TSV-based 3D stacking
			- base-die compute
			- possibly flash stacked like HBM
		- That is supportive for the packaging layer of the stack, especially foundry/platform vendors with leadership in **CoWoS / SoIC / Foveros / hybrid bonding / interposer-style integration**.
	- **Networking/interconnect becomes a bigger part of the AI bill of materials**:
		- The paper argues inference cares more about **latency than bandwidth** for many small messages.
		- It explicitly highlights:
			- high-connectivity topologies
			- in-network reduction / processing-in-network
			- placing compute closer to the NIC
		- This is bullish for low-latency AI networking and switch silicon, not just GPUs.
	- **Commercially, PNM looks more investable than PIM for datacenter inference**:
		- The authors are clear that PNM is the better datacenter fit because it preserves commodity memory economics and is much easier to program.
		- That is important because it favors solutions that extend or augment the current ecosystem rather than requiring a full bespoke memory-compute redesign.

- ## Company-level read-through
	- **Memory Big 3 (Samsung, SK hynix, Micron)**:
		- Positive on the existing HBM/DRAM thesis because the paper reinforces the memory wall, HBM cost pressure, and DRAM density slowdown.
		- Incrementally positive on NAND optionality because **HBF reframes flash as a future inference-memory tier**, not just SSD storage.
		- Samsung looks especially well positioned conceptually because it spans NAND, DRAM/HBM, and advanced packaging / logic integration.
	- **TSMC / Intel packaging ecosystem**:
		- Beneficiaries if the architectural roadmap shifts toward more 3D integration and more memory-logic co-packaging.
		- The paper is effectively a vote for more value migrating into the packaging/integration layer.
	- **NVIDIA and AI-networking vendors**:
		- Positive for $NVDA not only as GPU vendor but as a networking / system-architecture vendor.
		- The paper's interconnect section aligns with the importance of **NVLink, InfiniBand SHARP, and in-network acceleration**.
		- It also supports the view that full-stack AI system design matters more than chip-level FLOPS leadership alone.
	- **Marvell / CXL-memory-expansion style players**:
		- Positive read-through because the paper explicitly cites **Marvell Structera CXL-PNM** as an example of a more software-friendly near-memory approach.
		- If inference systems become more heterogeneous, memory-expansion and memory-fabric controllers could capture more value.
	- **Cerebras / Groq-style SRAM-first approaches**:
		- The paper is skeptical that SRAM-only architectures can carry the full workload as model sizes grow.
		- That does not kill the thesis for niche latency-sensitive systems, but it weakens the idea that SRAM alone can route around external memory indefinitely.

- ## Most important sections to feed back into existing memory work
	- **For [[DRAM-memory-ssd-index-thesis]]**:
		- Strong support for the claim that AI is turning memory into a strategic bottleneck rather than a commodity
		- Strong support for HBF as a real architectural possibility that can **expand NAND's role in inference**
		- Good evidence that **HBM economics worsen as technical complexity rises**, which supports pricing power but also motivates architectural substitution
	- **For [[2026-06-06-nvidia-cmx-kv-cache-flash-storage-tier]]**:
		- HBF is a more aggressive version of the same idea as CMX: flash moving up the memory hierarchy toward active inference
		- The common theme is that **NAND becomes a performance memory tier**, not just archival storage
	- **For packaging / networking work**:
		- The paper strengthens the idea that future AI semi winners include not just compute and memory vendors, but also **advanced packaging** and **low-latency interconnect** suppliers

- ## What is still speculative / what to watch
	- This is a **research agenda**, not a proof that these architectures are commercially imminent.
	- The biggest open questions are:
		- whether **HBF** can overcome endurance and read-latency issues well enough for real deployment
		- whether value accrues to **memory vendors** or instead to **system integrators / foundries / accelerator vendors**
		- whether **PNM** can move from promising demos into standard datacenter deployments
		- whether low-latency interconnect wins are enough to materially change cluster-level economics
	- The right monitoring variables:
		- HBF prototypes turning into product roadmaps
		- more commercial **compute-on-memory-base-die** announcements
		- growth in **CXL memory expansion / near-memory controllers**
		- evidence that hyperscalers optimize for **latency-per-token** and **performance-per-watt**, not just raw training-class FLOPS
