# [Intro to causal inference](causalcourse.com) - Brady Neal

## 1. Introduction

The goal is to infer the effect of a treatment/policy on some outcome.

### Simpson's paradox

Faced with a new disease and trying to minimize death, there are 2 treatments (T). A common one (A), and a scarce one (B). Patients can have a mild (0) or severe (1) condition (C). In the outcome (Y), the patient can either live (0) or die (1).

<img src="img/covid-27-0.png" width="85%">

**Simpson's paradox**: looking at just the total numbers, it seems like A is doing better than B, but looking at each specific condition, at mild and severe B does better. The paradox comes from unequal weighting: the total for T=A is heavily weighted by the mild cases, because there are so many more than severe cases. In T=B, the severe group has a much bigger weight.

> Which treatment do we choose? Depends on the causal structure of the problem.

Let us consider two scenarios: in scenario 1, **the condition is a cause of the treatment**, and both are a cause of the outcome. That means, the treatment is chosen based on condition, and outcome is determined by both the condition and the treatment.

<img src="img/scen1.png" width="30%">

If a patient has C=0, they get T=A because doctors save the scarce treatment (B) for the severe cases. If a patient has C=1, they get T=B. Looking at the mortality rate table, most people with C=0 get T=A, and most people with C=1 get T=B.

**Condition confounds the effect of treatment on mortality**. To correct for this, we have to examine the relationship of T and Y among patients with the same condition. The better treatment is the one yielding lower mortality in each condition: treatment B.

----------------------------------------

In scenario 2, **treatment is a cause of condition**, and both are a cause of the outcome.

<img src="img/scen2.png" width="30%">

If a patient gets T=B, they might wait a long time to take it because it is scarce, and the condition worsens to C=1. That is why among people with T=B, most of them have C=1, because they get sicker and transition from C=0 to C=1. With T=A, the patient gets it very fast and they remain in C=0. In this scenario, **T=A is preferred**.

### Correlation does not imply causation

The course will use the term *association* to refer to statistical dependence. Causation is not all or none. For any given amount of association, some degree can be causal. The phrase "association is not causation" simply means that the amount of association and the amount of causation can be different.

> Sleeping with shoes on is strongly correlated with waking up with a headache. But both sleeping with shoes on and headache can be explained by a common cause: drinking the night before (this is called a confounder)

<img src="img/shoes.png" width="30%">

Causal association states that the headache is caused by sleeping with shoes. The confounding association says that drinking affects both sleeping with shoes, and waking up with a headache. The association between shoes and headache is facilitated by the confounder. Total association (e.g. correlation) is the mixture of causal and confounding association. Both variables affect the outcome. This additional confounding association is why correlation does not imply causation.

### Then, what does imply causation? Potential outcomes

Given a headache, you can take a pill (T=1) or not (T=0). Each produces a different outcome: Yi(T=1) for no headache and Yi(T=0) for headache. *i* is used for one specific individual. The outcome is completely dependent on whether the patient takes the pill or not. The **causal effect** of taking the pill given a headache is the difference between the two potential outcomes, Yi(1) - Yi(0). 

> A potential outcome Y(t) is different from the observed outcome Y in that not all potential outcomes are observed. All potential outcomes can potentially be observed.

*The fundamental problem of causal inference* is that once an action is taken (factual), you can't observe the the other action (counterfactual), and cannot compute the causal effect. You cannot observe the individual treatment effect (ITE). Which is why potential outcomes are used to obtain the causal effect. By taking many people, Y(t) becomes random and we can obtain the average treatment effect (ATE), taking the average over *i*: E[Y(1)] and E[Y(0)], and obtain the causal effect.

In the specific example of the headache and the pill, the difference between potential outcomes (ATE) is equal to the difference in conditional expectations: E[Y(1)] - E[Y(0)]. This is a causal quantity obtained from the causal association between treatment and outcome. And in this example, the only conditional to the outcome is the treatment. Therefore, Y(1) = Y(T=1).

In general, because of the confounding association, this does not equal E[Y|T=1] - E[Y|T=0], because this is a mixture of confounding association and causal association, which is not causal since the condition has a confounding effect.

In the shoe sleepers example, the condition (drinking) makes the groups not comparable because most shoe sleepers drank the night before, whereas the others did not. The outcome of each group is determined by the condition of the group, the effects of the treatment and the condition are mixed together.

To make the groups comparable, to bypass the effect of condition in the treatment, in randomized control trials (RCT) the subjects are randomized into treatment group or control group, ensuring that condition cannot be a cause of the treatment. In RCT, the 'drunk people' are evenly distributed among the two groups. **A randomized experiment is one way of getting causation.**

### Observational studies

Sometimes it is not possible to randomize treatment in real-life scenarios. Some possible reasons:

* Ethical reasons (cannot randomize people to smoke to measure effect on lung cancer)
* Infeasability (cannot randomize countries into communist/capitalist systems to measure effect on GDP)
* Impossibility (cannot change a living person's DNA at birth to measure effect on breast cancer)

> How to measure causal effects in observational studies?

We can isolate the causal association by adjusting or controlling for confounders. When you control for the right variable W, and W is a sufficient adjustment set, the confounding association is blocked.

In the disease example, the only variable is condition, so we adjust for that. We can obtain  E[Y(t)] = E[Y|do(T=t)] = E<sub>C</sub>E[Y|t, C] by averaging over C

> Application to the disease example from the beginning

Assuming the scenario 1, where condition is a cause for treatment, we have to marginalize over C (the only variable). Since C is discrete, we can take a sum over C and calculate the probabilities for each condition.

<img src="img/covid-27.png" width="85%">

In the naive example (see first picture), the probability of the condition is wrong, because condition is a cause of treatment and it has not been taken into consideration. It only depends on the people taking the specific treatment. In this case, the probability of condition being mild = all the people with this condition, divided by all the people in total. This probability looks *across* all treatments, across the whole dataset.
