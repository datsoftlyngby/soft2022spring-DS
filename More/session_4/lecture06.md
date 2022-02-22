Lecture 6
=========

Why do we care about statistics?
--------------------------------

The main reason for our interest in statistics is to gain insights into
our data. These insights will help us build better models and avoid
embarrassing mistakes.

![xkcd on wedding cakes and
statistics.](_static/wedding-cakes.png){.align-centeralign-center}

Overview of Statistics and Probability
--------------------------------------

Let\'s first observe how the various terms relate to one another.

![Relation between Statistics and
Probability](_static/population_vs_sample.png){.align-centeralign-center}

::: {.glossary}

Descriptive Statistics

:   Descriptive statistics is what we can say about a sample by
    observing the sample itself. This is somewhat limited and mostly
    consists of summarizations of the data, e.g. like aggregates on a
    column in a database table.

Inferential Statistics

:   Inferential statistics is what we can say about a population based
    on what we know about a sample. That means that we can *infer*
    (deduce or conclude from evidence rather than from explicit
    statements) about the population based on a smaller sample.

Probability

:   Probability is what we can *generally* say about samples from a
    population. While important and interesting, we are not very
    concerned with probability in this course.
:::

A good explanation of the difference between descriptive and inferential
statistics is given here:

[Taylor, Courtney. \"The Difference Between Descriptive and Inferential
Statistics\"](https://www.thoughtco.com/differences-in-descriptive-and-inferential-statistics-3126224)

Probability
-----------

Probability Theory provides a framework for reasoning about the
likelihood of events.

::: {.glossary}

Experiment

:   In Probability Theory an experiment yields an outcome out of a set
    of possible outcomes, e.g. the experiment of tossing a coin has the
    set of possible outcomes [{head, tail}]{.title-ref}.

Sample Space S

:   The set of possible outcomes of an experiment is called a sample
    space. The sample space for tossing a coin is [{head,
    tail}]{.title-ref}.

Event E

:   An event is a possible outcome of an experiment, e.g. the event
    *head* when we toss a coin.

Probability of Outcome P(s)

:   The probability of an outcome is always greater than 0 and less than
    1, and the sum of the probability of all possible outcomes is 1, see
    the equations below.
:::

$$0 \leq P(s) \leq 1$$$$\sum p(s) = 1$$

Descriptive Statistics
----------------------

Descriptive statistics falls into two areas: *centrality* and
*variability*.

### Centrality

[n]{.title-ref} is the number of elements.

::: {.glossary}

Mean

:   The mean, or average, is most useful for homogeneous data (without
    outliers). The mean is given:
:::

$$\mu = \overline{x} = \frac{1}{n}\sum x$$

::: {.glossary}

Median

:   The exact middle value of the data set. If [n]{.title-ref} is even
    the median is the mean value of the two middle elements.
:::

::: {.glossary}

Mode

:   The mode is the most frequent element.
:::

### Variability

::: {.glossary}

Standard Deviation

:   The squares differences between the individual elements and the
    mean. It is calculated differently, depending on whether it is the
    population or sample. For the sample we are constrained by the need
    to change the number of observations to 1 less than the actual
    number of observations. This reduces the underestimating in our
    estimate and brings it closer to the probable population variance. A
    degree of freedom is lost every time we constrain the calculation.
    So changing the value of n means we lose a degree of freedom.
:::

For population: degrees of freedom lost = 0:

$$\sigma = \sqrt{\frac{\sum(x_i-\mu)^2}{n}}$$

For sample: degrees of freedom lost = 1:

$$s = \sqrt{\frac{\sum(x_i-\mu)^2}{n - 1}}$$

::: {.glossary}

Variance

:   Variance is a measure of the dissimilarity between samples.
:::

For samples: degrees of freedom 0:

$$s^2 = \frac{\sum(x_i-\mu)^2}{n}$$

For populations: degrees of freedom 1:

$$s^2 = \frac{\sum(x_i-\mu)^2}{n - 1}$$

### Correlation Analysis

Correlation analysis is concerned with relations between variables, e.g.
if one goes up, what happens to the other?

::: {.glossary}

Correlation Coefficient

:   A correlation coefficient is statistic measure of the degree that
    one variable Y is a function of another variable X. The correlation
    coefficient value ranges from -1 to 1, where 1 indicates perfect
    correlation, 0 indicates no correlation, and -1 indicates perfect
    negative correlation.
:::

The correlation coefficient needs interpretation, as there are no hard
or well-defined definitions of the coefficients. However, a good
starting point for interpretation could be:

  Lower Bound   Higher Bound   Effect Size
  ------------- -------------- -------------
  .00           .19            Very Weak
  .20           .39            Weak
  .40           .59            Moderate
  .60           .79            Strong
  .80           1.0            Very Strong

::: {.note}
::: {.title}
Note
:::

Bounds can be positive or negative.
:::

::: {.warning}
::: {.title}
Warning
:::

Correlation does not imply Causation!
:::

![xkcd on
correlation.](_static/correlation.png){.align-centeralign-center}

Python implements several correlation functions such as Pearson
Coefficient (for linear relationships) and Spearman Rank Coefficient
(for ranks and monotonic relationships).

A correlation matrix is a good way of getting an overview of several
variables.

![Correlation
Matrix.](_static/correlation-matrix.png){.align-centeralign-center}

::: {.note}
::: {.title}
Note
:::

Correlation analysis can not show correlations that are dependent on
complex combinations of other variables.
:::

```{=html}
<iframe src="_static/basic-statistics-np.html" width="700px" height="500px"></iframe>
```
Inferential Statistics
----------------------

As mentioned above inferential statistics is used to infer about the
population based on our knowledge about a sample. It is based on much
more complex mathematics than descriptive statistics, but we will not go
into detail with that. We use inferential statistics to test hypotheses.

::: {.glossary}
Null-Hypothesis

> The hypothesis that an observed difference (as between the means of
> two samples) is due to chance alone and not due to a systematic cause.
:::

An example:

-   Hypothesis: drinking large amounts of alcohol makes you fall over.
-   Null-Hypothesis: people will fall over the same amount whether they
    drink alcohol or not.

We usually take the approach of *rejecting the null-hypothesis* rather
than confirming our hypothesis.

Two terms are of very high importance in inferential statistics:

::: {.glossary}

Confidence Interval

:   The confidence interval is the limits within which a certain
    percentage (say 95% or 99%) of sample means will fall.

Significance

:   Statistic significance is a test of how likely we are to get our
    results given the null-hypothesis, or how likely we are falsely
    rejecting the null hypothesis. You can think of it as a measure of
    the usefulness of the research.
:::

In hypothesis testing we can make *Type 1* and *Type 2* errors:

![Type 1 and Type 2
Errors.](_static/type1-type2-error.jpg){.align-centeralign-center}

::: {.glossary}

Type 1 Error

:   Falsely rejecting the null-hypothesis - false positive.

Type 2 Error

:   Falsely accepting the null-hypothesis - false negative.
:::

Finally, we need to define the concepts of [dependent]{.title-ref} and
\`independent variables\`:

::: {.glossary}

Dependent variable

:   A variable (most often denoted Y) whose value depends on that of
    another variable. In an experiment it is a variable that we are not
    trying to manipulate.

Independent Variable

:   A variable (often denoted [X]{.title-ref}) whose variation does not
    depend on that of another variable. In an experiment it is the
    variable that we are trying to manipulate.
:::

Choosing a Statistical Test
---------------------------

We will not cover the various statistical tests, but you can use the
diagram below to help you choose the correct statistical test.

![Choosing a Statistical
Test.](_static/choosing-statistical-test.png){.align-centeralign-center}

Extra Reading on Statistics and Probability
-------------------------------------------

You can find a lot more information on statistics and probability in the
book below. The book is not required reading, but you can use it for
look up when you do projects.

[Downey, Allen B. \"Think Stats - Probability and Statistics for
Programmers, 2nd
Edition\"](https://greenteapress.com/wp/think-stats-2e/)
