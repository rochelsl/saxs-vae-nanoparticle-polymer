# saxs-vae-nanoparticle-polymer: Generative AI for inverse design of NP/polymer composites
A simple tool for simulating SAXS patterns on which a VAE neural network is trained on as an inverse design exercise.

## Contents
- "NP_core_shell_scattering_VAE.ipynb": full Colab/jupyter notebook
- "vae_model.pth": trained model (load in 3 lines)
- "real_vs_reconstructed.png": comparison plot of simulated and reconstructed scattering using the VAE.
- "latent_space.png": exemplary latent space plots of the VAE.
- "inverse_design_final_plot.png": comparison of inverse-design vs. near training data plot.

## Procedure
1) Nanoparticles (core/shell morphology) in a polymer matrix are generated and their scattering pattern is calculated using a simple form factor parameter variation.

2) A simple PyTorch MLP VAE is trained on the previosuly generated scattering patterns with 200 input datapoints (200-dimensional normalized curves). Plot the simulated data vs. the AI model-trained reconstructed data + latent space (color distinguishing by R_Core). Exemplary latent space plots are shown.
<img width="3557" height="1145" alt="real_vs_reconstructed" src="https://github.com/user-attachments/assets/2994bd06-ebae-4cc1-bb92-bee9b7a4a7ed" />
<img width="4133" height="1807" alt="latent_space" src="https://github.com/user-attachments/assets/22ed26f4-e2f1-483c-8751-84a0e737c838" />

3) Answering the question what composite a given pattern corresponds to. A sample  z  is created which is assumed to be a normal distribution ( N(0,1) ). This is the prior distribution the VAE was trained on.
4) 
This will return the 4 predicted physical parameters and answers "What composite generated this pattern?". The final reconstructed curve is displayed alongside the nearest training match is and the input scattering pattern are shown.
<img width="3557" height="1145" alt="real_vs_reconstructed" src="https://github.com/user-attachments/assets/4d9149ec-a088-4d6a-9a34-a293e5aed69c" />
