---
title: Machine Learning for Code and Documentation
summary: This research project at McGill University under the supervision of Dr. Jin Guo in the McGill Software Technology Lab seeks to critically assess the current capabilities and limitations of ML-based documentation generation tools. By focusing on the generation of pertinent and high-quality information, the project aims to enhance the utility of these tools for developers, ultimately leading to more efficient and effective software engineering practices. The success of this project could lead to more context-aware machine learning solutions that align closely with the nuanced needs of software engineers.

tags:
  - Software Engineering
  - Machine Learning
  - Learning and Adaptive Systems
  - Code Generation
date: '2023-08-15T00:00:00Z'

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: The diagram of Code and Documentation Generation
  focal_point: Smart

links:
#   - icon: twitter
#     icon_pack: fab
#     name: Follow
#     url: https://twitter.com/kwokhinchi
# url_code: ''
# url_pdf: 'https://drive.google.com/file/d/1yjm-Rq3Yvg7UHue-tSGtJNZRNZPrOeuX/view?usp=drive_link'
url_slides: 'https://docs.google.com/presentation/d/1OBVJ07WXGzge9d-UZCD76Cx5bwoX6Va_/edit?usp=drive_link&ouid=102358073185606588058&rtpof=true&sd=true'
# url_video: ''

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
# slides: example
---

<!-- Nowadays, with the advancement of production technologies, the manufacturing paradigm has gradually shifted from mass production to a small-batch and high-variety personalized production manner, urged by high flexible automation capabilities. In this paradigm, the existing inspection and assembly processes after manufacturing still rely to a large extent on either human operators with low efficiency or machines with low flexibility. To solve this issue, human-robot collaboration (HRC) has been a prevailing topic of recent concerns. Current robot control strategies in human-machine collaboration are mainly through pre-defined programming and do not yet meet the need for flexible and adaptable tasks in individualised production. To address this challenge, this paper proposes a deep reinforcement learning (DRL) approach based on metalearning to drive robots in HRC. It enables collaborative robots (cobots) to acquire basic skills and perform tasks based on personalised production requirements, improving learning efficiency and thus quickly adapting to new tasks for human operators. The robot control task was carried out in a simulated environment taken from a real production scenario to assess its efficacy. Experimental results show that our proposed method enables the robot to learn and perform HRC tasks quickly and outperforms the baseline DRL method in terms of success rate. -->


Machine learning techniques have been proposed to support a variety of software engineering tasks, such as code search, documentation generation, code migration, etc. While advances have been observed using publicly available datasets and common metrics, the impact of those techniques in practice is unclear. The context of tasks can be vastly different depending on the project phases, the expertise of the developers, and the objective of the tasks. Therefore, machine learning techniques need to consider the context of the tasks to make meaningful breakthroughs for supporting software engineers. The documentation task, in particular, concerns the generation of documentation given the source code. When the developers are writing high-quality documentation, they seldomly just repeat the source code. Instead, they record the usage of the code or the rationale of why the code is written in a certain way. Such information is critical to support the users to appropriately adapt their APls and enable the code maintainers to understand the code and respect the constraints. In this project, we aim to understand the limitations of the existing machine learning based documentation generation techniques. We investigate how they can support the users to create information that is both relevant and high quality.

Through this internship, we are more familiar with basic natural language processing (summarization) techniques and basic understanding of empirical methods. We are able to collect data from real software engineering projects and evaluate model performance within a software engineering task context. 