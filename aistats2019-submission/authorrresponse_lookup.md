 Pasted below. Weak reject, weak reject, reject. I think R1 and R2 have some useful feedback - they'd both like to see more about coarsening - but R3 doesn't seem to have understood it.

Some thoughts of my own: What are reasonable criteria for evaluating the importance of novel theoretical work? How can we drawn readers attention to these criteria? R2 in particular seems to have liked the paper, and understood a number of things I thought were important, but ultimately thought it wasn't good enough.



David

Some responses:

R1:
 - I think they underrate the significance of the relationship between PO and CSDT. I can agree it is well known that potential outcomes is related to interventions on the treatment variable, but the nature of this relationship is not well known - the convention P(Y_x)=P(Y|do(X=x)), for example, underspecifies the relationship. On the other hand, the fact that some assumption is necessary in order to apply potential outcomes to a decision problem is, to my knowledge, new. I also note that the causal theory I constructed for the potential outcomes model incorporates a Markov kernel for the conditional distribution P(W|Y_0,Y_1) - were this to appear in a graphical model, it would amount to the claim that the assignment W "depends causally" on the outcomes Y_0 and Y_1, which is not generally regarded as a valid claim by the graphical modelling community. There are solutions to representing counterfactual models with graphical models that typically involve assuming some deterministic model that takes noise as a source of input - granting that these may succeed, they are not straightforward and go much further than observing that the potential outcomes are related to interventions on the treatment variable.

 - I think there probably is a lot more interesting to say on the subject of coarsening, but also that it is quite important to be able to say exactly what you're assuming when you try to learn "stable causal relationships" without making specific commitments to what you can actually do. A lot of work on causal learning is precisely of this type.

 - Yes, there are interesting connections to reinforcement learning. Assuming the environment behaves according to a POMDP licenses a learner to adopt a certain class of causal theory. We have chosen to avoid discussing learning situations with a dynamic state in this paper.

 - I'm glad it's readable! Thank you for feedback on typos

R2:

 - I agree that avoiding commitments to causal philosophies at the outset is a strength of CSDT. I agree that it's not obvious exactly where this might pay off right now, but I also think that it is novel and significant that it can be done at all.

 - There are many questions we're interested in with regard to causality; it's definitely not obvious that CSDT is better for deciding what to condition on than existing graphical models. On the other hand, as we show, CSDT is able to formally characterise when a causal model is useful for a given decision problem. It's also not obvious how this could be done in general without essentially reinventing CSDT.

 - If I understand, the reviewer would have liked to see an example something like: introduce a causal model, discuss why we might a "realistic" causal theory is likely to be a coarsening of this, what sorts of coarsenings it might be and how we might choose a coarsening based on prior knowledge or other considerations. Knowing what examples people would be interested in seeing is useful to me, so thanks.

 - Thanks for feedback on typos.

Questions:

1. CSDT and SWIGs answer different questions - how to formalise causal decision problems vs how to graphically represent FFRCISTIGs (note that CSDT can be formalised entirely without string diagrams). That said, SWIGs may have an interesting relationship to causal theories. Two points: 1) SWIGs feature "two graphs in one" via node splitting with non-standard conditional independence rules, while causal theories explicitly draw out a pair of graphs (the experiment and the consequence). 2) SWIGs claim to make no assumptions that can't be tested by some intervention/RCT and causal theories explicitly represent the consequences of every available decision. My speculation is that any class of counterfactual distributions meeting the 'no extra assumptions' criterion is precisely the class of every joint distribution that features a particular causal theory as the marginals i.e. what SWIGs do with a class of counterfactual distributions is equivalent to what we do with a Markov kernel.

1a. A speculative answer on "graphs as they are generally used" vs causal theories: a particular choice of graph corresponds to a class of causal theory where the experiment (upper arm) and the consequence (lower arm) can be made to share some set of structural characteristics. I haven't got specific comments on factor graphs vs causal theories - there are many ways to represent the same thing with a picture, and we could probably represent causal theories with factor graphs that are augmented to distinguish probability measures from Markov kernels. I like string diagrams as their roots in probability theory are particularly transparent.

2. The given construction has an unnatural causal theory; you can definitely make some different choices about how you construct a theory from a PO model (though I think there are sensible reasons for preferring the given construction - other choices can lead to a PO model being very overparametrised, in which case it seems preferable to choose a simpler model to begin with). I will try to remove this ambiguity.

