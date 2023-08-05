---
title: Mutual Cognitive Human-Robot Collaborative Manufacturing System 基於人機互認知的機械人協作製造系統
summary: An Research and Entrepreneurship project aims to improve collaboration between humans and robots in the manufacturing industry through harnessing technologies such as cognitive Artificial Intelligence (AI) and Augmented Reality (AR). The system combines robots' high levels of accuracy, reliability, and repeatability with humans' flexibility and adaptability to optimise productivity for various manufacturing assembly tasks in a shared workspace, made by PolyU’s Research Group of AI for Industrial Digital Servitization (RAIDS).

tags:
  - Human-Centered Automation
  - Intelligent and Flexible Manufacturing
  - Learning and Adaptive Systems
  - Deep Learning
  - Robotics
date: '2022-12-01T00:00:00Z'

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: The diagram of MCHRCMS prototype
  focal_point: Smart

# links:
#   - icon: twitter
#     icon_pack: fab
#     name: Follow
#     url: https://twitter.com/kwokhinchi
# url_code: ''
# url_pdf: ''
url_slides: 'https://docs.google.com/presentation/d/1WOKw3FGCJllrwoo4R4wMfJNYU7Oi4Xtd/edit?usp=sharing&ouid=102358073185606588058&rtpof=true&sd=true'
url_video: 'https://www.youtube.com/watch?v=FHkH03IN4II'

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
# slides: example
---

Human-robot collaborative assembly (HRCA) is a crucial implementation in modern smart factories, enabling seamless communication and cooperation between human operators and robots in a shared workspace. HRCA plays a significant role in achieving personalized production with high efficiency, combining the accuracy and reliability of collaborative robots with the flexibility and adaptability of humans.

However, the increasing popularity of collaborative manufacturing between humans and Cobots has highlighted certain challenges. The application areas and control approaches of Cobots, especially for individualized tasks, are still immature. With the trend of mass customization, there is a lack of automated solutions for detailed product assembly, resulting in manual assembly as the predominant method for complex customized products among SMEs. Cobots lack the ability to adapt to new tasks easily, requiring manual reprogramming by engineers, leading to increased time costs and reduced fluency in human-robot collaboration.

To address the challenges of difficult customized production and insufficient robot flexibility in on-demand manufacturing, a cognitive Cobot control system is proposed to enhance human-robot collaboration. An augmented reality (AR) guided human-robot collaborative manufacturing system is developed for customized products, integrating virtual and realistic task planning, dynamic guidance of visual data, and information sharing through AR. The system provides human-in-the-loop control approaches to better leverage human operators' intelligence. This AR-assisted human-robot collaboration moves towards intelligent manufacturing, leveraging industrial information technology and artificial intelligence algorithms to identify customized products in complex industrial scenarios, significantly improving assembly efficiency in SMEs, enhancing robot capabilities, and freeing humans from repetitive processes.

**1) Context-aware holistic scene perception and task planning for HRC**
The production shop floor is generating a huge amount of multimedia information such as images and videos every day, and this explosive growth of visual information can be used as source domain data in different industrial scenarios. Classifying human and robot models in depth images and reconstructing live human-robot collaboration models in point cloud data, as shown in Figure 1. The human motion trajectory and robot motion trajectory in the reconstructed model are recorded in real time with different markers to delineate the worker activity area and robot activity area to obtain a global grasp of the entire human-robot collaborative assembly, and further plan the operation process dynamically according to the assembly instructions in the manufacturing system to improve the operation efficiency. Our system allows cobot to generate task planning through the AI recognition of workpiece, workspace and worker, both of which have been successfully patented, proving our value of innovation.
 
**2) Advanced human-robot collaborative assembly based on behavior understanding**
AR and the industrial metaverse internet increase the control flexibility. Human and robots can understand different process at once, and users do not have to do the programming themselves. The images of the assembly floor are captured to reconstruct the field model, migrate a high-precision classification model from the field of artificial intelligence at the cost of small sample training, plan the worker work area and robot work area rationally and update their behaviours in real time according to the human-robot motion trajectory, and finally make intelligent decisions on assembly tasks to perform production processes on demand. This pattern recognition and inference algorithm is a technological innovation in this system.
 
**3) Intelligent assembly based on Augmented Reality**
In order to achieve on-demand deployment and visualization of assembly instructions, a complete information flow has been constructed in the human-robot collaborative assembly system, the communication protocols between different devices have been defined to improve the communication mechanism of the system to achieve active interaction and adaptive decision-making between the human-robot-manufacturing system with high flexibility. The team has developed a preliminary architecture and provide multiple button control modes to facilitate the motion control data and promote further data analysis and reasoning decisions in collaborative human-robot assembly.
 
