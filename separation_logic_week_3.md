# *Week 3* Separation Logic

## Introduction

### Why separation logic?
* Using First Order Logic to prove programs that mutates data structure that usually depends opon **sharing** in these structures is hard to scale.
* Sepration Conjunction (P * Q)
  * *emp* is the unit of *****
  * P * Q is true of a state just if its heap compoenet can be split into two parts, one of which satisfies P and the other of which satisfies Q, in which P, Q denotee a set of states.
  * Updating formulae like in-place update of memory
  * P * not P can be consistent because P can hold of one portion of heap and not p of another

* Key Specification Pattern often employed in separation logic proofs: we use assertions that describe only as much state as is needed, and nothing else.
* Frame Axoim
  * The extra *-conjuct that is not touched
  * Use inference rule to avoid mentioning the frames at all in the specifications(pre-condition)
* Limitation of shape only analysis
  * CopyTree(P) program might change content






## Reference
* [CMU An Introduction to Separation Logic](https://www.cs.cmu.edu/~jcr/copenhagen08.pdf)
* [Separation Logic: A Logic for Shared Mutable Data Structures](https://www.cs.cmu.edu/~jcr/seplogic.pdf)
* [A Primer on Separation Logic](http://www0.cs.ucl.ac.uk/staff/p.ohearn/papers/Marktoberdorf11LectureNotes.pdf)
