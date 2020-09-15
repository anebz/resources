# [Intro to causal inference notes](http://www.causalcourse.com)

[![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg)](http://commonmark.org)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://GitHub.com/anebz/resources/graphs/commit-activity)
[![Ask me anything!](https://img.shields.io/badge/Ask%20me-anything-1abc9c.svg)](https://www.twitter.com/aberasategi)
[![GitHub Issues](https://img.shields.io/github/issues/Naereen/StrapDown.js.svg)](https://GitHub.com/anebz/resources/issues/)
[![PRs welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

* [Textbook for the course (pdf)](https://www.bradyneal.com/Introduction_to_Causal_Inference-Sep13_2020-Neal.pdf)
    - Changes regularly, check www.causalcourse.com for the latest update
* [Code for the textbook](https://github.com/bradyneal/causal-book-code)

## Table of contents

1. [Introduction](#1-introduction)
    1. Simpson's paradox: causal graphs
    2. Correlation does not imply causation: confounding
    3. What implies causation? potential outcomes and ATE
    4. Observational studies
2. [Potential outcomes](#2-potential-outcomes)
    1. Assumptions for identifiability
        1. Ignorability / exchangeability
        2. Conditional exchangeability / unconfoundedness
        3. Positivity
        4. No interference
        5. Consistency
    2. The adjustment formula
    3. Statistics terminology explanation
    4. A complete example with estimation
3. [Causal graphs](#3-causal-graphs)
    1. Bayesian networks and causal graphs
    2. Basic building blocks of graphs

--------------------------------------

## 1 Introduction

The goal of causal inference is to infer the effect of a treatment/policy on some outcome.

### 1.1. Simpson's paradox

Faced with a new disease and trying to minimize death, there are 2 treatments (T). A common one (A), and a scarce one (B). Patients can have a mild (0) or severe (1) condition (C). In the outcome (Y), the patient can either live (0) or die (1).

<div style="text-align:center"><img src="img/covid-27-0.png" width="85%"/></div>


**Simpson's paradox**: looking at just the total numbers, it seems like A is doing better than B, but looking at each specific condition, at mild and severe B does better. The paradox comes from unequal weighting: the total for T=A is heavily weighted by the mild cases, because there are so many more than severe cases. In T=B, the severe group has a much bigger weight.

> Which treatment do we choose? Depends on the causal structure of the problem.

Let us consider two scenarios: in scenario 1, **the condition is a cause of the treatment**, and both are a cause of the outcome. That means, the treatment is chosen based on condition, and outcome is determined by both the condition and the treatment.

<div style="text-align:center"><img src="img/scen1.png" width="30%"></div>

If a patient has C=0, they get T=A because doctors save the scarce treatment (B) for the severe cases. If a patient has C=1, they get T=B. Looking at the mortality rate table, most people with C=0 get T=A, and most people with C=1 get T=B.

**Condition confounds the effect of treatment on mortality**. To correct for this, we have to examine the relationship of T and Y among patients with the same condition. The better treatment is the one yielding lower mortality in each condition: treatment B.

----------------------------------------

In scenario 2, **treatment is a cause of condition**, and both are a cause of the outcome.

<div style="text-align:center"><img src="img/scen2.png" width="30%"></div>

If a patient gets T=B, they might wait a long time to take it because it is scarce, and the condition worsens to C=1. That is why among people with T=B, most of them have C=1, because they get sicker and transition from C=0 to C=1. With T=A, the patient gets it very fast and they remain in C=0. In this scenario, **T=A is preferred**.

### 1.2. Correlation does not imply causation

The course will use the term *association* to refer to statistical dependence. Causation is not all or none. For any given amount of association, some degree can be causal. The phrase "association is not causation" simply means that the amount of association and the amount of causation can be different.

> Sleeping with shoes on is strongly correlated with waking up with a headache. But both sleeping with shoes on and headache can be explained by a common cause: drinking the night before (this is called a confounder)

<div style="text-align:center"><img src="img/shoes.png" width="30%"></div>

Causal association states that the headache is caused by sleeping with shoes. The confounding association says that drinking affects both sleeping with shoes, and waking up with a headache. The association between shoes and headache is facilitated by the confounder. Total association (e.g. correlation) is the mixture of causal and confounding association. Both variables affect the outcome. This additional confounding association is why correlation does not imply causation.

We cannot properly estimate causation because the groups for both treatments are not comparable. Most people who sleep with their shoes on has been drinking, and most people sleeping without shoes has not been drinking.

### 1.3. Then, what does imply causation?

Given a headache, you can take a pill (T=1) or not (T=0). Each produces a different outcome: Yi(T=1) for no headache and Yi(T=0) for headache. *i* is used for one specific individual. The outcome is completely dependent on whether the patient takes the pill or not. The **causal effect** of taking the pill given a headache is the difference between the two potential outcomes, Yi(1) - Yi(0).

> A potential outcome Y(t) is different from the observed outcome Y in that not all potential outcomes are observed. All potential outcomes can potentially be observed.

*The fundamental problem of causal inference* is that once an action is taken (factual), you can't observe the the other action (counterfactual), and cannot compute the causal effect. You cannot observe the individual treatment effect (ITE). Which is why potential outcomes are used to obtain the causal effect. By taking many people, Y(t) becomes random and we can obtain the average treatment effect (ATE), taking the average over *i*: E[Y(1)] and E[Y(0)], and obtain the causal effect.

In the specific example of the headache and the pill, the difference between potential outcomes (ATE) is equal to the difference in conditional expectations: E[Y(1)] - E[Y(0)], which is a causal quantity obtained from the causal association between treatment and outcome. And in this example, the only conditional to the outcome is the treatment. Therefore, Y(1) = Y(T=1).

In general, because of the confounding association, E[Y(1)] - E[Y(0)] does not equal E[Y|T=1] - E[Y|T=0], because this is a mixture of confounding association and causal association, which is not causal since the condition has a confounding effect.

To obtain causation, we need to make groups comparable, we need to bypass the effect of condition in the treatment. **Randomized control trials (RCT)**randomly distribute the subjects into treatment group or control group, ensuring that condition cannot be a cause of the treatment. In RCT, the 'drunk people' are evenly distributed among the two groups. 

### 1.4. Observational studies

Sometimes it is not possible to randomize treatment in real-life scenarios. Some possible reasons:

* Ethical reasons (cannot randomize people to smoke to measure effect on lung cancer)
* Infeasability (cannot randomize countries into communist/capitalist systems to measure effect on GDP)
* Impossibility (cannot change a living person's DNA at birth to measure effect on breast cancer)

> How to measure causal effects in observational studies?

We can isolate the causal association by adjusting or controlling for confounders. When you control for the right variable W, and W is a sufficient adjustment set, the confounding association is blocked.

In the disease example, we adjust for the only available variable, condition. We can obtain E[Y(t)] = E[Y|do(T=t)] = E<sub>C</sub>E[Y|t, C] by averaging over C

> Application to the disease example from the beginning

Assuming the scenario 1, where condition is a cause for treatment, we marginalize over C (the only variable). Since C is discrete, we can take a sum over C and calculate the probabilities for each condition.

<div style="text-align:center"><img src="img/covid-27.png" width="85%"></div>

In the naive example (see first picture), the probability of the condition is wrong, because condition is a cause of treatment and it has not been taken into consideration. It only depends on the people taking the specific treatment. In this case, the probability of condition being mild equals all the people with this condition, divided by all the people in total. This probability looks *across* all treatments, across the whole dataset.

## 2 Potential outcomes

We can imagine a dataset with some individuals, where each one take one action and see a specific outcome. The counterfactual is not observed and we cannot calculate their individual ITE. In the naïve case, we can look at all individuals with treatment 1 (take the pill) and get the average. Same for treatment 0, and obtain the difference. This is the calculation of E[Y|T=1] - E[Y|T=0]. But this is an associational difference, not the ATE. We cannot do ATE because the groups of people choosing T=0 and T=1 are not comparable. The outcome of each group is determined by the condition of the group, the effects of the treatment and the condition are mixed together. If the condition (drunkenness, previous diseases etc.) was equally distributed, then we can use E[Y|T=1] - E[Y|T=0] to calculate the ATE.

<div style="text-align:center"><img src="img/ate.png" width="75%"></div>

What assumptions make the ATE equal to the associational difference?

### 2.1. Assumptions

> Ignorability / exchangeability

**Ignorability** says that the treatment assignment mechanism is ignorable, we can ignore the missing data, we can skip the question marks in the data under Y(1) and Y(0) in the image above. The outcomes of both treatments are independent of the treatment. There is no confounding, the covariates are not a cause of the treatment.

Another perspective to the same concept is **exchangeability**. The group A takes treatment 1, and have a certain expected outcome and vice versa for group B. Exchangeability means that if the groups are swapped, the expected values remain the same. And E[Y(1)|T=1] = E[Y(1)|T=0] = E[Y(1)]. Which means that the potential outcome Y(1) is independent of treatment. And same for Y(0). Both groups are comparable.

<div style="text-align:center"><img src="img/exch.png" width="50%"></div>

Making this assumption, we can reduce the ATE to the associational difference. E[Y(1) - Y(0)] = E[Y|T=1] - E[Y|T=0]. But it is not a very realistic assumption, because there is almost always confounding in the data. But this assumption can be done by running randomzed experiments.

> Conditional exchangeability / unconfoundedness

Usually the treatment groups are not exchangeable. But if we control for relevant variables by conditioning, then the groups can be exchangeable. The idea is that although the treatment and potential outcomes can be affected by confounding, within levels of X, they are not associated. Because exchangeability is not realistic, conditional exchangeability is used.

Exchangeability means that the outcome is independent with regards to the treatment. The confounding aspect X has no effect on T. **Conditional exchangeability/unconfoundedness** means that the outcome is independent with regards to the treatment, conditioned on X. Confounding exists, but it is blocked. This is an untestable assumption: we might have a conditional exchangeability conditioned on X, but if there is another confounder W, this is no longer true. We never know if there are more confounders.

The conditional ATE is E[Y(1) - Y(0) | X], which assuming the conditional exchangeability, we can turn into E[Y|T=1, X] - E[Y|T=0, X]. To obtain the normal ATE from this, we use the adjustment formula and we marginalize over X.

> Positivity

Can we simply condition on many covariates to achieve unconfoundedness? No, because it violates positivity, there is a tradeoff betweeen unconfoundedness and positivity.

**Positivity** says that for all values of covariates present in the population (anything with probability > 0), the probability of treatment is > 0 and < 1 for all values of treatment. 0 < P(T=1|X=x) < 1. In the populatoin X=x, if no one is given the treatmen we cannot observe the causal effect of the treatment, because no one got it. And same if everyone got the treatment.

Another perspective to positivity is **overlap**. If the population subsets that have received no treatmen (P(X|T=0)) and the population that have all received treatment (P(X|T=1)) have no overlap at all, there is a severe positivity violation. If they overlap, there is no violation among the covariates where there's overlap but in the covariates with no overlap, there is severe positivity violation. If they are completely overlapped, there is no positivity violation. This is the ideal situation for identifiability.

There is a positivity-unconfoundedness tradeoff: the more covariates you condition on, the more likely you are to satisfy unconfoundedness. But the more covariates you condition on, the worse positivity gets. If you want to estimate ATE (= sum_x(E[Y|T=1, X] - E[Y|T=0, X])) when you have a severe positivity violation, no overlap at all, you have to extrapolate because you are missing data. When summing over all x in the first part, there is no one who hasn't received treatment, there is no data to use. And same for the second part.

<div style="text-align:center"><img src="img/extrapolation.png" width="60%"></div>

> No interference

Another assumption is **no interference**: it says that an individual's potential outcome is only a function of the individual's own treatment. It doesn't depend on others' outcomes or treatments. Y<sub>i</sub>(t<sub>1</sub>, ...,t<sub>i</sub>, ...,  t<sub>n</sub>) = Y<sub>i</sub>(t<sub>i</sub>)

> Consistency

**Consistency** is the assumption that the observed outcome Y is actually the potential outcome under the observed treatment T.If T=t, then Y=Y(t), where Y is the observed outcome and Y(t) the potential outcome. If I get a specific treatment, then the potential outcome should be the same each time I get that treatment. If it's not, then the potential outcome isn't well defined.

### 2.2. The adjustment formula

**The adjustment formula**: by using these assumptions, the causal quantity can turn into a statistical quantity, going from the ATE to the associational difference, which is available data have since the probabilities of P(x, t, y) are known. A causal quantity (e.g. E[Y(t)]) is **identifiable** if it can be computed from a purely statistical quantity (e.g. E[(Y|t)]).

<div style="text-align:center"><img src="img/assumpt_formula.png" width="75%"></div>

### 2.3. Statistics terminology explanation

* Estimand: any quantity we want to estimate, ATE (causal estimand), statistical estimand
* Estimate: approximation of some estimand using data
* Estimation: process for getting from data and estimand, to estimate

<div style="text-align:center"><img src="img/id_est_flowchart.png" width="70%"></div>

### 2.4. A complete example with estimation

Example of estimation: effect of sodium intake on blood pressure. Treatment is sodium intake (continuous variable, depends on how much), outcome is systolic blood pressure (continuous variable). Covariates X: age and amount of protein excreted in urine. Using the data from [Luque-Fernandez et al. (2018)](https://academic.oup.com/ije/article/48/2/640/5248195), we know that the true ATE is 1.05.

Following the ATE simplification due to assumptions, we can use linear regression to learn E[Y|t, x], The code for this can be found in [Github](https://github.com/bradyneal/causal-book-code/blob/master/sodium_example.py) assuming linear parametric form Y = &alpha;T + &beta;X, to estimate &alpha; and &beta;.

<div style="text-align:center"><img src="img/est_ate.png" width="70%"></div>

This system has some limitations: assuming a linear parametric form, we assume that the causal effect is the same for all individuals. &beta; might be different. Yi(1) - Yi(0) = &alpha; * 1 + &beta;xi - &alpha; * 0 - &beta;xi = &alpha;

## 3 Causal graphs

This course handles directed acyclic graphs (DAGs). Nodes are connected through edges, paths can be established following these edges. Two nodes are immoral when they are both parents of a common node, but are not connected between them.

### 3.1. Bayesian networks and causa graphs

When obtaining the probability of a joint distribution, P(x1, ..., xn), we can decompose it as a product of P(x1) * P(x2|x1) * P(x3|x1, x2) and so on. Modelling all these parameters requires a lot of computation. But if x4 depends on x3 and on nothing else, P(x4|x1, x2, x3) = P(x4|x3) it becomes much simpler.

> Local Markov assumption

Given its parents in the DAG, a node X is independent of all of its non-descendants. The big product for the probability of the joint distribution can be simplified. With this assumption, each node depends only on its parents --> bayesian network factorization. This assumption refers to statistical independence.

<img src="https://render.githubusercontent.com/render/math?math=\Large P(x_1, ..., x_n) = \prod P(x_i | pa_i)">

With this assumption, there might be an edge between two nodes, but the nodes can be independent.

> Minimality assumption

This assumes the local Markov assumption, and also that adjacent nodes in the DAG are dependent. Connected nodes are not independent. This assumption refers to statistical dependence.

> Causal edges assumption

A variable X is a **cause** of a variable Y if Y can change in response to changes in X. In a directed graph, every parent is a direct cause of all its children. This referst o causal dependencies.

### 3.2. Basic building blocks of graphs

Graphical building blocks: chain, fork and immorality.

<div style="text-align:center"><img src="img/graph_block.png" width="50%"></div>

This is how association flows, dependence in chains and forks.

<div style="text-align:center"><img src="img/graph_dependence.png" width="50%"></div>

To obtain independence between X1 and X3, we can block the path

<div style="text-align:center"><img src="img/graph_dependence_block.png" width="50%"></div>

And so to prove conditional independence in chains, we can use these concepts

<div style="text-align:center"><img src="img/chain_condind.png" width="75%"></div>
