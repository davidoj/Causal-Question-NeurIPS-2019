Joint response to R1 and R1:

We believe these reviewers have provided a broadly accurate summary of the various elements of the paper, but we feel we've been unsuccessful in communicating how these elements fit together and their importance.

A brief recap: a CBN induces a rich causal theory, this is not our construction. Once you draw a DAG and give it a probability space, you get a model of interventions on every node whether you want it or not. While we are careful to note that we do require an element of interpretation to induce a PO theory, the complexity of this theory comes from the model on the science and the selection function, which are both fundamental elements of the version of PO we are interpreting. If we were to adopt the convention suggested by some reviewers - that the PO theory should admit only "hard interventions" on the selection function - we would find that the theory is dramatically overparametrised. Like CBNs, a PO model gives us more detail than we usually need - again, whether we want it or not. 

One response to these observations might be to presume that CBNs and PO are "inefficient" theories that provide a great deal of unnecessary detail. In this paper, we speculate instead that both approaches are deliberately putting a line bewteen what should be "changeable" and what should be "not changeable" - an interpretation supported by writings from key proponents of each school, which we quote. If we acknoweldge that such a division ought to be made, we implicitly raise two questions: how do we know that we have permitted enough "changeability", and how do we benefit from preventing some things from changing? We offer a formal answer to the first question, and a partial answer to the second. A causal theory induced from some causal model is "changeable" enough for a given decision problem if it can be coarsened to a causal theory suitable for that decision problem. On the other hand, a more flexible causal theory also imposes a weaker constraint on causal theories suitable for a given decision problem. At the extreme end, a saturated causal theory can be universally coarsened, but also imposes no constraint at all on viable theories for the given decision problem. We acknowledge that our treatment of this second point was quite cursory, and will work clarifying its importance to the whole story.

CSDT is necessary for this formalisation and the formalisation is stronger due to adopting CSDT:
 - Interventions and counterfactuals are given by the causal assumptions one makes. Decisions, on the other hand, are imposed by the problem to be solved. It only makes sense to ask how we can get from a causal model to a model relevant for a given decision problem if we specify the given decision problem - that is, even if we start with CBNs or POs, we would need to add all the elements of CSDT in order to define the notion of "coarsening" to begin with
 - Because we avoid making causal commitments in the formulation of CSDT, Theorem 7.2 is applicable to all causal decision problems, not just those where we accept a particular notion of intervention. That is, this result is stronger as a result of the lack of causal commitments CSDT makes



 > R1: This paper introduces Causal Statistical Decision theory (CDST), a generalization of statistical decision theory to consider consequences of decisions. The authors instantiate the Causal Bayesian Networks and Potential Outcomes frameworks in their new theory and point out similarities and differences. This is followed by a discussion about the "realism" of the induced theories and a notion of coarsening.

A key feature of CSDT is that it allows for causal reasoning without prior commitment to causal assumptions. This is why we believe it is significant that CSDT can model both Causal Bayesian Networks and Potential Outcomes (the latter subject to caveats noted in the paper). 

Causal theories induced by standard approaches don't simply model decision problems, they entail much more besides (directly modelling a decision problem is what we mean by "realistic", we will clarify this point). We provide a formal description of when these rich models are nonetheless useful for decision problems, a feature of causal modelling that is considered to be one of its key advantages and up until now lacked a formal statement.

> One of the main contributions of the paper, as highlighted by the authors in the introduction, is the representations of CBNs and PO as causal theories and a discussion of their differences. The novelty of this discussion is fairly minor however---it is well understood that potential outcomes in the way formulated here relate only to interventions on the treatment variable, as opposed to on every node. Moreover, no examples of CDST is given beyond CBNs and POs which begs the question: what have we gained? The authors do not point toward a particular direction towards "furthering our understanding" in the discussion section either.

There are many causal theories that are not causal theories induced by either potential outcomes or CBNs as constructed in the paper. However, we don't consider representative generality alone to be an especially important feature of CSDT. We could, for example, postulate a generalisation of CBNs that admit state and ancestor dependent interventions. Such a generalisation induces causal theories that are essentially saturated - there is an intervention yielding every possible consequence. As we mention at the end of the paper (a point which we will expand on), a saturated causal theory is uninformative - via coarsening, we can induce any causal theory for a given decision problem, and so assuming that the relevant theory is a coarsening of a saturated theory tells us nothing at all. We can make this tradeoff explicit - and neither CSDT nor PO can - precisely because CSDT doesn't regard "causes" as fundamental - which depend on what you assume about interventions - but instead considers "decisions" fundamental, which depend on the constraints of the given problem. Formalising this tradeoff is something CSDT can do that neither CBNs nor PO can do, because the latter would need to be extended to handle decision problems, and I would be surprised if such an extension yielded anything other than a special case of CSDT.

