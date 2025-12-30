---
layout: default
title: Beyond Fisher Forecasting
---

# Beyond Fisher Forecasting for Cosmology

*When Standard Statistical Methods Fall Short*

---

## The Big Picture

Before building expensive scientific experiments—like space telescopes or particle colliders—scientists need to know: *Will this experiment actually teach us something new?* This is where **forecasting** comes in. By simulating what an experiment might measure, researchers can predict how precisely they'll be able to determine important physical quantities before spending billions of dollars.

The **Fisher information matrix** has been the go-to tool for this forecasting for decades. It's fast, elegant, and mathematically convenient. But it has a hidden weakness: it assumes the world behaves in a very specific way. When that assumption breaks down, Fisher forecasts can be dangerously misleading.

Our paper introduces a practical test to determine *when* you can trust Fisher forecasts—and when you need something more sophisticated.

---

## Why Fisher Forecasting Works (Usually)

Imagine you're trying to measure two quantities—say, the expansion rate of the universe ($H_0$) and the amount of dark matter ($$\Omega_m$$). Your measurements will have some uncertainty, and typically you'll find that these uncertainties form an **ellipse** when plotted:

<div style="text-align: center; margin: 1.5rem 0;">
  <img src="/assets/imgs/FXCDM_BAO_Exact_Analytic_Fisher_Doublet_partly_filled_plus_curvature.png" alt="Fisher vs DALI contours" style="max-width: 100%; max-height: 400px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.3);">
  <p style="font-size: 0.9rem; color: #666; margin-top: 0.5rem;"><em>Comparison of Fisher (purple), DALI (green), and exact (orange) likelihood contours</em></p>
</div>

The Fisher matrix captures this ellipse perfectly. It tells you:

- How uncertain each parameter is (the width of the ellipse)
- How parameters are correlated (the tilt of the ellipse)
- All with just $$\mathcal{O}(N)$$ calculations for $$N$$ parameters

This efficiency is why Fisher forecasting dominates cosmology. Computing a full forecast might take seconds instead of days.

---

## When Fisher Fails: The Banana Problem

Fisher's mathematical elegance comes from a key assumption: the likelihood (roughly, the probability distribution of your measurements) must be **Gaussian**—a perfect bell curve. This requires:

1. **Data are Gaussian distributed** (often true for averaged measurements)
2. **Observables depend linearly on parameters** (often *not* true)

When the second condition fails, something interesting happens. Instead of nice elliptical contours, you get **banana-shaped** curves:

The measurements still constrain the parameters, but not in the symmetric way Fisher predicts. The Fisher matrix will claim you can measure a parameter equally well in both directions, when in reality one direction is much better constrained than the other.

**Real-world examples where Fisher fails:**

- Weak constraints on cosmological parameters (early universe measurements)
- Strong parameter degeneracies (when parameters are highly correlated)
- Highly non-linear models (dark energy equation of state)

---

## The DALI Solution

The **Derivative Approximation for LIkelihoods (DALI)** method extends Fisher forecasting by keeping more terms in a mathematical expansion. Think of it like this:

| Method | What it captures | Computation |
|--------|-----------------|-------------|
| **Fisher** | Elliptical (Gaussian) contours only | $$\mathcal{O}(N)$$ evaluations |
| **DALI** | Curved, asymmetric "banana" contours | $$\mathcal{O}(N^2)$$ evaluations |
| **Full MCMC** | Exact contours of any shape | $$\mathcal{O}(10^5 - 10^6)$$ evaluations |

DALI introduces two additional tensors beyond the Fisher matrix:

$$G_{\alpha\beta\gamma} = \mu_{,\alpha\beta} M \mu_{,\gamma}$$

$$H_{\alpha\beta\gamma\delta} = \mu_{,\alpha\beta} M \mu_{,\gamma\delta}$$

These capture how the observables $$\mu$$ curve with respect to the parameters, allowing DALI to detect non-Gaussian features that Fisher misses entirely.

---

## Our Key Contribution: A Validity Test

Here's the practical problem: **Fisher forecasting doesn't tell you when it's wrong.** You could be using Fisher to plan a major experiment, get beautiful elliptical forecasts, and have no idea that the real uncertainties are completely different.

Our paper provides a simple diagnostic:

<div style="background: rgba(77, 201, 139, 0.15); border-left: 4px solid #4dc98b; padding: 1rem 1.5rem; margin: 2rem 0; border-radius: 0 8px 8px 0;">
  <strong>The Cross-Section Test</strong><br>
  Compare 2D slices of Fisher and DALI likelihood surfaces. If the DALI contours show <strong>concavity</strong> (curved inward like a banana), Fisher is likely failing. If they match, Fisher is probably reliable.
</div>

This test requires only the modest additional computation of DALI (not a full MCMC), making it practical to run alongside any Fisher forecast as a sanity check.

We validated this approach using:

