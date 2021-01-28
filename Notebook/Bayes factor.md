# Bayes factor

$$
\frac{P\left(M_{2} \mid D\right)}{P\left(M_{1} \mid D\right)}=\frac{P\left(D \mid M_{2}\right)}{P\left(D \mid M_{1}\right)} \frac{P\left(M_{2}\right)}{P\left(M_{1}\right)}
$$

Here the ratio $P(M_2) / P(M_1)$ is the prior, and is often assumed to be equal to $1$ if no compelling prior evidence favors one model over another. The ratio $P(D~|~M_2) / P(D~|~M_1)$ is the Bayes factor, and is the key to Bayesian model selection.

The Bayes factor can be computed by evaluating the integral over the parameter likelihood:
$$
P(D \mid M)=\int_{\Omega} P(D \mid \theta, M) P(\theta \mid M) d \theta
$$
This integral is over the entire parameter space of the model, and thus can be extremely computationally intensive.

These samples give us a good idea of what the posterior for each model looks like, but we still must integrate this posterior to find the Bayes factor.

The tricky part of the integration is choosing the integration limits correctly; fortunately we can use the MCMC traces to find appropriate values.

For very high dimensional models

* [Nested Sampling](https://en.wikipedia.org/wiki/Nested_sampling_algorithm) is a sampling-based algorithm like MCMC, which is specially designed to compute Bayes factors.
* [Reversible Jump MCMC](https://en.wikipedia.org/wiki/Reversible-jump_Markov_chain_Monte_Carlo) (also see *bridge sampling*) can be used to sample multiple models in the same MCMC chain, so that the Bayes factor can be estimated directly from the joint trace 
* 