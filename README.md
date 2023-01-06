* * *
**News**
- ConfFuzz will be presented [at FOSDEM](https://fosdem.org/2023/schedule/event/cc_online_vulnerabilities/) as part of the Confidential Computing track.
- Our ConfFuzz [paper](https://arxiv.org/abs/2212.12904) was accepted to appear at [NDSS 2023](https://www.ndss-symposium.org/ndss2023/).

* * *

Software compartmentalization decomposes applications into lesser-privileged
components that only have access to what they need to do their job. Properly
applied, compartmentalization can limit the impact of many memory safety issues
by containing corruption within the vulnerable component. Use-cases are
plentiful: library sandboxing, protection of SSL keys, sandboxing of
network-facing code, and more.

In the last decade we have seen the appearance of many new mechanisms that
enable compartmentalization at a relatively low performance cost (Intel PKU,
the upcoming Intel PKS, CHERI hardware capabilities, vmfunc). This generated a
lot of research with a strong focus on compartmentalizing existing software, at
a fine grain (isolating libraries or components), and as automatically as
possible. The promises are great: the compartmentalization of legacy software,
with a low engineering effort, and at a low performance cost.

Alas, in this process, the interfaces between compartments are often neglected:
they are hard to reason about and difficult to secure automatically, and
compartmentalizing at finer and finer-grain exacerbates the issue. This is a
major problem, as weak interfaces enable for a wide range of attacks.

In this work, we study the impact of neglecting compartment interfaces. We
define and classify Compartment Interface Vulnerabilities (CIVs), and present
**ConfFuzz** a fuzzer specialized to catch them. Having applied it to 25
popular applications and 36 possible compartment APIs, revealing 629 interface
vulnerabilities, we present insights into what makes interfaces vulnerable, and
how to make them more resilient when compartmentalizing.

### Getting Started

Our [main README](https://github.com/conffuzz/conffuzz/blob/main/README.md) provides a step-by-step guide to get started with our prototype.

The data set of our NDSS'23 paper is [publicly available](https://github.com/conffuzz/conffuzz-ndss-data) under the [CC BY](https://creativecommons.org/licenses/by/4.0/) license.

### Publications

* **Assessing the Impact of Interface Vulnerabilities in Compartmentalized Software.**<br/>H. Lefeuvre, V-A. Bădoiu, B. Chien, F. Huici, N. Dautenhahn, P. Olivier.<br/>to appear in [**NDSS'23**](https://www.ndss-symposium.org/ndss2023/) [[ArXiv](https://arxiv.org/abs/2212.12904)] [[Data-Set](https://github.com/conffuzz/conffuzz-ndss-data)] [[Zenodo](https://doi.org/10.5281/zenodo.7505748)]

### Other Presentations

* **A Study of Fine-Grain Compartment Interface Vulnerabilities: What, Why, and What We Should Do About Them.**<br/>will be presented by [H. Lefeuvre](https://fosdem.org/2023/schedule/speaker/hugo_lefeuvre/) at [**FOSDEM'23**](https://fosdem.org/2023/schedule/event/cc_online_vulnerabilities/)

### Contact

[Hugo Lefeuvre](https://owl.eu.com), The University of Manchester: hugo.lefeuvre *at* manchester.ac.uk

* * *

ConfFuzz is an open-source project resulting from a collaboration between the
University of Manchester, Politehnica University of Bucharest, Rice University,
and Unikraft.io.

ConfFuzz is partly funded by a studentship from NEC Labs Europe, a Microsoft
Research PhD Fellowship, the UK’s EPSRC grants EP/V012134/1 (UniFaaS),
EP/V000225/1 (SCorCH), the EPSRC/Innovate UK grant EP/X015610/1 (FlexCap), the
EU H2020 grant agreements 871793 (ACCORDION) and 758815 (CORNET), and the NSF
CNS #2008867, #2146537, and ONR N00014-22-1-2057 grants.