3. This paper is definitely more concerned with theoretical sufficiency. That said, causal theories are fundamentally compositions of Markov kernels, and compositions of Markov kernels are what probabilistic programming languages model, so that is one route to practical application of causal theories.

4. If I've understood the paper correctly: yes, object conditioning can be well represented by CSDT and there is a relevant and novel identifiability result. Thanks for this tip.

5. CSDT is built on the assumption that we're dealing with a "decision and consequence" problem. I agree it isn't obvious how to pose a conterfactual question as such a problem. I think it's worth distinguishing between counterfactual questions that arise from the choice of counterfactuals as a modelling tool, which I think would be no great loss, and counterfactual questions that are "ends in themselves" (for example, questions like "were X's actions responsible for Y?") Having made that distinction, how causal theories help to pose questions of responsibility is an open question.


R3:

 - The convention P(Y_x)=P(Y|do(X=x)) underspecifies the relationship between the PO model constructed in the paper and a hypothetically equivalent CBN. In the given example of the intention to treat effect this convention would leave unspecified elements of the PO model that have practical consequences. A key point was that there are a variety of choices to be made when applying a PO model to a causal decision problem, and your suggestion is one possibility. As it is a common convention, it may be worth raising explicitly and noting its shortcomings. Also, see the discussion of "non-causal Markov kernels" in response to R1.

 - I agree potential outcomes and counterfactuals in Pearl's framework are different in that Pearl's framework includes both counterfactuals and interventions. However, Pearl does appear to accept that potential outcomes is a legitimate scheme for posing counterfactual questions and no notion of intervention is needed to construct potential outcomes models, as we show explicitly. The claim that arbitrary choices are necessary doesn't depend on our model in particular but on the fact that any scheme that provides statistical experiments but not consequence maps cannot solve causal problems without additional assumptions.

 - This paper presents a new means of representing causal decision problems and causal assumptions that does not require prior commitments to a philosophy of causality. We do not regard its contribution to be the application of causal reasoning to decision problems; indeed its contribution could be said to be the application of decision problems to causal reasoning. There is a lot of work in causality that is explicitly or implicitly concerned with decision making - this is why we think it is reasonable to take decision problems to be a foundational assumption. The suggested references are relevant in the sense that they also consider causal reasoning and decision problems, but I don't agree that they're unusually relevant compared to the wider literature on causal inference and decision theory.

 - We focussed on do-interventions as they're the most common type of intervention; there are many variants to be found in the literature. There are also extensions of CBNs that use more general types of graph (e.g. mDAGs, CPDAGs).  We consider the fact that every interventional model can be represented by a causal theory to be an important feature of CSDT, so we can add some comments on how variants of CBNs can be accommodated.

Questions

    1. [Summary] Please summarize the main claims/contributions of the paper in your own words.
        - This paper introduces Causal Statistical Decision theory (CDST), a generalization of statistical decision theory to consider consequences of decisions. The authors instantiate the Causal Bayesian Networks and Potential Outcomes frameworks in their new theory and point out similarities and differences. This is followed by a discussion about the "realism" of the induced theories and a notion of coarsening. 
    2. [Detailed Comments] Please enter a detailed review describing the strengths and weaknesses of the submission.
        - One of the main contributions of the paper, as highlighted by the authors in the introduction, is the representations of CBNs and PO as causal theories and a discussion of their differences. The novelty of this discussion is fairly minor however---it is well understood that potential outcomes in the way formulated here relate only to interventions on the treatment variable, as opposed to on every node. Moreover, no examples of CDST is given beyond CBNs and POs which begs the question: what have we gained? The authors do not point toward a particular direction towards "furthering our understanding" in the discussion section either.

        - The discussion of coarsening and its relation to the difference between intention-to-treat and received-treatment effects is interesting but doesn't go very far. It seems clear that we can represent this difference in CDST but not what this adds over representations in other frameworks.

        - It seems that the decision theory perspective should be related to the reinforcement learning/POMDP view of causality and decisions, yet this is not discussed in the paper. Much like the proposed framework, POMDPs allow for reasoning about consequences of decisions and their utility.

        - The paper is well-written and reads well despite consisting to a large extent of defining new notation and redefining established quantities. There are quite a few typos however, (e.g., missed slashes in \mathbf in a few places, the final sentence in the proof of Theorem 4.2, etc). 
    3. [Score] Please provide an overall score for the submission.
        Weak Reject: Borderline, tending to reject
    4. [Questions for the Authors] Please provide questions for authors to address during the author feedback period and point out which improvement would improve your score.
        Where do you see this work having impact in a way that existing frameworks will not? What is the independent strength of this work? 
    5. [Review Summary] Please enter a 1-2 sentence summary of your review explaining your overall score.
        The authors fail to motivate the usefulness of the proposed new framework beyond describing old frameworks in a new way. 
    6. [Reproducibility] Are the experiments (if present) detailed enough to allow reproducibility?
        N/A
    7. [Code] Was the code made available by the authors?
        No
    8. [Expertise] Please rate your expertise on the topic of this submission.
        High: Reviewer has published on the topic.
    9. [Confidence] Please rate your confidence in the score assigned.
        High: Reviewer has understood the main arguments in the paper, and has made high level checks of the proofs.

