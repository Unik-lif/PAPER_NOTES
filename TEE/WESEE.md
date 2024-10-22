## Title: 
WESEE: Using Malicious #VC Interrupts to Break AMD SEV-SNP
### Basic info
## Main Authors:
Benedict Schluter, Shweta Shinde, ETH Zurich
### Published in: 
S&P 24
### Problems:
#### What is your take-away message from this paper?
Solid things, hands-on experiences.

Great implementations and demostratations are of great importances.
#### What is the motivation for this work (both people problem and technical problem), and its distillation into a research question? Why doesn’t the people problem have a trivial solution? What are the previous solutions and why are they inadequate?
AMD SEV-SNP adopts `#VC` for secure communications between the guest VM and the hypervisor, while the safety is not essured. Attackers might exploit `#VC` to harm the guest VM.

No studies have been launched yet. A novel attack.
#### What is the proposed solution (hypothesis, idea, design)? Why is it believed it will work? How does it represent an improvement? How is the solution achieved?
several constraints on launching the attacks:
1. ability to trigger certain #VC
2. operations the handler performs based on exit_reason 
3. knowledge on the timing of injecting the next #VC, avoiding crash of the CVM
#### What is the author’s evaluation of the solution? What logic, argument, evidence, artifacts (e.g., a proof-of-concept system), or experiments are presented in support of the idea?
Build strong attack primitives => conduct attacks.
#### What is your analysis of the identified problem, idea and evaluation? Is this a good idea? What flaws do you perceive in the work? What are the most interesting or controversial ideas? For work that has practical implications, ask whether this will work, who would want it, what it will take to give it to them, and when might it become a reality?
Hardcore, start from an initial seemed-trivial start point, but gain great ability to harm the CVM at the last.
#### What are the paper’s contributions (author’s and your opinion)? Ideas, methods, software, experimental results, experimental techniques...?
My opinion: Great contributions on the study of #VC, especially for the challenge parts: show great efforts on the challenges discussed in $3.2, these are hands-on experiences.

#### What are future directions for this research (author’s and yours, perhaps driven by shortcomings or other critiques)?
Mitigations in Hardware should be adopted.

Co-design of TEEs are important.

#### What questions are you left with? What questions would you like to raise in an open discussion of the work (review interesting and controversial points, above)? What do you find difficult to understand? List as many as you can, at least three, not including questions that can be answered quickly by searching the internet
Difficult to understand the details invovled, if you are not quite interested in the attack methods of the paper, this might seemed to be tedious.

Questions:
- How do you extend your paper like this? #VC seemed to be a quite easy-to-find phenonmenon, but the work to make this attack practical is of great efforts. What drive you do it?
- For similar work, how can you make it easier for readers to read without focusing on the details of your work?
### MY READING METHODS:
Not applying other methods, quite time-consuming, not a good way.

In fact even as I've paid some time, many details of the paper still seemed to hard for me since I didn't have some hands-on experiences on it.