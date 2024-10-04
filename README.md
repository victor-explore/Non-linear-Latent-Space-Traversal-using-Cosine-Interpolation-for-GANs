# Non-linear Latent Space Traversal using Cosine Interpolation for GANs

This repository contains an implementation of non-linear latent space traversal using cosine interpolation for Generative Adversarial Networks (GANs). This technique provides a smooth transition between two points in the latent space, resulting in more visually pleasing image transformations.

## Overview

Latent space traversal is a technique used to explore the latent space of a GAN. By interpolating between two points in this space, we can generate a sequence of images that show a smooth transition between two different generated outputs. While linear interpolation is commonly used, non-linear methods like cosine interpolation can provide more aesthetically pleasing results.

## Cosine Interpolation Formula

The cosine interpolation between two values $a$ and $b$, with $t$ ranging from 0 to 1, is given by:

$$f(t) = a + (b - a) * (1 - \cos(\pi * t)) / 2$$

This formula creates a smooth S-curve transition, accelerating at the beginning and decelerating at the end. When applied to latent vectors, it results in more natural-looking interpolations in the generated image space.

## Implementation

The main function `cosine_latent_space_traversal` takes the following arguments:
- `generator`: The GAN generator model
- `start_vector`: The starting point in latent space
- `end_vector`: The ending point in latent space
- `num_samples`: The number of interpolation steps

It returns a tensor of generated images showing the transition from the start vector to the end vector.

## Usage

1. Load your pre-trained GAN generator model.
2. Generate or choose start and end vectors in the latent space.
3. Call the `cosine_latent_space_traversal` function with your generator and vectors.
4. Display or save the resulting interpolated images.
