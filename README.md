<div align="center">

  # A Suevy on the Application of Large Language Model in Scenario-Based Testing of Automated Driving Systems

</div>

<div align="center">

  ![GitHub stars](https://img.shields.io/github/stars/ftgTUGraz/LLM4ADSTest?style=social)
  ![GitHub forks](https://img.shields.io/github/forks/ftgTUGraz/LLM4ADSTest?style=social)

</div>



This repository accompanies the survey paper "[*A Survey on the Application of Large Language Models in Scenario-Based Testing of Automated Driving Systems*](https://arxiv.org/pdf/2505.16587v1)." It compiles recent academic and industrial works on how LLMs are used across different phases of scenario-based ADS testing. The survey also discusses key models, prompting strategies, safety concerns, and integration challenges.


Contributions are welcome—feel free to suggest new papers via issues or pull requests. Alternatively, you can also contact us via [yongqi.zhao@tugraz.at](mailto:yongqi.zhao@tugraz.at) and [dong.bi@tugraz.at](mailto:dong.bi@tugraz.at). **This repository will be continuously updated as new relevant papers emerge**, and we appreciate suggestions from the community to help keep the collection comprehensive and current.

## Citation
If you think this repo is useful, please cite our paper:
```bibtex
@misc{zhao2025surveyapplicationlargelanguage,
      title={A Survey on the Application of Large Language Models in Scenario-Based Testing of Automated Driving Systems}, 
      author={Yongqi Zhao and Ji Zhou and Dong Bi and Tomislav Mihalj and Jia Hu and Arno Eichberger},
      year={2025},
      eprint={2505.16587},
      archivePrefix={arXiv},
      primaryClass={cs.SE},
      url={https://arxiv.org/abs/2505.16587}, 
}
```


## Table of Contents
- [1. Related Survey](#1-related-survey)
  - [Survey of LLM](#survey-of-llm)
  - [Survey of Scenario-Based Testing](#survey-of-scenario-based-testing)
  - [Survey of LLM for AD](#survey-of-llm-for-ad)
  - [Survey of LLM for Miscellaneous Domains](#survey-of-llm-for-miscellaneous-domains)
- [2. Terminology](#2-terminology)
  - [Scenario](#scenario)
  - [Scenario Abstraction Level](#scenario-abstraction-level)
- [3. LLM Applications by Phase](#3-llm-applications-by-phase)
  - [3.1 Scenario Source](#31-scenario-source)
    - [Data Enrichment](#data-enrichment)
    - [Data Enrichment Through Hazard Analysis](#data-enrichment-through-hazard-analysis)
      - [Hazard Analysis and Risk Assessment (HARA)](#hazard-analysis-and-risk-assessment-hara)
      - [Systems Theoretic Process Analysis (STPA)](#systems-theoretic-process-analysis-stpa)
    - [Data Labeling](#data-labeling)
    - [Data Retrieval](#data-retrieval)
  - [3.2 Scenario Generation](#32-scenario-generation)
    - [LLM as an Human-Machine Interface](#llm-as-an-human-machine-interface)
      - [Structured representatio](#structured-representatio)
      - [Loss function and executable code](#loss-function-and-executable-code)
    - [LLM as an Data Interpreter](#llm-as-an-data-interpreter)
      - [Accident reports And Domain knowledge](#accident-reports-and-domain-knowledge)
      - [Naturalistic driving data](#naturalistic-driving-data)
    - [LLM as an Intermediate Format Generator](#llm-as-an-intermediate-format-generator)
      - [Driving policies](#driving-policies)
      - [Scenario elements](#scenario-elements)
      - [Functional & Abstract & Logical scenario](#functional--abstract--logical-scenario)
    - [LLM as an Standard Format Generator](#llm-as-an-standard-format-generator)
    - [LLM as an Executable Scenario Generator](#llm-as-an-executable-scenario-generator)
      - [Template Filling](#template-filling)
      - [End-to-End Generation](#end-to-end-generation)
      - [Hybrid Generation](#hybrid-generation)
  - [3.3 Scenario Selection](#33-scenario-selection)
  - [3.4 Test Execution](#34-test-execution)
    - [Anomaly Detection](#anomaly-detection)
    - [Simulation Setup Automation](#simulation-setup-automation)
    - [Scenario Optimization](#scenario-optimization)
    - [Hazard Prediction](#hazard-prediction)
  - [3.5 ADS Assessment](#35-ads-assessment)
    - [Safety performance evaluatio](#safety-performance-evaluatio)
    - [Intelligence level evaluation](#intelligence-level-evaluation)
- [4. License](#4-license)


## 1. Related Survey

### Survey of LLM
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**A Comprehensive Overview of Large Language Models**](https://arxiv.org/abs/2307.06435) | arxiv.org | 2023-7 | - | This article offers a concise yet comprehensive overview of recent advancements in Large Language Models (LLMs), covering core concepts and cutting-edge topics to help researchers and practitioners navigate the rapidly evolving LLM landscape and foster further innovation in the field. |
| [**A survey on large language models: Applications, challenges, limitations, and practical usage**](https://arxiv.org/abs/2401.13601) | arxiv.org | 2024-1 | [GitHub](https://github.com/anas-zafar/LLM-Survey) | Hadi et al. offers a comprehensive overview of LLMs, covering their history, architecture, train-ing methods, applications, challenges, and future directions to support their development and real-world deployment. |
| [**MM-LLMs: Recent Advances in MultiModal Large Language Models**](https://techrxiv.figshare.com/articles/preprint/A_Survey_on_Large_Language_Models_Applications_Challenges_Limitations_and_Practical_Usage/23589741/1/files/41501037.pdf) | arxiv.org | 2023 | [Project](https://mm-llms.github.io/) | Zhang et al. systematically analyze 126 multimodal LLMs (MLLMs), with detailed comparison of model design and benchmark performances. |
| [**Stop Overthinking: A Survey on Efficient Reasoning for Large Language Models**](https://arxiv.org/abs/2503.16419) | arxiv.org | 2025-3 | [Project](https://github.com/Eclipsess/Awesome-Efficient-Reasoning-LLMs) | Su et al. review efficient reasoning strategies, categorizing them into model-based, output-based, and prompt-based approaches. |
| [**A systematic survey of prompt engineering in large language models**](https://rotmandigital.ca/wp-content/uploads/2024/09/A-Systematic-Survey-of-Prompt-Engineering-in-Large-Language-Models.pdf) | arxiv.org | 2024 | - | Sahoo et al. provide a systematic overview of approaches used in prompt engineering, covering their methodologies, applications, models used and the datasets associated with each approach. offer a comprehensive survey on prompt engineering, including an evaluation of each methodology and a discussion on AI security, with a focus on vulnerability in prompt engineering. |
| [**Unleashing the potential of prompt engineering in large language models: a comprehensive review**](https://arxiv.org/abs/2310.14735) | arxiv.org | 2023-10 | - | Chen et al. offer a comprehensive survey on prompt engineering, including an evaluation of each methodology and a discussion on AI security, with a focus on vulnerability in prompt engineering. |
| [**Differentially private natural language models: Recent advances and future directions**](https://arxiv.org/abs/2301.09112) | arxiv.org | 2023-1 | - | Hu et al. review the use of differential privacy in natural language models. |
| [**Privacy issues in large language models: A survey**](https://arxiv.org/abs/2312.06717) | arxiv.org | 2023 | [GitHub](https://github.com/safr-ai-lab/survey-llm) | Neel and Chang present a survey on privacy issues in LLM more broadly. |
| [**Privacy Preserving Prompt Engineering: A Survey**](https://dl.acm.org/doi/full/10.1145/3729219) | ACM Computing Surveys | 2025-5 | - | Edemacu and Wu focus specifically on privacy concerns related to in in-context learning and prompting mechanisms. |

### Survey of Scenario-Based Testing
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**Scenario based testing of automated driving systems: A literature survey**](https://www.researchgate.net/profile/Demin-Nalic/publication/344896382_Scenario_Based_Testing_of_Automated_Driving_Systems_A_Literature_Survey/links/600806cba6fdccdcb868bf72/Scenario-Based-Testing-of-Automated-Driving-Systems-A-Literature-Survey.pdf) | FISITA web Congress | 2020 | - | This paper surveys 86 recent studies on scenario generation and evaluation methods for testing and validating Automated Driving Systems (ADS), highlighting the importance of simulation-based approaches to address safety, cost, and complexity challenges, and proposing a unified terminology and classification framework for these methods. |
| [**Finding Critical Scenarios for Automated Driving Systems: A Systematic Mapping Study**](https://ieeexplore.ieee.org/abstract/document/9763411) | IEEE Transactions on Software Engineering | 2022-4 | - | This paper presents a systematic mapping study on critical scenario identification for autonomous driving, introducing a comprehensive taxonomy, reviewing 86 studies from 2017–2020, and highlighting open challenges related to coverage, practicality, and scenario space explosion in support of ADS design, verification, and safety assurance. |
| [**A Survey on Scenario-Based Testing for Automated Driving Systems in High-Fidelity Simulation**](https://arxiv.org/abs/2112.00964) | arxiv.org | 2021-12 | - |  Zhong et al. focus on scenario-based testing utilizing high-fidelity simulation platforms. |
| [**A Survey on Safety-Critical Driving Scenario Generation—A Methodological Perspective**](https://ieeexplore.ieee.org/abstract/document/10089194) | IEEE Transactions on Intelligent Transportation Systems | 2023-3 | - | Ding et al. categorize generation methods into data driven, adversarial, and knowledge-based categories. |
| [**Survey on Scenario-Based Safety Assessment of Automated Vehicles**](https://ieeexplore.ieee.org/abstract/document/9090897) |  IEEE Access | 2020-5 | - | Riedmaier et al. advocate for the integration of formal verification methods within scenario-based testing|
| [**Literature Review of Verification and Validation Activities of Automated Driving Systems**](https://www.researchgate.net/profile/Jeffrey-Wishart/publication/349067126_Literature_Review_of_Verification_and_Validation_Activities_of_Automated_Driving_Systems/links/6022b3e0a6fdcc37a815b118/Literature-Review-of-Verification-and-Validation-Activities-of-Automated-Driving-Systems.pdf?origin=journalDetail&_tp=eyJwYWdlIjoiam91cm5hbERldGFpbCJ9) | SAE International Journal of Connected and Automated Vehicles | 2020-12 | - | Wishart et al. review current verification and validation practices to support the development of SAE standards. |
| [**Autonomous Vehicle Evaluation: A Comprehensive Survey on Modeling and Simulation Approaches**](https://ieeexplore.ieee.org/abstract/document/9605690) | IEEE Access | 2021-11 | [Project](https://creativecommons.org/licenses/by/4.0/) | Alghodhaifi et al. investigate evaluation efficiency, emphasizing the role of accelerated techniques as valuable complements to scenario-based approaches. |
| [**A Survey on Automated Driving System Testing: Landscapes and Trends**](https://dl.acm.org/doi/full/10.1145/3579642) | ACM Transactions on Software Engineering and Methodology | 2023-7 | - | Tang et al investigate evaluation efficiency, emphasizing the role of  AI-based techniques as valuable complements to scenario-based approaches. |
| [**Road Infrastructure Challenges Faced by Automated Driving: A Review**](https://www.mdpi.com/2076-3417/12/7/3477) | Applied Sciences | 2022-3 | - | Mihalj et al. explore the interaction between ADSs and physical infrastructure, offering perspectives on how environmental factors can influence the design of test scenarios. |
### Survey of LLM for AD
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**LLM4Drive: A Survey of Large Language Models for Autonomous Driving**](https://arxiv.org/abs/2311.01043) | arxiv.org | 2023-11 | [GitHub](https://github.com/Thinklab-SJTU/Awesome-LLM4AD) | This paper presents a comprehensive review of Large Language Models for Autonomous Driving (LLM4AD), highlighting current advancements, key challenges, and future directions, while offering real-time updates and open-source resources for researchers. |
| [**Vision Language Models in Autonomous Driving: A Survey and Outlook**](https://ieeexplore.ieee.org/abstract/document/10531702) | IEEE Transactions on Intelligent Vehicles | 2024-5 | [GitHub](https://github.com/ge25nab/Awesome-VLM-AD-ITS) | This paper provides a comprehensive survey of Vision-Language Models (VLMs) in Autonomous Driving (AD), covering tasks from perception to control, summarizing key datasets, metrics, and applications, and outlining current challenges, research gaps, and future directions. |
| [**A Survey on Multimodal Large Language Models for Autonomous Driving**](https://openaccess.thecvf.com/content/WACV2024W/LLVM-AD/html/Cui_A_Survey_on_Multimodal_Large_Language_Models_for_Autonomous_Driving_WACVW_2024_paper.html) | 2024 IEEE/CVF Winter Conference | 2024 | - | In a complementary study, Cui et al. systematically review the development, tools, datasets, and challenges of applying MLLMs in AD and map systems, with the aim of informing future research and practical implementation. |
| [**XLM for Autonomous Driving Systems: A Comprehensive Review**](https://arxiv.org/abs/2409.10484) | arxiv.org | 2024-9 | - | This survey offers a comprehensive overview of using next-generation language models (XLMs)—including LLMs, VLMs, and MLLMs—for autonomous driving systems, reviewing their architectures, tools, and applications, while highlighting deployment challenges and future research directions. |
| [**Large Language Models for Human-Like Autonomous Driving: A Survey**](https://ieeexplore.ieee.org/abstract/document/10919629) | 2024 ITSC | 2025-3 | - | This survey critically reviews the integration of Large Language Models (LLMs) into Autonomous Driving (AD), exploring their role in both modular and end-to-end systems, outlining key advancements, challenges, and future directions toward building safer and more human-like AD technologies. |
| [**Large models for intelligent transportation systems and autonomous vehicles: A survey**](https://www.sciencedirect.com/science/article/pii/S1474034624004348) | Advanced Engineering Informatics | 2024-10 | - | Gan et al. offer a comprehensive review of LLM applications in intelligent transportation systems, with an emphasis on scalable and efficient implementation. |
### Survey of LLM for Miscellaneous Domains
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**Tasks People Prompt: A Taxonomy of LLM Downstream Tasks in Software Verification and Falsification Approaches**](https://arxiv.org/abs/2404.09384) | arxiv.org | 2024-04 | – | Braberman et al. propose a taxonomy for LLM-based verification task. |
| [**Large Models Defining a New Era in Intelligence Testing: A Short Discussion and Exploration**](https://ieeexplore.ieee.org/abstract/document/10719620) | IEEE Transactions on Intelligent Vehicles | 2024-10 | – |  Zhou et al. outline frameworks and challenges associated with intelligent system testing. |
| [**Aligning Multimodal LLM with Human Preference: A Survey**](https://arxiv.org/abs/2503.14504) | IEEE Transactions on Intelligent Vehicles | 2025-3 | [GitHub](https://github.com/BradyFU/Awesome-Multimodal-Large-Language-Models/tree/Alignment) | Yu et al. survey alignment algorithms for MLLMs. |
| [**Delving Into Multi-Modal Multi-Task Foundation Models for Road Scene Understanding: From Learning Paradigm Perspectives**](https://ieeexplore.ieee.org/abstract/document/10540321) | IEEE Transactions on Intelligent Vehicles | 2024-5 | [GitHub](https://github.com/rolsheng/MM-VUFM4DS) | Luo et al. [27] review visual foundation models for road scene understanding. |
| [**Leveraging generative AI for urban digital twins: a scoping review on the autonomous generation of urban data, scenarios, designs, and 3D city models for smart city advancement**](https://link.springer.com/article/10.1007/s44212-024-00060-w) | Urban Informatics | 2024-10 | - | In the context of urban innovation, Xu et al. examine the integration of generative AI models with urban digital twins, emphasizing their potential to support smart city management. |

## 2. Terminology

### Scenario
|  Title  |   Venue  |   Date   |   Code   | Summary  |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**Defining and Substantiating the Terms Scene, Situation, and Scenario for Automated Driving**](https://ieeexplore.ieee.org/abstract/document/7313256) | 2015 IEEE 18th International Conference on Intelligent Transportation Systems | 2015-11 | - | This paper analyzes the scenario representation requirements across ISO 26262 development phases, proposes a consistent abstraction-level terminology, and demonstrates systematic scenario evolution throughout the safety-guided development process. |
| [**ASAM OpenSCENARIO DSL 2.1.0, Dynamic scenario description, 2024-03-07**](https://publications.pages.asam.net/standards/ASAM_OpenSCENARIO/ASAM_OpenSCENARIO_DSL/latest/conceptual-overview/scenario-abstraction.html) |  International Organization for Standardization, ISO 21448:2022 | 2022 | - | It is an ISO standard that addresses potential hazards arising from functional insufficiencies or misuse in advanced driver assistance and automated driving systems, beyond hardware or software failures. |
### Scenario Abstraction Level
|  Title  |   Venue  |   Date   |   Code   | Summary  |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**Scenarios for Development, Test and Validation of Automated Vehicles**](https://ieeexplore.ieee.org/abstract/document/8500406) |  2018 IEEE Intelligent Vehicles Symposium (IV) | 2018-10 | - | This paper analyzes the scenario representation requirements across ISO 26262 development phases, proposes a consistent abstraction-level terminology, and demonstrates systematic scenario evolution throughout the safety-guided development process. |
| [**Road vehicles — Safety of the intended functionality**](https://www.iso.org/standard/77490.html) |  ASAM | 2024 | - | ASAM OpenSCENARIO DSL 2.1.0 is a domain-specific language released in March 2024 for dynamically describing complex driving scenarios in the development and testing of automated driving systems. |

## 3. LLM Applications by Phase

### 3.1 Scenario Source
#### Data Enrichment
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**Learning a Bi-Directional Driving Data Generator Via Large Multi-Modal Model Tuning**](https://openreview.net/pdf?id=2UozyR49ZB) | OpenReview | 2024-11 | - | LLMs are applied for both trajectory-conditioned language generation and language-conditioned trajectory synthesis. |
| [**Mixing left and right-hand driving data in a hierarchical framework with llm generation**](https://ieeexplore.ieee.org/abstract/document/10636276) |  IEEE Robotics and Automation Letters | 2024-10 | - | right-hand driving trajectories are synthesized by LLMs using left-hand driving data as a reference. |
| [**Editable scene simulation for autonomous driving via collaborative llm-agents**](https://openaccess.thecvf.com/content/CVPR2024/html/Wei_Editable_Scene_Simulation_for_Autonomous_Driving_via_Collaborative_LLM-Agents_CVPR_2024_paper.html) | CVPR 2024 | 2024 | [GitHub](https://github.com/yifanlu0227/ChatSim) | LLMs have been adopted for ground truth generation. |
| [**Driving-RAG: Driving Scenarios Embedding, Search, and RAG Applications**](https://arxiv.org/abs/2504.04419) | arXiv | 2025 | - | The LLM performs reasoning, trajectory planning, and explanation by leveraging retrieved similar driving scenarios. |

#### Data Enrichment Through Hazard Analysis
##### Hazard Analysis and Risk Assessment (HARA)
|  Title  |   Venue  |   Date   |   Code   | Summary  |
|:--------|:--------:|:--------:|:--------:|:--------:|
| <br> [**Enhancing Autonomous Driving Safety Analysis with Generative AI: A Comparative Study on Automated Hazard and Risk Assessment**](https://arxiv.org/pdf/2410.23207) <br> | arxiv.org | 2024-11 | - | At Qualcomm, LLMs enable the identification of 20% more hazardous scenarios in an Autonomous Emergency Braking (AEB) case study compared to manual methods. |
| <br> [**Welcome Your New AI Teammate: On Safety Analysis by Leashing Large Language Models**](https://dl.acm.org/doi/pdf/10.1145/3644815.3644953) <br> | IEEE/ACM 3rd International Conference on AI Engineering-Software Engineering for AI | 2024-4 | - | Researchers of Volvo Cars investigated LLMs for generating scenarios and malfunctions from functional descriptions using a general framework without relying on standardized databases. |
| <br> [**Engineering Safety Requirements for Autonomous Driving with Large Language Models**](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=10628478) <br> | 2024 IEEE 32nd International Requirements Engineering Conference (RE) | 2024 | - | LLMs are applied to generate safety requirements and detect inconsistencies, which enhances efficiency in safety engineering while highlighting the need for expert validate to ensure accuracy. |

##### Systems Theoretic Process Analysis (STPA)
|  Title  |   Venue  |   Date   |   Code   | Summary  |
|:--------|:--------:|:--------:|:--------:|:--------:|
| <br> [**Hazard analysis in the era of AI: Assessing the usefulness of ChatGPT4 in STPA hazard analysis**](https://www.sciencedirect.com/science/article/pii/S092575352400198X) <br> | Safety Science | 2024 | - | Charalampidou et al. used ChatGPT-4 to generate loss scenarios for a unmanned aerial vehicle rescue system, yet noting the need for human validation.  |
| <br> [**Can Large Language Models Assist in Hazard Analysis?**](https://link.springer.com/chapter/10.1007/978-3-031-40953-0_35) <br> | International Conference on Computer Safety, Reliability, and Security | 2023 | - | Diemert et al. introduce a cooperative framework where LLMs assist hazard identification, though expert oversight is required due to inaccuracies. |
| <br> [**Safety analysis in the era of large language models: a case study of stpa using chatgpt**](https://www.sciencedirect.com/science/article/pii/S2666827025000052) <br> | Machine Learning with Applications | 2025 | - | Qi et al. extended this to automotive and energy systems, assessing human-LLM collaboration schemes. |
#### Data Labeling
|  Title  |   Venue  |   Date   |   Code   | Summary  |
|:--------|:--------:|:--------:|:--------:|:--------:|
| <br> [**Automated evaluation of large vision-language models on self-driving corner cases**](https://ieeexplore.ieee.org/abstract/document/10943406) <br> | 2025 IEEE/CVF Winter Conference on Applications of Computer Vision (WACV) | 2025-4 | - | Introduced the first benchmark for evaluating Large Vision-Language Models (LVLM) in the context of self-driving corner cases |
| <br> [**Synthetic datasets for autonomous driving: A survey**](https://ieeexplore.ieee.org/abstract/document/10313052) <br> |  IEEE Transactions on Intelligent Vehicles | 2023-11 | - | Manually annotate data is both costly and labor-intensive, thereby necessitating automated solutions to enhance the scalability and efficiency of dataset development |
#### Data Retrieval
|  Title  |   Venue  |   Date   |   Code   | Summary  |
|:--------|:--------:|:--------:|:--------:|:--------:|
| <br> [**A multi-model approach for video data retrieval in autonomous vehicle development**](https://link.springer.com/chapter/10.1007/978-3-031-78392-0_3) <br> | PROFES 2024 | 2024-11 | - | Video retrieve efficiency has been improved through the application of LLMs. |
| <br> [**Towards scenario retrieval of real driving data with large vision-language models**](https://pdfs.semanticscholar.org/8efb/fbb034bc406d5e17ff763f9e00ab2925f5a1.pdf) <br> | 10th International Conference on Vehicle Technology and Intelligent Transport Systems (VEHITS 2024) | 2024 | - | Three LVLMs (CLIP, BLIP-2, and BakLLaVA) were employed to perform image retrieve based on natural language queries. |
| <br> [**Unveiling objects with sola: An annotation-free image search on the object level for automotive data sets**](https://ieeexplore.ieee.org/abstract/document/10588869) <br> | 2024 IEEE Intelligent Vehicles Symposium (IV) | 2024-7 | - | Proposed an annotation-free, object-level image retrieval approach for AD datasets by combining panoptic segmentation with CLIP to support natural language queries. |
| <br> [**Bev-tsr: Text-scene retrieval in bev space for autonomous driving**](https://ojs.aaai.org/index.php/AAAI/article/download/32782/34937) <br> | AAAI Conference 2025 | 2025 | - | Incorporate LLMs and Bird’s Eye View (BEV) representations to enhance text-to-scene retrieval. |


### 3.2 Scenario Generation
#### LLM as an Human-Machine Interface
##### Structured representation
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| <br> [**chatsumo: Large language model for automating traffic scenario generation in simulation of urban mobility**](https://ieeexplore.ieee.org/abstract/document/10770822) | IEEE Transactions on Intelligent Vehicles | 2024-11 | – | LLMs have been utilized to interpret user input into structured scenario representations. |
| [**Controllable traffic simulation through llm-guided hierarchical chain-of-thought reasoning**](https://arxiv.org/abs/2409.15135) | arxiv.org | 2024-9 | – | Proposes a diffusion-based and LLM-enhanced traffic simulation framework with chain-of-thought reasoning and a Frenet-frame-based cost function. |
| [**Chat2scenario: Scenario extraction from dataset through utilization of large language model**](https://ieeexplore.ieee.org/abstract/document/10588843) | 2024 IEEE IV Symposium | 2024-6 | [GitHub](https://github.com/ftgTUGraz/Chat2Scenario) | Triggers Python script for automated file generation. |
| [**Benchmarking Large Language Models for Motorway Driving Scenario Understanding**](https://www.sae.org/publications/technical-papers/content/2025-01-7146/) | SAE International | 2025-1 | – | Evaluates six LLMs in interpreting motorway functional scenarios. |
| [**Language Conditioned Traffic Generation**](https://arxiv.org/abs/2307.07947) | SAE International | 2025-1 | [Project](https://ariostgx.github.io/lctgen/) | Uses structured representations and transformers to generate vehicle trajectories. |
| [**Text2Scenario: Text-Driven Scenario Generation for Autonomous Driving Test**](https://arxiv.org/abs/2503.02911) | arxiv.org | 2025-3 | [Demo](https://caixxuan.github.io/Text2Scenario.GitHub.io/) | Converts natural language into scenario elements and simulation files. |
| [**SceneDiffuser: Efficient and Controllable Driving Simulation Initialization and Rollout**](https://proceedings.neurips.cc/paper_files/paper/2024/hash/64ff8d0bf0b0fe2b872a42a0de9668f8-Abstract-Conference.html) | NeurIPS 2024 | 2024 | – | Unified diffusion-based framework with Proto constraints and language-driven control. |

##### Loss function and executable code
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**Language-Guided Traffic Simulation via Scene-Level Diffusion**](https://proceedings.mlr.press/v229/zhong23a.html) | 7th conference on robot learning | 2023-12 | – | In this paper, a loss function is derived from user-provided descriptions and integrated into a diffusion model to facilitate executable file generation. |
| [**Language-Driven Interactive Traffic Trajectory Generation**](https://proceedings.neurips.cc/paper_files/paper/2024/hash/8e63972d4d9d81b31459d787466ce271-Abstract-Conference.html) | NeurIPS 2024 | 2024 | [GitHub](https://github.com/X1a-jk/InteractTraj) | In this paper, the generated code, which includes interaction, vehicle, and map modules, is utilized by a transformer to synthesize vehicle trajectories. |
| [**DriveDreamer-2: LLM-Enhanced World Models for Diverse Driving Video Generation**](https://ojs.aaai.org/index.php/AAAI/article/view/33130) | AAAI Press | 2025-4 | [Project](https://drivedreamer2.github.io) | In this paper, code is applied to call functional libraries for producing vehicle trajectory data. |
| [**Text-to-Drive: Diverse Driving Behavior Synthesis via Large Language Models**](https://ieeexplore.ieee.org/abstract/document/10801754) |  2024 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS) | 2024-10 | [Project](https://text-to-drive.github.io/) | Nguyen et al. employ LLM to parse user language into driving behavior code, which is then used to guide reinforcement learning for generating diverse synthetic driving scenarios. |
#### LLM as an Data Interpreter
##### Accident reports And Domain knowledge
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**SoVAR: Build Generalizable Scenarios from Accident Reports for Autonomous Driving Testing**](https://dl.acm.org/doi/abs/10.1145/3691620.3695037) | 39th IEEE/ACM International Conference  | 2024-10 | – | In the study by Guo et al, a framework is proposed in which textual accident reports are parsed into a structured JSON2 format, which is subse-quently processed by a constraint solver to generate waypoints. |
| [**Domain Knowledge Distillation from Large Language Model: An Empirical Study in the Autonomous Driving Domain**](https://ieeexplore.ieee.org/abstract/document/10422308) | 2023 ITSC | 2024-2 | - | Tang et al. introduce a method in which technical documents are interpreted and transformed into structured ontological elements, enabling automated ontology construction. |
| [**CrashAgent: Crash Scenario Generation via Multi-modal Reasoning**](https://arxiv.org/pdf/2505.18341#page=1.92) | arxiv | 2025-5 | - | The paper presents CrashAgent, a framework that leverages multi-modal large language models to convert real-world crash reports into realistic, simulation-ready safety-critical driving scenarios. |
##### Naturalistic driving data
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**LLM-attacker: Enhancing Closed-loop Adversarial Scenario Generation for Autonomous Driving with Large Language Models**](https://arxiv.org/abs/2501.15850) | arxiv.org | 2025-1 | [Video](https://drive.google.com/file/d/1Zv4V3iG7825oyiKbUwS2Y-rR0DQIE1ZA/view?pli=1) | Mei et al. employ LLMs to identify the most threatening attacker in each scene from the Waymo Open Dataset[Cite](https://openaccess.thecvf.com/content/ICCV2021/html/Ettinger_Large_Scale_Interactive_Motion_Forecasting_for_Autonomous_Driving_The_Waymo_ICCV_2021_paper.html), enabling the creation of high-risk scenarios for improving the testing and training of autonomous driving systems |
| [**ChatBEV: A Visual Language Model that Understands BEV Maps**](https://arxiv.org/abs/2503.13938) | arxiv.org | 2025-3 | [GitHub](https://github.com/xuqingyao/ChatBEV) | LLMs are applied to interpret BEV maps derived from the nuPlan dataset[Cite](https://arxiv.org/abs/2106.11810), with the extracted spatial information subsequently used to guide a diffusion model for trajectory generation. |
| [**Enhancing Autonomous Vehicle Training with Language Model Integration and Critical Scenario Generation**](https://arxiv.org/abs/2404.08570) | arxiv.org | 2024-4 | [GitHub](https://github.com/zachtian/CRITICAL) |  Tian et al. integrate reinforcement learning and LLMs to optimize safety-critical driving scenarios in the HighwayEnv[GitHub](https://github.com/Farama-Foundation/HighwayEnv) simulation environment. |
| [**From Words to Collisions: LLM-Guided Evaluation and Adversarial Generation of Safety-Critical Driving Scenarios**](https://arxiv.org/pdf/2502.02145) | arxiv.org | 2025-5 | [GitHub](https://github.com/TUM-AVS/From-Words-to-Collisions) |  This paper evaluates and generates safety-critical driving scenarios by converting structured simulation data into natural language, enabling LLMs to assess collision risk and adversarially modify vehicle trajectories to synthesize risky scenarios. |
#### LLM as an Intermediate Format Generator
##### Driving policies
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**HumanSim: Human-Like Multi-Agent Novel Driving Simulation for Corner Case Generation**](https://openreview.net/forum?id=lVMKJxsIdC) | ECCV 2024 W-CODA Workshop | 2024-8 | [Project](https://humansim.github.io/) | User prompts are combined with environmental context and processed to derive driving strategies, which are subsequently used to inform a driver model. |
| [**Promptable Closed-loop Traffic Simulation**](https://arxiv.org/abs/2409.05863) | arxiv.org | 2024-9 | [Project](https://ariostgx.github.io/ProSim/) | User prompts are combined with environmental context and processed to derive driving strategies, which are subsequently used to inform an auto-regressive trajectory generation model. |
| [**ChatDyn: Language-Driven Multi-Actor Dynamics Generation in Street Scenes**](https://arxiv.org/abs/2412.08685) | arxiv.org | 2024-12 | [Project](https://vfishc.github.io/chatdyn/) |  Wei et al. demonstrate the use of LLMs to interpret linguistic descriptions for trajectory planning, thereby guiding behavior of autonomous agents. |
##### Scenario elements
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**DriveGen: Towards Infinite Diverse Traffic Scenarios with Large Models**](https://arxiv.org/abs/2503.05808) | arxiv.org | 2025-3 | - | An approach is presented in which maps and vehicle assets are generated from textual de-scriptions. Waypoints are selected using a VLM, followed by trajectory generation using a diffusion model. |
| [**LLMScenario: Large Language Model Driven Scenario Generation**](https://ieeexplore.ieee.org/abstract/document/10529537) | IEEE Transactions on Systems | 2024-5 | - | Critical corner cases are produced by integrating user language inputs, failure records, and scenario databases content. |
| [**Exploring Critical Testing Scenarios for Decision-Making Policies: An LLM Approach**](https://arxiv.org/abs/2412.06684) | arxiv.org | 2024-12 | - | A methodology is further extended in this paper, where scenario mutation, prior test feedback, and expert knowledge are incorporated to enhance scenario diversit. |
| [**ChatGPT-Based Scenario Engineer: A New Framework on Scenario Generation for Trajectory Prediction**](https://ieeexplore.ieee.org/abstract/document/10423819) |  IEEE Transactions on Intelligent Vehicles  | 2024-2 | - |  Descriptive inputs and datasets are processed to generate scenario configurations and associated parameter sets. |
##### Functional & Abstract & Logical scenario
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**When language and vision meet road safety: leveraging multimodal large language models for video-based traffic accident analysis**](https://arxiv.org/abs/2501.10604) | arxiv.org | 2025-1 | [GitHub](https://github.com/ai4ce/SeeUnsafe) | A MLLM is applied to analyze accident videos, generate narrative descriptions, and identify relevant objects, thereby enabling the transformation of raw video content into functional scenario representations. |
| [**TARGET: Automated Scenario Generation from Traffic Rules for Testing Autonomous Vehicles via Validated LLM-Guided Knowledge Extraction**](https://arxiv.org/abs/2305.06018) | arxiv.org | 2025-5 | - | Traffic regulations are parsed to produce abstract scenarios with defined syntax, which are subsequently converted into executable scripts through code generation. |
| [**Legend: A top-down approach to scenario generation of autonomous driving systems assisted by large language models**](https://dl.acm.org/doi/abs/10.1145/3691620.3695520) | 39th IEEE/ACM International Conference | 2024-10 | - | Accident reports are interpreted to extract logical scenarios, which are then instantiated as concrete scenarios using a search-based algorithm. |
#### LLM as an Standard Format Generator
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**A New Approach to AD/ADAS Test Scenario Generation Using Open-Source Intelligence and Large Language Models**](https://gupea.ub.gu.se/handle/2077/84479) | Bachelor’s thesis, University of Gothenburg and Chalmers University of Technology | 2024 | - | In the study by Zorin et al, accident data related to ADSs are collected from online sources and converted into key textual descriptions using Python scripts. LLMs are then utilized in conjunction with predefined templates to produce scenario files compliant with the ASAM OpenSCENARIO standard |
| [**LMM-enhanced Safety-Critical Scenario Generation for Autonomous Driving System Testing From Non-Accident Traffic Videos**](https://arxiv.org/abs/2406.10857) | arxiv.org | 2024-6 | - |  Tian et al. employ Large Multimodal Models (LMMs) to generate safety-critical scenarios from non-accident traffic videos. Optical flow data and Chain-of-Thought (CoT) reasoning are used to construct abstract representations, which are subsequently transformed into executable programs. |
#### LLM as an Executable Scenario Generator
##### Template Filling
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**A Generative AI-driven Application: Use of Large Language Models for Traffic Scenario Generation**](https://ieeexplore.ieee.org/abstract/document/10415934) | 2023 14th International Conference on Electrical and Electronics Engineering (ELECO) | 2024-2 | - | This work propose a method for generating SUMO scenario based on predefined templates. Structured prompts are designed to guide GPT-4 in producing XML files according to user-defined variables, such as the number of intersections and road segment lengths. |
##### End-to-End Generation
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**A Preliminary Attempt of Deploying AIGC in Autodriving Scenario Generation: Via LLM**](https://dl.acm.org/doi/abs/10.1145/3660395.3660411) | AIBDF 2023 | 2024-6 | - | End-to-end generation was first explored by Wang et al., who prompt general-purpose LLMs to generate XOSC files. |
| [**Dialogue-based generation of self-driving simulation scenarios using Large Language Models**](https://arxiv.org/abs/2310.17372) | arxiv.org | 2023-10 | - | To improve controllability, Miceli Barone et al. propose a dialogue-based system in which SCENIC programs are incrementally constructed through iterative user interactions. |
| [**From Dashcam Videos to Driving Simulations: Stress Testing Automated Vehicles against Rare Events**](https://arxiv.org/abs/2411.16027) | arxiv.org | 2024-11 | - | Miao et al. introduce ScriptGPT, which enables the translation of dashcam videos into SCENIC scripts using prompt-engineered video-language models. |
| [**ScenicNL: Generating Probabilistic Scenario Programs from Natural Language**](https://arxiv.org/abs/2405.03709) | arxiv.org | 2024-5 | - | To address the issue of structural correctness, Elmaaroufi et al. combine compositional prompting with compiler feedback to generate probabilistic scenarios from crash reports. |
##### Hybrid Generation
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**A New Approach to AD/ADAS Test Scenario Generation Using Open-Source Intelligence and Large Language Models**](https://gupea.ub.gu.se/handle/2077/84479) | Bachelor’s thesis, University of Gothenburg and Chalmers University of Technology | 2024-12 | - | Zorin et al. integrate real-world traffic incident data scraped from websites with LLM-based scenario completion methods to bridge open-source intelligence and executable simulation file generation. |
| [**Natural-language-driven Simulation Benchmark and Copilot for Efficient Production of Object Interactions in Virtual Road Scenes**](https://arxiv.org/abs/2312.04008) | arxiv.org | 2023-12 | - | Yang et al. introduce SimCopilot, which translates natural language descriptions of object interactions into simulation-ready codes using a language-to-interaction dataset, thereby balancing high-level abstraction with detailed execution. |
| [**Multimodal Large Language Model Driven Scenario Testing for Autonomous Vehicles**](https://arxiv.org/abs/2409.06450) | arxiv.org | 2024-9 | - | Lu et al. propose OmniTester, which incorporate prompt engineering, Retrieval-Augmented Generation (RAG), and external simulation tools (e.g., SUMO, CARLA) to improve the realism, diversity, and controllability of generated scenarios. |
| [**Realistic Corner Case Generation for Autonomous Vehicles with Multimodal Large Language Models**](https://arxiv.org/abs/2412.00243) | arxiv.org | 2024-12 | - | Lu et al. propose  AutoScenario, which incorporate prompt engineering, Retrieval-Augmented Generation (RAG), and external simulation tools (e.g., SUMO, CARLA) to improve the realism, diversity, and controllability of generated scenarios. |
| [**ChatScene: Knowledge-Enabled Safety-Critical Scenario Generation for Autonomous Vehicles**](https://openaccess.thecvf.com/content/CVPR2024/html/Zhang_ChatScene_Knowledge-Enabled_Safety-Critical_Scenario_Generation_for_Autonomous_Vehicles_CVPR_2024_paper.html) | CVPR 2024 | 2024 | [GitHub](https://github.com/javyduck/ChatScene) | Zhang et al. propose ChatScene, which decomposes textual inputs into subcomponents and retrieves relevant domain-specific code snippets to generate safety-critical scenarios |
| [**LMM-enhanced Safety-Critical Scenario Generation for Autonomous Driving System Testing From Non-Accident Traffic Videos**](https://arxiv.org/abs/2406.10857) | arxiv.org | 2024-6 | [GitHub](https://github.com/javyduck/ChatScene) | Expanding upon multimodal capabilities, Tian et al. applied Large Multimodal Models (LMMs) and road-agent retrieval mechanisms to construct semantically coherent and highly customized traffic scenes. |
| [**Traffic Scene Generation from Natural Language Description for Autonomous Vehicles with Large Language Model**](https://arxiv.org/abs/2409.09575) | arxiv.org | 2024-9 | [Project](https://basiclab.github.io/TTSG/) | Expanding upon multimodal capabilities, Ruan et al. applied Large Multimodal Models (LMMs) and road-agent retrieval mechanisms to construct semantically coherent and highly customized traffic scenes. |

### 3.3 Scenario Selection
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**Reality Bites: Assessing the Realism of Driving Scenarios with Large Language Models**](https://dl.acm.org/doi/abs/10.1145/3650105.3652296) | FORGE 2024 | 2024-4 | - | LLMs are employed to evaluate the consistency of driving trajectory with real-world conditions. This is achieved by using perturbed variants of the DeepScenario dataset [Cite](https://ieeexplore.ieee.org/abstract/document/10174023) and introducing a robustness score derived from standardized prompts. |
| [**DriveGenVLM: Real-world Video Generation for Vision Language Model based Autonomous Driving**](https://ieeexplore.ieee.org/abstract/document/10786438) | 2024 IEEE International Automated Vehicle Validation Conference (IAVVC) | 2024-10 | - |  Fu et al. utilize a diffusion model in combination with a VLM to generate, narrate, and interpret realistic driving videos. The realism of the outputs is verified to enhance scene understanding. Training on the Waymo Open Dataset [Cite](https://openaccess.thecvf.com/content_CVPR_2020/html/Sun_Scalability_in_Perception_for_Autonomous_Driving_Waymo_Open_Dataset_CVPR_2020_paper.html) demonstrated the effectiveness of this approach in advancing VLM applications in AD. |
| [**From Failures to Fixes: LLM-Driven Scenario Repair for Self-Evolving Autonomous Driving**](https://arxiv.org/pdf/2505.22067) | arxiv | 2025-05 | - |  The paper proposes SERA, a framework that uses LLMs to identify, retrieve, and repair failure scenarios, enabling autonomous driving systems to self-evolve and improve robustness. |

### 3.4 Test Execution
##### Anomaly Detection
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**Semantic anomaly detection with large language models**](https://link.springer.com/article/10.1007/s10514-023-10132-6) | Autonomous Robots | 2023-10 | [Project](https://sites.google.com/view/llm-anomaly-detection) | Elhafsi et al. apply OWL-ViT [Cite](https://link.springer.com/chapter/10.1007/978-3-031-20080-9_42) for visual feature extraction and GPT-3.5 for reasoning to detect anomalies in ADSs within the CARLA simulation environment. Their approach outperforms traditional Out-Of-Distribution (OOD) detection methods while offering interpretable analysis, although limitations remain due to the reliability of object detection and LLM inference. |
##### Simulation Setup Automation
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**ChatSUMO: Large Language Model for Automating Traffic Scenario Generation in Simulation of Urban MObility**](https://ieeexplore.ieee.org/abstract/document/10770822) | IEEE Transactions on Intelligent Vehicles | 2024-11 | - | LLMs are employed to modify traffic environments, generate traffic scenarios, and configure simulation files for platforms SUMO. The approache support real-time adjustments, enhance scenario diversity, and enable end-to-end automation without the need for manual intervention. |
| [**Generating Traffic Scenarios via In-Context Learning to Learn Better Motion Planner**](https://ojs.aaai.org/index.php/AAAI/article/view/33593) | Thirty-Ninth AAAI Conference on Artificial Intelligence | 2025-4 | - | LLMs are employed to modify traffic environments, generate traffic scenarios, and configure simulation files for platforms CARLA. The approache support real-time adjustments, enhance scenario diversity, and enable end-to-end automation without the need for manual intervention. |
| [**Realistic Corner Case Generation for Autonomous Vehicles with Multimodal Large Language Model**](https://arxiv.org/abs/2412.00243) | arxiv.org | 2024-12 | - | LLMs are employed to modify traffic environments, generate traffic scenarios, and configure simulation files for platforms CARLA. These approaches support real-time adjustments, enhance scenario diversity, and enable end-to-end automation without the need for manual intervention. |
| [**Natural-language-driven Simulation Benchmark and Copilot for Efficient Production of Object Interactions in Virtual Road Scenes**](https://arxiv.org/abs/2312.04008) | arxiv.org | 2023-12 | - | Yang et al. construct virtual traffic scenes in the LGSVL simulator based on natural language descriptions, introducing a language-to-interaction dataset introduced to support benchmarking and further development in simulation setup automation. |
##### Scenario Optimization
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**Multimodal Large Language Model Driven Scenario Testing for Autonomous Vehicles**](https://arxiv.org/abs/2409.06450) | arxiv.org | 2024-9 | - | Lu et al. utilize a LLM integrated with a RAG module to iteratively validate and refine scenarios based on simulation feedback from CARLA and SUMO. |
| [**Dialogue-based generation of self-driving simulation scenarios using Large Language Models**](https://arxiv.org/abs/2310.17372) | arxiv.org | 2023-10 | - | An LLM is used to automatically correct and update SCENIC code in response to both simulation results and user feedback, until successful execution is achieved in CARLA. |
| [**A Generative AI-driven Application: Use of Large Language Models for Traffic Scenario Generation**](https://ieeexplore.ieee.org/abstract/document/10415934) |  2023 14th International Conference on Electrical and Electronics Engineering (ELECO) | 2024-2 | - | GPT-4 is applied to parse error messages generated by SUMO and to modify the simulation files accordingly. |
| [**On Simulation-Guided LLM-based Code Generation for Safe Autonomous Driving Software**](https://arxiv.org/abs/2504.02141) | arxiv.org | 2025-4 | - | An LLM is leveraged to generate and iteratively refine control code from natural language descriptions based on simulation feedback in Esmini [Cite](https://github.com/esmini/esmini), thereby forming a closed-loop workflow integrating code generation, simulation, and correction. |
| [**From Dashcam Videos to Driving Simulations: Stress Testing Automated Vehicles against Rare Events**](https://arxiv.org/abs/2411.16027) | arxiv.org | 2024-11 | - | To refine scenario fidelity during execution, Miao et al. utilize LLM to perform similarity analysis between simulated scenarios and dashcam crash video. |
##### Hazard Prediction
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**INSIGHT: Enhancing Autonomous Driving Safety through Vision-Language Models on Context-Aware Hazard Detection and Edge Case Evaluation**](https://arxiv.org/pdf/2502.00262) | arxiv.org | 2025-02 | - | This work proposes INSIGHT, a vision-language model framework that localizes and explains potential hazards in autonomous driving scenes to enhance edge-case safety during test execution. |



### 3.5 ADS Assessment
##### Safety performance evaluation
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**ChatSUMO: Large Language Model for Automating Traffic Scenario Generation in Simulation of Urban MObility**](https://ieeexplore.ieee.org/abstract/document/10770822) | IEEE Transactions on Intelligent Vehicles | 2024-11 | - | A LLM is used to interpret SUMO output files, extract relevant metrics such as traffic density, travel time, and emissions, and synthesizes analytical summaries to support efficient evaluation and comparison of simulation outcomes. |
| [**What to Explain and How? The Challenges and Future of Using Large Language Models to Generate Explanations for Lawyers in Autonomous Car Accidents**](https://ceur-ws.org/Vol-3803/paper7.pdf) | ECAI’24: Workshop on Multimodal, Affective, and Interactive Explainable AI (MAI-XAI) | 2024-10 | - | Xu et al. explore the potential of LLMs to generate legal explanations for ADS-related accident cases. The limitations of the models are evaluated, and improvements are proposed through domain-specific adaption and enhanced contextual reasoning. |
| [**Collision Scenario Analysis for Autonomous Vehicles Using Multimodal Deep Learning Models**](https://www.researchgate.net/profile/Jerry-Gao/publication/389628278_Collision_Scenario_Analysis_for_Autonomous_Vehicles_Using_Multimodal_Deep_Learning_Models/links/67ca1a17cc055043ce6eb04e/Collision-Scenario-Analysis-for-Autonomous-Vehicles-Using-Multimodal-Deep-Learning-Models.pdf) | 2025 IEEE International Conference on Artifical Intelligence | 2025-03 | - | This paper presents a multimodal framework that combines deep learning and LLaMA 3 to analyze autonomous vehicle collisions. It extracts environmental features from dashcam videos and uses language models to infer causes and impacts, achieving high accuracy and offering deeper safety insights. |
##### Intelligence level evaluation
| Title | Venue | Date | Code | Summary |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**A Comprehensive LLM-powered Framework for Driving Intelligence Evaluation**](https://arxiv.org/abs/2503.05164) | arxiv.org | 2025-3 | - | You et al. [42] employ LLMs to perform hierarchical assessments by using CoT prompting combined with RAG. The models simulate human-like reasoning across multiple decision-making levels, and their outputs are validated through CARLA simulations and human evaluators. |

## License
This work is licensed under the Creative Commons Attribution-NonCommercial 4.0 International License. To view a copy of this license, visit http://creativecommons.org/licenses/by-nc/4.0/





