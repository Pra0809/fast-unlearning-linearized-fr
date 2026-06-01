# Fast Unlearning on Linearized Face Recognition Models

Research project (ongoing) — Project Group, M.Sc. Computer Science, Paderborn University.

## Problem
Removing specific identities from a trained face recognition model
without retraining the whole system — a growing requirement under
privacy regulations like GDPR.

## Approach (high level)
Building on the Linearizer framework of Berman et al. (2025) to expose
a pre-trained face recognition backbone as a linear operator in a
learned latent space, then editing that operator to suppress target
identities.

## Status
- Role: Lead contributor (team of 2),
- Backbones: iResNet50 with ArcFace and AdaFace loss
- Datasets: MS1MV2 training subset; verification on LFW, CFP-FP,
  AgeDB-30, CALFW, CPLFW
- Paper: in preparation; methodology and full results withheld until
  publication
- Code: maintained in private university research-group repository
  (RAIB-group); will be released upon paper publication

## Headline results (early findings)
At 50 forget identities, achieves strong selective forgetting while
preserving general verification accuracy on all five standard benchmarks.
Detailed metrics, hyperparameters, and methodology will be released
with the paper.

## Related work
- Berman, Hallak & Shocher, *Who said neural networks aren't linear?*, arXiv:2510.08570, 2025
- Bourtoule et al., *Machine Unlearning*, IEEE S&P 2021
- Foster et al., *Selective Synaptic Dampening*, AAAI 2024

## Contact
For details under NDA / academic discussion: prashantchandra142@gmail.com
