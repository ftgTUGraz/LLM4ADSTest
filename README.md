# The application of large language model on scenario-based testing of automated driving systems: a survey

![GitHub stars](https://img.shields.io/github/stars/ftgTUGraz/LLM4ADSTest?color=yellow)
![GitHub forks](https://img.shields.io/github/forks/ftgTUGraz/LLM4ADSTest?color=9cf)
[![GitHub license](https://img.shields.io/github/license/ftgTUGraz/LLM4ADSTest)](https://github.com/ftgTUGraz/LLM4ADSTest/blob/main/LICENSE)


This is a collection of research papers about the application of Large Language Model (LLM) on scenario-based testing of automated driving systems. This survey not only reviews how LLMs are applied in scenario-based testing (e.g., phases, models, and strategies), but also investigates critical challenges (e.g., safety risks) and practical considerations (e.g., integration with industry-standard tools) to provide a holistic view of their real-world. Maintained by zhaoyongqi2022 and dongbi0719.



## Table of Contents 
- [Overview of LLM4ADSTest](#overview-of-llm4adstest)
  - [Survey of LLM](#survey-of-llm)
  - [Survey of LLM Application](#survey-of-llm-application)
  - [Survey of LLM for AD](#survey-of-llm-for-ad)
  - [Survey of Scenario Generation](#survey-of-scenario-generation)
  - [Survey of V&V](#survey-of-vv)
- [LLM APPLICATION PHASE](#llm-application-phase)
- [LLM CONDUCTED TASK](#llm-conducted-task)
  - [Scenario Source](#scenario-source)
  - [Scenario Generation](#scenario-generation)
  - [Scenario Selection](#scenario-selection)
  - [Test Execution](#test-execution)
  - [ADS Assessment](#ads-assessment)
- [Citation](#citation)
- [License](#license)


## 1. Overview of LLM4ADSTest

### Survey of LLM
- [A survey on large language models: Applications, challenges, limitations, and practical usage](https://techrxiv.figshare.com/articles/preprint/A_Survey_on_Large_Language_Models_Applications_Challenges_Limitations_and_Practical_Usage/23589741/1/files/41501037.pdf)
  - Authors: Hadi, Muhammad Usman and Qureshi, Rizwan and Shah, Abbas and Irfan, Muhammad and Zafar, Anas and Shaikh, Muhammad Bilal and Akhtar, Naveed and Wu, Jia and Mirjalili, Seyedali and others.(2023)
  - Key words: Large Language Models, Generative AI, Conversational AI, Co-pilots, Natural language processing, GPT, ChatGPT, Bing, Bard, AI-enabled Tools, AI chatbots.
  - Summary: Hadi et al. offers a comprehensive overview of LLMs, covering their history, architecture, train-ing methods, applications, challenges, and future directions to support their development and real-world deployment.
  - Source: [multi-modality, synthetic data generation, auto-annotation, driving, LLM applications](https://github.com/anas-zafar/LLM-Survey)

- [Tasks People Prompt: A Taxonomy of LLM Downstream Tasks in Software Verification and Falsification Approaches](https://arxiv.org/abs/2404.09384)
  - Authors: V´ıctor A. Braberman, Bonomo-Braberman, Flavia and Charalambous, Yiannis and Colonna, Juan G. and Cordeiro, Lucas C. and de Freitas, Rosiane.(2024)
  - Key words: Downstream Task, LLM4SE, Large Language Models, Prompt Engineering, Software Engineering, Software Verification, Software Testing, Taxonomy
  - Summary: Braberman et al. systematically review how LLM are utilized in software testing and verification by analyzing over 100 studies, proposing a taxonomy of downstream tasks to reveal patterns and guide future research.
 
- [Large models for intelligent transportation systems and autonomous vehicles: A survey](https://www.sciencedirect.com/science/article/pii/S1474034624004348)
  - Authors: Lu Gan, Wenbo Chu, Guofa Li, Xiaolin Tang, Keqiang Li.(2024)
  - Key words: ntelligent transportation systems, Autonomous vehicles, Survey, Large models, Efficient deployment techniques.
  - Summary: Gan et al. system-atically review the applications, challenges, and deployment techniques of large models in intelligent transportation systems and autonomous vehicles, aiming to guide their efficient and scalable implementation.

- [Delving Into Multi-Modal Multi-Task Foundation Models for Road Scene Understanding: From Learning Paradigm Perspectives](https://ieeexplore.ieee.org/abstract/document/10540321)
  - Authors: Sheng Luo, Wei Chen, Wanxin Tian, Rui Liu, Luanxuan Hou, Xiubao Zhang, Haifeng Shen,Ruiqi Wu, Shuyi Geng, Yi Zhou, Ling Shao, Yi Yang, Bojun Gao, Qun Li and Guobin Wu.(2024)
  - Key words: Foundation Model, Visual Understanding,Multi-modal Learning, Multi-task Learning, Road Scene.
  - Summary: Luo et al. analyze multi-modal multi-task visual understanding foundation models (MM-VUFMs) for road scenes, highlighting their capabilities, learning paradigms, challenges, and future trends, while offering an open-source repository to support ongoing research.
  - Source: https://github.com/rolsheng/MM-VUFM4DS

- [Leveraging generative ai for urban digital twins: a scoping review on the autonomous generation of urban data, scenarios, designs, and 3d city models for smart city advancement](https://link.springer.com/article/10.1007/s44212-024-00060-w)
  - Authors: Haowen Xu, Femi Omitaomu, Soheil Sabri, Sisi Zlatanova, Xiao Li4 and Yongze Song.(2024)
  - Key words: Generative artifcial intelligence, Smart city, Urban digital twin, 3D city modeling, Urban planning, Deep learning.
  - Summary: Xu et al. explore the integration of generative AI models with urban digital twins to enhance the intelligent, scalable, and automated planning and management of smart cities, focusing on key urban subsystems such as transportation, energy, water, and infrastructure. 

- [Chatgpt is on the horizon: Could a large language model be suitable for intelligent traffic safety research and applications?](https://arxiv.org/abs/2303.05382)
  - Authors: Ou Zheng, Mohamed Abdel-Aty, Dongdong Wang, Zijin Wang, and Shengxuan Ding.(2023)
  - Key words: Intelligent Traffic Safety, Large Language Models, Computer Vision, Data Automation, Cross-modality Learning.
  - Summary: Zheng et al. explore the transformative potential of ChatGPT and LLMs in intelligent traffic safety systems, demonstrating their applications, addressing deployment challenges, and proposing multi-modal learning for enhanced decision-making.

- [Large models defining a new era in intelligence testing: A short discussion and exploration](https://ieeexplore.ieee.org/abstract/document/10719620)
  - Authors: Rui Zhou, Jingwei Ge, Jing Yang, Peijun Ye, Yuchen Li, and Levente Kovács.(2024)
  - Key words: —Intelligent system, intelligence testing, funda-mental intelligence, scenario engineering.
  - Summary: Zhou et al. provide a concise overview of the rapid progress in intelligent system testing empowered by large models, focusing on key components such as the Testing Operating System, Testing Foundational Intelligence, and Testing Scenario Engineering, along with their associated challenges. 

- [Aligning multimodal llm with human preference: A survey](https://arxiv.org/abs/2503.14504)
  - Authors: Tao Yu, Yi-Fan Zhang, Chaoyou Fu, Junkang Wu, Jinda Lu, Kun Wang, Xingyu Lu, Yunhang Shen, Guibin Zhang, Dingjie Song, Yibo Yan, Tianlong Xu, Qingsong Wen, Zhang Zhang, Yan Huang, Liang Wang, Tieniu Tan.(2025)
  - Key words: Multimodal Large Language Model, MLLM Alignment, Alignment with Human Preference. 
  - Summary: Yu et al. present a comprehensive review of alignment algorithms for MLLMs, covering their application scenarios, dataset construction, evaluation benchmarks, and future directions to address challenges such as truthfulness, safety, and human preference alignment. 
  - Source: https://github.com/BradyFU/Awesome-Multimodal-Large-Language-Models/tree/Alignment

- [Stop overthinking: A survey on efficient reasoning for large language models](https://arxiv.org/abs/2503.16419)
  - Authors: Yang Sui, Yu-Neng Chuang, Guanchu Wang, Jiamu Zhang, Tianyi Zhang, Jiayi Yuan, Hongyi Liu, Andrew Wen, Shaochen Zhong, Hanjie Chen, Xia Hu.(2025) 
  - Summary: Sui et al. present the first structured survey on efficient reasoning in LLM, categorizing current approaches into model-based, output-based, and prompt-based strategies, and discussing training data, small model capabilities, and evaluation methods to address the "overthinking phenomenon" and enhance real-world applicability. 
  - Source: https://github.com/Eclipsess/Awesome-Efficient-Reasoning-LLMs

- [rivacy preserving prompt engineering: A survey](https://dl.acm.org/doi/full/10.1145/3729219)
  - Authors: Kennedy Edemacu, Xintao Wu(2024)
  - Key words: Pre-trained language models, large language models, prompting, in-context learning
  - Summary: Pre-trained language models (PLMs) have demonstrated significant proficiency in solving a wide range of general natural language processing (NLP) tasks. Researchers have observed a direct correlation between the performance of these models and their sizes. As a result, the sizes of these models have notably expanded in recent years, persuading researchers to adopt the term large language models (LLMs) to characterize the larger-sized PLMs. The size expansion comes with a distinct capability called in-context learning (ICL), which represents a special form of prompting and allows the models to be utilized through the presentation of demonstration examples without modifications to the model parameters. Although interesting, privacy concerns have become a major obstacle in its widespread usage. Multiple studies have examined the privacy risks linked to ICL and prompting in general, and have devised techniques to alleviate these risks. Thus, there is a necessity to organize these mitigation techniques for the benefit of the community. In this survey, we provide a systematic overview of the privacy protection methods employed during ICL and prompting in general. We review, analyze, and compare different methods under this paradigm. Furthermore, we provide a summary of the resources accessible for the development of these frameworks. Finally, we discuss the limitations of these frameworks and offer a detailed examination of the promising areas that necessitate further exploration.

- [A systematic survey of prompt engineering in large language models: Techniques and applications](https://rotmandigital.ca/wp-content/uploads/2024/09/A-Systematic-Survey-of-Prompt-Engineering-in-Large-Language-Models.pdf)
  - Authors: Pranab Sahoo, Ayush Kumar Singh, Sriparna Saha, Vinija Jain, Samrat Monda and Aman Chadha.(2024)
  - Summary: Sahoo et al. provide a systematic overview of approaches used in prompt engineering, covering their methodologies, applications, models used and the datasets associated with each approach. offer a comprehensive survey on prompt engineering, including an evaluation of each methodology and a discussion on AI security, with a focus on vulnerability in prompt engineering.

- [Unleashing the potential of prompt engineering in large language models: a comprehensive review](https://arxiv.org/abs/2310.14735)
  - Authors: Banghao Chen, Zhaofeng Zhang, Nicolas Langren´e, Shengxin Zhu.(2023)
  - Key words: prompt engineering, Large Language Models, AI-generated content, adversarial attacks, evaluation, AI agent, GPT-4, Vision-Language Models.
  - Summary: Chen et al. offer a comprehensive survey on prompt engineering, including an evaluation of each methodology and a discussion on AI security, with a focus on vulnerability in prompt engineering. 

- [Differentially private natural language models: Recent advances and future directions](https://arxiv.org/abs/2301.09112)
  - Authors: Lijie Hu, Ivan Habernal, Lei Shen, Di Wang.(2023)
  - Summary: Hu et al. review the use of differential privacy in natural language models. 

- [Privacy issues in large language models: A survey](https://arxiv.org/abs/2312.06717)
  - Authors: Seth Neel, Peter Chang.(2024)
  - Key words: Large Language Models, Privacy
  - Summary: Neel and Chang present a survey on privacy issues in LLM more broadly.
  - Source: https://github.com/safr-ai-lab/survey-llm


### Survey of LLM Application

这里是关于 LLM 应用的综述。

### Survey of LLM for AD

这里介绍 LLM 在自动驾驶（AD）中的应用。

### Survey of Scenario Generation

有关场景生成的研究综述。

### Survey of V&V

验证与确认（V&V）的相关研究综述。

## 2. LLM APPLICATION PHASE

描述 LLM 在不同阶段的应用。

## 3. LLM CONDUCTED TASK

### 3.1 Scenario Source
#### Data Enrichment
|  Title  |   Venue  |   Date   |   Code   | Summary  |
|:--------|:--------:|:--------:|:--------:|:--------:|
| <br> [**Learning a Bi-Directional Driving Data Generator Via Large Multi-Modal Model Tuning**](https://openreview.net/pdf?id=2UozyR49ZB) <br> | OpenReview | 2024-11 | - | LLMs are applied for both trajectory-conditioned language generation and language-conditioned trajectory synthesis. |
| <br> [**Learning a Bi-Directional Driving Data Generator Via Large Multi-Modal Model Tuning**](https://openreview.net/pdf?id=2UozyR49ZB) <br> | OpenReview | 2024-11 | - | LLMs are applied for both trajectory-conditioned language generation and language-conditioned trajectory synthesis. |

#### Data Labeling
#### Data Retrieval
介绍数据或场景的来源。

### 3.2 Scenario Generation

详细说明如何生成测试场景。

### 3.3 Scenario Selection

如何选择合适的场景进行测试。

### 3.4 Test Execution

测试执行流程说明。  

### 3.5 ADS Assessment

自动驾驶系统的评估方式。

## Citation

如需引用本文档或研究内容，请参考如下格式……

## License

本项目使用 MIT License。


