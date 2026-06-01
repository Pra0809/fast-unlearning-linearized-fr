<div align="center">

# Fast Unlearning on Linearized Face Recognition Models

**A novel approach to selective identity forgetting via neural-network linearization.**

![Status](https://img.shields.io/badge/status-in_progress-yellow)
![Type](https://img.shields.io/badge/type-research_project-blue)
![Paper](https://img.shields.io/badge/paper-in_preparation-orange)
![Level](https://img.shields.io/badge/program-M.Sc.%20Project%20Group%20(20%20ECTS)-informational)

*Project Group · M.Sc. Computer Science · Paderborn University · 2025 – 2026*

</div>

---

## Problem

Modern face recognition systems learn to project face images into a high-dimensional embedding space, where identity similarity is measured by cosine distance. Removing the influence of a specific person — say, in response to a GDPR deletion request — without harming the model's ability to recognise everyone else is surprisingly hard. The naive solution, retraining the whole network from scratch, takes weeks of GPU time. Existing approximate unlearning methods (SISA, Fisher forgetting, Selective Synaptic Dampening) were designed for closed-set classification with softmax outputs, and don't translate cleanly to face recognition's open-set embedding setting.

## Approach 

Building on the recently introduced **Linearizer framework** (Berman et al., 2025), this project wraps a pre-trained face recognition backbone in an invertible network that exposes the model's input-to-output behaviour as a single matrix operator in a learned latent space. Once the model is linear in that latent system, identity-specific information can be located and edited using classical linear-algebra tools — turning machine unlearning into a closed-form matrix operation rather than an iterative optimization problem.

```
        ┌──────────────────────────────────────────────────────────┐
        │                                                          │
 Face   │   Frozen        Invertible        Matrix       Inverse   │   Modified
Image ──┼──> Backbone ──> Encoder g ──> Operator A ──> Decoder g⁻¹ ┼──> Embedding
        │   (iResNet50)   (Linearizer)     (edited)                │
        │                                                          │
        └──────────────────────────────────────────────────────────┘
                                            ↑
                                  Edited to suppress
                                  target identities
```

*Full methodology, algorithm details, and hyperparameters are withheld until paper publication.*

## My role

- **Lead contributor** (team of 2)
- Supervised by faculty at Paderborn University
- Year-long project group, 20 ECTS — currently halfway through

## Scope and setup

| Element | Details |
|---|---|
| **Backbones** | iResNet50 with ArcFace and AdaFace losses |
| **Training data** | MS1MV2 subset (96k embeddings across 5000 identities) |
| **Verification benchmarks** | LFW, CFP-FP, AgeDB-30, CALFW, CPLFW |
| **Scale tested** | 50, 100, and 1,000 forget identities |
| **Framework** | Python, PyTorch, NumPy, Linearizer architecture (invertible coupling networks) |

## Headline results (early findings)

At the 50-identity forget scale, the method achieves strong selective forgetting while preserving general verification accuracy across all five benchmarks. The closed-form nature of the edit means unlearning completes in **milliseconds**, in contrast to hours required by fine-tuning baselines.

> Full metrics, ablation studies, and scalability analysis will be released with the paper.

## Status

- 🔬 **Research in progress** — paper in preparation
- 🔒 **Code** is maintained in the private research group repository [RAIB-group/FastUL_LinearFR](https://github.com/RAIB-group/FastUL_LinearFR); it will be released publicly once the paper is published
- 📄 **Detailed report and paper draft** are not shared publicly to preserve research-publication integrity; available under NDA / academic discussion on request

## Related work

- N. Berman, A. Hallak, A. Shocher. *Who said neural networks aren't linear?* arXiv:2510.08570, 2025.
- L. Bourtoule et al. *Machine Unlearning.* IEEE Symposium on Security and Privacy, 2021.
- J. Foster, S. Schoepf, A. Brintrup. *Fast machine unlearning without retraining through selective synaptic dampening.* AAAI 2024.
- J. Deng et al. *ArcFace: Additive angular margin loss for deep face recognition.* CVPR 2019.
- M. Kim, A. K. Jain, X. Liu. *AdaFace: Quality adaptive margin for face recognition.* CVPR 2022.

## Contact

For academic discussion or recruiter follow-up:

- 📧 [prashantchandra142@gmail.com](mailto:prashantchandra142@gmail.com)
- 💼 [LinkedIn](https://www.linkedin.com/in/prashant-chandra-817453238)
- 🏛️ Research group: [RAIB-group](https://github.com/RAIB-group)

---

<div align="center">
<sub>Last updated: November 2026 · Paper in preparation</sub>
</div>
