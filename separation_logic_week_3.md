# *Week 3* Separation Logic

## Introduction

### Why separation logic?
* Using First Order Logic to prove programs that mutates data structure that usually depends opon **sharing** in these structures is hard to scale.
* Sepration Conjunction (P * Q)
  * *emp* is the unit of *
  * P * Q is true of a state just if its heap compoenet can be split into two parts, one of which satisfies P and the other of which satisfies Q, in which P, Q denotee a set of states.
  * Updating formulae like in-place update of memory
  * P * not P can be consistent because P can hold of one portion of heap and not p of another
* What P and Q can be ?
  * Spatial Formula F
```sml
  F ::= emp | x -> t | P t | F * F
  % P is a predicate symbol (useful for inductive structure like tree and list)
```
* Key Specification Pattern often employed in separation logic proofs: we use assertions that describe only as much state as is needed, and nothing else.
* Frame Axoim
  * The extra *-conjuct that is not touched
  * Use inference rule to avoid mentioning the frames at all in the specifications(pre-condition)
* Soundness of frame rule
  * A formula that is provable is true
  * Two extra facts about the programming languages
    * Safety monotonicity
    * Frame property -> Any kind of computation on big memory can be condensed to smaller memory
    * These lemma imply the locality of all commands
* Limitation of shape only analysis
  * CopyTree(P) program might change content
* Bi-abudction
```
?X * A |- B * ?Y

------------
{A * ?X}
{B} proc {C}
B * ?Y
```

## Conclusion
* Separation Logic is a combination of
  * Programming Language
  * Assertion Language
  * and rules for Hoare triples
* Power of Separation Logic comes from compositionality:
  * proofs of sub-programs can be comobined into proofs of whole programs
* Compositionality depends on the frame rule

## Further Reading
* [A semantic basis for local reasoning](https://pdfs.semanticscholar.org/2948/8d50923a674af28bbb656a852fdf9abfdcef.pdf)
* [Compositional shape analysis by means of bi-abduction](http://www0.cs.ucl.ac.uk/staff/p.ohearn/papers/popl09.pdf)

## Reference
* [CMU An Introduction to Separation Logic](https://www.cs.cmu.edu/~jcr/copenhagen08.pdf)
* [Separation Logic: A Logic for Shared Mutable Data Structures](https://www.cs.cmu.edu/~jcr/seplogic.pdf)
* [A Primer on Separation Logic](http://www0.cs.ucl.ac.uk/staff/p.ohearn/papers/Marktoberdorf11LectureNotes.pdf)
* [James brotherston - An Introduction to Separation Logic]()
