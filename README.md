[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

# Awesome Generative Recommendation

A curated, practical, and research-oriented repository for **generative recommendation**, **generative retrieval**, **generative search**, and closely related industrial deployment work.

This page is an upgraded version of the original resource list. It merges:

- the existing paper collection,
- audited additions from recent 2026 papers,
- public datasets and challenge releases,
- industrial deployment reports,
- and a clearer structure for long-term maintenance.

## Scope

This repository focuses on the **generative search/recommendation route**:

- semantic IDs / tokenization,
- unified generative search and recommendation,
- post-training and preference alignment,
- scaling, serving, inference, and reranking,
- reliability, cold-start, bias, and generalization.

It does **not** treat the following as the same thing:

- **Generative abilities**: rewrite, summary, question generation, etc.
- **Generative search/recommendation route**: unified modeling with semantic IDs, constrained decoding, or end-to-end generation.
- **Agentic Search**: search-surface-native orchestration with query typing, tools, clarification, and result restructuring.
- **Agentic recommender systems**: agentizing internal recsys modules and control loops.

## Curation Policy

- Descriptions are kept at source-supported granularity, typically from the abstract, paper page, or an official dataset/system page.
- When only title- and abstract-level evidence is available, the note stays high-level and avoids stronger claims not made by the source.
- When source details are not disclosed, this page does not infer them.
- For arXiv items, `Published` uses the first public submission date. For some non-arXiv items, only year or year-month is currently verified, and we keep that granularity explicitly.
- Recent additions in this page were expanded by following both institutional lines and citation neighborhoods around core papers such as `OneRec`, `OneSearch`, `OneSearch-V2`, `OneRanker`, and `RankGR`.

## Contents

- [Tutorials](#tutorials)
- [Datasets and Challenges](#datasets-and-challenges)
- [Surveys](#surveys)
- [Industrial Reports and Deployment](#industrial-reports-and-deployment)
- [Tokenization and Semantic IDs](#tokenization-and-semantic-ids)
- [Unified Generative Search Recommendation and Retrieval](#unified-generative-search-recommendation-and-retrieval)
- [Reasoning Post-training and Alignment](#reasoning-post-training-and-alignment)
- [Scaling Serving Inference and Reranking](#scaling-serving-inference-and-reranking)
- [Reliability Bias Cold-start and Generalization](#reliability-bias-cold-start-and-generalization)
- [Diffusion Models](#diffusion-models)
- [Optimization Adapters and Other Directions](#optimization-adapters-and-other-directions)
- [2026 Highlights](#2026-highlights)
- [Contributing](#contributing)

## Tutorials

- **Towards Large Generative Recommendation: A Tokenization Perspective** [[CIKM 2025 Tutorial]](https://large-genrec.github.io/cikm2025.html) — Source: CIKM 2025 Tutorial | Published: 2025

## Datasets and Challenges

- **OpenOneRec-RecIF** [[Hugging Face]](https://huggingface.co/datasets/OpenOneRec/OpenOneRec-RecIF) — Source: Hugging Face | Published: 2026-01-07
  - Public dataset page with `createdAt=2026-01-07`, `lastModified=2026-01-28`, Apache-2.0 license, and benchmark/task files including `product_pid2sid`, `video_ad_pid2sid`, and `pid2caption`.
- **Tencent Advertising Algorithm Challenge 2025: All-Modality Generative Recommendation** [[Paper]](https://arxiv.org/abs/2604.04976) — Source: arXiv | Published: 2026-04-04
  - Introduces `TencentGR-1M` and `TencentGR-10M`, a rare public all-modality benchmark line tailored for generative recommendation in industrial advertising.

## Surveys

- **A Survey of Generative Search and Recommendation in the Era of Large Language Models** [[Paper]](https://arxiv.org/abs/2404.16924) — Source: arXiv | Published: 2024-04-25
  - A broad survey that explicitly bridges generative search and recommendation in the LLM era.
- **A Survey on Generative Recommendation: Data, Model, and Tasks** [[Paper]](https://arxiv.org/abs/2510.27157) — Source: arXiv | Published: 2025-10-31
  - Organizes the field along data, model, and task axes, making it a broad entry survey for the GR literature.
- **A Survey of Generative Recommendation from a Tri-Decoupled Perspective: Tokenization, Architecture, and Optimization** [[Paper]](https://www.preprints.org/manuscript/202512.0203/v1/download) — Source: Preprints.org | Published: 2025-12
  - Frames the literature around three core design axes: tokenization, architecture, and optimization.
- **Generative Recommendation: A Survey of Models, Systems, and Industrial Advances** [[Paper]](https://www.authorea.com/doi/pdf/10.36227/techrxiv.176523089.94266134/v2) — Source: TechRxiv | Published: 2025-12-20
  - Emphasizes model families, system design, and industrial deployment trends rather than only algorithm taxonomies.
- **Generative recommender systems: A comprehensive survey on model, framework, and application** [[Paper]](https://doi.org/10.1016/j.inffus.2025.103919) — Source: Information Fusion | Published: 2026-03
  - Provides a broad survey spanning data sources, feature representation, model architecture, information fusion, and evaluation.

## Industrial Reports and Deployment

- **OneRec: Unifying Retrieve and Rank with Generative Recommender and Iterative Preference Alignment** [[Paper]](https://arxiv.org/abs/2502.18965) — Source: arXiv | Published: 2025-02-26
  - Recasts retrieve-and-rank recommendation as one unified generative model with iterative preference alignment.
- **OneRec Technical Report** [[Paper]](https://arxiv.org/abs/2506.13695) — Source: arXiv | Published: 2025-06-16
  - Production-scale generative recommendation at Kuaishou.
  - The paper reports large-scale deployment, 25% total QPS handling, and strong online gains in a local-life scenario.
- **Large Language Model as Universal Retriever in Industrial-Scale Recommender System** [[Paper]](https://arxiv.org/abs/2502.03041) — Source: arXiv | Published: 2025-02-05
  - Explores whether one LLM-style generative retriever can cover multiple industrial retrieval objectives.
- **MTGenRec: An Efficient Distributed Training System for Generative Recommendation Models in Meituan** [[Paper]](https://arxiv.org/abs/2505.12663) — Source: arXiv | Published: 2025-05-19
  - A systems paper on distributed training support for industrial GR models in Meituan.
- **MTGR: Industrial-Scale Generative Recommendation Framework in Meituan** [[Paper]](https://arxiv.org/abs/2505.18654) — Source: arXiv | Published: 2025-05-24
  - An industrial Meituan framework that keeps generative scalability while preserving useful traditional recommendation signals.
- **OneRec-V2 Technical Report** [[Paper]](https://arxiv.org/abs/2508.20900) — Source: arXiv | Published: 2025-08-28
  - An updated OneRec report focused on scaling the original end-to-end framework and revisiting model and serving bottlenecks.
- **OneRec-Think: In-Text Reasoning for Generative Recommendation** [[Paper]](https://arxiv.org/abs/2510.11639) — Source: arXiv | Published: 2025-10-13
  - Adds explicit in-text reasoning to generative recommendation instead of treating generation as a purely implicit predictor.
- **OpenOneRec Technical Report** [[Paper]](https://arxiv.org/abs/2512.24762) — Source: arXiv | Published: 2025-12-31
  - Introduces an open data and benchmark stack, including RecIF-style evaluation, to narrow the gap between recommendation and broader intelligence benchmarks.
- **MiniOneRec: An Open-Source Framework for Scaling Generative Recommendation** [[Paper]](https://arxiv.org/abs/2510.24431) — Source: arXiv | Published: 2025-10-28
  - Provides an open-source framework for testing whether GR-style scaling laws can be studied on public benchmarks with lightweight post-training.
- **RelayGR: Scaling Long-Sequence Generative Recommendation via Cross-Stage Relay-Race Inference** [[Paper]](https://arxiv.org/abs/2601.01712) — Source: arXiv | Published: 2026-01-05
  - A systems paper on long-sequence GR serving under strict latency and P99 constraints.
- **Generative Recommendation for Large-Scale Advertising** [[Paper]](https://arxiv.org/abs/2602.22732) — Source: arXiv | Published: 2026-02-26
  - Production-oriented advertising GR at Kuaishou with explicit deployment, latency, QPS, and online revenue gains.
- **OneMall: One Architecture, More Scenarios -- End-to-End Generative Recommender Family at Kuaishou E-Commerce** [[Paper]](https://arxiv.org/abs/2601.21770) — Source: arXiv | Published: 2026-01-29
  - A Kuaishou e-commerce family that unifies multiple shopping surfaces such as product cards, short video, and live streaming under one generative framework.
- **OneRanker: Unified Generation and Ranking with One Model in Industrial Advertising Recommendation** [[Paper]](https://arxiv.org/abs/2603.02999) — Source: arXiv | Published: 2026-03-03
  - A Tencent advertising system paper that deeply couples generation and ranking inside one model and reports online GMV gains.
- **MBGR: Multi-Business Prediction for Generative Recommendation at Meituan** [[Paper]](https://arxiv.org/abs/2604.02684) — Source: arXiv | Published: 2026-04-03
  - Multi-business production GR at Meituan with online A/B validation on production traffic.
- **Next-Scale Generative Reranking: A Tree-based Generative Rerank Method at Meituan** [[Paper]](https://arxiv.org/abs/2604.05314) — Source: arXiv | Published: 2026-04-07
  - A notable 2026 extension of the route into generative reranking.
- **Deploying Semantic ID-based Generative Retrieval for Large-Scale Podcast Discovery at Spotify** [[Paper]](https://arxiv.org/abs/2603.17540) — Source: arXiv | Published: 2026-03-18
  - Production-scale generative retrieval/discovery with online user impact.
- **Semantic IDs for Recommender Systems at Snapchat: Use Cases, Technical Challenges, and Design Choices** [[Paper]](https://arxiv.org/abs/2604.03949) — Source: arXiv | Published: 2026-04-05
  - A rare industrial design retrospective on SID deployment in multiple production models.
- **GPR: Towards a Generative Pre-trained One-Model Paradigm for Large-Scale Advertising Recommendation** [[Paper]](https://arxiv.org/abs/2511.10138) — Source: arXiv | Published: 2025-11-13
  - Recasts large-scale advertising recommendation as a generative pre-trained one-model paradigm rather than a traditional multi-stage stack.
- **OnePiece: The Great Route to Generative Recommendation -- A Case Study from Tencent Algorithm Competition** [[Paper]](https://arxiv.org/abs/2512.07424) — Source: arXiv | Published: 2025-12-08
  - A Tencent competition-oriented case study that summarizes how the generative route can be organized as a practical industrial recipe.
- **EGA-V2: An End-to-end Generative Framework for Industrial Advertising** [[Paper]](https://arxiv.org/abs/2505.17549) — Source: arXiv | Published: 2025-05-23
  - Presents an end-to-end industrial advertising framework that replaces fragmented cascades with a unified generative formulation.
- **PLUM: Adapting Pre-trained Language Models for Industrial-scale Generative Recommendations** [[Paper]](https://arxiv.org/abs/2510.07784) — Source: arXiv | Published: 2025-10-09
  - Adapts pre-trained language models to industrial GR through semantic tokenization, continued pretraining, and task adaptation.
- **OxygenREC: An Instruction-Following Generative Framework for E-commerce Recommendation** [[Paper]](https://arxiv.org/abs/2512.22386) — Source: arXiv | Published: 2025-12-26
  - Pushes e-commerce GR toward instruction-following and reasoning-driven intent understanding across multiple recommendation scenarios.

## Tokenization and Semantic IDs

- **Learnable Item Tokenization for Generative Recommendation** [[Paper]](https://arxiv.org/abs/2405.07314) — Source: arXiv | Published: 2024-05-12
- **Generative Recommender with End-to-End Learnable Item Tokenization** [[SIGIR 2025]](https://arxiv.org/abs/2409.05546) [[Code]](https://github.com/RUCAIBox/ETEGRec) — Source: arXiv | Published: 2024-09-09
  - A representative end-to-end tokenization direction.
- **ActionPiece: Contextually Tokenizing Action Sequences for Generative Recommendation** [[Paper]](https://arxiv.org/abs/2502.13581) — Source: arXiv | Published: 2025-02-19
- **A Simple Contrastive Framework Of Item Tokenization For Generative Recommendation** [[Paper]](https://arxiv.org/abs/2506.16683) — Source: arXiv | Published: 2025-06-20
  - Revisits item tokenization with a simpler contrastive formulation for generative recommendation.
- **FusID: Modality-Fused Semantic IDs for Generative Music Recommendation** [[Paper]](https://arxiv.org/abs/2601.08764) — Source: arXiv | Published: 2026-01-13
  - A strong multimodal SID example with detailed public methodology.
- **Generating Long Semantic IDs in Parallel for Recommendation** [[Paper]](https://arxiv.org/abs/2506.05781) — Source: arXiv | Published: 2025-06-06
  - Generates long semantic IDs in parallel to reduce autoregressive cost while preserving richer identifier capacity.
- **From IDs to Semantics: A Generative Framework for Cross-Domain Recommendation with Adaptive Semantic Tokenization** [[Paper]](https://arxiv.org/abs/2511.08006) — Source: arXiv | Published: 2025-11-11
  - Uses adaptive semantic tokenization to move beyond raw item IDs in cross-domain generative recommendation.
- **Pctx: Tokenizing Personalized Context for Generative Recommendation** [[Paper]](https://arxiv.org/abs/2510.21276) — Source: arXiv | Published: 2025-10-24
  - Personalizes tokenization by encoding user-specific context instead of relying only on static item semantics.
- **MMQ: Multimodal Mixture-of-Quantization Tokenization for Semantic ID Generation and User Behavioral Adaptation** [[Paper]](https://arxiv.org/abs/2508.15281) — Source: arXiv | Published: 2025-08-21
  - Uses multimodal mixture-of-quantization tokenization to improve SID generation and behavioral adaptation.
- **Generative Recommendation with Semantic IDs: A Practitioner’s Handbook** [[Paper]](https://arxiv.org/abs/2507.22224) — Source: arXiv | Published: 2025-07-29
  - A useful handbook-style summary of the SID route.
- **Bi-Level Optimization for Generative Recommendation: Bridging Tokenization and Generation** [[Paper]](https://arxiv.org/abs/2510.21242) — Source: arXiv | Published: 2025-10-24
  - Explicitly connects tokenizer optimization and generation quality through a bilevel view.
- **FORGE: Forming Semantic Identifiers for Generative Retrieval in Industrial Datasets** [[Paper]](https://arxiv.org/abs/2509.20904) — Source: arXiv | Published: 2025-09-25
  - Studies SID formation in industrial datasets and highlights the need for larger public multimodal resources.
- **HiD-VAE: Interpretable Generative Recommendation via Hierarchical and Disentangled Semantic IDs** [[Paper]](https://arxiv.org/abs/2508.04618) — Source: arXiv | Published: 2025-08-06
  - Pushes SID design toward hierarchical and disentangled representations for more interpretable GR.
- **Semantic IDs for Joint Generative Search and Recommendation** [[Paper]](https://arxiv.org/abs/2508.10478) — Source: arXiv | Published: 2025-08-14
  - Explicitly studies how one semantic-ID space can support both search and recommendation.
- **Learning Vector-Quantized Item Representation for Transferable Sequential Recommenders** [[Paper]](https://arxiv.org/abs/2210.12316) — Source: arXiv | Published: 2022-10-22
  - An early vector-quantization line that underpins later semantic-ID tokenization work.
- **Differentiable Semantic ID for Generative Recommendation** [[Paper]](https://arxiv.org/abs/2601.19711) — Source: arXiv | Published: 2026-01-27
  - Makes SID learning differentiable to reduce objective mismatch.
- **PIT: A Dynamic Personalized Item Tokenizer for End-to-End Generative Recommendation** [[Paper]](https://arxiv.org/abs/2602.08530) — Source: arXiv | Published: 2026-02-09
  - Personalizes item tokenization itself rather than relying only on global static identifiers.
- **Rethinking Generative Recommender Tokenizer: Recsys-Native Encoding and Semantic Quantization Beyond LLMs** [[Paper]](https://arxiv.org/abs/2602.02338) — Source: arXiv | Published: 2026-02-02
  - A key 2026 paper arguing for recsys-native tokenizer design.
- **End-to-End Semantic ID Generation for Generative Advertisement Recommendation** [[Paper]](https://arxiv.org/abs/2602.10445) — Source: arXiv | Published: 2026-02-11
  - Directly tackles objective misalignment in two-stage SID generation.
- **Unleash the Potential of Long Semantic IDs for Generative Recommendation** [[Paper]](https://arxiv.org/abs/2602.13573) — Source: arXiv | Published: 2026-02-14
- **Variable-Length Semantic IDs for Recommender Systems** [[Paper]](https://arxiv.org/abs/2602.16375) — Source: arXiv | Published: 2026-02-18
  - Replaces fixed-length codes with adaptive-length semantic identifiers for better efficiency-capacity trade-offs.
- **IntRR: A Framework for Integrating SID Redistribution and Length Reduction** [[Paper]](https://arxiv.org/abs/2602.20704) — Source: arXiv | Published: 2026-02-24
  - Revisits semantic-ID redistribution and length reduction as a joint efficiency-quality problem.
- **LLM-Aligned Geographic Item Tokenization for Local-Life Recommendation** [[Paper]](https://arxiv.org/abs/2511.14221) — Source: arXiv | Published: 2025-11-18
  - Adapts geographic-aware tokenization to local-life recommendation, highlighting a domain-specific extension of the SID route.
- **GateSID: Adaptive Gating for Semantic-Collaborative Alignment in Cold-Start Recommendation** [[Paper]](https://arxiv.org/abs/2603.22916) — Source: arXiv | Published: 2026-03-24
  - Balances semantic and collaborative signals with adaptive gating for cold-start recommendation.
- **Drift-Aware Continual Tokenization for Generative Recommendation** [[Paper]](https://arxiv.org/abs/2603.29705) — Source: arXiv | Published: 2026-03-31
  - Addresses representation drift when tokenizers and item spaces evolve over time.
- **Stop Treating Collisions Equally: Qualification-Aware Semantic ID Learning for Recommendation at Industrial Scale** [[Paper]](https://arxiv.org/abs/2603.00632) — Source: arXiv | Published: 2026-02-28
  - Focuses on heterogeneous semantic-ID collision severity and proposes collision-aware learning at industrial scale.
- **DOS: Dual-Flow Orthogonal Semantic IDs for Recommendation in Meituan** [[Paper]](https://arxiv.org/abs/2602.04460) — Source: arXiv | Published: 2026-02-04
  - Uses dual-flow orthogonal semantic IDs to reduce mismatch between codebook space and generation space in production GR.
- **Grounded Token Initialization for New Vocabulary in LMs for Generative Recommendation** [[Paper]](https://arxiv.org/abs/2604.02324) — Source: arXiv | Published: 2026-04-02
  - Highlights token initialization as an underappreciated bottleneck.
- **Semantic Trimming and Auxiliary Multi-step Prediction for Generative Recommendation** [[Paper]](https://arxiv.org/abs/2604.05329) — Source: arXiv | Published: 2026-04-07
  - Addresses semantic dilution and high-granularity SID inefficiency.
- **CRAB: Codebook Rebalancing for Bias Mitigation in Generative Recommendation** [[Paper]](https://arxiv.org/abs/2604.05113) — Source: arXiv | Published: 2026-04-06
  - A new 2026 paper on semantic-token frequency imbalance and popularity bias.

## Unified Generative Search Recommendation and Retrieval

- **Recommender Systems with Generative Retrieval** [[Paper]](https://arxiv.org/abs/2305.05065) — Source: arXiv | Published: 2023-05-08
  - An early baseline that reframes recommendation as autoregressive generative retrieval over semantic IDs.
- **Preference Discerning with LLM-Enhanced Generative Retrieval** [[Paper]](https://arxiv.org/abs/2412.08604) — Source: arXiv | Published: 2024-12-11
  - Uses LLM-inferred preferences to improve generative retrieval under limited explicit preference supervision.
- **Sparse Meets Dense: Unified Generative Recommendations with Cascaded Sparse-Dense Representations** [[Paper]](https://arxiv.org/abs/2503.02453) — Source: arXiv | Published: 2025-03-04
  - Tries to bridge sparse generative modeling and dense retrieval-style precision inside one unified framework.
- **PinRec: Outcome-Conditioned, Multi-Token Generative Retrieval for Industry-Scale Recommendation Systems** [[Paper]](https://arxiv.org/abs/2504.10507) — Source: arXiv | Published: 2025-04-09
  - An industry-scale generative retrieval direction that conditions on outcomes and uses multi-token item generation.
- **Unified Generative Search and Recommendation** [[Paper]](https://arxiv.org/abs/2504.05730) — Source: arXiv | Published: 2025-04-08
  - A foundational paper for joint search and recommendation modeling.
- **GRAM: Generative Recommendation via Semantic-aware Multi-granular Late Fusion** [[Paper]](https://arxiv.org/abs/2506.01673) — Source: arXiv | Published: 2025-06-02
  - Uses semantic-aware multi-granular late fusion to better integrate rich item information in GR.
- **TBGRecall: A Generative Retrieval Model for E-commerce Recommendation Scenarios** [[Paper]](https://arxiv.org/abs/2508.11977) — Source: arXiv | Published: 2025-08-16
  - Targets e-commerce retrieval specifically rather than only general sequential recommendation.
- **MISS: Multi-Modal Tree Indexing and Searching with Lifelong Sequential Behavior for Retrieval Recommendation** [[Paper]](https://arxiv.org/abs/2508.14515) — Source: arXiv | Published: 2025-08-20
  - Combines multimodal tree indexing with lifelong behavior modeling for retrieval recommendation.
- **Test-Time Scaling Strategies for Generative Retrieval in Multimodal Conversational Recommendations** [[Paper]](https://arxiv.org/abs/2508.18132) — Source: arXiv | Published: 2025-08-25
  - Studies test-time scaling for multimodal conversational generative retrieval rather than only single-turn settings.
- **OneSearch: A Preliminary Exploration of the Unified End-to-End Generative Framework for E-commerce Search** [[Paper]](https://arxiv.org/abs/2509.03236) — Source: arXiv | Published: 2025-09-03
  - A preliminary industrial exploration of unified end-to-end generative modeling for e-commerce search.
- **OneSearch-V2: The Latent Reasoning Enhanced Self-distillation Generative Search Framework** [[Paper]](https://arxiv.org/abs/2603.24422) — Source: arXiv | Published: 2026-03-25
  - Strong industrial evidence for generative search backbone evolution.
- **UniSearch: Rethinking Search System with a Unified Generative Architecture** [[Paper]](https://arxiv.org/abs/2509.06887) — Source: arXiv | Published: 2025-09-08
  - Argues that search should be rebuilt around a unified generative architecture rather than loosely connected stages.
- **GLASS: A Generative Recommender for Long-sequence Modeling via SID-Tier and Semantic Search** [[Paper]](https://arxiv.org/abs/2602.05663) — Source: arXiv | Published: 2026-02-05
- **DualGR: Generative Retrieval with Long and Short-Term Interests Modeling** [[Paper]](https://arxiv.org/abs/2511.12518) — Source: arXiv | Published: 2025-11-16
  - Combines long- and short-term interest modeling for industrial generative retrieval.
- **SynerGen: Contextualized Generative Recommender for Unified Search and Recommendation** [[Paper]](https://arxiv.org/abs/2509.21777) — Source: arXiv | Published: 2025-09-26
  - Uses a single contextualized generative backbone for both personalized search and recommendation.

## Reasoning Post-training and Alignment

- **Think Before Recommend: Unleashing the Latent Reasoning Power for Sequential Recommendation** [[Paper]](https://arxiv.org/abs/2503.22675) — Source: arXiv | Published: 2025-03-28
  - Introduces inference-time reasoning or extra compute as a way to improve sequential recommendation.
- **Why Thinking Hurts? Diagnosing and Rectifying the Reasoning Shift in Foundation Recommender Models** [[Paper]](https://arxiv.org/abs/2602.16587) — Source: arXiv | Published: 2026-02-18
  - Directly questions whether explicit CoT-style reasoning can hurt SID-based foundation recommenders.
- **Parallel Latent Reasoning for Sequential Recommendation** [[Paper]](https://arxiv.org/abs/2601.03153) — Source: arXiv | Published: 2026-01-06
- **ReSearch: Learning to Reason with Search for LLMs via Reinforcement Learning** [[Paper]](https://arxiv.org/abs/2503.19470) — Source: arXiv | Published: 2025-03-25
  - Uses reinforcement learning to interleave explicit search operations with reasoning during generation.
- **Retrieval-in-the-Chain: Bootstrapping Large Language Models for Generative Retrieval** [[Paper]](https://arxiv.org/abs/2510.13095) — Source: arXiv | Published: 2025-10-15
  - Examines whether explicit reasoning and retrieval steps help generative retrieval beyond plain decoding.
- **Generative Reasoning Recommendation via LLMs** [[Paper]](https://arxiv.org/abs/2510.20815) — Source: arXiv | Published: 2025-10-23
  - Builds a unified understanding-reasoning-prediction view of LLM-based recommendation.
- **Towards Context-aware Reasoning-enhanced Generative Searching in E-commerce** [[Paper]](https://arxiv.org/abs/2510.16925) — Source: arXiv | Published: 2025-10-19
  - Injects richer context and reasoning into e-commerce generative search.
- **SAGE: Sequence-level Adaptive Gradient Evolution for Generative Recommendation** [[Paper]](https://arxiv.org/abs/2601.21452) — Source: arXiv | Published: 2026-01-29
  - A preference-optimization direction targeting sequence-level multi-objective alignment in GR.
- **Climber-Pilot: A Non-Myopic Generative Recommendation Model Towards Better Instruction-Following** [[Paper]](https://arxiv.org/abs/2602.13581) — Source: arXiv | Published: 2026-02-14
  - Uses non-myopic generation to improve instruction-following in large-scale GR.
- **DeepInterestGR: Mining Deep Multi-Interest Using Multi-Modal LLMs for Generative Recommendation** [[Paper]](https://arxiv.org/abs/2602.18907) — Source: arXiv | Published: 2026-02-21
  - Targets the shallow-interest problem with deeper multi-interest modeling from multimodal signals.
- **Reasoning over Semantic IDs Enhances Generative Recommendation** [[Paper]](https://arxiv.org/abs/2603.23183) — Source: arXiv | Published: 2026-03-24
- **Robust Post-Training for Generative Recommenders: Why Exponential Reward-Weighted SFT Outperforms RLHF** [[Paper]](https://arxiv.org/abs/2603.10279) — Source: arXiv | Published: 2026-03-10
- **Beyond Interleaving: Causal Attention Reformulations for Generative Recommender Systems** [[Paper]](https://arxiv.org/abs/2603.10369) — Source: arXiv | Published: 2026-03-11
  - Revisits the common item-action interleaving formulation and proposes more efficient causal attention structures.
- **Iterative Semantic Reasoning from Individual to Group Interests for Generative Recommendation with LLMs** [[Paper]](https://arxiv.org/abs/2603.13934) — Source: arXiv | Published: 2026-03-14
  - Extends semantic reasoning from individual behavior understanding toward group-level interest structure.
- **Causal Direct Preference Optimization for Distributionally Robust Generative Recommendation** [[Paper]](https://arxiv.org/abs/2603.22335) — Source: arXiv | Published: 2026-03-21
  - Adds causal invariance to preference optimization to improve robustness under distribution shift.
- **APAO: Adaptive Prefix-Aware Optimization for Generative Recommendation** [[Paper]](https://arxiv.org/abs/2603.02730) — Source: arXiv | Published: 2026-03-03
  - Targets the mismatch between token-level training losses and beam-search style inference.

## Scaling Serving Inference and Reranking

- **RelayGR: Scaling Long-Sequence Generative Recommendation via Cross-Stage Relay-Race Inference** [[Paper]](https://arxiv.org/abs/2601.01712) — Source: arXiv | Published: 2026-01-05
- **Action is All You Need: Dual-Flow Generative Ranking Network for Recommendation** [[Paper]](https://arxiv.org/abs/2505.16752) — Source: arXiv | Published: 2025-05-22
  - A generative ranking line that replaces heavy manual feature engineering with raw sequential behavior modeling.
- **UniMixer: A Unified Architecture for Scaling Laws in Recommendation Systems** [[Paper]](https://arxiv.org/abs/2604.00590) — Source: arXiv | Published: 2026-04-01
- **Vectorizing the Trie: Efficient Constrained Decoding for LLM-based Generative Retrieval on Accelerators** [[Paper]](https://arxiv.org/abs/2602.22647) — Source: arXiv | Published: 2026-02-26
  - Targets accelerator-friendly constrained decoding for industrial generative retrieval.
- **RankGR: Rank-Enhanced Generative Retrieval with Listwise Direct Preference Optimization in Recommendation** [[Paper]](https://arxiv.org/abs/2602.08575) — Source: arXiv | Published: 2026-02-09
  - Adds listwise direct preference optimization and lightweight reranking to industrial GR.
- **HiGR: Efficient Generative Slate Recommendation via Hierarchical Planning and Multi-Objective Preference Alignment** [[Paper]](https://arxiv.org/abs/2512.24787) — Source: arXiv | Published: 2025-12-31
  - Extends generative recommendation to slate generation with hierarchical planning and multi-objective preference alignment.
- **Generative Reasoning Re-ranker** [[Paper]](https://arxiv.org/abs/2602.07774) — Source: arXiv | Published: 2026-02-08
  - Uses reasoning-style generation at the reranking stage rather than only at retrieval.
- **GeoGR: A Generative Retrieval Framework for Spatio-Temporal Aware POI Recommendation** [[Paper]](https://arxiv.org/abs/2602.10411) — Source: arXiv | Published: 2026-02-11
  - Extends generative retrieval into spatio-temporal POI recommendation with stronger context modeling.
- **Multimodal Generative Retrieval Model with Staged Pretraining for Food Delivery on Meituan** [[Paper]](https://arxiv.org/abs/2602.06654) — Source: arXiv | Published: 2026-02-06
  - A Meituan food-delivery retrieval system that uses staged pretraining for multimodal generative retrieval.
- **Constraint-Aware Generative Re-ranking for Multi-Objective Optimization in Advertising Feeds** [[Paper]](https://arxiv.org/abs/2603.04227) — Source: arXiv | Published: 2026-03-04
  - Treats constrained reranking as bounded neural decoding with constraints integrated directly into inference.
- **Quantized Inference for OneRec-V2** [[Paper]](https://arxiv.org/abs/2603.11486) — Source: arXiv | Published: 2026-03-12
  - Studies low-precision inference for GR and highlights recommender-specific quantization challenges.
- **A Generative Re-ranking Model for List-level Multi-objective Optimization at Taobao** [[Paper]](https://arxiv.org/abs/2505.07197) — Source: arXiv | Published: 2025-05-12
  - A Taobao industrial paper on list-level multi-objective generative reranking with reported online gains.
- **NLGR: Utilizing Neighbor Lists for Generative Rerank in Personalized Recommendation Systems** [[Paper]](https://arxiv.org/abs/2502.06097) — Source: arXiv | Published: 2025-02-10
  - Improves evaluator-generator style generative reranking by leveraging neighbor-list information.
- **Breaking the Likelihood Trap: Consistent Generative Recommendation with Graph-structured Model** [[Paper]](https://arxiv.org/abs/2510.10127) — Source: arXiv | Published: 2025-10-11
  - Questions pure likelihood-based generative reranking and pushes toward graph-structured consistency.
- **Next-Scale Generative Reranking: A Tree-based Generative Rerank Method at Meituan** [[Paper]](https://arxiv.org/abs/2604.05314) — Source: arXiv | Published: 2026-04-07
- **NEZHA: A Zero-sacrifice and Hyperspeed Decoding Architecture for Generative Recommendations** [[Paper]](https://arxiv.org/abs/2511.18793) — Source: arXiv | Published: 2025-11-24
  - Targets faster GR decoding without depending on a separate draft model or verifier.
- **GRN: Generative Rerank Network for Context-wise Recommendation** [[Paper]](https://arxiv.org/abs/2104.00860) — Source: arXiv | Published: 2021-04-02
  - An earlier foundation for treating reranking as sequence generation with context-dependent item interactions.
- **Climber: Toward Efficient Scaling Laws for Large Recommendation Models** [[Paper]](https://dl.acm.org/doi/10.1145/3746252.3761561) — Source: ACM CIKM 2025 | Published: 2025-11-10
  - Studies how to realize more efficient scaling behavior in large recommendation models under practical compute budgets.

## Reliability Bias Cold-start and Generalization

- **How Well Does Generative Recommendation Generalize?** [[Paper]](https://arxiv.org/abs/2603.19809) — Source: arXiv | Published: 2026-03-20
  - Important for challenging the overly broad "GR generalizes better" narrative.
- **Cold-Starts in Generative Recommendation: A Reproducibility Study** [[Paper]](https://arxiv.org/abs/2603.29845) — Source: arXiv | Published: 2026-03-31
  - Especially useful for grounding cold-start claims.
- **Bringing Model Editing to Generative Recommendation in Cold-Start Scenarios** [[Paper]](https://arxiv.org/abs/2603.14259) — Source: arXiv | Published: 2026-03-15
  - Applies model-editing style knowledge injection to cold-start items without full retraining.
- **CRAB: Codebook Rebalancing for Bias Mitigation in Generative Recommendation** [[Paper]](https://arxiv.org/abs/2604.05113) — Source: arXiv | Published: 2026-04-06

## Diffusion Models

- **DiffusionGS: Generative Search with Query Conditioned Diffusion in Kuaishou** [[Paper]](https://arxiv.org/abs/2508.17754) — Source: arXiv | Published: 2025-08-25
  - A query-conditioned diffusion framework for generative search, with the query acting as an explicit intent anchor.
- **DiffuGR: Generative Document Retrieval with Diffusion Language Models** [[Paper]](https://arxiv.org/abs/2511.08150) — Source: arXiv | Published: 2025-11-11
  - Explores diffusion language models as an alternative to left-to-right document generation in generative retrieval.
- **DiffGRM: Diffusion-based Generative Recommendation Model** [[Paper]](https://arxiv.org/abs/2510.21805) — Source: arXiv | Published: 2025-10-21
  - Replaces autoregressive SID decoding with masked discrete diffusion to better capture intra-item consistency.
- **DimeRec: A Unified Framework for Enhanced Sequential Recommendation via Generative Diffusion Models** [[Paper]](https://arxiv.org/abs/2408.12153) — Source: arXiv | Published: 2024-08-22
  - Uses diffusion for sequential recommendation with an emphasis on stronger representations and improved diversity.
- **Discrete Conditional Diffusion for Reranking in Recommendation** [[Paper]](https://arxiv.org/abs/2308.06982) — Source: arXiv | Published: 2023-08-14
  - A diffusion-based reranking direction for discrete recommendation lists.
- **Masked Diffusion Generative Recommendation** [[Paper]](https://arxiv.org/abs/2601.19501) — Source: arXiv | Published: 2026-01-27
  - Replaces left-to-right semantic-ID decoding with masked diffusion generation.
- **FAVE: Flow-based Average Velocity Establishment for Sequential Recommendation** [[Paper]](https://arxiv.org/abs/2604.04427) — Source: arXiv | Published: 2026-04-06
  - A flow-based alternative that continues the non-autoregressive direction for sequential recommendation.

## Optimization Adapters and Other Directions

The following adjacent bridge papers are not core `semantic ID + generative decoding` papers, but they are increasingly important for understanding where the route may evolve next:

- from `item token` modeling,
- to `feature-token unified backbones`,
- and potentially toward richer `sample-level token` hypotheses.

- **RCLRec: Reverse Curriculum Learning for Modeling Sparse Conversions in Generative Recommendation** [[Paper]](https://arxiv.org/abs/2603.28124) — Source: arXiv | Published: 2026-03-30
  - Focuses on sparse conversion supervision rather than only click- or next-item-heavy objectives.
- **Awakening Dormant Users: Generative Recommendation with Counterfactual Functional Role Reasoning** [[Paper]](https://arxiv.org/abs/2602.13134) — Source: arXiv | Published: 2026-02-13
  - Uses counterfactual functional-role reasoning to target low-conversion but still-engaged users in e-commerce.
- **Continual Low-Rank Adapters for LLM-based Generative Recommender Systems** [[Paper]](https://arxiv.org/abs/2510.25093) — Source: arXiv | Published: 2025-10-29
  - Uses continual low-rank adapters to track shifting user interests without full model retraining.
- **ADORE: Autonomous Domain-Oriented Relevance Engine for E-commerce** [[Paper]](https://arxiv.org/abs/2512.02555) — Source: arXiv | Published: 2025-12-02
  - An e-commerce relevance engine that combines synthetic data generation, synthesis, and distillation.
- **Towards Distribution Matching between Collaborative and Language Spaces for Generative Recommendation** [[Paper]](https://arxiv.org/abs/2504.07363) — Source: arXiv | Published: 2025-04-10
  - Studies how to better match collaborative and language spaces inside generative recommendation.
- **Align$^3$GR: Unified Multi-Level Alignment for LLM-based Generative Recommendation** [[Paper]](https://arxiv.org/abs/2511.11255) — Source: arXiv | Published: 2025-11-14
  - Aligns token-level, behavior-modeling, and preference objectives inside one LLM-based GR framework.
- **Pantheon: Personalized Multi-objective Ensemble Sort via Iterative Pareto Policy Optimization** [[Paper]](https://arxiv.org/abs/2505.13894) — Source: arXiv | Published: 2025-05-20
  - An industrial multi-objective sorting framework built around iterative Pareto-style policy optimization.
- **Actions Speak Louder than Words: Trillion-Parameter Sequential Transducers for Generative Recommendations** [[Paper]](https://arxiv.org/abs/2402.17152) — Source: arXiv | Published: 2024-02-27
  - Treats recommendation as generative transduction with very large sequential transducers rather than classic discriminative towers.
- **ESANS: Effective and Semantic-Aware Negative Sampling for Large-Scale Retrieval Systems** [[Paper]](https://dl.acm.org/doi/10.1145/3696410.3714600) — Source: ACM WWW 2025 | Published: 2025-04-22
  - Focuses on semantic-aware negative sampling for large-scale retrieval training, especially under false-negative and efficiency pressure.
- **Adapting Large Language Models by Integrating Collaborative Semantics for Recommendation** [[Paper]](https://arxiv.org/abs/2311.09049) — Source: arXiv | Published: 2023-11-15
  - Injects collaborative semantics into LLM-style recommenders to better align language modeling with recommendation behavior.
- **One Model, Two Markets: Bid-Aware Generative Recommendation** [[Paper]](https://arxiv.org/abs/2603.22231) — Source: arXiv | Published: 2026-03-23
  - Uses bid-aware control signals to jointly model commercial relevance and monetization objectives in generative recommendation.
- **OneTrans: Unified Feature Interaction and Sequence Modeling with One Transformer in Industrial Recommender** [[Paper]](https://arxiv.org/abs/2510.26104) — Source: arXiv | Published: 2025-10-30
  - An important bridge paper showing that sequential tokens and non-sequential feature tokens can be unified into one industrial backbone with online GMV gains.
- **HyFormer: Revisiting the Roles of Sequence Modeling and Feature Interaction in CTR Prediction** [[Paper]](https://arxiv.org/abs/2601.12681) — Source: arXiv | Published: 2026-01-19
  - Refines the unified-backbone idea by arguing that not all tokens should interact symmetrically, using Global Tokens as a more controlled interface.
- **TokenFormer: Unify the Multi-Field and Sequential Recommendation Worlds** [[Paper]](https://arxiv.org/abs/2604.13737) — Source: arXiv | Published: 2026-04-15
  - A new 2026 warning that naive feature-sequence unification can cause Sequential Collapse Propagation, making it a key paper for understanding the limits of full token unification.

## 2026 Highlights

If you only want the most important 2026 additions, start here:

- [OneSearch-V2](https://arxiv.org/abs/2603.24422) — Source: arXiv | Published: 2026-03-25
- [Generative Recommendation for Large-Scale Advertising](https://arxiv.org/abs/2602.22732) — Source: arXiv | Published: 2026-02-26
- [OneRanker](https://arxiv.org/abs/2603.02999) — Source: arXiv | Published: 2026-03-03
- [MBGR](https://arxiv.org/abs/2604.02684) — Source: arXiv | Published: 2026-04-03
- [Next-Scale Generative Reranking at Meituan](https://arxiv.org/abs/2604.05314) — Source: arXiv | Published: 2026-04-07
- [RankGR](https://arxiv.org/abs/2602.08575) — Source: arXiv | Published: 2026-02-09
- [Constraint-Aware Generative Re-ranking](https://arxiv.org/abs/2603.04227) — Source: arXiv | Published: 2026-03-04
- [GLIDE at Spotify](https://arxiv.org/abs/2603.17540) — Source: arXiv | Published: 2026-03-18
- [Semantic IDs at Snapchat](https://arxiv.org/abs/2604.03949) — Source: arXiv | Published: 2026-04-05
- [ReSID](https://arxiv.org/abs/2602.02338) — Source: arXiv | Published: 2026-02-02
- [DIGER](https://arxiv.org/abs/2601.19711) — Source: arXiv | Published: 2026-01-27
- [UniSID](https://arxiv.org/abs/2602.10445) — Source: arXiv | Published: 2026-02-11
- [Drift-Aware Continual Tokenization](https://arxiv.org/abs/2603.29705) — Source: arXiv | Published: 2026-03-31
- [GTI](https://arxiv.org/abs/2604.02324) — Source: arXiv | Published: 2026-04-02
- [STAMP](https://arxiv.org/abs/2604.05329) — Source: arXiv | Published: 2026-04-07
- [CRAB](https://arxiv.org/abs/2604.05113) — Source: arXiv | Published: 2026-04-06
- [How Well Does Generative Recommendation Generalize?](https://arxiv.org/abs/2603.19809) — Source: arXiv | Published: 2026-03-20
- [Cold-Starts in Generative Recommendation: A Reproducibility Study](https://arxiv.org/abs/2603.29845) — Source: arXiv | Published: 2026-03-31
- [Robust Post-Training for Generative Recommenders](https://arxiv.org/abs/2603.10279) — Source: arXiv | Published: 2026-03-10
- [Tencent Advertising Algorithm Challenge 2025](https://arxiv.org/abs/2604.04976) — Source: arXiv | Published: 2026-04-04

## Contributing

Contributions are welcome.

### Guidelines

1. Please use direct paper links whenever possible.
2. When adding a note, keep it at abstract- or official-page-supported granularity.
3. If you add industrial claims, prefer papers or official dataset/system pages over second-hand summaries.
4. Avoid writing conclusions that the source does not explicitly support.

### Preferred Format

Use one of the following:

- **`- Paper Title** [[Paper]](direct_link) — Source: arXiv | Published: 2026-03-25`
- `  - One-sentence, source-grounded note about the paper's main contribution or scope.`
- **`- Paper Title** [[Paper]](direct_link) — Source: ACM CIKM 2025 | Published: 2025-11-10`

If code or datasets are available, feel free to add:

- `[[Code]](link)`
- `[[Dataset]](link)`

### Areas of Interest

- Generative search and recommendation frameworks
- Semantic ID and tokenization strategies
- Generative retrieval and grounded generation
- Reasoning-enhanced recommendation
- Production deployment and serving systems
- Cold-start, bias, robustness, and generalization
