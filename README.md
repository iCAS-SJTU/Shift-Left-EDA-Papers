# Shift Left Techniques in Electronic Design Automation: A Survey


[TO-DO] welcome paragraph and simple introduction of the survey, together with arxiv link.

[TO-DO] continuous updating and welcome to contribute and suggest. 


## Introduction


## Table of Contents

- [Introduction](#-introduction)
- [Shift-Left in Pre-RTL](#-shift-left-in-pre-rtl)
    - [Pre-RTL Simulation Models](#pre-rtl-simulation-models)
    - [Software-defined Hardware](#software-defined-hardware)
    - [Design Space Exploration (DSE) in Early Design Phases](#design-space-exploration-dse-in-early-design-phases)
- [Shift-Left in Front-End RTL](#-shift-left-in-front-end-rtl)
    - [Prediction in HLS](#prediction-in-hls)
    - [Prediction in RTL](#prediction-in-rtl)
    - [Physically-Aware Logic Synthesis](#physically-aware-logic-synthesis)
- [Shift-Left in FloorPlanning (FP)](#-shift-left-in-floorplanning-fp)
    - [Congestion-Aware/Routability-Driven FP](#congestion-awareroutability-driven-fp)
    - [CTS-Aware FP](#cts-aware-fp)
    - [Dataflow-Aware FP](#dataflow-aware-fp)
    - [Thermal-Aware FP](#thermal-aware-fp)
    - [EM/IR-Aware FP](#emir-aware-fp)
- [Shift-Left in Placement](#-shift-left-in-placement)
    - [Power-Aware Placement](#power-aware-placement)
    - [ECO-Aware Placement](#eco-aware-placement)
    - [DRC-Aware Placement](#drc-aware-placement)
    - [Early CTS](#early-cts)
    - [Early Routing](#early-routing)
- [Shift-Left in CTS](#-shift-left-in-cts)
    - [Aging-Aware CTS](#aging-aware-cts)
    - [Congestion-Aware CTS](#congestion-aware-cts)
    - [Early Routing](#early-routing)
- [Shift-Left in Routing](#-shift-left-in-routing)
    - [EM-Aware Routing](#em-aware-routing)
    - [ECO-Aware Routing](#eco-aware-routing)
    - [Power-Aware Routing](#power-aware-routing)
- [Shift-Left in Signoff](#-shift-left-in-signoff)
    - [Signoff-ECO Integration](#signoff-eco-integration)
- [Shift-Left in Verification and Testing](#-shift-left-in-verification-and-testing)
    - [Verification Shift-Left](#verification-shift-left)
    - [Testing Shift-Left](#testing-shift-left)



## Shift-Left in Pre-RTL
### Pre-RTL Simulation Models
- (2011) ACM SIGARCH Computer Architecture News: The gem5 simulator. [[paper](https://dl.acm.org/doi/10.1145/2024716.2024718)]</br>
- (2020) arXiv preprint: The gem5 simulator: Version 20.0+. [[paper](https://arxiv.org/abs/2007.03152)]</br>
- (2011) International Conference for High Performance Computing, Networking, Storage and Analysis (SC): Sniper: Exploring the level of abstraction for scalable and accurate parallel multi-core simulation. [[paper](https://ieeexplore.ieee.org/document/6114398)]</br>
- (2010) International Symposium on High-Performance Computer Architecture (HPCA): Interval simulation: Raising the level of abstraction in architectural simulation [[paper](https://ieeexplore.ieee.org/document/5416636)]</br>
- (2013) ACM SIGARCH Computer Architecture News: ZSim: Fast and accurate microarchitectural simulation of thousand-core systems [[paper](https://dl.acm.org/doi/10.1145/2508148.2485963)] [[code](https://github.com/s5z/zsim)]</br>
- (2011) IEEE Computer Architecture Letters: DRAMSim2: A cycle accurate memory system simulator [[paper](https://ieeexplore.ieee.org/document/5732229)] [[code](https://github.com/umd-memsys/DRAMSim2)]</br>
- (2020) IEEE Computer Architecture Letters: DRAMsim3: A cycle-accurate, thermal-capable DRAM simulator [[paper](https://ieeexplore.ieee.org/document/8999595)] [[code](https://github.com/umd-memsys/DRAMsim3)]</br>
- (2019) IEEE International Symposium on Performance Analysis of Systems and Software (ISPASS): Timeloop: A systematic approach to dnn accelerator evaluation [[paper](https://ieeexplore.ieee.org/document/8695666)] [[code](https://github.com/NVlabs/timeloop)]</br>
- (2014) ACM SIGARCH Computer Architecture News: Aladdin: A pre-RTL, power-performance accelerator simulator enabling large design space exploration of customized architectures [[paper](https://ieeexplore.ieee.org/document/6853196)] [[code](https://github.com/harvard-acc/ALADDIN)]</br>
- (2022) IEEE/ACM International Symposium on Microarchitecture (MICRO): Sparseloop: An analytical approach to sparse tensor accelerator modeling [[paper](https://dl.acm.org/doi/abs/10.1109/MICRO56248.2022.00096)] [[code](https://github.com/Accelergy-Project/micro22-sparseloop-artifact)]</br>
- (2024) IEEE International Symposium on Performance Analysis of Systems and Software (ISPASS): CiMLoop: A flexible, accurate, and fast compute-in-memory modeling tool [[paper](https://ieeexplore.ieee.org/document/10590023/)] [[code](https://github.com/mit-emze/cimloop)]</br>
- (2019) IEEE International Electron Devices Meeting (IEDM): DNN+ NeuroSim: An end-to-end benchmarking framework for compute-in-memory accelerators with versatile device technologies [[paper](https://ieeexplore.ieee.org/document/8993491)] [[code](https://github.com/neurosim/DNN_NeuroSim_V1.0)]</br>
- (2009) ACM/IEEE International Symposium on Microarchitecture (MICRO): McPAT: An integrated power, area, and timing modeling framework for multicore and manycore architectures [[paper](https://ieeexplore.ieee.org/document/5375438)] [[code](https://github.com/HewlettPackard/mcpat)]
- (2017) ACM Transactions on Architecture and Code Optimization (TACO): CACTI 7: New tools for interconnect exploration in innovative off-chip memories [[paper](https://dl.acm.org/doi/10.1145/3085572)]
- (2009) HP Laboratories Technical Report: CACTI 6.0: A tool to model large caches [[paper](https://www.researchgate.net/publication/242516869_Cacti_60_A_tool_to_model_large_caches)]
- (2019) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): Accelergy: An architecture-level energy estimation methodology for accelerator designs [[paper](https://ieeexplore.ieee.org/document/8942149)] [[code](https://github.com/Accelergy-Project/accelergy)]
- (2022) IEEE Intersociety Conference on Thermal and Thermomechanical Phenomena in Electronic Systems (iTherm): From 2.5 D to 3D chiplet systems: Investigation of thermal implications with HotSpot 7.0 [[paper](https://ieeexplore.ieee.org/document/9899649)]
- (2006) IEEE Transactions on Very Large Scale Integration (VLSI) Systems: HotSpot: A compact thermal modeling methodology for early-stage VLSI design [[paper](https://ieeexplore.ieee.org/document/1650228)] [[code](https://github.com/uvahotspot/HotSpot)]
- (2010) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): 3D-ICE: Fast compact transient thermal modeling for 3D ICs with inter-tier liquid cooling [[paper](https://ieeexplore.ieee.org/document/5653749)] [[code](https://esl.epfl.ch/3D-ICE)]
- (2021) IEEE International Symposium on Workload Characterization (IISWC): HotGauge: A methodology for characterizing advanced hotspots in modern and next generation processors [[paper](https://ieeexplore.ieee.org/document/9668287)]
- (2018) IEEE Embedded Systems Letters: HotSniper: Sniper-based toolchain for many-core thermal simulations in open systems [[paper](https://ieeexplore.ieee.org/document/8444047)]
- (2022) ACM Transactions on Architecture and Code Optimization (TACO): CoMeT: An integrated interval thermal simulation toolchain for 2D, 2.5 D, and 3D processor-memory systems [[paper](https://dl.acm.org/doi/10.1145/3532185)]
- (2023) International Green and Sustainable Computing Conference (IGSC): Hot-LEGO: Architect Microfluidic Cooling Equipped 3DIC with Pre-RTL Thermal Simulation [[paper](https://dl.acm.org/doi/10.1145/3634769.3634801)]
- (2025) IEEE Journal on Emerging and Selected Topics in Circuits and Systems: Cool-3D: An End-to-End Thermal-Aware Framework for Early-Phase Design Space Exploration of Microfluidic-Cooled 3DICs [[paper](https://doi.org/10.1109/JETCAS.2025.3590065)]
### Software-defined Hardware
- (2025) Springer SOC-Based Solutions in Emerging Application Domains: Software-Defined SOCs [[paper]()][[code]()]
- (2011) ACM SIGARCH computer architecture news: The gem5 simulator [[paper]()][[code]()]
- (2021) ACM/IEEE Workshop on Machine Learning for CAD (MLCAD): A survey of graph neural networks for electronic design automation [[paper]()][[code]()]
### Workload Modeling
- (2011) ACM SIGARCH computer architecture news The gem5 simulator [[paper]()][[code](https://www.gem5.org/)]
- (2011) International Conference for High Performance Computing, Networking, Storage and Analysis Sniper: Exploring the level of abstraction for scalable and accurate parallel multi-core simulation [[paper]()][[code](https://snipersim.org/w/The-Sniper-Multi-Core-Simulator)]
- (2019) IEEE international symposium on performance analysis of systems and software (ISPASS) Timeloop: A systematic approach to dnn accelerator evaluation [[paper]()][[code](https://github.com/NVlabs/timeloop)]
- (2021) IEEE Transactions on Computers ZigZag: Enlarging joint architecture-mapping design space exploration for DNN accelerators [[paper]()][[code](https://github.com/zigzag-project/zigzag)]

### Design Space Exploration (DSE) in Early Design Phases
- (2005) Asia and South Pacific Design Automation Conference (ASP-DAC)： Thermal-driven multilevel routing for 3-D ICs [[paper]()]
- (2019) IEEE international symposium on performance analysis of systems and software (ISPASS): Timeloop: A systematic approach to dnn accelerator evaluation [[paper]()][[code](https://github.com/NVlabs/timeloop)]
- (2022) IEEE Journal on Emerging and Selected Topics in Circuits and Systems Aero: Design space exploration framework for resource-constrained cnn mapping on tile-based accelerators [[paper]()]
- (2021) IEEE Transactions on Computers: ZigZag: Enlarging joint architecture-mapping design space exploration for DNN accelerators [[paper]()][[code](https://github.com/zigzag-project/zigzag)]

## Shift-Left in Front-End Design Phase
### Predictions in HLS
- (2017) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): COMBA: A comprehensive model-based analysis framework for high level synthesis of real applications [[paper]()]
- (2013) Euromicro Conference on Digital System Design: A fast and autonomous HLS methodology for hardware accelerator generation under resource constraints [[paper]()]
- (2012) Design, Automation & Test in Europe Conference & Exhibition (DATE): Compositional system-level design exploration with planning of high-level synthesis [[paper]()]
- (2014) IEEE International Conference on Computer Design (ICCD): Design space exploration of multiple loops on FPGAs using high level synthesis [[paper]()]
- (2017) Annual Design Automation Conference: FlexCL: An analytical performance model for OpenCL workloads on flexible FPGAs [[paper]()]
- (2016) IEEE International Symposium on High Performance Computer Architecture (HPCA): A performance analysis framework for optimizing OpenCL applications on FPGAs [[paper]()]
- (2009) Communications of the ACM: Roofline: an insightful visual performance model for multicore architectures [[paper]()]
- (2013) International Journal of Reconfigurable Computing: Performance Modeling for FPGAs: Extending the Roofline Model with High-Level Synthesis Tools [[paper]()]
- (2021) Great Lakes Symposium on VLSI: Ironman: Gnn-assisted design space exploration in high-level synthesis via reinforcement learning [[paper]()]
- (2022) ACM/IEEE Design Automation Conference: High-level synthesis performance prediction using GNNs: benchmarking, modeling, and advancing [[paper]()]
- (2017) Design, Automation & Test in Europe Conference & Exhibition (DATE): Design space exploration of FPGA-based accelerators with multi-level parallelism [[paper]()]
- (2016) International Conference on Field Programmable Logic and Applications (FPL): Efficient and reliable high-level synthesis design space explorer for FPGAs [[paper]()]
- (2013) Annual Design Automation Conference: On learning-based methods for design-space exploration with high-level synthesis [[paper]()]
- (2018) IEEE Annual International Symposium on Field-Programmable Custom Computing Machines (FCCM): Fast and accurate estimation of quality of results in high-level synthesis with machine learning [[paper]()]
- (2018) International Conference on Computer-Aided Design: HLSPredict: Cross platform performance prediction for FPGA high-level synthesis [[paper]()]
- (2019) Asia and South Pacific Design Automation Conference: Xppe: cross-platform performance estimation of hardware accelerators using machine learning [[paper]()]
- (2016) ACM SIGARCH Computer Architecture News: Automatic generation of efficient accelerators for reconfigurable hardware [[paper]()]
- (2006) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: Design space pruning through early estimations of area/delay tradeoffs for FPGA implementations [[paper]()]
- (2015) Design, Automation & Test in Europe Conference & Exhibition (DATE): Exploiting loop-array dependencies to accelerate the design space exploration with high level synthesis [[paper]()]
- (2017) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): HLScope+: Fast and accurate performance estimation for FPGA HLS [[paper]()]
- (2016) Annual Design Automation Conference: Lin-analyzer: A high-level performance analysis tool for FPGA-based accelerators [[paper]()]
- (2019) International Conference on Field Programmable Logic and Applications (FPL): Pyramid: Machine learning framework to estimate the optimal timing and resource usage of a high-level synthesis design [[paper]()]
- (2020) International Conference on Computer-Aided Design: Accurate operation delay prediction for FPGA HLS using graph neural networks [[paper]()]
- (2020) Asia and South Pacific Design Automation Conference (ASP-DAC): HL-Pow: A learning-based power modeling framework for high-level synthesis [[paper]()]
- (2015) Design, Automation & Test in Europe Conference & Exhibition (DATE): Dynamic power and performance back-annotation for fast and accurate functional hardware simulation [[paper]()]
- (2012) ACM International Symposium on Physical Design: Towards layout-friendly high-level synthesis [[paper]()]
- (2018) International Conference on IC Design & Technology (ICICDT): Wire congestion aware high level synthesis flow with source code compiler [[paper]()]
- (2019) Design, Automation & Test in Europe Conference & Exhibition (DATE): Machine learning based routing congestion prediction in FPGA high-level synthesis [[paper]()]
- (2021) IEEE Access: High-level annotation of routing congestion for Xilinx Vivado HLS designs [[paper]()]
### Prediction in RTL
- (2023) IEEE/ACM International Conference on Computer Aided Design (ICCAD): MasterRTL: A Pre-Synthesis PPA Estimation Framework for Any RTL Design [[paper]()]
- (2025) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: Transferable Presynthesis PPA Estimation for RTL Designs With Data Augmentation Techniques [[paper]()]
- (2022) Annual International Symposium on Computer Architecture (ISCA): SNS’s not a synthesizer: a deep-learning-based synthesis predictor [[paper]()]
- (2019) Annual Design Automation Conference (DAC): A Learning-Based Recommender System for Autotuning Design Flows of Industrial High-Performance Processors [[paper]()]
- (2020) Asia and South Pacific Design Automation Conference (ASP-DAC): FIST: A Feature-Importance Sampling and Tree-Based Method for Automatic Design Flow Parameter Tuning [[paper]()]
- (2021) IEEE/ACM International Conference On Computer Aided Design (ICCAD): Fast and Accurate PPA Modeling with Transfer Learning [[paper]()]
- (2023) ACM/IEEE Workshop on Machine Learning for CAD (MLCAD): ASAP: Accurate Synthesis Analysis and Prediction with Multi-Task Learning [[paper]()]
- (2021) Synopsys, Inc. Technical Report: Shift Left with RTL Architect for Faster Time-to-Results [[paper]()]
- (2025) arXiv: CircuitFusion: Multimodal Circuit Representation Learning for Agile Chip Design [[paper]()]
- (2025) arXiv: The Graph’s Apprentice: Teaching an LLM Low Level Knowledge for Circuit Quality Estimation [[paper]()]
- (2025) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): RTLRewriter: Methodologies for Large Models aided RTL Code Optimization [[paper]()]
- (2018) Annual Design Automation Conference (DAC): Developing synthesis flows without human knowledge [[paper]()]
- (2020) ACM/IEEE Workshop on Machine Learning for CAD (MLCAD): Decision Making in Synthesis cross Technologies using LSTMs and Transfer Learning [[paper]()]
- (2021) Asia and South Pacific Design Automation Conference (ASP-DAC): Read your Circuit: Leveraging Word Embedding to Guide Logic Optimization [[paper]()]
- (2022) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): Applying GNNs to Timing Estimation at RTL [[paper]()]
- (2023) ACM/IEEE Workshop on Machine Learning for CAD (MLCAD): Using Graph Neural Networks for Timing Estimations of RTL Intermediate Representations [[paper]()]
- (2024) Asia and South Pacific Design Automation Conference (ASP-DAC): LSTP: A Logic Synthesis Timing Predictor [[paper]()]
- (2022) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): How Good Is Your Verilog RTL Code? A Quick Answer from Machine Learning [[paper]()]
- (2023) ACM/IEEE Workshop on Machine Learning for CAD (MLCAD): Early Identification of Timing Critical RTL Components using ML based Path Delay Prediction [[paper]()]
- (2021) IEEE Nordic Circuits and Systems Conference (NorCAS): RTL Delay Prediction Using Neural Networks [[paper]()]
- (2025) International Conference on Machine Learning: Bridging Layout and RTL: Knowledge Distillation based Timing Prediction [[paper]()]
- (2024) ACM/IEEE Design Automation Conference (DAC): Annotating Slack Directly on Your Verilog: Fine-Grained RTL Timing Evaluation for Early Optimization [[paper]()]
- (2020) ACM/IEEE Design Automation Conference (DAC): GRANNITE: Graph Neural Network Inference for Transferable Power Estimation [[paper]()]
- (2023) IEEE International Symposium on Circuits and Systems (ISCAS): GRASPE: Accurate Post-Synthesis Power Estimation from RTL using Graph Representation Learning [[paper]()]
- (2021) IEEE/ACM International Symposium on Microarchitecture (MICRO): APOLLO: An Automated Power Modeling Framework for Runtime Power Introspection in High-Volume Commercial Microprocessors [[paper]()]
- (2019) Annual Design Automation Conference (DAC): PRIMAL: Power Inference using Machine Learning [[paper]()]
- (2019) IEEE/ACM International Symposium on Microarchitecture (MICRO): Simmani: Runtime Power Modeling for Arbitrary RTL with Automatic Signal Selection [[paper]()]
- (2015) Asia and South Pacific Design Automation Conference: Early stage real-time SoC power estimation using RTL instrumentation [[paper]()]
- (2022) Ansys, Inc. Product Brief: Ansys PowerArtist [[paper]()]
- (2023) ennocad Press Release: EnFortius® RPA empowers flagship AI chip design companies to achieve early power analysis [[paper]()]
- (2023) Synopsys, Inc. Technical Report: Achieving Consistent RTL Power Analysis Accuracy [[paper]()]
- (2022) International Conference on Neural Information Processing Systems (NIPS): Versatile multi-stage graph neural network for circuit representation [[paper]()]
- (2019) IFIP/IEEE International Conference on Very Large Scale Integration (VLSI-SoC): CongestionNet: Routing Congestion Prediction Using Deep Graph Neural Networks [[paper]()]
- (2021) IEEE/ACM International Conference On Computer Aided Design (ICCAD): Generalizable Cross-Graph Embedding for GNN-based Congestion Prediction [[paper]()]
- (2022) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: Preplacement Net Length and Timing Estimation by Customized Graph Neural Network [[paper]()]
- (2025) arXiv: VeriLoC: Line-of-Code Level Prediction of Hardware Design Quality from Verilog Code [[paper]()]
### Physically-Aware Logic Synthesis
- (1995) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: Combining technology mapping and placement for delay-minimization in FPGA designs [[paper]()]
- (2001) IEEE/ACM International Conference on Computer Aided Design (ICCAD): Addressing the timing closure problem by integrating logic optimization and placement [[paper]()]
- (1998) IEEE/ACM International Conference on Computer-Aided Design: Wireplanning in logic synthesis [[paper]()]
- (1999) IEEE/ACM International Conference on Computer-Aided Design: An integrated algorithm for combined placement and libraryless technology mapping [[paper]()]
- (2008) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): Delay-optimal simultaneous technology mapping and placement with applications to timing optimization [[paper]()]
- (2011) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: Simultaneous Technology Mapping and Placement for Delay Minimization [[paper]()]
- (1991) IEEE International Conference on Computer-Aided Design: Layout driven logic restructuring/decomposition [[paper]()]
- (1991) ACM/IEEE Design Automation Conference: Layout driven technology mapping [[paper]()]
- (1998) Annual Design Automation Conference (DAC): A DSM design flow: putting floorplanning, technology-mapping, and gate-placement together [[paper]()]
- (2007) Proceedings of the IEEE: Techniques for Fast Physical Synthesis [[paper]()]
- (1998) International Conference on Computer Design: Combining technology mapping with post-placement resynthesis for performance optimization [[paper]()]
- (2018) Springer International Publishing: Physical Awareness Starting at Technology-Independent Logic Synthesis [[paper]()]
- (2023) IEEE International Conference on Computer Design (ICCD): Delay-driven physically-aware logic synthesis with informed search [[paper]()]
- (2025) Asia and South Pacific Design Automation Conference (ASP-DAC): Revisit MBFF: Efficient Early-Stage Multi-bit Flip-Flops Clustering with Physical and Timing Awareness [[paper]()]
- (2004) IEEE/ACM International Conference on Computer Aided Design (ICCAD): A new incremental placement algorithm and its application to congestion-aware divisor extraction [[paper]()]
- (2001) IEEE/ACM International Conference on Computer Aided Design (ICCAD): Congestion aware layout driven logic synthesis [[paper]()]
- (2002) Design, Automation and Test in Europe Conference and Exhibition (DATE): Layout driven decomposition with congestion consideration [[paper]()]
- (2016) International Journal of Hybrid Information Technology: A Study of Floorplanning Challenges and Analysis of macro placement approaches in Physical Aware Synthesis [[paper]()]
- (1993) IEEE International ASIC Conference and Exhibit: Placement and placement driven technology mapping for FPGA synthesis [[paper]()]
- (2003) ACM/SIGDA International Symposium on Field Programmable Gate Arrays (FPGA): Placement-driven technology mapping for LUT-based FPGAs [[paper]()]
- (2002) Design, Automation and Test in Europe Conference and Exhibition (DATE): Congestion-aware logic synthesis [[paper]()]
- (2003) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: Global and local congestion optimization in technology mapping [[paper]()]
- (2024) ACM/IEEE Design Automation Conference (DAC): Lesyn: Placement-aware Logic Resynthesis for Non-Integer Multiple-Cell-Height Designs [[paper]()]
- (2016) Design, Automation & Test in Europe Conference & Exhibition (DATE): A synthesis-parameter tuning system for autonomous design-space exploration [[paper]()]
- (2018) International Journal of Engineering & Technology: Optimization of physically-aware synthesis for digital implementation flow [[paper]()]
- (2025) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): Physically Aware Synthesis Revisited: Guiding Technology Mapping with Primitive Logic Gate Placement [[paper]()]
- (2024) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: PowerSyn: A Logic Synthesis Framework With Early Power Optimization [[paper]()]
- (2024) Conference of Science and Technology for Integrated Circuits (CSTIC): Integration of Shift-Left Updates into Logic Synthesis and Macro Placement [[paper]()]
### Physically-Aware HLS
- (1991) ACM/IEEE Design Automation Conference: 3D scheduling: high-level synthesis with floorplanning [[paper]()]
- (2002) IEEE/ACM International Conference on Computer Aided Design (ICCAD): Layout-driven resource sharing in high-level synthesis [[paper]()]
- (2024) ACM/IEEE Design Automation Conference (DAC): A High Level Approach to Co-Designing 3D ICs [[paper]()]
- (2014) ACM/SIGDA International Symposium on Field-Programmable Gate Arrays (FPGA): Fast and effective placement and routing directed high-level synthesis for FPGAs [[paper]()]
- (2020) ACM/IEEE Design Automation Conference (DAC): Analysis and Optimization of the Implicit Broadcasts in FPGA HLS to Improve Maximum Frequency [[paper]()]
- (2015) IEEE International Conference on ASIC (ASICON): Clock skew estimate modeling for FPGA high-level synthesis and its application [[paper]()]
- (2003) International Conference on ASIC: Reallocation and Rescheduling after floor-planning for timing optimization [[paper]()]
- (2015) Annual Design Automation Conference (DAC): Physically aware high level synthesis design flow [[paper]()]
- (2008) IEEE Pacific-Asia Workshop on Computational Intelligence and Industrial Application: Congestion Aware High Level Synthesis Combined with Floorplanning [[paper]()]
- (2000) Annual Design Automation Conference (DAC): Unifying behavioral synthesis and physical design [[paper]()]
- (2006) IEEE Computer Society Annual Symposium on Emerging VLSI Technologies and Architectures (ISVLSI): A Novel Approach to Performance-Oriented Datapath Allocation and Floorplanning [[paper]()]
- (2015) ACM/SIGDA International Symposium on Field-Programmable Gate Arrays (FPGA): Mapping-Aware Constrained Scheduling for LUT-Based FPGAs [[paper]()]
- (1998) IEEE/ACM International Conference on Computer-Aided Design: Integrating floorplanning in data-transfer based high-level synthesis [[paper]()]
- (2015) Annual Design Automation Conference (DAC): Area-efficient pipelining for FPGA-targeted high-level synthesis [[paper]()]

## Shift-Left in FloorPlanning (FP)
### Feedthrough-aware  FP
- (2025) Association for Computing Machinery: FTAFP: A Feedthrough-Aware Floorplanner for Hierarchical Design of Large-Scale SoCs [[paper]()]
- (2025) arXiv: One Step Beyond: Feedthrough & Placement-Aware Rectilinear Floorplanner [[paper]()]
- (2022) International Conference on Communications, Circuits and Systems (ICCCAS): Channel Based SoC Feedthrough Insertion Methodology [[paper]()]
- (2012) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): Reclaiming Over-the-IP-Block Routing Resources with Buffering-Aware Rectilinear Steiner Minimum Tree Construction [[paper]()]
- (2025) International Symposium on Quality Electronic Design (ISQED): Die Area Reduction by Decongesting Top Channels Using Novel Feedthrough Insertion Methodology in Hierarchical SoC Designs [[paper]()]
### CTS-Aware FP
- (2021) Electronics: An Investigation of Clock Skew Using a Wirelength-Aware Floorplanning Process in the Pre-Placement Stages of MSV Layouts [[paper]()]
- (2005) IEEE International Symposium on Circuits and Systems (ISCAS): Floorplanning with clock tree estimation [[paper]()]
- (2013) International Conference on Intelligent Systems, Modelling and Simulation: ASIC Clock Tree Estimation in Design Planning [[paper]()]
- (1999) Annual Design Automation Conference (DAC): A Floorplan-Based Planning Methodology for Power and Clock Distribution in ASICs [[paper]()]
- (2004) International Symposium on Physical Design: Power-aware clock tree planning [[paper]()]
- (2007) Design, Automation and Test in Europe Conference (DATE): System Level Clock Tree Synthesis for Power Optimization [[paper]()]
- (2015) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): Synthesis for Power-Aware Clock Spines [[paper]()]
- (2017) Asia and South Pacific Design Automation Conference (ASP-DAC): Algorithm for Synthesis and Exploration of Clock Spines [[paper]()]
### Power/Thermal-Aware FP
- (1998) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: A Matrix Synthesis Approach to Thermal Placement [[paper]()]
- (2005) International Symposium on Quality Electronic Design (ISQED): Thermal-Aware Floorplanning Using Genetic Algorithms [[paper]()]
- (2004) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): A Thermal-Driven Floorplanning Algorithm for 3D ICs [[paper]()]
- (2014) ETRI Journal: Thermal-Aware Floorplanning with Min-Cut Die Partition for 3D ICs [[paper]()]
- (2005) Journal of Instruction-Level Parallelism: A case for thermal-aware floorplanning at the microarchitectural level [[paper]()]
- (2015) Microprocessors and Microsystems: Thermal aware floorplanning incorporating temperature dependent wire delay estimation [[paper]()]
- (2023) IEEE Electronic Components and Technology Conference (ECTC): Thermal-Aware SoC Macro Placement and Multi-chip Module Design Optimization with Bayesian Optimization [[paper]()]
- (2023) IEEE Transactions on Very Large Scale Integration (VLSI) Systems: Thermal-Aware Fixed-Outline 3-D IC Floorplanning: An End-to-End Learning-Based Approach [[paper]()]
- (2024) Technical Report: ATPlace2.5D: Analytical Thermal-Aware Chiplet Placement Framework for Large-Scale 2.5D-IC [[paper]()]
- (2007) Asia and South Pacific Design Automation Conference (ASP-DAC): Noise-Direct: A Technique for Power Supply Noise Aware Floorplanning Using Microarchitecture Profiling [[paper]()]
- (2006) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): Voltage Island Aware Floorplanning for Power and Timing Optimization [[paper]()]
- (2019) Cadence Press Release: Cadence Launches Celsius Thermal Solver [[paper]()]
### EM/IR-Aware FP
- (1999) Annual Design Automation Conference (DAC): A Floorplan-Based Planning Methodology for Power and Clock Distribution in ASICs [[paper]()]
- (2001) Asia and South Pacific Design Automation Conference (ASP-DAC): Integrated Power Supply Planning and Floorplanning [[paper]()]
- (2005) WSEAS/IASME International Conference on Computer Engineering and Applications: Floorplanning with IR-drop consideration [[paper]()]
- (2009) IEEE Asia Pacific Conference on ASIC: Floorplan and Power/Ground Network Co-Design Using Guided Incremental Floorplanning [[paper]()]
- (2002) Asia and South Pacific Design Automation Conference (ASP-DAC): Power Supply Noise Aware Floorplanning and Decoupling Capacitance Placement [[paper]()]
- (2010) Asia and South Pacific Design Automation Conference (ASP-DAC): Three-Dimensional IC Floorplan and Power/Ground Network Co-Synthesis [[paper]()]
- (2013) International Conference on Computer-Aided Design and Computer Graphics (CAD/Graphics): Voltage Drop Aware Power Pad Assignment and Floorplanning for Multi-Voltage SoC Designs [[paper]()]
- (2022) Analog Integrated Circuits and Signal Processing: P/G Pin Position-Aware Voltage Island Floorplanning for IR Drop Security [[paper]()]
## Shift-Left in Placement
### Timing-Driven Placement
- (2007) Asia and South Pacific Design Automation Conference: Micro-architecture pipelining optimization with throughput-aware floorplanning [[paper]()]
- (2005) Annual Design Automation Conference (DAC): Microarchitecture-Aware Floorplanning Using a Statistical Design of Experiments Approach [[paper]()]
- (2021) IEEE Transactions on Very Large Scale Integration (VLSI) Systems: Dataflow-Aware Macro Placement Based on Simulated Evolution Algorithm for Mixed-Size Designs [[paper]()]
- (2019) Design, Automation & Test in Europe Conference & Exhibition (DATE): RTL-aware dataflow-driven macro placement [[paper]()]
- (2021) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: Multilevel Dataflow-Driven Macro Placement Guided by RTL Structure and Analytical Methods [[paper]()]
- (2022) International Symposium on Physical Design (ISPD): RTL-MP: Toward Practical, Human-Quality Chip Planning and Macro Placement [[paper]()]
- (2024) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: Hier-RTLMP: A Hierarchical Automatic Macro Placer for Large-Scale Complex IP Blocks [[paper]()]
- (2025) International Symposium of Electronics Design Automation (ISEDA): IncreDFlip: Incremental Dataflow-Driven Macro Flipping for Efficient Macro Placement Refinement [[paper]()]
- (2025) arXiv preprint: DAS-MP: Enabling High-Quality Macro Placement with Enhanced Dataflow Awareness [[paper]()]
- (2024) Design, Automation & Test in Europe Conference & Exhibition (DATE): Standard cells do matter: Uncovering hidden connections for high-quality macro placement [[paper]()]
- (2019) Annual Design Automation Conference: Dreamplace: Deep learning toolkit-enabled gpu acceleration for modern vlsi placement [[paper]()][[code](https://github.com/limbo018/DREAMPlace)]
- (2018) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: Replace: Advancing solution quality and routability validation in global placement [[paper]()]
- (2024) International Symposium on Physical Design: Incremacro: Incremental macro placement refinement [[paper]()]
- (2002) International Symposium on Physical Design: Net criticality revisited: An effective method to improve timing in physical design [[paper]()]
- (2002) IEEE/ACM International Conference on Computer-Aided Design: A novel net weighting algorithm for timing-driven placement [[paper]()]
- (2022) Design, Automation & Test in Europe Conference & Exhibition (DATE): DREAMPlace 4.0: Timing-driven global placement with momentum-based net weighting [[paper]()][[code](https://github.com/limbo018/DREAMPlace)]
- (2015) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): OpenTimer: A high-performance timing analysis tool [[paper]()][[code](https://github.com/OpenTimer/OpenTimer)]
- (2024) International Symposium on Physical Design: Timing-driven analytical placement according to expected cell distribution range [[paper]()]
- (2024) IEEE/ACM International Conference on Computer-Aided Design: Hybrid modeling and weighting for timing-driven placement with efficient calibration [[paper]()]
- (2025) Design, Automation & Test in Europe Conference (DATE): Timing-driven global placement by efficient critical path extraction [[paper]()]
- (1993) International Design Automation Conference: Prime: A timing-driven placement tool using a piecewise linear resistive network approach [[paper]()]
- (1995) Annual ACM/IEEE Design Automation Conference: Timing driven placement for large standard cell circuits [[paper]()]
- (2022) ACM/IEEE Design Automation Conference: Differentiable-timing-driven global placement [[paper]()]
### Routability-Aware Placement
- (2012) Annual Design Automation Conference: The DAC 2012 routability-driven placement contest and benchmark suite [[paper]()]
- (2011) International Symposium on Physical Design: The ISPD-2011 routability-driven placement contest and benchmark suite [[paper]()]
- (2011) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): Ripple: An effective routability-driven placer by iterative cell movement [[paper]()]
- (2011) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): Routability-driven analytical placement for mixed-size circuit designs [[paper]()]
- (2011) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): A SimPLR method for routability-driven placement [[paper]()]
- (2011) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: SimPL: An effective placement algorithm [[paper]()]
- (2013) Annual Design Automation Conference: Optimization of placement solutions for routability [[paper]()]
- (2014) Asia and South Pacific Design Automation Conference (ASP-DAC): Analytical placement of mixed-size circuits for better detailed-routability [[paper]()]
- (2018) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: Replace: Advancing solution quality and routability validation in global placement [[paper]()]
- (2013) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: NCTU-GR 2.0: Multithreaded collision-aware global routing with bounded-length maze routing [[paper]()]
- (2012) International Conference on Computer-Aided Design: ICCAD-2012 CAD contest in design hierarchy aware routability-driven placement and benchmark suite [[paper]()]
- (2014) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: NTUplace4h: A novel routability-driven placement algorithm for hierarchical mixed-size circuit designs [[paper]()]
- (2010) International Symposium on Physical Design: What makes a design difficult to route [[paper]()]
- (2013) ACM International Symposium on Physical Design: Case study for placement solutions in ISPD11 and DAC12 routability-driven placement contests [[paper]()]
- (2014) International Symposium on Physical Design: ISPD 2014 benchmarks with sub-45nm technology rules for detailed-routing-driven placement [[paper]()]
- (2011) Design, Automation & Test in Europe Conference & Exhibition (DATE): Global placement with deep learning-enabled explicit routability optimization [[paper]()]
- (2018) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): RouteNet: Routability prediction for mixed-size designs using convolutional neural network [[paper]()]
- (2019) Annual Design Automation Conference: Dreamplace: Deep learning toolkit-enabled gpu acceleration for modern vlsi placement [[paper]()][[code](https://github.com/limbo018/DREAMPlace)]
- (2022) IEEE/ACM International Conference on Computer-Aided Design: Pin accessibility and routing congestion aware DRC hotspot prediction using graph neural network and U-Net [[paper]()]
- (2025) ACM Transactions on Design Automation of Electronic Systems: Early Stage DRC Hotspot Prediction for Mixed-Size Designs Through an Efficient Graph-Based Deep Learning [[paper]()]
- (2025) Technical Report: PGR-DRC: Pre-Global Routing DRC Violation Prediction Using Unsupervised Learning [[paper]()]
- (2015) Asia and South Pacific Design Automation Conference: Detailed-routing-driven analytical standard-cell placement [[paper]()]
- (2015) International Symposium on Physical Design: ISPD 2015 benchmarks with fence regions and routing blockages for detailed-routing-driven placement [[paper]()]
- (2017) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: NTUplace4dr: A detailed-routing-driven placer for mixed-size circuit designs with technology and region constraints [[paper]()]
- (2022) ACM/IEEE Design Automation Conference: Xplace: An extremely fast and extensible global placement framework [[paper]()]
- (2025) Annual Design Automation Conference: Differentiable Net-Moving and Local Congestion Mitigation for Routability-Driven Global Placement [[paper]()]
### Power-Aware Placement
- (2008) CRC Press: Handbook of algorithms for physical design automation [[paper]()]
- (2002) Prentice Hall: Digital integrated circuits [[paper]()]
- (2011) International Symposium on Physical Design: Obstacle-aware clock-tree shaping during placement [[paper]()]
- (2023) IEEE/ACM International Conference on Computer Aided Design (ICCAD): Clock aware low power placement [[paper]()]
- (2015) ACM Transactions on Design Automation of Electronic Systems (TODAES): ePlace: Electrostatics-based placement using fast fourier transform and Nesterov’s method [[paper]()][[code](https://github.com/limbo018/ePlace)]
- (2011) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: SimPL: An effective placement algorithm [[paper]()]
### Signoff-Aware Placement
- (2021) Siemens EDA Technical Report: Shifting Left In P&R With In-Design Signoff Fill For Faster And More Accurate Tapeouts [[paper]()]



## Shift-Left in CTS
### Aging-Aware CTS
- (2009) Design, Automation & Test in Europe Conference & Exhibition (DATE): Analysis and optimization of NBTI induced clock skew in gated clock trees [[paper]()]
- (2013) International Symposium on Quality Electronic Design (ISQED): A novel flow for reducing clock skew considering NBTI effect and process variations [[paper]()]
- (2024) JOURNAL OF SEMICONDUCTOR TECHNOLOGY AND SCIENCE: BTI Tolerant Clock Tree Synthesis using LP-based Supply Voltage Alignment [[paper]()]
- (2020) IEEE International Symposium on Circuits and Systems (ISCAS): Symmetrical Buffered Clock Tree Synthesis Considering NBTI [[paper]()]
- (2010) International Symposium on Physical Design: Skew management of NBTI impacted gated clock trees [[paper]()]
- (2010) Asia and South Pacific Design Automation Conference (ASP-DAC): Critical-PMOS-aware clock tree design methodology for anti-aging zero skew clock gating [[paper]()]
- (2013) ACM Transactions on Design Automation of Electronic Systems (TODAES): Low-power anti-aging zero skew clock gating [[paper]()]
- (2015) Great Lakes Symposium on VLSI: Electromigration-aware clock tree synthesis for TSV-based 3D-ICs [[paper]()]
### Congestion-Aware CTS
- (2019) International Conference on Recent Trends on Electronics, Information, Communication & Technology (RTEICT): Clock tree synthesis techniques for optimal power and timing convergence in soc partitions [[paper]()]
- (2013) International Journal of Advanced Research in Electrical, Electronics and Instrumentation Engineering: A Novel Clock Distribution Technology-Multisource Clock Tree System (MCTS) [[paper]()]
- (2010) IEEE Computer Society Annual Symposium on VLSI: Pattern-driven clock tree routing with via minimization [[paper]()]
### Thermal/Power-Aware Routing
- (2014) International Symposium on Low Power Electronics and Design: Buffered clock tree synthesis considering self-heating effects [[paper]()]
- (2011) IEEE Transactions on Very Large Scale Integration (VLSI) Systems: Fast power-and slew-aware gated clock tree synthesis [[paper]()]
- (2013) ACM Transactions on Design Automation of Electronic Systems (TODAES): Low-power anti-aging zero skew clock gating [[paper]()]
- (2019) ACM Transactions on Design Automation of Electronic Systems (TODAES): Thermal-aware 3D symmetrical buffered clock tree synthesis [[paper]()]

### On-CHip Variation(OCV)-Aware CTS
- (2011) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: Robust chip-level clock tree synthesis [[paper]()]
- (2003) Design, Automation and Test in Europe Conference and Exhibition (DATE): Reduced delay uncertainty in high performance clock distribution networks [[paper]()]
- (2003) International Symposium on Physical Design: Process variation aware clock tree routing [[paper]()]
- (2008) ACM Transactions on Reconfigurable Technology and Systems (TRETS): Statistical analysis and process variation-aware routing and skew assignment for FPGAs [[paper]()]
- (2014) Great Lakes Symposium on VLSI: OCV-aware top-level clock tree optimization [[paper]()]
- (2011) International Symposium on Physical Design (ISPD): Cross link insertion for improving tolerance to variations in clock network synthesis [[paper]()]
- (2011) Asia and South Pacific Design Automation Conference (ASP-DAC): Robust clock tree synthesis with timing yield optimization for 3D-ICs [[paper]()]

## Shift-Left in Routing

### ECO-Aware Routing
- (2021) IEEE International Conference on Computer Design (ICCD): Core-eco: Concurrent refinement of detailed place-and-route for an efficient eco automation [[paper]()]
- (2014) International Symposium on VLSI Design, Automation and Test: A power delivery network (PDN) engineering change order (ECO) approach for repairing IR-drop failures after the routing stage [[paper]()]
- (2001) IEEE/ACM International Conference on Computer Aided Design (ICCAD): Multilevel approach to full-chip gridless routing [[paper]()]
- (2012) Asia and South Pacific Design Automation Conference (ASP-DAC): ECO timing optimization with negotiation-based re-routing and logic re-structuring using spare cells [[paper]()]
- (2024) IEEE Transactions on Systems, Man, and Cybernetics: Systems: Timing-Driven Obstacle-Avoiding X-Architecture Steiner Minimum Tree Algorithm With Slack Constraints [[paper]()]
### EM-Aware Routing
- (2002) IEEE Transactions on Very Large Scale Integration (VLSI) Systems: Quantifying and enhancing power awareness of VLSI systems [[paper]()]
- (2024) International Conference on Advances in Computing, Communication and Materials (ICACCM): Hybrid Optimization Algorithms for Dynamic and Static Power Reduction in Low-Power VLSI Circuits [[paper]()]
- (2005) IEEE Transactions on Very Large Scale Integration (VLSI) Systems: POMR: A power-aware interconnect optimization methodology [[paper]()]
- (2005) Asia and South Pacific Design Automation Conference: Thermal-driven multilevel routing for 3-D ICs [[paper]()]
### Power/THermal-Aware Routing
- (2018) Great Lakes Symposium on VLSI: Electromigration Design Rule aware Global and Detailed Routing Algorithm [[paper]()]
- (2012) International Conference on Computer-Aided Design: Electromigration-aware routing for 3D ICs with stress-aware EM modeling [[paper]()]
- (2019) IEEE Transactions on Very Large Scale Integration (VLSI) Systems: EM-aware and lifetime-constrained optimization for multisegment power grid networks [[paper]()]
- (2024) Great Lakes Symposium on VLSI: An electromigration-aware wire sizing methodology via particle swarm optimization [[paper]()]
- (2018) Conference on Ph.D. Research in Microelectronics and Electronics (PRIME): Increasing EM robustness of placement and routing solutions based on layout-driven discretization [[paper]()]

## Shift-Left in Signoff
- (2024) Springer AI-Enabled Electronic Circuit and System Design: Harnessing Graph Learning for Efficient Timing Signoff [[paper]()]
- (2024) IEEE/ACM International Conference on Computer-Aided Design: One-for-all: An unified learning-based framework for efficient cross-corner timing signoff [[paper]()]
- (2023) IEEE International Conference on Artificial Intelligence Circuits and Systems (AICAS): RC-GNN: Fast and accurate signoff wire delay estimation with customized graph neural networks [[paper]()]
- (2023) ACM Transactions on Design Automation of Electronic Systems: Eco-gnn: Signoff power prediction using graph neural networks with subgraph approximation [[paper]()]
- (2022) Asia and South Pacific Design Automation Conference (ASP-DAC): A graph neural network method for fast ECO leakage power optimization [[paper]()]
- (2018) IEEE/ACM International Conference on Computer-Aided Design (ICCAD): Machine-learning-based dynamic IR drop prediction for ECO [[paper]()]
- (2025) ACM Transactions on Design Automation of Electronic Systems: Graph Neural Network-Based Glitch Rate Prediction at the Signoff Stage [[paper]()]


## Shift-Left for Verification and Testing
### Formal Verification
- (2017) Springer Formal System Verification: Formal verification—the industrial perspective [[paper]()]
- (2024) arXiv preprint: VeriCHERI: Exhaustive Formal Security Verification of CHERI at the RTL [[paper]()]
- (2024) Technical Report: A Deep Dive into Formal Verification Techniques for Ensuring Functional Correctness in Custom AI Accelerator Architectures at the Register-Transfer Level (RTL) [[paper]()]
- (2025) ACM International Conference on Architectural Support for Programming Languages and Operating Systems: RTL verification for secure speculation using contract shadow logic [[paper]()]
- (2021) Proceedings of the ACM on Programming Languages: Formal verification of high-level synthesis [[paper]()]
- (2013) Proceedings of the KNS 2013 spring meeting: Equivalence Checking between Pre-synthesis and Post-synthesis Programs by Using VIS [[paper]()]
- (2025) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: Hierarchical Formal Verification of Hardware [[paper]()]
- (2013) Latin American Test Workshop: Formal equivalence checking between high-level and RTL hardware designs [[paper]()]
- (2024) International Symposium on Formal Methods: A Case Study on Formal Equivalence Verification Between a C/C++ Model and Its RTL Design [[paper]()]
- (2018) Electronics: A survey on formal verification techniques for safety-critical systems-on-chip [[paper]()]
- (2021) IEEE/ACM International Symposium on Microarchitecture: Synthesizing formal models of hardware from RTL for efficient verification of memory model implementations [[paper]()]
- (2019) Euromicro Conference on Digital System Design (DSD): Formal verification methodology in an industrial setup [[paper]()]
- (2015) Encyclopedia of Information Science and Technology: Formal verification methods [[paper]()]
- (2025) arXiv preprint: Assertionforge: Enhancing formal verification assertion generation with structured representation of specifications and rtl [[paper]()]
- (2024) arXiv preprint: Towards llm-powered verilog rtl assistant: Self-verification and self-correction [[paper]()]
- (2025) IEEE European Test Symposium (ETS): Large Language Models (LLMs) for Verification, Testing, and Design [[paper]()]
- (2025) Design, Automation & Test in Europe Conference (DATE): Fveval: Understanding language model capabilities in formal verification of digital hardware [[paper]()]
- (2024) IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems: Rtlcoder: Fully open-source and efficient llm-assisted rtl code generation technique [[paper]()]
- (2024) IEEE/ACM International Conference on Computer-Aided Design: Openllm-rtl: Open dataset and benchmark for llm-aided design rtl generation [[paper]()]
- (2024) IEEE International Test Conference India (ITC India): Laag-rv: Llm assisted assertion generation for rtl design verification [[paper]()]
- (2025) arXiv preprint: SV-LLM: An Agentic Approach for SoC Security Verification using Large Language Models [[paper]()]
### Physical Verification
- (2024) Cadence Design Systems, Inc. Product Page: Innovus Implementation System [[paper]()]
- (2024) Siemens EDA Technical Report: Calibre Shift Left Solutions Optimize IC Design Flow Productivity [[paper]()]
- (2021) Siemens Digital Industries Software Technical Paper: A Game Changer for IP Designers: Design-Stage Verification [[paper]()]
- (2019) Synopsys, Inc. Technical Report: Faster and Smarter LVS for the SoC Era: Introducing Explorer LVS [[paper]()]


## Citation and Feedback

[TODO] bibtex for citation, and welcome for feedback
