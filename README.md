# Awesome AI Cyber Deception [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of tools, papers and resources where **artificial intelligence meets cyber deception**.

Cyber deception uses fake assets — honeypots, decoys, honeytokens and false data — to detect, delay and study attackers. AI changes this field in two directions:

- **AI for deception.** Large language models (LLMs) and reinforcement learning (RL) make decoys more realistic, adaptive and cheap to deploy.
- **Deception for AI.** New traps catch AI hacking agents, poison AI scrapers and detect attacks on LLM applications and agents.

This list covers both directions, plus the classic foundations that most AI work builds on.

Maintained by [Cyreslab AI](https://github.com/Cyreslab-AI). Contributions are welcome — read the [contribution guidelines](CONTRIBUTING.md) first.

## Contents

- [LLM-Powered Honeypots](#llm-powered-honeypots)
- [Deception for AI Systems](#deception-for-ai-systems)
  - [Canaries and Prompt-Injection Traps](#canaries-and-prompt-injection-traps)
  - [MCP and AI Infrastructure Honeypots](#mcp-and-ai-infrastructure-honeypots)
  - [Tarpits and Poisoning Against AI Crawlers](#tarpits-and-poisoning-against-ai-crawlers)
- [AI for Honeypot Data Analysis](#ai-for-honeypot-data-analysis)
- [Foundational Deception Tools](#foundational-deception-tools)
  - [Honeypots](#honeypots)
  - [Honeytokens and Decoys](#honeytokens-and-decoys)
  - [Tarpits](#tarpits)
- [Simulation and Gym Environments](#simulation-and-gym-environments)
- [Datasets](#datasets)
- [Frameworks and Standards](#frameworks-and-standards)
- [Papers](#papers)
  - [Surveys](#surveys)
  - [LLM-Based Honeypots](#llm-based-honeypots-papers)
  - [Reinforcement Learning and Game Theory](#reinforcement-learning-and-game-theory)
  - [Deception Against AI Attackers](#deception-against-ai-attackers)
  - [Generative AI for Decoys and Honeywords](#generative-ai-for-decoys-and-honeywords)
  - [Human Studies](#human-studies)
- [Books](#books)
- [Talks](#talks)
- [Blogs and Articles](#blogs-and-articles)
- [Courses and Training](#courses-and-training)
- [Commercial Platforms](#commercial-platforms)
- [Communities and Events](#communities-and-events)
- [Related Lists](#related-lists)

---

## LLM-Powered Honeypots

Honeypots that use an LLM to generate responses, so they can imitate any command, page or service without hand-written rules.

- [Beelzebub](https://github.com/beelzebub-labs/beelzebub) - Low-code honeypot framework that uses an LLM to imitate SSH, HTTP, TCP, Telnet and MCP services.
- [Galah](https://github.com/0x4D31/galah) - Web honeypot that uses an LLM to write a realistic HTTP response to each request.
- [DECEIVE](https://github.com/Cisco-Talos/DECEIVE) - Proof-of-concept SSH honeypot in which an LLM simulates the whole system and summarizes each session. Originally from Splunk.
- [shelLM](https://github.com/stratosphereips/shelLM) - Linux shell honeypot from Stratosphere Lab that generates shell output with an LLM.
- [VelLMes](https://github.com/stratosphereips/VelLMes-AI-Deception-Framework) - LLM deception framework that imitates SSH, MySQL, POP3 and HTTP services.
- [LLM Agent Honeypot](https://github.com/PalisadeResearch/llm-honeypot) - Cowrie-based SSH honeypot from Palisade Research that uses prompt-injection traps to detect AI hacking agents. See the [live dashboard](https://ai-honeypot.palisaderesearch.org/).
- [HoneyGPT](https://github.com/zyw-286/HoneyGPT) - LLM SSH/Telnet honeypot on top of Cowrie that infers attacker intent and adapts its answers.
- [DataTrap](https://github.com/ThalesGroup/dd-honeypot) - Multi-protocol honeypot from Thales that mixes recorded payloads with LLM-generated responses.
- [honey-ai](https://github.com/martidu4/honey-ai) - All-in-one honeypot on local LLMs that imitates SSH, HTTP, FTP, SMTP, MySQL, Redis, RDP and more.
- [HoneyAgents](https://github.com/mrwadams/honeyagents) - Proof of concept that joins honeypots with AI agents to analyze threats and update deny lists.
- [Sparkle](https://github.com/AlloySecureGroup/Sparkle) - LLM honeypot for security research.
- [Lophiid](https://github.com/mrheinen/lophiid) - Hybrid AI web honeypot for large-scale exploitation attempts. *Archived.*

## Deception for AI Systems

### Canaries and Prompt-Injection Traps

- [Vigil](https://github.com/deadbits/vigil-llm) - Scanner for risky LLM inputs with canary-token checks for prompt leaks and goal hijacking.
- [Rebuff](https://github.com/protectai/rebuff) - Prompt-injection detector that puts canary words in prompts to detect leaks. *Archived.*
- [agent-canary](https://github.com/DorianChn/shanchuanzhi-agent-canary) - Decoy MCP tools and canary tokens that alert when an agent is hijacked or leaks data.
- [Tracebit canary honeytokens skill](https://github.com/tracebit-com/tracebit-canary-honeytokens-skill) - Agent skill that deploys canary credentials with Tracebit Community Edition.
- [meridian-portal](https://github.com/chrisochrisochriso-cmyk/meridian-portal) - Honeypot for AI agents: each trap puts a unique canary in the page, so the canary in the agent output proves the injection.
- [MIRAGE](https://github.com/BrightGir/AI-Honeypot) - AI honeypot with decoy LLM personas and fake data to study prompt injection and jailbreaks.
- [hot-potato](https://github.com/brandy-savage/hot-potato) - Prompt-injection honeypot with a naive AI in a Docker sandbox that obeys every injected instruction.
- [honeyprompt](https://github.com/johnzilla/honeyprompt) - Terminal tool that uses honeypot pages and prompt-injection canaries to detect unsafe AI browsing agents.

### MCP and AI Infrastructure Honeypots

Traps for attacks on [Model Context Protocol](https://modelcontextprotocol.io/) servers and exposed AI infrastructure. Beelzebub (above) also has an MCP mode.

- [Wasphole](https://github.com/riza/wasphole) - MCP honeypot with fake tools, canary credentials, session replay and alerts.
- [honeymcp](https://github.com/kosiorkosa47/honeymcp) - Honeypot that imitates an MCP server to collect threat intelligence on attacks against AI agents.
- [mcp-honeypot](https://github.com/cerebral-work/mcp-honeypot) - Research honeypot that watches agent attacks against MCP servers.
- [f3-mcp-honeypot](https://github.com/5h4d0wn1k/f3-mcp-honeypot) - Decoy MCP tool server that fingerprints and traps AI agents.
- [Ollama-Honeypot](https://github.com/SakuraTomoya-Wzy/Ollama-Honeypot) - Honeypot that imitates an exposed Ollama LLM server.

### Tarpits and Poisoning Against AI Crawlers

Tools that trap or feed junk data to AI scrapers that ignore site rules.

- [Nepenthes](https://zadzmo.org/code/nepenthes/) - The first anti-AI tarpit: an endless maze of pages with Markov-chain text that traps LLM crawlers.
- [Iocaine](https://iocaine.madhouse-project.org/) - Reverse proxy that serves an endless maze of junk text to poison AI scrapers.
- [Quixotic](https://marcusb.org/hacks/quixotic.html) - Feeds bots and LLM scrapers obfuscated Markov text in place of the real content.
- [Cloudflare AI Labyrinth](https://blog.cloudflare.com/ai-labyrinth/) - Managed Cloudflare feature that sends suspected AI crawlers into mazes of AI-generated decoy pages. *Not open source.*
- [HellPot](https://github.com/yunginnanet/HellPot) - HTTP tarpit that sends an endless text stream to bots that ignore `robots.txt`.
- [Pyison](https://github.com/JonasLong/Pyison) - Python tarpit for AI crawlers.
- [nepenthes-py](https://github.com/NEPENTHESWEB/nepenthes-py) - Python rewrite of the Nepenthes tarpit.
- [konterfAI](https://codeberg.org/konterfai/konterfai) - Model poisoner that generates nonsense content for LLM scrapers.
- [caddy-defender](https://github.com/JasonLovesDoggo/caddy-defender) - Caddy module that blocks AI crawlers and cloud IP ranges, or sends them garbage.
- [ai-tarpit](https://github.com/fluffy-critter/ai-tarpit) - Honeypot that poisons the data of AI scrapers.
- [ai-scraping-defense](https://github.com/rhamenator/ai-scraping-defense) - Layered anti-scraper system with tarpits, honeypots and optional LLM analysis.
- [ai.robots.txt](https://github.com/ai-robots-txt/ai.robots.txt) - List of AI crawler user agents that many tarpits and blocklists use. *Related resource.*
- [Anubis](https://github.com/TecharoHQ/anubis) - Proof-of-work gate against AI crawlers. It blocks and does not deceive. *Related resource.*

## AI for Honeypot Data Analysis

- [TANNER](https://github.com/mushorg/tanner) - Analysis engine for the SNARE web honeypot that classifies web attacks and chooses the response.
- [Finch](https://github.com/0x4D31/finch) - TLS reverse proxy that fingerprints clients (JA3/JA4) and can route suspect traffic to decoys such as Galah.
- [GreyNoise](https://www.greynoise.io/) - Global honeypot sensor network that classifies internet scanning traffic, with LLM-based analysis. *Commercial, with a free tier.*

Also see HoneyGPT and HoneyAgents in [LLM-Powered Honeypots](#llm-powered-honeypots).

## Foundational Deception Tools

Classic open-source tools. Most AI deception research builds on or compares against these.

### Honeypots

- [T-Pot](https://github.com/telekom-security/tpotce) - All-in-one platform that runs many honeypots with an Elastic dashboard.
- [Cowrie](https://github.com/cowrie/cowrie) - Medium/high-interaction SSH and Telnet honeypot. Many LLM honeypots extend it.
- [OpenCanary](https://github.com/thinkst/opencanary) - Modular honeypot daemon from Thinkst for many services.
- [Dionaea](https://github.com/DinoTools/dionaea) - Low-interaction honeypot that captures malware.
- [Conpot](https://github.com/mushorg/conpot) - Honeypot for industrial control systems (ICS/SCADA).
- [SNARE](https://github.com/mushorg/snare) - Web application honeypot sensor, controlled by TANNER.
- [Glutton](https://github.com/mushorg/glutton) - Generic honeypot that accepts connections on all ports.
- [Heralding](https://github.com/johnnykv/heralding) - Honeypot that captures credentials on many protocols.
- [qeeqbox honeypots](https://github.com/qeeqbox/honeypots) - 30 low-interaction honeypots in one Python package.
- [Honeytrap](https://github.com/honeytrap/honeytrap) - Extensible honeypot framework.
- [DShield sensor](https://github.com/DShield-ISC/dshield) - SANS Internet Storm Center honeypot sensor that feeds [DShield](https://www.dshield.org/).
- [Modern Honey Network](https://github.com/pwnlandia/mhn) - Central server to deploy and manage honeypots.
- [Honeyd](https://github.com/DataSoft/Honeyd) - Creates virtual honeypot hosts on a network. *Classic.*

### Honeytokens and Decoys

- [Canarytokens](https://github.com/thinkst/canarytokens) - Honeytokens (URLs, documents, cloud keys and more) that alert when used. Free hosted service at [canarytokens.org](https://canarytokens.org/).
- [DejaVu](https://github.com/bhdresh/Dejavu) - Deception framework that places decoys across a network.
- [DCEPT](https://github.com/secureworks/dcept) - Deploys Active Directory honeytokens and detects their use.
- [honeyλ](https://github.com/0x4D31/honeyLambda) - Serverless fake HTTP endpoints that act as honeytokens.
- [Artillery](https://github.com/BinaryDefense/artillery) - Blue-team tool with honeypot ports and file monitoring.

### Tarpits

- [Endlessh](https://github.com/skeeto/endlessh) - SSH tarpit that sends an endless banner.
- [endlessh-go](https://github.com/shizunge/endlessh-go) - Endlessh in Go, with Prometheus metrics.

## Simulation and Gym Environments

Training environments where RL agents learn to attack and defend networks, often with decoy actions.

- [CybORG](https://github.com/cage-challenge/CybORG) - Cyber Operations Research Gym, used by the CAGE challenges.
- [CAGE Challenge 2](https://github.com/cage-challenge/cage-challenge-2) - Autonomous defense challenge whose blue agent actions include decoy deployment. Also see [1](https://github.com/cage-challenge/cage-challenge-1), [3](https://github.com/cage-challenge/cage-challenge-3) and [4](https://github.com/cage-challenge/cage-challenge-4).
- [CyberBattleSim](https://github.com/microsoft/CyberBattleSim) - Microsoft network simulation where automated agents attack and defend.
- [Cyberwheel](https://github.com/ORNL/cyberwheel) - Oak Ridge National Laboratory RL environment for defensive and offensive agents, with decoy support.
- [CSLE](https://github.com/Kim-Hammar/csle) - Research platform that finds security policies with RL, game theory and optimal control.
- [PrimAITE](https://github.com/Autonomous-Resilient-Cyber-Defence/PrimAITE) - UK training environment for autonomous cyber defense agents.
- [NASim](https://github.com/Jjschwartz/NetworkAttackSimulator) - Network Attack Simulator for training AI penetration-testing agents.
- [YAWNING-TITAN](https://github.com/dstl/YAWNING-TITAN) - Graph-based cyber simulation from Dstl for training defensive agents. *Archived.*

## Datasets

- [LLM-Honeypot-Logs](https://huggingface.co/datasets/palisaderesearch/LLM-Honeypot-Logs) - Session logs from the Palisade LLM Agent Honeypot (access on request).
- [honeypot-data](https://github.com/0x4D31/honeypot-data) - Public honeypot datasets with HTTP and TLS (JA3/JA4) fingerprints.
- [HoneyDB](https://honeydb.io/) - Community honeypot data from many sensors, with an API.
- [ICS-Honeypot-Dataset](https://github.com/fras3c/ICS-Honeypot-Dataset) - Three months of IT and ICS interactions from an internet-facing HoneyICS deployment.
- [BETH Dataset](https://www.kaggle.com/datasets/katehighnam/beth-dataset) - Labeled kernel-process and DNS logs from cloud honeypots, for anomaly detection.
- [Global SSH and Telnet Honeypot Logs](https://www.kaggle.com/datasets/nlaha11/global-ssh-and-telnet-honeypot-logs-cowrie) - Cowrie logs from honeypots in many regions.
- [AWS Honeypot Attack Data](https://www.kaggle.com/datasets/casimian2000/aws-honeypot-attack-data) - Attack records from honeypots on AWS.
- [cowrie_dataset](https://huggingface.co/datasets/yenrong/cowrie_dataset) - Small Cowrie SSH honeypot dataset on Hugging Face.
- [CAIDA Network Telescope](https://www.caida.org/catalog/datasets/telescope-near-real-time_dataset/) - Near-real-time traffic to a large unused IP block, for studies of scanning and backscatter.
- [Sicherheitstacho](https://sicherheitstacho.eu/) - Live dashboard of attacks seen by the Deutsche Telekom T-Pot honeypot network.
- [Stratosphere datasets](https://www.stratosphereips.org/datasets-overview) - Labeled malware and normal network captures for ML research.
- [SecRepo](https://www.secrepo.com/) - Index of security datasets, including honeypot and network logs.

## Frameworks and Standards

- [MITRE Engage](https://engage.mitre.org/) - Framework to plan denial, deception and adversary engagement. See the [matrix](https://engage.mitre.org/matrix/) and [data](https://github.com/mitre/engage).
- [MITRE D3FEND — Deceive](https://d3fend.mitre.org/tactic/d3f:Deceive/) - D3FEND techniques for decoy files, accounts, network resources and more.
- [MITRE ATLAS](https://atlas.mitre.org/) - Knowledge base of adversary tactics against AI and ML systems.
- [NIST SP 800-160 Vol. 2 Rev. 1](https://csrc.nist.gov/pubs/sp/800/160/v2/r1/final) - Cyber-resiliency guide that lists deception as a resiliency technique.
- [NIST SP 800-172](https://csrc.nist.gov/pubs/sp/800/172/final) - Enhanced controls for CUI that include adversary deception requirements.
- [NIST SP 800-53 Rev. 5](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) - Control catalog with SC-26 (Decoys) and SC-30 (Concealment and Misdirection).
- [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/) - Main risk list for LLM applications. Useful context when you build or harden LLM decoys.

## Papers

### Surveys

- [SoK: Honeypots & LLMs, More Than the Sum of Their Parts?](https://arxiv.org/abs/2510.25939) - Bridges et al., 2025. Systematizes research on LLM-based honeypots.
- [Cyber Deception: State of the Art, Trends and Open Challenges](https://arxiv.org/abs/2409.07194) - Beltrán López et al., 2024.
- [Game-Theoretic and Machine Learning-based Approaches for Defensive Deception: A Survey](https://arxiv.org/abs/2101.10121) - Zhu et al., IEEE COMST, 2021.
- [Three Decades of Deception Techniques in Active Cyber Defense](https://arxiv.org/abs/2104.03594) - Zhang et al., Computers & Security, 2021.
- [A Game-Theoretic Taxonomy and Survey of Defensive Deception](https://arxiv.org/abs/1712.05441) - Pawlick et al., ACM Computing Surveys, 2017.
- [Deep Reinforcement Learning for Autonomous Cyber Defence: A Survey](https://arxiv.org/abs/2310.07745) - Palmer et al., 2023.
- [Cyber Deception for Computer and Network Security: Survey and Challenges](https://arxiv.org/abs/2007.14497) - Lu et al., 2020.
- [A Survey of Network Requirements for Enabling Effective Cyber Deception](https://arxiv.org/abs/2309.00184) - Sayed et al., 2023.
- [Demystifying Deception Technology: A Survey](https://arxiv.org/abs/1804.06196) - Fraunholz et al., 2018.

<a id="llm-based-honeypots-papers"></a>
### LLM-Based Honeypots

- [LLM in the Shell: Generative Honeypots](https://arxiv.org/abs/2309.00155) - Sladić et al., 2023. shelLM: an LLM simulates a Linux shell, tested with human users.
- [HoneyGPT: Breaking the Trilemma in Terminal Honeypots with Large Language Model](https://arxiv.org/abs/2406.01882) - Wang et al., 2024.
- [LLM Honeypot: Leveraging LLMs as Advanced Interactive Honeypot Systems](https://arxiv.org/abs/2409.08234) - Otal & Canbaz, 2024. Fine-tunes an open LLM on attacker commands.
- [VelLMes: A High-Interaction AI-Based Deception Framework](https://arxiv.org/abs/2510.06975) - Sladić et al., 2025. Multi-service LLM honeypots tested against human attackers.
- [AdvancedShelLM: A Stateful Multi-Agent LLM Honeypot for SSH Deception](https://arxiv.org/abs/2606.27990) - Sladić et al., 2026.
- [Improving LLM-Based SSH Honeypots Through Prompting and Fine-Tuning](https://arxiv.org/abs/2608.18686) - Sladić et al., 2026. Local open-weight models in place of cloud LLMs.
- [Honeyval: An Evaluation Framework for LLM-Powered HTTP Honeypots](https://arxiv.org/abs/2605.29963) - Vero et al., 2026.
- [LLMPot: LLM-Based Honeypot for Industrial Protocol and Physical Process Emulation](https://arxiv.org/abs/2405.05999) - Vasilatos et al., 2024.
- [A Generative Model Based Honeypot for Industrial OPC UA Communication](https://arxiv.org/abs/2410.21574) - Sassnick et al., 2024.
- [LLMHoney: A Real-Time SSH Honeypot with LLM-Driven Dynamic Response Generation](https://arxiv.org/abs/2509.01463) - Malhotra, 2025.
- [SBASH: Designing and Evaluating RAG vs. Prompt-Tuned LLM Honeypots](https://arxiv.org/abs/2510.21459) - Adebimpe et al., 2025.
- [Design and Development of an Intelligent LLM-Based LDAP Honeypot](https://arxiv.org/abs/2509.16682) - Jiménez-Román et al., 2025.
- [Inducing Personality in LLM-Based Honeypot Agents (SANDMAN)](https://arxiv.org/abs/2503.19752) - Newsham et al., 2025. LLM agents act as fake human users on decoy hosts.
- [SPADE: Adaptive Cyber Deception with Generative AI and Structured Prompt Engineering](https://arxiv.org/abs/2501.00940) - Ahmed et al., IEEE CCWC, 2025.
- [Koney: A Cyber Deception Orchestration Framework for Kubernetes](https://arxiv.org/abs/2504.02431) - Kahlhofer et al., 2025.
- [Application Layer Cyber Deception without Developer Interaction](https://arxiv.org/abs/2405.12852) - Kahlhofer & Rass, 2024.

### Reinforcement Learning and Game Theory

- [Adaptive Honeypot Engagement through Reinforcement Learning of Semi-Markov Decision Processes](https://arxiv.org/abs/1906.12182) - Huang & Zhu, GameSec, 2019.
- [HoneyIoT: Adaptive High-Interaction Honeypot for IoT Devices Through Reinforcement Learning](https://arxiv.org/abs/2305.06430) - Guan et al., WiSec, 2023.
- [CybORG: A Gym for the Development of Autonomous Cyber Agents](https://arxiv.org/abs/2108.09118) - Standen et al., 2021.
- [Incorporating Deception into CyberBattleSim for Autonomous Defense](https://arxiv.org/abs/2108.13980) - Walter et al., 2021.
- [Informing Autonomous Deception Systems with Cyber Expert Performance Data](https://arxiv.org/abs/2109.00066) - Major et al., 2021.
- [On Autonomous Agents in a Cyber Defence Environment](https://arxiv.org/abs/2309.07388) - Kiely et al., 2023.
- [Inroads into Autonomous Network Defence using Explained Reinforcement Learning](https://arxiv.org/abs/2306.09318) - Foley et al., 2023.
- [Honeypot Allocation for Cyber Deception in Dynamic Tactical Networks](https://arxiv.org/abs/2308.11817) - Sayed et al., GameSec, 2023.
- [Strategic Learning for Active, Adaptive, and Autonomous Cyber Defense](https://arxiv.org/abs/1907.01396) - Huang & Zhu, 2019.
- [Machine Theory of Mind for Autonomous Cyber-Defence](https://arxiv.org/abs/2412.04367) - Swaby et al., 2024.
- [Network and Device Level Cyber Deception for Contested Environments Using RL and LLMs](https://arxiv.org/abs/2603.17272) - Sahu et al., 2026.
- [Cyber Deception for Mission Surveillance via Hypergame-Theoretic Deep Reinforcement Learning](https://arxiv.org/abs/2603.20981) - Wan et al., 2026.

### Deception Against AI Attackers

- [Hacking Back the AI-Hacker: Prompt Injection as a Defense Against LLM-driven Cyberattacks](https://arxiv.org/abs/2410.20911) - Pasquini et al., 2024. Mantis: decoys with prompt injections that stop LLM agents. [Code](https://github.com/pasquini-dario/project_mantis).
- [LLM Agent Honeypot: Monitoring AI Hacking Agents in the Wild](https://arxiv.org/abs/2410.13919) - Reworr & Volkov, 2024.
- [LLM-Based Penetration Testing in the Presence of Honeypots](https://arxiv.org/abs/2609.08093) - Xie et al., 2026.
- [Honeyquest for LLMs: Rethinking Cyber Deception for AI Attackers](https://arxiv.org/abs/2606.21037) - Prinos et al., 2026.
- [When Agents Talk: Honeytokens under Shared Memory](https://arxiv.org/abs/2608.11436) - Gans, 2026.
- [AgentShield: Deception-Based Compromise Detection for Tool-Using LLM Agents](https://arxiv.org/abs/2605.11026) - Rassul, 2026.
- [HoneyTrap: Deceiving LLM Attackers to Honeypot Traps with Resilient Multi-Agent Defense](https://arxiv.org/abs/2601.04034) - Li et al., 2026.
- [Let Them Steal: Trapping LLM Extraction Attacks with Knowledge Honeypot](https://arxiv.org/abs/2606.15810) - Dai et al., 2026.
- [MemPot: Defending Against Memory Extraction Attack with Optimized Honeypots](https://arxiv.org/abs/2602.07517) - Wang et al., 2026.
- [Forewarned is Forearmed: A Survey on LLM-Based Agents in Autonomous Cyberattacks](https://arxiv.org/abs/2505.12786) - Xu et al., 2025. Background on the attackers these defenses target.

### Generative AI for Decoys and Honeywords

- [Act as a Honeytoken Generator! An Investigation into Honeytoken Generation with LLMs](https://arxiv.org/abs/2404.16118) - Reti et al., 2024.
- [A Fake Online Repository Generation Engine for Cyber Deception (FORGE)](https://ieeexplore.ieee.org/document/8638562/) - Chakraborty et al., IEEE TDSC, 2019.
- [Using Word Embeddings to Deter IP Theft through Automated Generation of Fake Documents (WE-FORGE)](https://dl.acm.org/doi/10.1145/3418289) - Abdibayev et al., ACM TMIS, 2021.
- [Controllable Fake Document Infilling for Cyber Deception](https://arxiv.org/abs/2210.09917) - Hu et al., Findings of EMNLP, 2022.
- [TSM: Measuring the Enticement of Honeyfiles with Natural Language Processing](https://arxiv.org/abs/2203.07580) - Timmer et al., 2022.
- [Honeyfile Camouflage: Hiding Fake Files in Plain Sight](https://arxiv.org/abs/2405.04758) - Timmer et al., 2024.
- [Contextual Chart Generation for Cyber Deception](https://arxiv.org/abs/2404.04854) - Nguyen et al., 2024.
- [IoTFlowGenerator: Crafting Synthetic IoT Device Traffic Flows for Cyber Deception](https://arxiv.org/abs/2305.00925) - Bao et al., FLAIRS, 2023.
- [Generation of Automatic and Realistic Artificial Profiles](https://arxiv.org/abs/1807.00125) - Paradise et al., 2018.
- [Attack Graph Obfuscation](https://arxiv.org/abs/1903.02601) - Polad et al., 2019.
- [Honeywords: Making Password-Cracking Detectable](https://dl.acm.org/doi/10.1145/2508859.2516671) - Juels & Rivest, ACM CCS, 2013. The original honeywords paper.
- [HoneyGen: Generating Honeywords Using Representation Learning](https://dl.acm.org/doi/10.1145/3433210.3453092) - Dionysiou et al., AsiaCCS, 2021.
- [How to Attack and Generate Honeywords](https://ieeexplore.ieee.org/document/9833598/) - Wang et al., IEEE S&P, 2022.
- [Targeted Honeyword Generation with Language Models](https://arxiv.org/abs/2208.06946) - Yu & Martin, 2022.
- [Honey, I Chunked the Passwords: Generating Semantic Honeywords Using Pre-trained Language Models](https://link.springer.com/chapter/10.1007/978-3-031-35504-2_5) - Yu & Martin, DIMVA, 2023.
- [When AI Defeats Password Deception! Distinguishing Passwords and Honeywords (PassFilter)](https://arxiv.org/abs/2407.16964) - Dani et al., 2024.
- [Differential Privacy and NLP to Generate Decoy Messages in Honey Encryption](https://arxiv.org/abs/2010.15985) - Panchal, 2020.

### Human Studies

- [Examining the Efficacy of Decoy-based and Psychological Cyber Deception](https://www.usenix.org/conference/usenixsecurity21/presentation/ferguson-walter) - Ferguson-Walter et al., USENIX Security, 2021.
- [The Tularosa Study: Quantifying the Effectiveness of Cyber Deception](https://aisel.aisnet.org/hicss-52/st/cybersecurity_and_sw_assurance/2/) - Ferguson-Walter et al., HICSS, 2019. Controlled experiment with more than 130 professional red teamers.
- [Honeyquest: Rapidly Measuring the Enticingness of Cyber Deception Techniques](https://arxiv.org/abs/2408.10796) - Kahlhofer et al., RAID, 2024.
- [Game of Travesty: Decoy-Based Psychological Cyber Deception for Proactive Human Agents](https://arxiv.org/abs/2309.13403) - Hu et al., 2023.

## Books

- [Foundations of Cyber Deception](https://link.springer.com/book/10.1007/978-3-031-93867-2) - Springer, 2026. Includes chapters on game theory with foundation models.
- [Cyber Deception: Techniques, Strategies, and Human Aspects](https://link.springer.com/book/10.1007/978-3-031-16613-6) - Springer, 2023.
- [Autonomous Cyber Deception](https://link.springer.com/book/10.1007/978-3-030-02110-8) - Al-Shaer et al., Springer, 2019. Reasoning, adaptive planning and evaluation of autonomous decoys.
- [Cyber Deception: Building the Scientific Foundation](https://link.springer.com/book/10.1007/978-3-319-32699-3) - Jajodia et al., Springer, 2016.
- [Cyber Denial, Deception and Counter Deception](https://link.springer.com/book/10.1007/978-3-319-25133-2) - Heckman et al., Springer, 2015. Introduces the Cyber-Deception Chain.

## Talks

- [Decoding Galah, an LLM-Powered Web Honeypot](https://www.youtube.com/watch?v=XGsm4Qcc_Ag) - Adel Karimi, DEF CON 32. Also given at [hack.lu 2024](https://pretalx.com/hack-lu-2024/talk/LGTEXR/).
- [Teaching Your Reverse Proxy to Think](https://defcon.org/html/defcon-33/dc-33-creator-talks.html) - Adel Karimi, DEF CON 33. Introduces Finch with AI-driven deception responses.
- [Every AI Talk from BSidesLV, Black Hat and DEF CON 2024](https://tldrsec.com/p/tldr-every-ai-talk-bsideslv-blackhat-defcon-2024) - tl;dr sec summary of the AI security talks.

## Blogs and Articles

- [Introducing DECEIVE](https://www.splunk.com/en_us/blog/security/deceive-ai-honeypot-concept.html) - Splunk. A honeypot where an LLM simulates a Linux shell and judges each session.
- [AI Labyrinth](https://blog.cloudflare.com/ai-labyrinth/) - Cloudflare. AI-generated decoy pages that waste the time of rule-breaking scrapers.
- [Threat Actors Actively Targeting LLMs](https://www.greynoise.io/blog/threat-actors-actively-targeting-llms) - GreyNoise. Honeypot data on campaigns that scan for exposed LLM endpoints.
- [GreyNoise Labs Grimoire](https://www.labs.greynoise.io/grimoire/) - Research write-ups based on GreyNoise sensor data.
- [Catching AI Red Teamers in the Wild Using Reverse Prompt Injection](https://itnext.io/catching-ai-red-teamers-in-the-wild-using-reverse-prompt-injection-as-a-honeypot-detection-36e2f3327611) - Beelzebub team. Uses prompt injection in a honeypot to detect AI agents.

## Courses and Training

- [Active Defense and Cyber Deception](https://www.antisyphontraining.com/course/active-defense-and-cyber-deception-with-john-strand/) - John Strand, Antisyphon Training. Hands-on course on honeypots, honeytokens, attribution and the legal limits of active defense.
- [ADHD: Active Defense Harbinger Distribution](https://adhdproject.github.io/) - Free Linux distribution of active-defense and deception tools.

## Commercial Platforms

Listed in alphabetical order. No ranking or endorsement.

- [Acalvio ShadowPlex](https://www.acalvio.com/shadowplex/) - Autonomous deception platform that uses AI to place decoys and honeytokens.
- [Commvault ThreatWise](https://www.commvault.com/platform/threatwise) - Deception for early warning of attacks on data (formerly TrapX).
- [CounterCraft](https://www.countercraftsec.com/blog/launch-cyber-deception-platform/) - Deception platform that uses decoy environments for threat intelligence.
- [Fidelis Deception](https://fidelissecurity.com/solutions/deception/) - Automated decoys and breadcrumbs in the Fidelis Elevate XDR platform.
- [Lupovis](https://www.lupovis.io/) - Deception platform with AI-generated decoys and external threat intelligence.
- [Proofpoint Identity Threat Defense](https://www.proofpoint.com/us/products/identity-threat-defense) - Identity-focused deception (formerly Illusive).
- [Rapid7 InsightIDR Deception](https://www.rapid7.com/products/insightidr/features/deception-technology/) - Honeypots, honey users, honey credentials and honey files in Rapid7 SIEM.
- [SentinelOne Singularity Hologram](https://www.sentinelone.com/platform/singularity-hologram/) - Network decoys (formerly Attivo Networks).
- [Thinkst Canary](https://canary.tools/) - Hardware, virtual and cloud honeypots with low-noise alerts.
- [Tracebit](https://tracebit.com/) - Cloud and identity deception with canary resources and credentials at scale.
- [WebDecoy API Honeypots](https://webdecoy.com/product/endpoints/) - Hosted API decoys for observing automated probes against public-facing applications.
- [Zscaler Deception](https://www.zscaler.com/products-and-solutions/deception-technology) - Decoys and lures in the Zscaler Zero Trust platform (formerly Smokescreen).

## Communities and Events

- [The Honeynet Project](https://www.honeynet.org/) - Long-running non-profit research group for honeypots and deception, with yearly workshops and [Google Summer of Code](https://www.honeynet.org/gsoc/) projects.
- [AIDC Workshop](https://aidcworkshop.github.io/) - Workshop on autonomous intelligent defense, including active deception and honeypots.
- [ACM AACD Workshop](https://aacd24.github.io/) - ACM Workshop on Adaptive and Autonomous Cyber Defense.

## Related Lists

- [awesome-honeypots](https://github.com/paralax/awesome-honeypots) - The largest list of honeypot software and resources.
- [awesome-deception (Tracebit)](https://github.com/tracebit-com/awesome-deception) - Articles, papers, conferences and tools on cyber deception.
- [Awesome-Deception](https://github.com/tolgadevsec/Awesome-Deception) - Deception-based security, honeypots and honeytokens.
- [Awesome-AI-Deception](https://github.com/0xNslabs/Awesome-AI-Deception) - Small list on AI and cyber deception.
- [awesome-genai-cyberhub](https://github.com/Ashfaaq98/awesome-genai-cyberhub) - LLMs in cybersecurity, with a section on LLM honeypots.
- [awesome-llm-security](https://github.com/corca-ai/awesome-llm-security) - Tools, papers and projects on LLM security.
- [awesome-ai-security](https://github.com/ottosulin/awesome-ai-security) - Resources on AI security.
- [Awesome-AI-Security](https://github.com/TalEliyahu/Awesome-AI-Security) - Resources, research and tools to secure AI systems.
- [offensive-ai-compilation](https://github.com/jiep/offensive-ai-compilation) - Resources on offensive AI, to understand the attacker side.

---

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, Cyreslab AI has waived all copyright and related rights to this work.
