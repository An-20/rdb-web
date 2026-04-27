## Binomial distribution
The **binomial distribution** is a discrete probability distribution. The conditions for a binomial distribution are:
- fixed number of trials
- each trial has two outcome: success or fail
- each trial is independent
- each trial has a constant probability of success

A variable $X$ distributed binomially with number of trials $n$ and probability of success $p$ is denoted:
$$
X \sim B(n, p)
$$

For a given $X = x$, the probability is given by:
$$
P(X = x) = \begin{pmatrix}n\\x\end{pmatrix}p^x(1-p)^{n-x}
$$

#### Normal approximation
A binomial distribution $X \sim B(n, p)$, $q = 1 - p$ can be **approximated by a normal distribution** with parameters:
$$
\mu = np\quad\quad\sigma^2=npq
$$
This holds for sufficiently large $n$, such that $np \gt 5$ and $nq \gt 5$.

#### Binomial hypothesis testing
A **hypothesis test** is used to determine whether the value of a population parameter, such as the population mean or standard deviation, has changed from an assumed one.

When hypothesis testing the binomial distribution, the parameter being tested is the probability or proportion of success, $p$:
- State the **null** ($H_0$) and **alternate** ($H_1$) hypotheses, defining any parameters.
- State the distribution that the test statistic should follow.
- Calculate the probability of observing the given value or more extreme of the test statistic, finding the $p$-value. 
- Compare the $p$-value to the significance level. For two-tailed tests, compare the $p$-value to half the significance level.
- If the $p$-value is less than the significance level, reject the null hypothesis.
- State the conclusion in context, making sure to not use overly certain language, e.g. "there is sufficient evidence to suggest..."

Alternatively, the **critical region** can be used. The critical region is the set of values of the test statistic that should lead to rejecting the null hypothesis, bounded by the critical values. The other values form the **acceptance region**.

The **actual significance level** is the probability of incorrectly rejecting the null hypothesis, It is the probability of being in the critical region, and is always $\le$ to the significance level.

## Normal distribution
The **normal distribution** is a continuous probability distribution that models many real-world situations. A variable $X$ distributed normally with mean $\mu$ and variance $\sigma^2$ is denoted:
$$
X \sim N(\mu, \sigma^2)
$$

The following facts about the normal distribution are expected (*IS*):
- About two-thirds of values lie in the range $\mu \pm \sigma$.
- About 95% of values lie in the range $\mu \pm 2\sigma$. 
- Almost all (99.97%) of values lie in the range $\mu \pm 3\sigma$.
- The points of inflection of the normal curve lie at $x = \mu \pm \sigma$.

#### Z-score
The **Z-score** is the number of standard deviations above the mean that a value $x$ is.
$$
z = \frac{x - \mu}{\sigma}
$$
The **Z-score** can be used to find unknown means or standard deviations.

#### Normal hypothesis testing
The **sample mean**, denoted $\bar X$, or possibly $\bar X_n$, is a random variable described by a distribution for the mean of $n$ observations. The sample mean is distributed differently to the original normal:
$$
X \sim N(\mu, \sigma^2) \implies \bar X_n \sim\left(\mu, \frac{\sigma^2}{n}\right)
$$
The variance is divided by $n$, so the standard deviation is divided by $\sqrt n$. 

When hypothesis testing the normal distribution, the parameter being tested is the population mean, $\mu$.
- State the null ($H_0$) and alternate ($H_1$) hypotheses, defining any parameters.
- State the distribution that the test statistic should follow.
- Use the distribution to find the probability of an outcome as or more extreme occurring, finding the $p$-value. Compare the $p$-valuje against the significance level.
- Alternatively, find the critical region for a given significance level and check if the data lies within the critical region.

## Correlation coefficient
When testing whether there is correlation between two variables, the parameter being tested is the **population correlation coefficient**, $\rho$, by looking at values of the sample correlation coefficient, $r$:
- State the null ($H_0$) and alternate ($H_1$) hypotheses. These will be in terms of $\rho$.
- Look up in the table the critical value for $r$ for the given significance level, sample size, and tail type.
- Compare $|r|$ against the critical value, If $|r|$ is greater, then reject $H_0$.
