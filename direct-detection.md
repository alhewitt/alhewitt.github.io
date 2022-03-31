---
layout: default
---

# Direct Detection of Solar Angular Momentum Loss with the Wind Spacecraft

## TL;DR

I was lucky to be given the opportunity to work with [AWESoME Stars](https://empslocal.ex.ac.uk/AWESoMeStars/) at the University of Exeter during the summer between my 3rd and 4th years there. I worked under Prof. Sean Matt and Dr. Adam Finley to obtain a direct measurement of the angular momentum loss rate of the Sun using data from the *Wind* spacecraft. My specific role was to analyse the data to produce the measurement with guidance from the others on the team. The results were written up by Adam and published in the Astrophysical Journal Letters as [*Direct Detection of Solar Angular Momentum Loss with the Wind Spacecraft*](https://arxiv.org/abs/1910.10177).

## Introduction

The Sun is the closest star to us, the only one whose stellar wind is directly measurable. Our knowledge of our star is used as a reference for how we expect other stars in the universe to behave. It is difficult to understand a process in other stars if it is not first understood in the Sun.

The solar wind is an example of something which is not completely understood. It is a stream of charged particles, consisting mostly of protons and electrons from the ionisation of hydrogen, and alpha particles from the ionisation of helium during fusion within the Sun. This wind doesn't travel at one average speed, rather it travels in one of two types of stream; fast and slow. Slow wind is not fully understood, but it is known that it has conditions resembling those at the Sun's corona with an average speed of 400 kms$$^{-1}$$, and originates from areas of the Sun with closed magnetic field lines. The fast wind is better understood, at an average speed of 700 kms$$^{-1}$$. Its conditions match those of the Sun's photosphere, and it originates from coronal holes and areas of open flux. Through the solar wind, the Sun loses approximately 10$$^{12}$$ gs$$^{-1}$$, and this mass carries with it angular momentum.

Over the lifetime of a star, its rotation about its axis will change significantly. During periods of contraction, such as during its formation, conservation of angular momentum causes the rotation to speed up. While on the main sequence however, angular momentum can be lost due to particles in the stellar wind carrying angular momentum away from the Sun, as well as stresses in its own magnetic field applying a torque. 

Multiple methods of estimating the angular momentum loss of the Sun use models to predict a value. Each method yields a different result. Without an experimental value to work towards, it is impossible to know which of these models is the most accurate.

This project aims to produce a value for the rate at which the Sun is losing angular momentum.

## Open flux

The angular momentum flux of the Sun can be calculated theoretically. Magneto Hydrodynamic (MHD) models can be used to obtain a value, and there are many methods of doing so. One such method uses the open flux.

The open flux, the flux along the open field lines in the solar magnetic field, can be related to the Alfvén radius. This is the radius at which the bulk velocity of the waves in the magnetic field equals the Alfvén velocity (Belenkaya et al., 2014). This radius is important, as mathematically, the stresses in the magnetic field exert the torque required to produce co-rotation at the Alfvén radius (Weber and Davis, 1967), though this does not happen physically. Knowing this distance, it is possible to calculate the torque on the Sun due to the magnetic stresses. 

Open flux is defined as
\begin{equation}
\label{eq:flux_integral}
\phi=\int\mathbf{B}\cdot d\mathbf{s}.
\end{equation}
By evaluating the integral over the surface of a sphere, the open flux can be calculated using

\begin{equation}
\label{eq:open-flux}
\phi_{open}=4\pi \langle R^2 |B_r|_{hr} \rangle_{27 days},
\end{equation}

by assuming that the field lines at this radius will be predominantly open. The magnetic field is taken in one hour cadence in order to reduce small time-scale fluctuations before taking the modulus.

Using this value, the magnetisation parameter can be calculated as
\begin{equation}
\label{eq:magnetisation}
\Upsilon_{open} = \frac{\phi_{open}^2 / R_*^2}{\dot{M}v_{esc}},
\end{equation}
where $$R_*$$ is the solar radius ($$6.96\times10^{10}$$cm) and $$v_{esc}=\sqrt{2GM_*/R_*}$$ with $$M_*$$ being the solar mass $$1.99\times10^{33}$$ g. $$\dot{M}$$ represents the mass loss:
\begin{equation}
\label{eq:mdot}
\dot{M}=4\pi\langle R^2 v_r \rho\rangle_{27 days}.
\end{equation}

The magnetisation parameter can be used to obtain the average alfvén radius:

\begin{equation}
\label{alfven}
\frac{\langle R_A \rangle}{R_*} = K_o[\Upsilon_{open}]^{m_o},
\end{equation}

where $$K_o=0.33$$ and $$m_o=0.371$$ (Finley and Matt, 2018) which then allows the torque due to the solar wind to be calculated as

\begin{equation}
\tau = \dot{M}\Omega_*R_*^2 \left( \frac{\langle R_A \rangle}{R_*} \right) ^2.
\end{equation}

$$
\tau = \dot{M}\Omega_*R_*^2 \left( \frac{\langle R_A \rangle}{R_*} \right) ^2.
$$

Here $$\Omega_*$$ is the solar rotation rate, $$2.6\times10^{-6}$$ rads$$^{-1}$$.

This value for the torque can then be compared to that produced via the other three methods, and with the result from the *Wind* data arrived at in this report. Previously, a value of $$2.28\times10^{30}$$ erg was obtained using data from the Ulysses and ACE spacecrafts by Finley et al., 2018.

<p align="center">
  <figure><img src="assets/img/solar/MassLoss.png" alt="MassLoss.png"/>
  <figcaption>**Figure 1:** Mass flux calculated using equation (5). Proton and alpha contributions are plotted in blue and red respectively, with the total mass flux in dashed black.The solid black line is a 13 CR running average of this total. Teal is the open flux, which reflects the solar activity level.</figcaption></figure>
</p>

Results.
