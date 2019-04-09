# Paper Planning

## Title

**How to Ask a Causal Question**

Gets the general idea across, definitely open to change

## Halfway between an abstract and a TL;DR

There is consensus agreement that causal questions are different from questions of statistical inference. There's less agreement on what precisely constitutes a causal question. Potential outcomes and causal graphical models are two broad frameworks that can be used to pose causal questions, and each facilitates different kinds of questions.

There is also substantial interest in applying knowledge from the field of machine learning to the task of causal inference. Quite generally, machine learning techniques can be understood as a set of approaches to solving statistical decision problems. 

Here we propose that causal questions can be understood as causal decision problems, an extension of statistical decision problems. In doing this, we build a bridge between the worlds of causal inference and ordinary machine learning. Connecting to machine learning, we show that causal decision problems can be reduced to statistical decision problems if (?and only if?) the problem is "identifiable" (a property for which we are able to provide a more general definition than existing causal frameworks), while a reduction in the reverse direction is always possible. In connection with the causal inference literature, we show how the existing frameworks of causal Bayesian networks and potential outcomes can arise as special cases of causal prospects, which are the concept analogous to hypothesis classes in ordinary statistical decision problems.

## Srtucture plan

(Will be pruned)

### Literature survey:
 - Approaches to modelling causes
 - "Native" problems for each approach
 - Statistical decision problems

### Causal decision problems
 - Definition as extension of statistical decision problem
 - Simplified problems, identifiability and reduction to/from statistical decision problems
 - No free lunch causal

### Connection to other causal frameworks
 - Causal theories via universal conditional independence
 - Causal Bayesian networks as a special case
  - Soft interventions as a natural extension of the special case
  - Standard interventions imply Markovian models/non-standard interventions do not
 - "Full-blown" potential outcomes as a special case
  - "Simple" potential outcomes accomplishes most of the same things with less complication

 - Other interesting classes of framework: nested Markov models and single world intervention graphs

### CDP approach to Causal inference problems ("Library of examples")
 - Structure discovery
  - Faithfulness (speculative: faithfulness without CMC)
  - Linear non-Gaussian noise
  - Hidden causes (speculative)
  - Front door criterion (speculative)
 - Estimating causal effects
  - ETT/LATE


## Timeline

Deadline: May 23

Pretty damn good draft needed: May 16

 - April 8 - April 15: Feedback on overall story. Definition of CDP, statement/proof of reductions (mostly already written). CBNs from universal conditional independence (about 40% written already)
 - April 15 - April 22: Feature complete "Connection to other causal frameworks"
 - April 22 - April 29: At least 3 solid examples from "CDP approach to..." (some of these are partially already written)
 - April 29 - May 6: If I'm done and bored, I'll try to lift the theory to the continuous case.
 - May 6 - May 13: Feature complete draft
