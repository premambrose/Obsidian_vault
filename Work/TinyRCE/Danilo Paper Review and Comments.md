- ## Needs to be addressed before 9th Feb
	- [x] **English quality to be improved**
	- [x] Paper organization (results, experimental setup and implementation) to be improved
	- [x]  Main differences in a table of learning vs inferencies of tinyRCE
	- [x] Catastrophic forgetting vs forgetting mechanism, classes without forgetting the past one. 
	- [x] Introduction is disconnected from proposed solution (needs improvement)
		- We shall make clearer that the need is to learn classes as they are experienced by the user and not using the classic paradigma to collect the data in data set and the perform supervised learning with back prop, which is the current practice. The latter implies that the set of classes is preset in advance while we need to learn as they go in order to have a more flexible approach more personalizable
	- [x] Fig. 3 (RCE structure) is missing
	- [x] Include [paper](https:openreview.net/forum?id=zGvRdBW06F5) about advances in training at microcontroller-scale
	- [x] Compare with [Paper](https://openreview.net/forum?=id=zGvRdBW06F5)
	- [x] Explain why 25 times feature reduction using the feature extractor.
	- [x] Move related work on hypershperical classifier to "Related works" section
	- [x] Theoritical MACC for train CNN and RCE in section VII is not explained clearly
	- [x] Add explanation to two phases in learning ( 1. Record, feature conversion, store & 2. training RCE with features stored before in memory)
	- [x] References are sometimes used incorrectly (Need to check the review for which  paper)    ![[Pasted image 20230205211239.png]]
	- [x] Remove concept drift from paper (maybe in future works)
		- [x] not made clear the sequence learning- testing with respect to the classes learnt  in which of these sessions in figure 2

- ## Coding and Simulations

	- [x] Experiment varying size of feature extractor (CNN_FE_BP)
	- [x] To explain how the datasets mimicked Concept drift scenarios
	- [x] Catastrophic forgetting vs forgetting mechanism needs to be addressed
	- [x] The experiment setup on continual learning is not fully relevant to showcase the solution

- ## Could be added
	- [x] Algorithm to show Continuous Pruning and Learning setup 
	- [x] Another dataset ([KWS](https://arxiv.org/abs/1711.07128))