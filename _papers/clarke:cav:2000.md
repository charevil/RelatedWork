---
doi: 10.1007/10722167_15
ENTRYTYPE: inproceedings
abstract: We present an automatic iterative abstraction-refinement methodology in which the initial abstract model is generated by an automatic analysis
  of the control structures in the program to be verified. Abstract models may admit erroneous (or ``spurious'') counterexamples. We devise new symbolic
  techniques which analyze such counterexamples and refine the abstract model correspondingly. The refinement algorithm keeps the size of the abstract state
  space small due to the use of abstraction functions which distinguish many degrees of abstraction for each program variable. We describe an implementation
  of our methodology in NuSMV. Practical experiments including a large Fujitsu IP core design with about 500 latches and 10000 lines of SMV code confirm
  the effectiveness of our approach.
added: 2020-05-01
address: Berlin, Heidelberg
authors:
- Edmund M. Clarke
- Orna Grumberg
- Somesh Jha
- Yuan Lu
- Helmut Veith
booktitle: Computer Aided Verification
editor: Emerson, E. Allen and Sistla, Aravinda Prasad
isbn: 978-3-540-45047-4
layout: paper
pages: 154-169
publisher: Springer Berlin Heidelberg
read: false
readings: []
title: Counterexample-guided abstraction refinement
year: 2000
topics:
notes:
- CEGAR
papers:
---

{% include links.html %}
