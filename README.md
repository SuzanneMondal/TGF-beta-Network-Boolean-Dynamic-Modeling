# TGFb-Network-Boolean-Dynamic-Modelling

The models developed and the programs written are adapted for a six-node network based on TGF-beta signaling in cancer cells. A figure describing this network cited from the article titled, '[Boolean dynamic modeling of cancer signaling networks: Prognosis, progression, and therapeutics](https://www.che.iitb.ac.in/web/faculty/ganesh/pdfs/2021/booleanModelingCancerSignalingNetworks.pdf),' authored by Sherekar S. and Viswanathan G., published in Computational and Systems Oncology in 2021, is shown below.

![TGFB network](https://github.com/user-attachments/assets/c0c6bdc9-db2a-4be2-853c-c4d9ad217c4a)

### Boolean Dynamic Modeling Fundamentals

*1. State Transition Matrix (STM) and State Transition Graph (STG):*
An element 𝑇𝑖𝑗 of the state transition matrix (STM) specifies the probability of achieving a one-step transition from 𝑠𝑖 to 𝑠𝑗.
The state transition graph (STG) is a directed graph which includes all possible network states as nodes and the transitions between them as directed edges.

*2. Fixed Point Attractors (FPs) and graph paths:*
FPs are the network states that terminate a path from any node on the state transition graph (STG). A path on the STG means kicking off the dynamics of the graph's network at a certain network state and visiting several other states (following some directions on the graph), and finally stabilizing the dynamics of the network at an FP.

### Exploratory Analysis

*1. Node/Vertex Covers:*
A network’s node or vertex cover is a set of vertices that includes at least one endpoint of every edge of a graph. Node covers afford subgraphs that can be focused on, leaving out the graph-nodes that aren’t a part of the cover, to broadly study the effects of changes in the whole graph with simplification.

*2. Longest paths starting from every state:*
The longest paths starting from every network state could help in finding sweeping paths that cover a significant number of nodes. These paths can be used to understand how strongly connected nodes in the graph are.

*3. All paths on STG:*
The STG has paths starting from each graph-node--even the FPs have paths that terminate directly into themselves (self-loops). To find all the paths starting from every graph-node and ending in each graph-node could be hepful to gauge how likely it is for a network-state transition to occur from one to every other.

### Questions Attempted to be Answered

Q.1: Among the paths starting from each graph-node, how many can end in multiple FPs? Which graph-nodes appear most frequently among all paths?

Q.2: Among the paths starting from each graph-node, which FPs end how many paths?

Q.3: Of the 4 numeric data below, do two or more appear to be correlated: 
number of 'switched on' and 'switched off' statuses in a network-state
how many complete paths arise from a network-state 
how long paths arising from a network-state tend to be on average
how many distinct FPs appear across all paths arising from a network-state

Q.4: Is there anything notable about the network-states of the FPs? Are there any similarities between the network-states of the FPs?

Q.5: Is any graph-node's presence in a path steering the path to end with a specific FP, always? In other words, are there any graph-nodes that are biased towards a specific FP?

Q.6: Are there any cyclic paths in the STG that are cyclic (except those starting from the FPs)?

Q.7: Which nodes appear most abundantly across all paths (starting from each graph-node)? Are these nodes significant in any way?

Q.8: How frequently does a graph-node appear in a path's second-to-last position and what are the number of paths ending in each FP?

Q.9: Is it certain that there are no cyclic paths (except FPs' paths) across all paths in the STG?

---

**All files in this repository, except this one and 'Workspace_variables,' comprise codes and outputs. It is advisable to load 'Workspace_variables' into your Matlab workspace to ensure all programs run independently of the order in which the programs are executed. The file names follow the convention: n_abbreviation -- where n is a number that corresponds to a number in the sequence in which the programs were written and 'abbreviation' contains the abbreviated form of what is achieved through the program. The expanded form of 'abbreviation' can be found below in this file.**

*Matlab files contained in this repository:*
1_TGGen: State Transition Matrix (STM) and State Transition Graph (STG) generation
2_StatesFPsProbab: Numeric network-states and corresponding graph-node IDs (nodes); fixed point attractor (FPs) states and corresponding graph-node IDs; probabilities of settling into FPs from all initial states with unique first network update orders
3_LPDomNode: Longest paths generation; most appearing (dominant) nodes across longest paths; most appearing FPs across longest paths
4_AllPosPaths: All possible paths on the graph
5_Q1: Paths ending in multiple FPs and graph-nodes appearing most frequently (across all possible paths)
6_Q2: Number of times each FP end a path (acoss all possible paths)
7_Q3: Are there any correlations between a network-state's: 1) # switched on and switched off network-nodes, and/or 2) # complete paths arising from it, and/or 3) average length of complete paths arising from it, and/or 4) # distinct FPs appearing across its complete paths
8_Q4: Network-states of FPs
9_Q5: Specific FP biases
10_Q6: STG cyclic paths (excluding FP-sourced paths)
11_Q7: Graph-nodes appearing most frequently across all paths and their significance
12_Q8: Graph-nodes' frequency appearing at second-to-last position in path and # paths ending in each FP
13_Q9: Substatiate presence of no cyclic paths across all paths