We would also like to clarify that the PO induced causal theory is not equivalent to a CBN induced causal theory with intervention limited to the treatment assignment. The provision for inducing particular dependences of the treatment assignment on both state and possible outcomes is beyond the reach of the simple family of CBNs we discuss, and indeed beyond the reach of many CBNs with generalised interventions (interventions inducing arbitrary dependence on state and on possible "future" outcomes is nontrivial). The ability to model this type of dependence may be useful if our available decisions influence incentives - we wish to know how individuals will select themselves into or out of treatment based on their judgments of possible future outcomes, and we don't know exactly what their judgements will be.

> The discussion of coarsening and its relation to the difference between intention-to-treat and received-treatment effects is interesting but doesn't go very far. It seems clear that we can represent this difference in CDST but not what this adds over representations in other frameworks.

See above for how we plan to extend this.

> It seems that the decision theory perspective should be related to the reinforcement learning/POMDP view of causality and decisions, yet this is not discussed in the paper. Much like the proposed framework, POMDPs allow for reasoning about consequences of decisions and their utility.

It's true that CSDT is related to reinforcement learning; our view is that reinforcement learning assumes a certain family of causal theories. We avoided discussing this as it requires us to deal with the sequential nature of reinforcement learning problems, but we will add a mention of the connection.

> Where do you see this work having impact in a way that existing frameworks will not? What is the independent strength of this work? 

See the discussion above about generality vs informativeness of causal theories as an answer to this question that is already in the paper, though we acknowledge that we need to expand on it to make the point explicitly.


> A generalization of causal inference using statistical decision theory into causal statistical decision theory.
> POs and DAGs from the perspective of CSDTs.
> The paper uses statistical decision theory to develop what they call, Causal Statistical Decision theory. The theory provides a descriptive way of formalization joint distributions over different aspects of causal decision theories.
> This was an entertaining paper to read, to say the least. The paper poses causal decision making in the most generalized form that I have seen, which is both good and bad. It is good because it allows for reasoning without subscribing to a particular philosophy. I think the issue is that I am not sure as it stands CSDT and string diagrams make it easy to reason about the various issues that arise in causal inference practice, like what to condition on.

Taken together, we feel that this is a good summary. Regarding the benefits of CSDT, please see our response to reviewer #1: the generality of our CSDT us to formalise a tradeoff between the generality and informativeness of particular causal theories.

> I think the idea of rich causal theories, while a natural part of the paper, seemed a bit superfluous for me, considering that it is later said that realistic theories are what is required and then DAGs and POs may be the same in that sense.

> I particularly enjoyed the discussion about coarsening. While abstract, I think this is what grounds the whole paper for me. There should be more discussion about coarsening. For example, the most interesting part for me was the idea of reusability and how to generate coarsened causal theories and pick one that makes sense to the practitioner. Discussing the ability to add constraints to such generation in this process would've been a home run.

The fact that CBN and PO induced theories are rich is better understood as a feature of the CBN and PO frameworks than as a decision of ours. If you draw a DAG and give it a probability space, you get a model of interventions on every node whether you want it or not. Similarly, the model on the science is an integral element of the PO approach we studied, but it is very overparametrised if all we care about is hard interventions on the treatment assignment. One response to these observations might be to presume that CBNs and PO are inefficient theories that model a whole lot of useless stuff for no apparent reason. Our response was to suppose that their richness is not an accident, and they are making deliberate tradeoffs in terms of what is modeled as changeable and what is not changeable - an interpretation supported by writings from key proponents of each school. The idea of coarsening captures when the CBN or PO accounts have incorporated "enough" flexibility. The size of the set of possible coarsenings captures how much we have simplified the problem by accepting the CBN or PO account of *what doesn't change*. This latter point was, admittedly, given very cursory treatment and we will expand on it to make it clearer.

> Overall, while enjoyed reading the paper, I'm not sure it is of sufficient practical import as I understand it now.

We hope that you might reconsider this judgement in light of our clarifications above. To reiterate, the tradeoff between flexibility and informativeness is something that can only be formalised with CSDT.

> Please add discussion about SWIGs: https://www.csss.washington.edu/Papers/wp128.pdf. I would like to see why the authors suppose CSDT may be a better to look at POs and DAGs than SWIGs.

CSDT answers questions such as the above that SWIGs cannot. There are interesting connections to SWIGs that are not fully worked out at this stage (for example, SWIGs, like CBNs, use non-standard interpretations to represent "two graphs in one", one graph for the statistical experiment and one graph for consequence model; CSDT, on the other hand, draws both graphs in full), but we will add a mention.

> 1a. Moreover, there seems to a connection between the provided string diagrams and factor graphs. Can you comment?

We agree that there are connections between various graphical languages but we have no specific comments at this stage.

> I am not sure I agree with the claim that POs have unnatural causal theories because the consequence maps are not given. This may be a consequence of the proposed formalization of the PO framework right?

Please see the detailed response above for the reasoning behind this choice.

> How do the authors foresee practitioners using CSDT in practice? I had trouble following the paper which makes me think it is more for theoretical sufficiency rather than practical use.



        4. Is there an easy way to frame object conditioning into CSDT ? http://auai.org/uai2019/proceedings/papers/393.pdf

        5. If I wanted to compute a counterfactual estimate, given a CSDT, how would I do it? Interventional estimates were clear.