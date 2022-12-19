---
title: Argus
---

Argus is a Proof Of Concept for Computer Vision ADAS model validation and evaluation, based on an adversarial approach.

Argus is:

- Versatile 
- Explainable
- Scalable
- Statistically Robust
- Cost-Effective
- Easy to implement
- Constantly improving


# Background and Theory

This chapter explores the reasoning behind the development of Argus, the challenge it aims to solve and the academic inspiration that supports it.

The main source of inspiration is based mainly on [Multi-weather city: Adverse weather stacking for autonomous driving by Musat et al](https://openaccess.thecvf.com/content/ICCV2021W/AVVision/papers/Musat_Multi-Weather_City_Adverse_Weather_Stacking_for_Autonomous_Driving_ICCVW_2021_paper.pdf)

```{toctree}
:maxdepth: 1
:caption: Why Argus

background/problem
background/research
theory/dimensionality
theory/sim2real
theory/gans
theory/evaluation

```

# Architecture

This chapter briefly explores the architectural implementation of Argus, its tradeoffs, challenges and its design implications.

```{toctree}
:caption: Architecture
:maxdepth: 1

arch/datasets
arch/stackable-pp
arch/infra-devops-mlops
arch/data-flywheel
arch/future-work

```

# Use Cases

This chapter briefly explores the use cases of Argus and some examples.

```{toctree}
:caption: Use Cases
:maxdepth: 1

uses/cases
uses/client-facing
uses/internal-facing
```

# SaaS

This chapter briefly explores the economics of Argus as a SaaS.

```{toctree}
:caption: SaaS
:maxdepth: 1

saas/income-sources
saas/costs
saas/licensing-legal
```
