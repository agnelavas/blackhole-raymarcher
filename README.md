# Relativistic Kerr Black Hole Ray-Marcher & Lensing Engine

A real-time WebGL and GLSL GPU shader simulation modeling general relativistic null-geodesic ray tracing in curved spacetime. The engine computes gravitational light bending around rotating and non-rotating black holes, rendering gravitational lensing, photon spheres, and relativistic Doppler beaming on accretion disk plasma at 60 FPS.

---

## General Relativistic Principles

### 1. Spacetime Curvature & Null Geodesics
Light rays follow null geodesics in pseudo-Riemannian spacetime governed by the geodesic equation:

$$\frac{d^2 x^\mu}{d\lambda^2} + \Gamma^\mu_{\alpha\beta} \frac{dx^\alpha}{d\lambda} \frac{dx^\beta}{d\lambda} = 0$$

Where $\Gamma^\mu_{\alpha\beta}$ represents the Christoffel symbols of the spacetime metric. Photons passing near the Schwarzschild radius ($r_s = \frac{2GM}{c^2}$) experience extreme deflection angles:

$$\Delta\phi \approx \frac{4GM}{c^2 b}$$

In the strong-field regime near the photon sphere ($r_{\text{ph}} = 1.5\,r_s$), photons orbit the singularity before escaping, creating the characteristic Einstein rings and halo profiles.

### 2. Relativistic Doppler Beaming & Headlight Effect
Accretion disk plasma orbits the compact object at relativistic fractions of light speed ($v \sim 0.3c\text{--}0.5c$). The observed intensity $I_{\text{obs}}$ is boosted or attenuated relative to the emitter rest-frame intensity $I_{\text{em}}$ via the relativistic invariant:

$$I_{\text{obs}} = \delta^4 I_{\text{em}}$$

Where the Doppler factor $\delta$ is:

$$\delta = \frac{1}{\gamma (1 - \beta \cos\theta)}, \quad \gamma = \frac{1}{\sqrt{1 - \beta^2}}$$

* **Approaching Plasma ($\cos\theta > 0$):** Strongly beamed, intensified, and blueshifted toward shorter wavelengths (electric cyan/white).
* **Receding Plasma ($\cos\theta < 0$):** Strongly dimmed and redshifted toward longer wavelengths (deep red/copper).

---

## Live WebGL Deployment

Launch the live interactive GPU canvas directly in your browser:
**[https://agnelavas.github.io/blackhole-raymarcher/](https://agnelavas.github.io/blackhole-raymarcher/)**

---

## Local Execution

Run a local HTTP static server:
```powershell
python -m http.server 8000