---
layout: default
title: Primordial Non-Gaussianity
---

# Machine Learning for Primordial Non-Gaussianity

*Teaching Computers to Find Hidden Patterns in the Early Universe*

---

<div class="callout callout--accent">
  <strong><i class="fas fa-hourglass-half"></i> Paper in Preparation</strong><br>
  This research is ongoing. A publication is currently in the works.
</div>

## The Challenge: Finding a Needle in the Cosmic Haystack

The Cosmic Microwave Background (CMB)—light from when the universe was just 380,000 years old—contains subtle clues about what happened during **inflation**, the ultra-rapid expansion in the first fraction of a second after the Big Bang. One of the most important clues is **primordial non-Gaussianity (PNG)**: tiny deviations from perfectly random fluctuations that would reveal the physics of inflation.

<figure class="figure figure--muted">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/ed/WMAP_2012.png/1280px-WMAP_2012.png" alt="All-sky map of the Cosmic Microwave Background showing temperature fluctuations">
  <figcaption><em>The Cosmic Microwave Background from WMAP. Hidden within these temperature fluctuations may be signatures of primordial non-Gaussianity. (Credit: NASA/WMAP)</em></figcaption>
</figure>

The problem? These PNG signals are incredibly weak. Current observations show the CMB is *almost* perfectly Gaussian—any non-Gaussian signal is buried under noise and foreground contamination. Traditional statistical methods have pushed detection limits significantly, but they may not be optimal for extracting every last bit of information from the data.

This is where **machine learning** enters the picture.

---

## Why Machine Learning?

Traditional PNG detection relies on measuring specific statistical quantities like the **bispectrum** (the three-point correlation function). This approach works well but has limitations:

| Traditional Methods | Machine Learning |
| ------------------- | ---------------- |
| Hand-designed statistics | Learns optimal features from data |
| Computationally expensive at high resolution | Can be faster once trained |
| May miss unexpected signal types | Can discover unanticipated patterns |
| Well-understood statistical properties | Requires careful validation |

The key insight is that neural networks are **universal function approximators**—given enough data and the right architecture, they can learn to extract information in ways that might not be obvious to human researchers.

---

## Our Approach

Our research explores using **convolutional neural networks (CNNs)** and other deep learning architectures to detect PNG directly from CMB maps. The basic idea:

### Training on Simulations

Since we don't have access to many universes to test on, we generate thousands of **simulated CMB maps**:

1. **Gaussian maps**: Simulations with no PNG (the null hypothesis)
2. **Non-Gaussian maps**: Simulations with varying levels of PNG

The neural network learns to distinguish between these two classes, effectively learning what PNG "looks like" in CMB data.

### Types of Non-Gaussianity

PNG isn't just one thing—different inflationary models predict different *shapes* of non-Gaussianity:

- **Local PNG ($$f_{\rm NL}^{\rm local}$$)**: Correlations between modes of very different sizes. Predicted by multi-field inflation models.
- **Equilateral PNG ($$f_{\rm NL}^{\rm equil}$$)**: Correlations between modes of similar sizes. Associated with non-standard kinetic terms.
- **Orthogonal PNG ($$f_{\rm NL}^{\rm ortho}$$)**: A combination designed to be independent of the above.

---

## Advantages of the ML Approach

### 1. End-to-End Learning

Instead of reducing a CMB map to summary statistics (potentially losing information), neural networks can work directly with the full map data. This **map-to-constraint** approach preserves all available information.

### 2. Handling Realistic Complications

Real CMB data isn't clean. It includes:

- **Instrumental noise**: Random fluctuations from the detector
- **Galactic foregrounds**: Emission from our own Milky Way
- **Point sources**: Bright objects that contaminate the signal
- **Masking**: Regions of sky we can't use

Neural networks can learn to handle these complications if trained on realistic simulations that include them.

### 3. Speed at Inference Time

Once trained, a neural network can analyze a CMB map in seconds—far faster than computing the full bispectrum, which scales poorly to high resolution.

---

## Challenges and Considerations

Machine learning isn't a magic solution. Key challenges include:

<div class="callout callout--warning">
  <strong>The Simulation Gap</strong><br>
  Neural networks learn from simulations, but real data may differ in subtle ways. Ensuring the network generalizes to real observations requires careful validation and understanding of systematic effects.
</div>

**Other considerations:**

- **Interpretability**: Understanding *what* the network learned is harder than with traditional statistics
- **Statistical calibration**: Ensuring error bars are accurate, not just precise
- **Computational cost of training**: While inference is fast, training requires significant resources
- **Domain shift**: The network must work on data slightly different from its training set

---

## The Bigger Picture

This research sits at the intersection of cosmology, statistics, and computer science. By developing ML tools for PNG detection, we're not just looking for one signal—we're building frameworks that could:

- Improve constraints on inflationary physics from current and future CMB experiments
- Provide templates for applying ML to other cosmological observables
- Discover unexpected features that traditional analyses might miss

The ultimate goal is to extract every possible bit of information about the early universe from our observations. Machine learning gives us new tools to approach this fundamental question: *What happened in the first moments after the Big Bang?*

---

## Related Topics

<div class="pill-row">
  <a class="pill" href="{{ '/research/png' | relative_url }}"><i class="fas fa-star"></i> The Early Universe</a>
  <a class="pill" href="{{ '/research/ml' | relative_url }}"><i class="fas fa-brain"></i> Machine Learning in Physics</a>
  <a class="pill" href="https://github.com/JBrandonS/MLPNG" target="_blank" rel="noopener"><i class="fab fa-github"></i> GitHub Repository</a>
</div>

---

<div class="page-back">
  <a class="pill pill--lg" href="{{ '/publications' | relative_url }}">← Back to Publications</a>
</div>