- **Expansion history data** (BAO, cosmic chronometers, quasars)
- **CMB power spectra** (simulated Simons Observatory and CMB-S4)
- **Primordial abundances** (Big Bang nucleosynthesis measurements)

In each case, when our test flagged potential problems, comparison with exact MCMC sampling confirmed the Fisher approximation was indeed failing.

---

## Practical Takeaways

1. **Don't blindly trust Fisher forecasts** for weakly constraining data or degenerate parameters
2. **Use our DALI cross-section test** as a quick diagnostic before committing to expensive MCMC
3. **DALI isn't always better**—for sub-linear parameter dependence, it can perform worse than Fisher
4. **When in doubt, sample the exact likelihood**, but now you have a way to know when doubt is warranted

---

## Publication Details

<div style="background: linear-gradient(135deg, rgba(126, 211, 216, 0.08) 0%, rgba(26, 26, 46, 0.05) 100%); border: 1px solid rgba(126, 211, 216, 0.3); border-radius: 12px; padding: 2rem; margin: 2rem 0; box-shadow: 0 4px 15px rgba(0,0,0,0.1);">

<h3 style="margin: 0 0 1.5rem 0; color: #7ed3d8; font-size: 1.3rem; border-bottom: 2px solid rgba(126, 211, 216, 0.3); padding-bottom: 0.75rem;">
  <i class="fas fa-file-alt" style="margin-right: 0.5rem;"></i> Beyond Fisher Forecasting for Cosmology
</h3>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 1.5rem;">

<div>
  <p style="margin: 0 0 0.3rem 0; font-size: 0.85rem; color: #888; text-transform: uppercase; letter-spacing: 0.5px;">Authors</p>
  <p style="margin: 0; font-size: 1rem;">Joseph Ryan, <strong>Brandon Stevenson</strong>, Cynthia Trendafilova, Joel Meyers</p>
</div>

<div>
  <p style="margin: 0 0 0.3rem 0; font-size: 0.85rem; color: #888; text-transform: uppercase; letter-spacing: 0.5px;">Institution</p>
  <p style="margin: 0; font-size: 1rem;">Southern Methodist University</p>
</div>

<div>
  <p style="margin: 0 0 0.3rem 0; font-size: 0.85rem; color: #888; text-transform: uppercase; letter-spacing: 0.5px;">Journal</p>
  <p style="margin: 0; font-size: 1rem;">Physical Review D <strong>107</strong>, 103506</p>
</div>

<div>
  <p style="margin: 0 0 0.3rem 0; font-size: 0.85rem; color: #888; text-transform: uppercase; letter-spacing: 0.5px;">Published</p>
  <p style="margin: 0; font-size: 1rem;">May 8, 2023</p>
</div>

</div>

<div style="margin-top: 1.5rem; padding-top: 1rem; border-top: 1px solid rgba(126, 211, 216, 0.2);">
  <p style="margin: 0 0 0.3rem 0; font-size: 0.85rem; color: #888; text-transform: uppercase; letter-spacing: 0.5px;">DOI</p>
  <a href="https://doi.org/10.1103/PhysRevD.107.103506" target="_blank" style="color: #7ed3d8; font-family: monospace; font-size: 0.95rem;">10.1103/PhysRevD.107.103506 <i class="fas fa-external-link-alt" style="font-size: 0.75rem; margin-left: 0.3rem;"></i></a>
</div>

</div>

---

## Related Links

<div style="display: flex; flex-wrap: wrap; gap: 1rem; margin: 1.5rem 0;">
  <a href="https://doi.org/10.1103/PhysRevD.107.103506" target="_blank" style="color: #7ed3d8; text-decoration: none; padding: 0.6rem 1.2rem; border: 1px solid #7ed3d8; border-radius: 4px; display: inline-flex; align-items: center; gap: 0.5rem;"><i class="fas fa-book"></i> Paper (Phys. Rev. D)</a>
  <a href="/assets/pdfs/dali.pdf" style="color: #7ed3d8; text-decoration: none; padding: 0.6rem 1.2rem; border: 1px solid #7ed3d8; border-radius: 4px; display: inline-flex; align-items: center; gap: 0.5rem;"><i class="fas fa-file-pdf"></i> Download PDF</a>
  <a href="https://github.com/JBrandonS/DALI" target="_blank" style="color: #7ed3d8; text-decoration: none; padding: 0.6rem 1.2rem; border: 1px solid #7ed3d8; border-radius: 4px; display: inline-flex; align-items: center; gap: 0.5rem;"><i class="fab fa-github"></i> GitHub Repository</a>
</div>

---

<div style="text-align: center; margin-top: 3rem;">
  <a href="{{ "/publications" | relative_url }}" style="color: #7ed3d8; text-decoration: none; padding: 0.6rem 1.5rem; border: 1px solid #7ed3d8; border-radius: 4px; display: inline-block;">← Back to Publications</a>
</div>
