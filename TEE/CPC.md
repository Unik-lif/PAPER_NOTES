## Title: 
CPC: Flexible, Secure, and Efficient CVM Maintenance with Confidential Procedure Calls
### Basic info
## Main Authors:
Jiahao Chen, Haibo Chen, SJTU IPADS
### Published in: 
ATC 24
### Problems:
#### What is your take-away message from this paper?
Maintenance of the CVM => what will involve and what each of these methods do.

read more literartures.
#### What is the motivation for this work (both people problem and technical problem), and its distillation into a research question? Why doesn’t the people problem have a trivial solution? What are the previous solutions and why are they inadequate?
Maintenance of the CVM.

Maintenance support for CVM.

3 problems:
1. Not sufficient flexibility
2. TCB enlarge 
3. significant performance

Sum: choice of the maintenance operations is wrong. First, performance degradation. Second, unable to run (strong tolerance requirements.)

#### What is the proposed solution (hypothesis, idea, design)? Why is it believed it will work? How does it represent an improvement? How is the solution achieved?
extends the semantics of vCPU scheduling => host invocations of maintenance procedures.

pre-allocate hvCPU (Host virtual CPU) along with gvCPU, and scheduling hvCPU when we want to have needs to maintain the CVM.

Using HyperCall to bridge the CVM and the host, less costly than the former or possible ideas mentioned before.

Implementation is done in SVSM and CCA platform.
#### What is the author’s evaluation of the solution? What logic, argument, evidence, artifacts (e.g., a proof-of-concept system), or experiments are presented in support of the idea?
Multiple-VMs in maintaince.

Use case study methods: list three typical scenerios, evaluate them, to support the idea.

#### What is your analysis of the identified problem, idea and evaluation? Is this a good idea? What flaws do you perceive in the work? What are the most interesting or controversial ideas? For work that has practical implications, ask whether this will work, who would want it, what it will take to give it to them, and when might it become a reality?
The maintainence problem can be solved using remote module in Cloud Platform, 00SEVen.md (Security' 24) pointed that.

The idea here extends the semantics and kinda break our conventions to use vCPU, which is interesting.

Yes, it is a good idea.

My concerns might lay on the demand of maintainence, so why maintainence of the CVM is important? Why when we build CVM, the cloud platform might not be so concerned on this kinda of problem and didn't propose their own ways to do this at the cost of sleeping vcpus.

Guess cloud platform providers might need this paper to study the necessarities of the CPC, or efficient maintainence.
#### What are the paper’s contributions (author’s and your opinion)? Ideas, methods, software, experimental results, experimental techniques...?
Contributions:
1. analysis on dilemma of mainstream CVM maintenence
2. CPC design is elegent

Methods:
1. Creatively put the CPC in the Guest VM, and then find methods to tackle the obstacles.
2. Aimed at a good point to mitigate current problem, but not like an incremental work. => A new design instead of the main-stream design.

Experimental results:
1. Not only the result, but also provide another optimized version
2. Multi-Platforms
3. Cases study to show the performance
#### What are future directions for this research (author’s and yours, perhaps driven by shortcomings or other critiques)?
Resources utilization. (Author's and Mine.)
#### What questions are you left with? What questions would you like to raise in an open discussion of the work (review interesting and controversial points, above)? What do you find difficult to understand? List as many as you can, at least three, not including questions that can be answered quickly by searching the internet
More details about the maintainence

differences between introspections and maintainences.

Difficult to understand: Base knowledge and security analysis part.

### MY READING METHODS:
Skip the 2.6. section, and skim the 7. section.

cost nearly 3 hours.