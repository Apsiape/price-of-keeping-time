# The price of keeping time

Seth Douglas and Nidhal Mghirbi — October 2026.

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23310632.svg)](https://doi.org/10.5281/zenodo.23310632)

[Read the manuscript](paper/main.pdf) · [TeX source](paper/main.tex) ·
[Machine checks](verification/README.md)

A device that runs a quantum operation which does not respect time translation needs its own clock. This paper
asks what owning that clock costs.

- **Gates.** The clock is paid for in capital, in the energy range of the heat baths, and in an energy that comes back
  only as a lottery, each growing faster than the number of uses as the error vanishes.
- **The batch law.** With a returned clock, the batch work per use of every channel is a single-letter quantity B. It
  equals the thermodynamic capacity when the channel's environment can carry its energy change, and can exceed it
  otherwise, even for channels of capacity zero.
- **How large the clock must be.** At fixed error, the same condition sets how the clock's capital spread must grow:
  not at all for covariant channels, like the square root of the number of uses when the environment can carry the
  energy change (by a construction that does not attain the optimal work), and at least linearly when it cannot.
- **Time reversal.** In batch with a returned clock, a Gibbs-preserving qutrit channel costs 0.1547 kT per use, while
  its Petz reverse costs nothing.
- **Noise horizon.** Any fixed amount of full-rank thermal noise makes both directions free, but for a finite run
  what matters is the expected number of noisy uses. If it tends to zero, the original work rate remains; if it
  diverges, sublinear work is possible; if it tends to a positive finite value, the work rate stays positive,
  between two envelopes whose equality is open.

All rates here are optimal asymptotic work rates at vanishing error over the complete interaction, with hardware
allowed to grow; where a controller comes back only approximately, its actual mean energy and entropy are also
refunded up to sublinear changes.

This repository contains the manuscript, its source, and the machine checks that accompany it. It is version 1.0.2 of the Zenodo record [doi:10.5281/zenodo.23310632](https://doi.org/10.5281/zenodo.23310632); that concept DOI always resolves to the latest version. Version 1.0.1 is [doi:10.5281/zenodo.23310740](https://doi.org/10.5281/zenodo.23310740) and version 1.0.0 is [doi:10.5281/zenodo.23310633](https://doi.org/10.5281/zenodo.23310633). The manuscript is the
authority for exact statements and hypotheses; [verification/README.md](verification/README.md) lists what is checked
by machine and what is proved only in the text.

## Reproduce

Requires Python 3.10+ with the packages in [verification/requirements.txt](verification/requirements.txt), a TeX
distribution with the packages listed in paper/main.tex, and, for the formal proofs, Lean 4 with Mathlib as described
in [verification/README.md](verification/README.md).

    python -m pip install -r verification/requirements.txt
    python paper/build.py
    python verification/run_all.py

The build refuses to finish on any undefined reference or citation, duplicate label or overfull line. Each check
prints what it verifies and exits with status 0 when it passes.
Until Mathlib is set up as described there, the Lean step reports that it was skipped and the run
fails; the Python checks do not need it.

## Companions

This paper is one of four on the thermodynamics of time order, each with its own repository:
- [Only quantum channels save work by waiting](https://github.com/Apsiape/save-work-by-waiting) · [doi:10.5281/zenodo.23310624](https://doi.org/10.5281/zenodo.23310624)
- [The work cost of answering in real time](https://github.com/Apsiape/answering-in-real-time) · [doi:10.5281/zenodo.23310628](https://doi.org/10.5281/zenodo.23310628)
- [The price of time order](https://github.com/Apsiape/price-of-time-order) · [doi:10.5281/zenodo.23310622](https://doi.org/10.5281/zenodo.23310622)

Earlier papers it builds on are listed, with the exact results used and where, in the appendix "Results from the
companion papers" of the manuscript.

## Reading guide

For the organizing principle, read the introduction, Figure 1 and Table 2 of *The price of time order*. For the device model,
the law for repeated channels and the free set, read *Only quantum channels save work by waiting*. For processes with
memory and the classical example of an order cost, read *The work cost of answering in real time*. For returned
clocks, the batch law and the time reverse, read *The price of keeping time*. Readers following proofs should note that
the finite-source module of *The work cost of answering in real time* (Appendix E, Lemma 12) is established
independently of the channel results it helps to prove.

## License and citation

The manuscript and repository content are available under **CC BY 4.0**. The software and machine-readable
verification artifacts are additionally available under the **MIT License**, at your option; see
[RIGHTS.md](RIGHTS.md) for the scope. [CITATION.cff](CITATION.cff) provides machine-readable citation metadata. Please cite the manuscript by its concept DOI, [10.5281/zenodo.23310632](https://doi.org/10.5281/zenodo.23310632).
