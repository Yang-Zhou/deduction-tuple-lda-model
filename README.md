Tuple LDA
===================

LDA treats document as a multinomial distribution of topics, and treat a topic as a multinomial 
distribution of words.
According to this thoughts, a document is treated as a distribution of events, and an event is 
treated as a distribution of tuple consisting of objects, predicates and subjects(That's why the model is called Tuple LDA).
Idea illustrates below:

![Plate representation](https://raw.github.com/Yang-Zhou/deduction-tuple-lda-model/master/TLDA_illustrate.png)

Using plate model from PGM to represent the idea：

![Plate representation](https://raw.github.com/Yang-Zhou/deduction-tuple-lda-model/master/graph.png)


### Generating process

> Sample frame distribution θ from Dirichlet(α) Sample subject distribution φs from Dirichlet(β) Sample predicate distribution φv from Dirichlet(β) Sample object distribution φo from Dirichlet(β)

> Document-Frame
*  For each frame in d, sample fm ∼ Multinomial(θ_m):

> Frame-Roles
*  For each semantic roles in fm:
    +     (a) Sample s_m ∼ Multinomial(φ_s^(m))
    +     (b) Sample v_m ∼ Multinomial(φ_v^(m)) 
    +     (c) Sample o_m ∼ Multinomial(φ_o^(m))
