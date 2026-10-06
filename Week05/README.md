# Week 05 — MR Physics: Larmor, Bloch Equations & Slice Selection

Nuclear magnetic resonance fundamentals: spin precession, the Larmor equation,
the Bloch equations ($T_1/T_2$ relaxation), tumor-vs-normal tissue contrast, and
z-gradient slice selection.

## Contents

| File | Description |
|------|-------------|
| [GyromagneticRatio.ipynb](GyromagneticRatio.ipynb) | Computes the proton gyromagnetic ratio $\gamma$ from the Larmor equation $\omega = \gamma B_0$ given $B_0 = 2.35\ \text{T}$ and a 100 MHz resonance frequency, with explicit unit conversions, compared against the CODATA value. |
| [BlochEquations.ipynb](BlochEquations.ipynb) | Solves the Bloch equations for free precession after a 90° pulse in a homogeneous field (analytic + `solve_ivp`), plots $M_x, M_y, M_z$ and the 3D trajectory, and overlays tumor vs normal-tissue precession spirals from measured $T_1/T_2$. |
| [SliceSelection.ipynb](SliceSelection.ipynb) | Simulates z-gradient slice selection: the linear $f(z)$ mapping, the rectangular excitation band (frequency/k-space view), the time-domain sinc RF pulse, and an FFT check mapping frequency back to the excited slice. |
| 1971_Science_Damadian.pdf | Damadian (1971), *Tumor detection by nuclear magnetic resonance*. |
| L10.pdf | Lecture slides. |
| Precession-WheelExperiment_PaulCallaghan.mp4 | Sir Paul Callaghan's spinning-wheel demonstration of precession. |

## Key concepts

- **Larmor equation**: $\omega_{\text{Larmor}} = \gamma B_0$ and $f_{\text{Larmor}} = \dfrac{\gamma}{2\pi} B_0$
- Unit conversions: MHz → Hz, cyclic frequency $f$ → angular frequency $\omega = 2\pi f$
- Proton gyromagnetic ratio: $\gamma \approx 2.675\times10^{8}$ rad s$^{-1}$ T$^{-1}$, i.e. $\gamma/2\pi \approx 42.58$ MHz/T
- **Bloch equations**: transverse decay with $T_2$, longitudinal recovery with $T_1$; tumor tissue shows elevated $T_1/T_2$ (Damadian)
- **Slice selection**: a gradient makes $f(z)=(\gamma/2\pi)(B_0+G_z z)$; a rect frequency band (sinc RF pulse) selects a slab of thickness $\Delta z = BW/[(\gamma/2\pi)G_z]$

## References — Paul Callaghan MRI/NMR video lectures

Sir Paul Callaghan's video series on the principles of NMR and MRI:

- Playlist: <https://www.youtube.com/watch?v=jUKdVBpCLHM&list=PLbMizTOj9NEmNUhHHi08cZKTeMAnpO2En&index=2>
