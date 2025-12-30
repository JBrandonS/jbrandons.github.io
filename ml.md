---
layout: default
title: Machine Learning in Physics
---

# Teaching Computers to See the Universe

*What if computers could learn to find patterns in the universe that humans can't see?*

That's exactly what machine learning does for physics research. By training computers on massive amounts of data, we can uncover hidden signals in everything from the oldest light in the universe to the tiniest particles inside a proton.

---

## What is Machine Learning?

Imagine teaching a child to recognize cats. You don't give them a rulebook—you show them thousands of pictures, and eventually they just *know* what a cat looks like. Machine learning works the same way. Instead of programming a computer with explicit rules, we feed it examples and let it figure out the patterns on its own.

<div style="text-align: center; margin: 2rem 0;">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/46/Colored_neural_network.svg/500px-Colored_neural_network.svg.png" alt="Diagram of an artificial neural network showing input layer, hidden layers, and output layer" style="max-width: 350px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.3);">
  <p style="color: #888; font-size: 0.9rem; margin-top: 0.5rem;">A neural network: data flows in through the input layer (left), gets processed through hidden layers (middle), and produces predictions on the right. Credit: Glosser.ca, CC BY-SA 3.0, via Wikimedia Commons</p>
</div>

In physics, we use a type of machine learning called **neural networks**—computer systems loosely inspired by how brain cells connect. These networks can process millions of data points and find subtle correlations that would take humans years to spot. Using Python libraries like TensorFlow and Keras, we build these networks to tackle problems that traditional methods struggle with.

---

## Finding Whispers from the Big Bang

One of my research areas uses machine learning to study the **Cosmic Microwave Background (CMB)**—ancient light from when the universe was just 380,000 years old. This "baby picture" of the cosmos contains tiny temperature variations that hold clues about what happened in the first fraction of a second after the Big Bang.

<div style="text-align: center; margin: 2rem 0;">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/ed/WMAP_2012.png/1280px-WMAP_2012.png" alt="All-sky map of the Cosmic Microwave Background showing temperature fluctuations" style="max-width: 100%; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.3);">
  <p style="color: #888; font-size: 0.9rem; margin-top: 0.5rem;">The CMB as seen by the WMAP satellite. Colors show tiny temperature differences—these patterns contain secrets about the early universe. Credit: NASA/WMAP Science Team, Public Domain, via Wikimedia Commons</p>
</div>

The challenge? We're looking for incredibly faint signals called **Primordial Non-Gaussianity (PNG)**—subtle deviations from randomness that could reveal what powered cosmic inflation. It's like trying to hear a whisper at a rock concert. Neural networks trained on simulated CMB data can learn to pick out these whispers far better than traditional statistical methods.

<div style="background: rgba(126, 211, 216, 0.1); border-left: 4px solid #7ed3d8; padding: 1rem 1.5rem; margin: 2rem 0; border-radius: 0 8px 8px 0;">
  <strong style="color: #7ed3d8;">Learn more:</strong> Explore the physics of the early universe and primordial non-Gaussianity on my <a href="png" style="color: #7ed3d8;">PNG research page</a>.
</div>

---

## Mapping the Inside of a Proton

My other research focus uses machine learning to understand what happens inside protons—the particles at the heart of every atom. Through a technique called **Deep Inelastic Scattering (DIS)**, physicists fire electrons at protons to probe their internal structure.

<div style="text-align: center; margin: 2rem 0;">
  <img src="https://upload.wikimedia.org/wikipedia/commons/c/c1/DIS.svg" alt="Diagram showing deep inelastic scattering where an electron exchanges a virtual photon with a quark inside a proton" style="max-width: 350px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.3);">
  <p style="color: #888; font-size: 0.9rem; margin-top: 0.5rem;">Deep inelastic scattering: an electron probes inside a proton by exchanging a virtual photon with quarks. Credit: Wikimedia Commons, Public Domain</p>
</div>

Inside each proton is a sea of quarks and gluons—and at high energies, gluons multiply until they reach a crowded state called **gluon saturation**. Understanding this phenomenon requires analyzing complex scattering data with many variables. Neural networks excel here: they can learn the relationships between collision parameters and predict outcomes that help us map the proton's internal landscape.

<div style="background: rgba(126, 211, 216, 0.1); border-left: 4px solid #7ed3d8; padding: 1rem 1.5rem; margin: 2rem 0; border-radius: 0 8px 8px 0;">
  <strong style="color: #7ed3d8;">Learn more:</strong> Dive into the physics of proton structure and gluon saturation on my <a href="dis" style="color: #7ed3d8;">DIS research page</a>.
</div>

---

## Why Machine Learning Matters for Physics

Physics generates enormous amounts of data—from satellite observations spanning the entire sky to particle collisions happening millions of times per second. No human could analyze it all. Machine learning doesn't replace physicists; it amplifies what we can do.

By combining physics knowledge with tools like NumPy and SciPy for data processing and TensorFlow for neural networks, we can:

- **Detect weaker signals** than ever before possible
- **Analyze larger datasets** in reasonable timeframes  
- **Find unexpected patterns** that might lead to new discoveries

The upcoming **Electron-Ion Collider** at Brookhaven National Laboratory will generate unprecedented amounts of data about proton structure in the early 2030s. Machine learning will be essential for extracting the physics from that flood of information.

The universe has left us clues everywhere—in ancient light, in scattered electrons, in data waiting to be understood. Machine learning helps us read those clues.

---

<div style="text-align: center; margin-top: 3rem;">
  <a href="{{ "/research" | relative_url }}" style="color: #7ed3d8; text-decoration: none; padding: 0.6rem 1.5rem; border: 1px solid #7ed3d8; border-radius: 4px; display: inline-block;">← Back to Research</a>
</div>