Reviewer #2
Questions

    1. [Summary] Please summarize the main claims/contributions of the paper in your own words.
        A generalization of causal inference using statistical decision theory into causal statistical decision theory.

        POs and DAGs from the perspective of CSDTs.
    2. [Detailed Comments] Please enter a detailed review describing the strengths and weaknesses of the submission.
        The paper uses statistical decision theory to develop what they call, Causal Statistical Decision theory. The theory provides a descriptive way of formalization joint distributions over different aspects of causal decision theories.

        This was an entertaining paper to read, to say the least. The paper poses causal decision making in the most generalized form that I have seen, which is both good and bad. It is good because it allows for reasoning without subscribing to a particular philosophy. I think the issue is that I am not sure as it stands CSDT and string diagrams make it easy to reason about the various issues that arise in causal inference practice, like what to condition on.

        I think the idea of rich causal theories, while a natural part of the paper, seemed a bit superfluous for me, considering that it is later said that realistic theories are what is required and then DAGs and POs may be the same in that sense.

        I particularly enjoyed the discussion about coarsening. While abstract, I think this is what grounds the whole paper for me. There should be more discussion about coarsening. For example, the most interesting part for me was the idea of reusability and how to generate coarsened causal theories and pick one that makes sense to the practitioner. Discussing the ability to add constraints to such generation in this process would've been a home run.

        Overall, while enjoyed reading the paper, I'm not sure it is of sufficient practical import as I understand it now.



        Writing :

        Moreover, please consider revising the notation in the paper to make it easier to follow.

        While I think I managed to infer the notation, there are a bunch of places where bolding is missing. considering that this is a significant distinguishing detail, this is an issue in the paper.

        For example, what are X_C, Y_C, W_C? counterfactuals?

    3. [Score] Please provide an overall score for the submission.
        Weak Reject: Borderline, tending to reject
    4. [Questions for the Authors] Please provide questions for authors to address during the author feedback period and point out which improvement would improve your score.
        1. Please add discussion about SWIGs: https://www.csss.washington.edu/Papers/wp128.pdf
        I would like to see why the authors suppose CSDT may be a better to look at POs and DAGs than SWIGs.

        1a. Moreover, there seems to a connection between the provided string diagrams and factor graphs. Can you comment?

        2. I am not sure I agree with the claim that POs have unnatural causal theories because the consequence maps are not given. This may be a consequence of the proposed formalization of the PO framework right?

        3. How do the authors foresee practitioners using CSDT in practice? I had trouble following the paper which makes me think it is more for theoretical sufficiency rather than practical use.

        4. Is there an easy way to frame object conditioning into CSDT ? http://auai.org/uai2019/proceedings/papers/393.pdf

        5. If I wanted to compute a counterfactual estimate, given a CSDT, how would I do it? Interventional estimates were clear.
    5. [Review Summary] Please enter a 1-2 sentence summary of your review explaining your overall score.
        I think the theory is worth exploring more but I am not sure how to contextualize this in existing work.
    6. [Reproducibility] Are the experiments (if present) detailed enough to allow reproducibility?
        NA
    7. [Code] Was the code made available by the authors?
        No
    8. [Expertise] Please rate your expertise on the topic of this submission.
        Medium: Reviewer is well-read on the topic, but has not published in it.
    9. [Confidence] Please rate your confidence in the score assigned.
        High: Reviewer has understood the main arguments in the paper, and has made high level checks of the proofs.

