## Title: 
00SEVen – Re-enabling Virtual Machine Forensics: Introspecting Confidential VMs Using Privileged in-VM Agents
### Basic info
## Main Authors:
Fabian Schwarz, Christian Rossow, CISPA
### Published in: 
Security 24
### Problems:
#### What is your take-away message from this paper?
Can be studied with [CPC](https://www.usenix.org/conference/atc24/presentation/chen-jiahao)

Scheduling should be taken into account.

Should Learn more by reading the security analysis and other parts, so a closer look might be needed.
#### What is the motivation for this work (both people problem and technical problem), and its distillation into a research question? Why doesn’t the people problem have a trivial solution? What are the previous solutions and why are they inadequate?
CVM is a double-sword, using it disable VMI.

First to re-enabling secure remote VMI for CVM.

Former forensic tools lack VMI features, and insecure (entitle full control)

Challenge is the forensic tools depend on the resources controlled by the untrusted hypervisor.
#### What is the proposed solution (hypothesis, idea, design)? Why is it believed it will work? How does it represent an improvement? How is the solution achieved?
hypothesis: hypervisor is not trusted. 

Idea: similar threat model to SVSM, and add remote introspection part to regulate.

Design: A natural design, **Key Part**: extend the hypervisor with VMPL-aware scheduling and I/O operations, therefore bind a virtual I/O device for VMI channel.

Solid with joint work in Network/OS kernel. Solution seems to be reasonable.
#### What is the author’s evaluation of the solution? What logic, argument, evidence, artifacts (e.g., a proof-of-concept system), or experiments are presented in support of the idea?
incorporate all compatible policies of a Paper. Remote Direct Memory Introspection

Compared to KVMi, add 20 % overhead at most for remove TLS.

Microbenchmarks: one set-up => ticks.

A thorough evaluation with macro and micro benchmarks.
#### What is your analysis of the identified problem, idea and evaluation? Is this a good idea? What flaws do you perceive in the work? What are the most interesting or controversial ideas? For work that has practical implications, ask whether this will work, who would want it, what it will take to give it to them, and when might it become a reality?
This idea bridges the gap between introspection and CVM.

The novelty is great (first work) but not significant (seems we have the similar paper lik CPC from SJTU in the same year).

**Below answers might need closer look**
Flaws: 

#### What are the paper’s contributions (author’s and your opinion)? Ideas, methods, software, experimental results, experimental techniques...?
- First bridge to VMI and CVM.
- My opinion: adds more security concerns, extend views like rootkit and others.

Ideas using scheduling to bind vCPU VMPL0 is cool.

#### What are future directions for this research (author’s and yours, perhaps driven by shortcomings or other critiques)?
Still the co-design is always the idea, but I would like to avoid to only talking about this.

The shortcomming might still be the primitives this paper use still are hard to implement, how to transfer the similar idea to other platforms? **The reliance on the modified hypervisor might not be a good idea.** As pointed by the author.

#### What questions are you left with? What questions would you like to raise in an open discussion of the work (review interesting and controversial points, above)? What do you find difficult to understand? List as many as you can, at least three, not including questions that can be answered quickly by searching the internet
**closer look**

### MY READING METHODS:
Skipping, done in 2 hours. => still need to improve.

But maybe a closer look should be needed, see Stanford notes later.