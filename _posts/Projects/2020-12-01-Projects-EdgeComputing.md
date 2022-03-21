---
title: "Edge Computing Simulation"
tags: [Projects, Edge Computing]
permalink: /projects/edge-computing/
categories:
  - Projects
header:
  overlay_image: /assets/images/3.EC-header2.jpg
  overlay_filter: rgba(0,0,0,0.2)
  actions:
    - label: "Project Github"
      url: "https://github.com/chaerim-kim/EdgeCloudSim"
---

> 👩🏻‍💻 A Final Year Project on Edge Computing that simulates and evaluates different edge architectures

This project simulates different edge architectures deployed in a domain such as Autonomous Vehicles and Industry 4.0 to depict the effect of the computational and networking system parameters on the performance results, using [EdgeCloudSim](https://github.com/CagataySonmez/EdgeCloudSim).


**Examination Fields**: Edge Computing, Augmented Reality, Facial Recognition, EdgeCloudSim, Performance evaluation


## Table of Contents
- [👁‍🗨 Abstract](#-abstract)  
- [💡 Findings](#-findings)  
  - [Experiment Design](#experiment-design)  
  - [Results and Hypothesis Verification](#results-and-hypothesis-verification)  
    - [Snippet of the report](#snippet-of-the-report)
  - [Recommendations](#recommendations)  
- [Installation / 실행 방법](#installation--실행-방법)
- [How to generate EdgeCloudSim MATLAB graphs](#how-to-generate-edgecloudsim-matlab-graphs)
- [💡 Full report](https://github.com/chaerim-kim/EdgeCloudSim/files/5623637/KIM20-FINAL.pdf)
- [➰ Project Duration](#-project-duration)
- [📜 License](#-license)



## 👁‍🗨 Abstract
The rapid growth of the Internet of Things (IoT) has brought edge computing paradigm under the spotlight. Edge computing brings computing resources closer to end-devices, to meet the increasing needs of performance requirements. This report aims to investigate the effect of computational and networking system parameters on the performance of a face recognition application. The project will evaluate the performance of single-tier, two-tier, and two-tier with Edge Orchestrator (EO) architecture through an empirical investigation, using EdgeCloudSim. The results showed that the best performance could be achieved by utilising two-tier with EO architecture, with high VM processing speed and numerous edge servers. Based on the investigation of the parameters, recommendations for future application design and deployment are made, which will help to design a scalable and effective application.


## 💡 Findings

### Experiment Design
- **Hypothesis 1** – Increase in WLAN bandwidth and VM processing speed reduces the service time.  
- **Hypothesis 2** – Increase in the number of edge servers and VM capacity reduces the percentage of failed tasks.

Hypothesis | Experiment | Parameter | Values
-- | -- | -- | --
N/A | 1 | Initial experiment | -
Hypothesis 1 | 2 | Bandwidth (Mbps) | 100 | 300 | 500
Hypothesis 1 | 3 | VM processing speed (MIPS) | 1000 | 2000 | 3000
Hypothesis 2 | 4 | Number of edge servers per location | 2 | 4 | 6
Hypothesis 2 | 5 | VM capacity (KB) | 50000 | 75000 | 100000



### Results and Hypothesis Verification

Number | Hypothesis | Verification
-- | -- | --
Hypothesis 1 | Increase in WLAN bandwidth and VM processing speed reduces the service time. | -  Increasing the bandwidth lead to the improvement of service time, although the reduction was not significant.-  Increasing the VM processing speed contributed to reducing the service time to a great extent.-  Both parameters have proven to be effective in reducing service time. Therefore, the hypothesis holds true for this experiment.
Hypothesis 2 | Increase in the number of edge servers and VM capacity reduces the percentage of failed tasks. | -  Increasing the number of edge servers significantly reduced the percentage of failed tasks, validating hypothesis 2.-  VM capacity did not affect the percentage of failed tasks, disproving hypothesis 2.-  The results partially confirm hypothesis 2.



### Snippet of the report
> Section 6.2.1 Effect of WLAN bandwidth  

The experiment was designed to investigate the effect of changing the WLAN bandwidth on the performance results. The simulation identified that the **network delay decreased slightly as the WLAN bandwidth increased but had a minor impact on other evaluation metrics.**

(A)  100 Mbps | (B)  300 Mbps | (C)  500 Mbps
-- | -- | --
![image](https://user-images.githubusercontent.com/33334078/100761284-129ba280-3436-11eb-918f-8c67e236d4c7.png) | ![image](https://user-images.githubusercontent.com/33334078/100761308-19c2b080-3436-11eb-8c3a-1b5c8302a875.png) | ![image](https://user-images.githubusercontent.com/33334078/100761343-22b38200-3436-11eb-85f3-13b6772ff800.png)



### Recommendations

#### 1. Importance of EO
In general, **using the two-tier with EO architecture always provides better performance**, as it has the ability to balance the increasing workload. However, it is recommended that two-tier architecture without the EO is utilised in the following scenarios:
- If the available WLAN bandwidth is small, the network delay that incurs when orchestrating the load might affect the performance.
- If the number of edge servers is exceptionally low, to minimise communication
overhead on already congested edge nodes.

#### 2. Devising the Edge Architecture
It is important to realise that there exists a **trade-off between available resources and the performance of the application.** Therefore, depending on the application requirements and characteristics such as task size, the edge deployment and task offloading scheme should be considered carefully.

#### 3. Management of Edge Nodes
Due to the heterogeneity and distributed nature of the edge servers, they are not as well maintained as the centralised cloud datacenter. The lack of maintenance could mean that the edge is prone to failures, which severely impacts the availability of edge servers. **Hence, the management of the nodes through software updates rather than hardware is recommended.**



### 💡 The full report can be accessed (downloaded) [here](https://github.com/chaerim-kim/EdgeCloudSim/files/5623637/KIM20-FINAL.pdf)


## Installation / 실행 방법

### To compile the application:
```
./compile.sh
```

### 1. To run the default configuration singly:
```
./runner.sh out_folder default_config edge_devices.xml applications.xml α
```
- ./runner.sh to run the shell script
- out_folder to define a folder for simulation result to be outputted to
- edge_devices.xml to define edge devices file to be used
- applications.xml to define application file to be used
- α to set the iteration number

### 2. Or to run the simulation in parallel:
```
./run_scenarios.sh α β
```
- ./run_scenarios.sh takes the runner.sh and runs several iterations in parallel
- α defines the number of processors
- β defines the number of iterations to be performed

The simulator outputs the results of 5 different iterations, where the ‘ite.log’ files are provided as a human-readable log of the simulation results, and files in folder ite’n’ to be fed to MATLAB for plot generation



## How to generate EdgeCloudSim MATLAB graphs
Refer to my another post.
[How to generate EdgeCloudSim MATLAB graphs](https://chaerim-kim.github.io/projects/edge-computing/ecs)


## ➰ Project Duration
October 2019 - May 2020



## 📜 License
This project is licensed under the terms of the MIT license.
> You can check out the full license [here](#https://opensource.org/licenses/mit-license.php)

- [EdgeCloudSim](https://github.com/CagataySonmez/EdgeCloudSim)
