## LITERATURE REVIEWs

### AN EXTENSIVE EVALUATION OF PDDL CAPABILITIES IN OFF-THE-SHELF LLMS (https://arxiv.org/pdf/2502.20175, by Kaustubh Vyas, Damien Graux, Sebastien Montella etc.)**

 LLMs are capable of translating natural language descriptions into syntactically valid PDDL representations. However, there are gaps in between gold-standard models and gold-standard models. Kaustubh et al. (2025) focused on seven major families, and explored their ability in reasoning capabilities and executing potential complete planning tasks from aspects of parsing, generating, and reasoning PDDL. Zero-shot prompting was applied in 13,000 (NL-instruction, PDDL-problem) pairs' experiments to ensure an unbiased assessment of the models without modifying states. The researchers pointed out that some models (e.g., ... ) demonstrate moderate proficiency in handling PDDL, while the majority (...) struggle to convert natural language instructions into fully correct PDDL representations. Some smaller LLMs like .., have disappointing performace in producting parsable PDDL.

several evaluation methods were applied to score the LLMs abilities in generating PDDL domains, problems and plans.


### Large Language Models as Planning Domain Generators**

### Exploring and Benchmarking Planning Capabilities of Large Language Models

[EXPLORING AND BENCHMARKING PLANNING CAPABILITIES OF LARGE LANGUAGE MODELS.pdf](https://github.com/user-attachments/files/21094318/EXPLORING.AND.BENCHMARKING.PLANNING.CAPABILITIES.OF.LARGE.LANGUAGE.MODELS.pdf)

**PDDL-based datasets**

**BlocksWorld**: BlocksWorld is a standard planning problem from International Planning Conference (IPC)-2000. This domain consists of a set of blocks, a table and a robot hand, where the goal is to move from one block configuration to another. A dataset for 3 to 7 blocks was generated. As detailed in the Appendix B.1, we produced 28k unique BlocksWorld samples. From these, 25.5k were randomly selected for the training set and 2,500 (around 9% of 25.5k) for the validation set. 

**Logistics**: Logistics is an AI planning problem from IPC-1998 expressed in PDDL that involves arranging the delivery of packages to their destinations using trucks within cities and airplanes between cities. The aim is to optimize transportation modes under constraints such as vehicle capacities and locations, showcasing model’s ability to manage multi-step logistics efficiently.

**Mini-Grid**: Mini-Grid is a task from Artificial Intelligence Planning Systems (AIPS)-1998, also expressed in PDDL. We create various floorplans with rooms containing random configurations of
key shapes. The goal then is for a robot to navigate from an initial position to a designated goal cell.


PDDL problems are solved using a classic planner Fast-Downward (https://github.com/aibasel/downward).


**natural language datasets:** Trip Planning and Calendar Scheduling tasks 

On these benchmarks, we assess LLM performance using **In-Context Learning (ICL)**, **Supervised Fine-Tuning (SFT)**, and **chain-of-thought (CoT)** methods for planning.

