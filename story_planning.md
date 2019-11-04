# Story planning


## Motivation

 - Interpretational idiosyncracy and weird metaphysical commitments of existing approaches to causality
 - Aims of my approach:
 	- Founded on well established mathematics (probability theory, statistical decision theory)
 		- Easy to port a number of foundational results from SDT
 		- Speculative: more transparent connection between causality and other branches of mathematics = a better starting point for formalising causality
 	- Generic theory of causal inference that avoids causal assumptions in order to write the question down in the first place
 		- We can compare theories that are incommensurate in their conception of "causality"
 		- We can state results that must hold for any conception of causality if decision principles are accepted
 		- We may be able to avoid making *too many* causal assumptions
 		- We still make commitments to decision making principles (uncertainty represented with probability; expected utility accepted); plausible that these assumptions are independent of causal assumptions

## Approach

 - Motivation: add consequences to Wald (/Blackwell, Le-Cam)
 - Motivation: what is the "general type" of a CBN?
 - Result: CSDT, causal theories
 - Explaining CSDT & causal theories:
 	- Language: string diagrams
 		- Category theory axioms, coherence theorems, Jacobs' additions
 		- Exchangeability in a string diagram
 		- Fong & Jacob's relations of string diagrams to causal Bayesian networks
 	- Simple case: unconditional consequences
 	- Simple case: reused consequence ("policyless bandits")
 	- Causal Bayesian Networks
 		- How to convert
 		- Explaining the "cut" operation of Jacobs/Pearl's edge-cutting operation as a conjunction of causal assumptions
 	- Potential Outcomes
 		- Arbitrary choices; proposed solution
 		- Heckman's "policy-relevant treatment effects" as potential outcomes derived causal theories
 	- Examining a paradox: Newcomb's problem
 		- Necessary to reject preemption or strong symmetry
 		- EDT rejects admissibility, allows for weak symmetry

## Open/WIP questions

### Aim: well established foundations

 - From statistical decision theory:
 	- Complete class theorem
 	- Purification
 	- Theory dominance
 - Extending probabilistic notions to Markov kernels:
 	- Disintegration/conditional probability
 	- Conditional independence
 	- Bayesian inversion
 - Quantitative comparison of stochastic matrices


### Aim: generic theory of causal inference; what new things can we learn?

 - Theory comparison
 	- Extending dominance from statistical experiments
 - Novel identification results
 	- Are existing results special case of theory randomisations/coarsenings?
 	- Identification in the presence of randomisation/coarsening
 	- Identification in the presence of masking & inference from invariance
