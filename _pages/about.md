---
permalink: /
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am a fourth year math PhD student at UCLA working with [Guido Montúfar](https://www.math.ucla.edu/~montufar/). I'm interested in deep learning theory. Optimization and generalization in neural networks are often nicer than one might expect. I've worked towards understanding this by characterizing how optimization and generalization are influenced by the relative scaling of parameter count, dataset size, and dataset dimensionality.

Here are some simple ideas behind some of my research:

- There is a lot of room in high-dimensional space, and in turn it becomes exponentially easier to fit a dataset as its dimension increases. Conversely, if we fix the dimension and drastically increase the size of our dataset, it becomes difficult to perfectly fit the dataset, *no matter how many parameters we have*.

- Critical points of neural network loss landscapes satisfy equations like $\nabla_w f \cdot (\hat{y} - y) = 0.$ It's easier for the prediction $\hat{y}$ to match the true value $y$ than for the Jacobian $\nabla_w f$ to be low rank.

- Gradient descent induces a strong inductive bias and pushes neural networks to a "simplest possible" solution that fits the data. This often works in our favor, but could work against us if the dataset is too noisy.

