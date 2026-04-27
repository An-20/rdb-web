A **population** is all the individuals of interest.
A **sample** is taken from the population to estimate a population parameter - some characteristic of the population, such as the population mean, or population standard deviation. 
A sample must be **representative** to provide a good estimate - the distribution of values in the sample must be roughly the same as the whole population. **Bias** is where the sample is not representative of the whole population.

## Sampling methods (all *IS*)

###### Simple random sampling
In simple random sampling, every possible sample of the population of a given size has an equal chance of being selected. This can be done by using a random number generator to select individuals from the population. Simple random sampling provides a true random sample with no bias, but can only be used if a list of the entire population is known.

###### Systematic sampling
In systematic sampling, individuals are selected at regular intervals from a list of the population ordered in some way, with a random starting point. This can prevent clustering of data, but the sample is less random as independence is lost.

###### Stratified sampling
In stratified sampling, the population is split into groups based on relevant factors, then within each group random sampling is performed, in proportion to the size of that group compared the overall population. Stratified sampling produces a representative sample over the factors identified, but requires additional information, which can be time consuming and expensive.

###### Cluster sampling
In cluster sampling, the population is split into clusters based on convenience (e.g. individuals located physically close to each other), and then randomly choosing some clusters to research further. Cluster sampling can be cheaper and easier as only some clusters are considered. However, cluster sampling is less accurate as choosing an unrepresentative cluster can affect the outcome.

###### Opportunity sampling
In opportunity sampling, respondents are chosen based on availability and convenience - only people who are willing to take part are sampled. This does not produce a random sample and can introduce bias, but is cheap and convenient.

###### Quota sampling
In quota sampling, the population is split into groups based on relevant factors (like in stratified sampling), then within each group opportunity sampling is used. The sample will be representative over the identified factors, as the researchers can control exactly how many of which groups are sampled. However, there can be biases introduced from the opportunity sampling, and the results may not be generalisable to the wider population.


## Measures of central tendency

|               | Mode                                                                                          | Median                                                           | Mean                                                                                                              |
| ------------- | --------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Advantages    | Very easy to find <br><br>Not affected by outliers <br><br>Can be used for non-numerical data | Easy to find for ungrouped data <br><br>Not affected by outliers | Easy to find <br><br>Uses all the values <br><br>The total for a given number of values can be calculated from it |
| Disadvantages | Does not use every value <br><br>May not exist (or there may be more than one)                | Does not use every value <br><br>Often not understood            | Outliers can distort it <br><br>Has to be calculated                                                              |
| Used for      | Non-numerical data <br><br>Finding the most likely value                                      | Data with outliers                                               | Data with values that are spread in a balanced way                                                                |

An **outlier** is (*IS*):
- any value more than 1.5 interquartile ranges away from the nearest quartile
- any value more than 2 standard deviations away from the mean

The vertical axis on a histogram is frequency density. The area under a histogram represents frequency.

## Measures of spread
**Standard deviation**, $\sigma$, is the root mean square deviation from the mean (*given*):
$$
\sigma = \sqrt{\frac{\Sigma(x - \bar x)^2}{n}}
= \sqrt{\frac{\Sigma x^2}{n} - \bar x^2}
$$

For grouped data, the standard deviation and variance can be estimated using a calculation using the midpoint of each group (*given*):
$$
\sigma = \sqrt{\frac{\Sigma f(x - \bar x)^2}{f}}
= \sqrt{\frac{\Sigma fx^2}{f} - \bar x^2}
$$