**4) AR dynamic guidance for closed-loop information flow based on Industrial Internet**
Based on an augmented reality device visualization platform, a closed-loop information flow between the manufacturing system, the vision sensor and the human-robot is constructed. Based on the visual recognition and intelligent production results of the system, the assembly instructions are adaptively deployed to dynamically plan the assembly process to improve the efficiency of human-robot collaborative work, while visualizing the work instructions to assist the human-robot to quickly complete the highly flexible assembly of the connector and realize the active interaction in human-robot assembly.

With the deployment of this system, perception, reasoning, and cognition capabilities are enhanced, enabling complex environment perception, motion path tracking, and shared assembly tasks between humans and Cobots. The system dynamically communicates instructions on an AR platform, creating a new model of flexible, rapidly adaptable, highly automated, and cost-effective customized product assembly.


人機協作裝配作為現代智能工廠的主要實現方式之一，允許人類操作員和協作式機器人在一個共享的工作空間內完成各種製造裝配任務。由於其靈活的自動化能力，人機協作裝配在實現大規模個性化生產方面一直發揮著重要的作用。它將協作機器人高精確度、可靠性及可重複性的特性與人類的高靈活性和適應性相互結合，以實現最優化的生產力。

隨著這種協作製造模式的普及，協作式機器人在機器人市場上所佔的比例明顯增加。然而，相應的應用領域和協作式機器人的控制方法仍未發展成熟，特別是在應對個性化的任務上，機器人缺乏適應新任務的能力，需要工程師對其重新進行程式設計，過程增加了時間成本及降低了雙方協作的流暢性。在現有的製造模式中，大規模定制化生產成為了一種新趨勢。然而，在缺乏產品細節裝配相關自動化解決方案的前提下，人工裝配仍然是中小型企業用於複雜定制化產品的主流裝配方法。

為了解決定制化生產所面對的困難和機器人靈活性不足的問題，我們提出一個基於人機互認知的機械人協作製造系統以改善雙方的協作效率。為了在高度精細和靈活的裝配情況下實現智能操作，我們開發了一套增強現實（AR）引導的人機協作製造系統。它集成了虛擬現實的任務規劃及視覺數據的動態引導，並增強了協作式機器人的人工智能和AR信息共享，以用戶友好的方式提供人為監督的控制方法，從而更好地融合操作員和協作式機器人的智慧。AR輔助的人機協作柔性生產走向了數字化的智能製造，並將人工智能領域的算法模型遷移到複雜的工業場景中，實現了以小樣品為代價的定制化產品的識別，增強協作機器人執行多模式任務的能力。系統將人從重複的機械作業中解放出來，使人機協作成為工業企業的最佳選擇。

通過部署這一系統，我們增強了系統的感知、推理和認知能力，包括工業人員和機器人的智能。實現了對複雜環境的感知和運動路徑的追蹤，根據感知信息在人和協作式機器人之間共享裝配任務，並適應快速實現個性化生產進度。同時，系統在AR平台上交互式地可視化和動態地傳遞指令，形成了一個新的柔性、多用途、快速適應性、高度自動化和成本效益的定制化產品裝配模式。

Awards: 
1. [APICTA](https://apicta.org/apicta-2022/): Being a member of the HKSAR delegation and winning the largest yearly international ICT awards that all the participants are ranked in the top 3 among their regions/ countries. Our team is the first Hong Kong winner in the tertiary student category in the past 4 years. 
2. [HKICT Grand Award and Gold Award](https://www.hkictawards.hk/award_en.php?year=2022&aid=8): Ranked in the top 0.3% to win the overall championship among 330 participating teams in Student innovation catorgory
3. [Gold Award of Internet+](https://www.polyu.edu.hk/ise/news-and-events/news/2022/20221201-student-award/): Ranked in the top 0.009% to win the highest award among 3,400,000 participating teams
4. [Second Prize (Entrepreneurship Proposal Track) of The 8th Hong Kong University Student Innovation and Entrepreneurship Competition 2022](https://www.hkchallengeplus.com/en/)

Students:
- Tsang Chin-lok, Mphil student (Department of Aeronautical and Aviation Engineering)
- Li Chengxi, PhD student (Department of Industrial and Systems Engineering (ISE))
- Kwok Hin-chi, undergraduate student (ISE)
- Other members of RAIDS

Supervisor:
Ir Dr Zheng Pai, Assistant Professor (ISE), Wong Tit Shing Young Scholar in Smart Robotics, and leader of RAIDS


