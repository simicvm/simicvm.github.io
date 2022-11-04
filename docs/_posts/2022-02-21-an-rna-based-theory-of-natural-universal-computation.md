---
layout: post
title: "An RNA-based Theory of Natural Universal Computation"
author: "Marko Simic"
categories: journal
tags: [documentation,sample]
image: an-rna-based-thoery-of-natural-universal-computation.jpeg
---

Biological systems perform many forms of computation, not just in their brains (if they have one) but also on the cellular level. Examples of such computations are:

- using vision to guide wing movement in insect flight,
- language acquisition in humans,
- decision-making in single-celled ciliates.

Akhlaghpour (2022) explores the possibility that computation in living organisms is based on intracellular RNA processing rather than neurons and neural networks in brains, and molecular cascades, gene regulatory networks, and signal transduction pathways in cells.

Given the distinct and complex anatomy of mammalian brains, it is not self-evident that they “play by the rules” of our computation theory. But if we assume that they do, and that they “run” algorithms to solve problems, it would certainly be beneficial for them to be universal computers (i.e. [Touring-complete](https://en.wikipedia.org/wiki/Turing_completeness)). Moreover, universal computation seems to be quite ubiquitous and easy to accidentally implement (check [Surprisingly Turing-Complete](https://www.gwern.net/Turing-complete) for some fun examples).

Both brains and cellular systems can be categorized as finite-dimensional dynamical systems. This category of systems can perform universal computation, but Moor (1998) conjectured that
> no finite-dimensional system capable of universal computation is stable with respect to perturbations, or generic according to any reasonable definition.

That lack of structural stability makes these dynamical systems **physically unrealizable**. Moreover, a necessary but not sufficient condition for universal computation is a memory expansion, i.e., the system should be able to recruit more memory space when needed during the process of computation. Unfortunately, biological neural networks can’t easily satisfy this condition, and the few proposed solutions also make them structurally unstable and hence not present/realistic in nature.

But computation does not need to be based on neural networks. One of the most promising places to look for a universal computer in nature is in the **molecular biology of polynucleotides**. In such systems, precise sequences of polynucleotides enable memory expansion. Polynucleotides even resemble the strings we use in computation. They also possess other properties that make them good vehicles for biological computation like thermodynamic stability, spatial compactness, the low energy cost of modification.

Ruben (2000) gives a brief overview of existing DNA/RNA-based computational models. Still, all of them are design-oriented, and it would be hard to argue that any of them could have arisen in nature through evolution.

> The question is not whether it is feasible to artificially implement a universal computation system using polynucleotides, but whether it is reasonable to consider that nature may have already done so.

Non-coding RNA is an RNA molecule that is not translated into a protein. The functional significance of these molecules is still debated, and there is a possibility they serve a yet undiscovered role. The question of non-coding RNA function has even been called *"the most important issue in genetics."* **In this work, the author proposes a theory that the non-coding RNA contains the data and programming material for the biological universal computer** and demonstrates that universal computation through RNA is in principle attainable without assuming overly complex molecular machinery. The proposed model is based on **combinatory logic**, which is Turing-complete. Computation in these models is a decentralized process in which enzymes make local modifications to RNA molecules according to basic rules.

Combinatory logic uses the application of primitive **combinators** to perform computation. Combinators are a higher-order function that uses only function application and previously defined combinators to represent a result from its arguments. There are different sets of combinators that can be used to compute any computable function, with the two most common being `S K` and `B C K W`. These combinators are defined as:

```
Sxyz = xz(yz)
Bxyz = x(yz)
Cxyz = xzy
Kxy = x
Wxy = xyy
```

where capital letters denote combinators, and lower case letters represent variables that can be replaced by any combinatory term. Combinatory logic is conventionally left-associative, and the notation `xy` is equivalent to the return value of the function `x` when given input `y`.

To perform computation on RNA strands using combinatory logic, cells would need to have four distinct and independent enzymes that implement combinators `B C K W`. The specific RNA modifications necessary to execute the combinators depend on the combinator set used. But it is possible to evaluate the model’s plausibility without assuming the exact basis set. Any set of primitive combinators, to achieve universal computation, must have at least one combinator that:

- deletes terms (deletion),
- reorders terms (reordering),
- duplicates terms (duplication),
- adds parentheses (nesting).

**Deletion**: The enzyme responsible for implementing the deletion operation needs to excise a segment of RNA. Splicing is one of the most common RNA modifications, and many enzymes are known to mediate it.

**Reordering**: The enzyme responsible for implementing the operation only needs to conduct something as simple as swapping two elements corresponding to successive terms. Similar RNA modifications are already known to occur in cells. Post-transcriptional reordering of exons was first observed in the early 1990s.

**Duplication**: This operation is not as trivial as the previous two. Duplication of arbitrary long sequences requires an enzyme that can synthesize a copy of an RNA element. The most promising candidate enzyme is RNA polymerase (RNAP), which synthesizes RNA from DNA. But if we allow self-referencing in combinatory logic, we could still achieve universal computation without the need for duplication operation, just by using an addressing system.

**Nesting**: A nesting operation composes two terms as a single nested term, and parenthesis matching is critical for this operation. Enzymes that apply combinators need to recognize and count whole terms. One solution for this problem is to utilize the base-pairing properties of RNA that produces **stems and loops** in the RNA strands, which can be used to represent parentheses and nested terms, respectively.

The components needed to implement these operations are very familiar and unsophisticated, unlike previous DNA/RNA-based computational models. Based on that, **it is entirely plausible that nature may have already achieved an RNA-based universal computation system.**

Despite its simplicity, there are still challenges with the proposed model:

- The same RNA strands can change shape and fold into different kinetically stable structures, which can produce ambiguities in parenthesis matching. Therefore, a stable and controlled secondary structure is necessary for the outlined model to work.
- To serve as memory engrams, RNA molecules have to be stable over extended periods, or the information must be transcribed into DNA.
- RNA modifications occur at the rate of roughly 36–200 bits/s. It remains to be seen if this is fast enough to facilitate animal cognition.

RNA-based computational models outlined in this work are meant as proof of principle that universal computation is in the reach of molecular biology without the need to invoke implausible molecular processes. Universal computation is achieved through a **decentralized process** where distinct memory-less enzymes make local modifications to RNA molecules according to basic rules. The modification can happen in **parallel** across many RNA strands (even at multiple locations within the same strand), and the order of operations does not matter.

> If the outlined model of RNA-based computation is correct, neurons in the brain might serve the purpose of rapid communication across cells rather than the processing system itself.

We can validate this hypothesis by showing that specific non-coding RNA is necessary for cognition, and their modification impacts animal behavior. On the other hand, we can invalidate the hypothesis by showing that non-coding RNA is dispensable and can be replaced by random sequences without any impact on cognition, development, or cell function.

### References

Akhlaghpour, H. (2022). An RNA-based theory of natural universal computation. Journal of theoretical biology, 537, 110984.

Moore, C. (1998). Finite-dimensional analog computers: Flows, maps, and recurrent neural networks. In 1st International Conference on Unconventional Models of Computation-UMC (Vol. 98, pp. 59–71).

Ruben, A. J., & Landweber, L. F. (2000). The past, present and future of molecular computing. Nature Reviews Molecular Cell Biology, 1(1), 69–72.