Reviewer #3
Questions

    1. [Summary] Please summarize the main claims/contributions of the paper in your own words.
        This paper proposes causal statistical decision theory by extending statistical decision theory via employing consequences and utilities instead of loss.
        The authors showed that how causal Bayesian network and potential outcome model can induce causal theories.
    2. [Detailed Comments] Please enter a detailed review describing the strengths and weaknesses of the submission.

        First, it is great to see how the two central causal frameworks can be interpreted using very different formulation with respect to causal theory.
        Although the paper is not written quite friendly to the researchers not familiar with such notation, I somehow managed to understand the central theme of the paper.
        However, the paper seems to contain several errors in regards to CBNs and their connections to causal theory.
        Hence, I would like to point out several problems, which hurt the credibility of the claims presented in the paper.


        — (Misrepresenting CBN & PO)
        The term ‘counterfactual’ used in (the simplest form of) potential outcome framework is more similar to ‘interventional’ in Pearl’s framework.
        That is, the term ‘counterfactual’ is not the same as the ‘counterfactual’ used in Pearl’s framework.
        In the PO, Y(0) and Y(1) is nothing but the value of Y given do(X=0) and do(X=1), respectively.
        (Note that there is a subtle issue since Pearl’s full-fledged model is Structural (or Functional) Causal Model. One cannot say ‘counterfactual’ with a CBN. It must be an SCM.)
        Hence, several sentences the authors mentioned are wrong:
        e.g.,
        “Against Pearl’s claim that counterfactual models subsume interventional ones, we find that arbitrary choices must be made in order to represent potential outcomes models as causal theories. “
        “Rather than occupying different levels of a hierarchy, each yields a different kind of rich causal theory. “

        Further, the potential outcome working with an assignment mechanism is no different from a conditional distribution P(X|W) where W is a ‘backdoor admissible variables’ used in a CBN.
        A ’backdoor criterion’ is one of the graphical conditions connecting P(Y|do(X)) with P(V) (where V are observed variables)
        In other words, PO framework (as presented in the paper) is a CBN where W is treated as a single variable (e.g., high-dimensional) & G = {W→X, W→Y, X→Y}.
        Whether a variable is manipulable or not is constraints residing outside the representation of CBN.


        — (No proper literature review for work in CBN:)
        Work on the optimization over a causal Bayesian network exists.
        LB’2018, LB’2019.
        These papers concern about optimization over CBNs (strictly speaking, SCM) even when there are non-manipulable variables.
        In the paper, there exists a single variable ‘Y’ which represents utility, but it is trivial to define a variable computing utilities.
        The sentence, “For example, a CBN G defines an intervention operation for every random variable that has been represented as a node of G“
        As I mentioned earlier, it is not a CBN, but the authors who allowed that every variable is intervenable.
        In the paper, ITT is also plausibly represented (an example of the canonical instrumental variable model is given.)

        Further,
        do-intervention is only one type of intervention mainly used in CBN literature.
        However, soft-intervention (or stochastic intervention) has been in the literature for more than a decade. (see Tian 2008)
        It allows the change of mechanism based on observed covariates.


        Minor comments.

        J^*_{MM} and J^*_{Mm}
        mathbf not properly used twice.
        side of4 → side of Eq. (4)
        an more realistic → a more realistic
        measure over over this set → measure over this set
        missing a space before reference ( Bayesian networks(Bishop 2006) & influence diagrams(Dawid, 2002) )


        References

        Tian 2008 Identifying Dynamic Sequential Plans, J. Tian, in Proceedings of the Conference on Uncertainty in Artificial Intelligence (UAI), 2008.
        LB’2018 Structural Causal Bandits: Where to Intervene? S. Lee, E. Bareinboim NeurIPS-18. In Proceedings of the 32nd Annual Conference on Neural Information Processing Systems, 2018.
        LB’2019 Structural Causal Bandits with Non-manipulable Variables S. Lee, E. Bareinboim AAAI-19. In Proceedings of the 33rd AAAI Conference on Artificial Intelligence, 2019.
    3. [Score] Please provide an overall score for the submission.
        Reject: Clearly below the acceptance threshold
    4. [Questions for the Authors] Please provide questions for authors to address during the author feedback period and point out which improvement would improve your score.
        no specific question.
    5. [Review Summary] Please enter a 1-2 sentence summary of your review explaining your overall score.
        An interesting question answered through the lens of causal theory, but failed to capture the essence of Pearl's framework.
    6. [Reproducibility] Are the experiments (if present) detailed enough to allow reproducibility?
        no.
    7. [Code] Was the code made available by the authors?
        No
    8. [Expertise] Please rate your expertise on the topic of this submission.
        Low: Reviewer has seen talks and read a few papers on the topic.
    9. [Confidence] Please rate your confidence in the score assigned.
        Medium: Reviewer has understood the main points in the paper, but skipped the proofs and technical details.

