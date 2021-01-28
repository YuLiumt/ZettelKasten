## Bayes' theorem

$$
p(\theta \mid d)=\frac{p(d \mid \theta) p(\theta)}{p(d)}
$$

where we refer to $p(\theta \mid d)$ as the posterior of the data, $p(d \mid \theta)$ the likelihood, $p(d)$ the evidence, and $p(\theta)$ the prior. 

## Prior

The prior $p(\theta)$ describes an understanding of the system before knowing anything about the data $d(t)$; the choice of prior is very important, as a poorly chosen prior will strongly bias the entire parameter estimation and likely lead to flat posteriors or wildly incorrect parameter estimations.

## Likelihood

The likelihood $p(d \mid \theta)$ is the probability of obtaining the data $d(t)$ observed, given the parameters $\theta$ being considered. In essence, it is the model we choose for the data, and the part we have most control over.

## Evidence

The denominator $p(d)$ is called the evidence, and is a normalisation factor which can be used to directly compare one model of the data with another.