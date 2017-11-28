# MEETING NOTES
Discussion points for weekly meeting with supervisors.


## 1 - PAPERS AND RESEARCH

1.  Passing the **next bit test** is equivalent to passing all polynomial-time
    statistical randomness tests.
1.  **Next bit test is theoretical** (it is expressed in terms of "all possible
    polynomial-time algorithms"). If a CSPRNG can be shown to pass the next-bit
    test we know the output also passes statistical tests for randomness, but
    algorithmically showing proof of passing the theoretical test is unfeasible.
2.  The **Sadeghiyan-Mohajeri test** builds a "pattern tree" of an input, and
    using that tree, computes the probability of predicting the next bit in the
    pattern at any point.
3.  The **practical next-bit test** (PNT) is a better implementation of the SM
    test. This should set basis for discrimination.
4.  If the model passes the PNT, then it should pass all the tests in the NIST
    test suite. The NIST test suite can be used as the final validation tool.
    Alternatively we could use **ent** or other such tools.
5.  **Hopfield Neural Networks** as used in the paper I read don't fit the GAN
    model very well, the idea there is to produce unpredictable behavior by
    preventing convergence.


## 2 - DESIGN DETAILS

1.  Output of generator will be string of booleans, because in the field of
    PRNGs, binary sequences are the standard.
2.  **Simultaneous gradient descent for both networks**: Ian Goodfellow
    considers this the best approach.
3.  Multiple training steps for discriminator for each one training step of
    generator -> because generator learns better with optimal discriminator


## 3 - RESEARCH DETAILS

1.  Passing statistical randomness tests is only one aspect of CSPRNGs. For
    true security they must also be secure in regards to state etc. These
    requirements are outlined in NIST documents. In your report (or maybe the
    paper) you should consider the complexity of state extension attacks etc
    (i.e. vulnerability of the states of neural networks, whether the networks
    should be periodically retrained, etc).