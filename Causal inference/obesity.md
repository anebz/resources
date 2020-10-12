# Does obesity shorten life? The importance of well-defined interventions to answer causal questions - Hernán & Taubman

## [Paper](https://www.nature.com/articles/ijo200882)

We argue that observational studies of obesity (high BMI, BMI >30) and mortality violate the condition of consistency of counterfactual (potential) outcomes, a necessary condition for meaningful causal inference, because:

1. They do not explicitly specify the interventions on BMI that are being compared
2. Different methods to modify BMI may lead to different counterfactual mortality outcomes, even if they lead to the same BMI value in a given person

This violation of consistency affects the ability to address two additional conditions, necessary for causal inference: exchangeability and positivity. 

The consistency violations not only preclude the estimation of well-defined causal effects but also compromise our ability to estimate ill-defined causal effects.

Randomized control trials (RCT) compare the distribution of the outcome Y of interest under 2+ interventions that are randomly assigned. If the distribution of the outcome varies by levels of the assigned intervention, we say that A has a causal effect on Y.

In this case, the obesity in RCT was not compared. BMI is not an intervention, but rather a potential result of many different types of intervention. If we intervene on physical activity, or nutrition, maybe we are improving BMI but that does not mean the obesity level is changed. We are not adjusting for relevant confounders. Not all interventions in BMI have the same effects on mortality.

In observational studies, we cannot observe the counterfactual. In this case, we do not konw how people have changed their BMI during the years. The counterfactual outcome is too vague a concept, which means that any causal contrast involving that counterfactual is ill defined. We cannot obtain a well-defined causal effect.

Exchangeability is expected in large randomized experiments, but unlikely to hold in many observational studies. In the RCT, exchangeability is held because everyone, regardless of their health or lifestyle, has the same probability of being assigned to the physical activity intervention. But in an observational study of physical activity, healthier and more health-conscious subjects are more likely to be in the exercise group. There is confounding for the effect of physical activity.

It is impossible to check if conditional exchangeability is met in an observational study. Investigators cannot possibly observe the subjects' counterfactual outcomes and cannot be certain that their efforts to measure all confounders have resulted in approximate conditional exchangeability. **This uncertainty is a fundamental shortcoming of causal inference from observational data.**

Apart from that, the consistency condition is violated. In order to achieve an approximate conditional exchangeability, we need to identify and measure the confounders for the effect of obesity on mortality. Diet, exercise, clinical diseases, complex genetic factors, environmental factors, etc. can all be confounders. It is very hard to measure all of these, which makes conditional exchangeability hard to achieve.

Conditional exchangeability cannot be guaranteed even when contrasting the outcome distribution under two well-defined interventions. But for many well-defined interventions (drug therapy, cigarette smoking), we can argue that the major common causes of exposure and outcome do not include complex physiological or genetic processes, or if they do, their proxies (indications for drug therapy) are sufficient to adjust for confounding. Confounders for well-defined interventions may then be easier to identify than those for ill-defined interventions.

Identifying all relevant confounders, and thus the causal effect of interest, is even harder for ill-defined interventions than for well-defined ones.

Causal effects cannot be defined, much less computed, in the absence of a well-defined intervention. Without a well-defined intervention, we can have a gross violation of the consistency assumption. Different methods to change BMI may lead to different counterfactual outcomes, even if they each achieve the same BMI value. The way we achieve the specific BMI we want can affect the outcome (death), completely separate from the weight.

Without well-defined counterfactual outcomes, the assumption of conditional exchangeability becomes even less likely to be met than usual. Attempting to control all confounding requires delving so far into the biological processes that we may encounter violations of the positivity assumption.

To conclude, if the goal is to inform policy, it may be better to focus on modifiable lifestyle behaviors than on obesity itself, regardless of whether we use observational studies or randomized trials.

The do operator means holding a variable constant. P(mortality=y|do(obesity=x)) is undefined, because the consequences of obesity depend on how we choose to manipulate it. This probability is not formally a function of x, but a one-to-many mapping. In its original conception, P(mortality=y|do(obesity=x)) doesn't depend on any choice of intervention: it is independent of how the event obesity=x came about.
