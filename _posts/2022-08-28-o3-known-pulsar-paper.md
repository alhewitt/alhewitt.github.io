---
title: "Searches for Gravitational Waves from Known Pulsars at Two Harmonics in the Second and Third LIGO-Virgo Observing Runs"
date: 2022-08-28
permalink: /publications/o3-known-pulsar-paper/
categories:
  - PhD
  - Publications
tags:
  - Lancaster
  - Gravitational Waves
  - Pulsars
  - Unfinished
toc: true
toc_sticky: true
toc_item: 
header:
  teaser: /assets/img/o3paper/h0.jpg
---

**[LIGO Science Summary](https://www.ligo.org/science/Publication-O3KnownPulsars/) (first draft written by me, with improvements thanks to others in the collaboration).**

## Gravitational waves from pulsars

{% capture fig_img %}
![Foo]({{ "/assets/img/o3paper/cws.gif" | relative_url }})
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>A pulsar with some ellipticity emitting gravitational waves as it rotates. Credit: Graham Woan.</figcaption>
</figure>

In order for an object to emit gravitational radiation, it needs to have some mass asymmetry. Imagine a frictionless rod submerged in water. If you rotate the rod about its long axis, you would not observe any waves. This is because it is rotationally symmetric. If you rotate the rod along another axis, however, you would expect to see waves. Similar to this, a mass with some acceleration will create waves in space-time. Pulsars are hypothesised to have some ellipticity, also referred to as “mountains” which can be caused at “birth” or during their lifetimes through processes such as accretion. Unlike Earth’s mountains they are merely a few centimetres tall, but even that is enough to have an effect noticable on Earth.

As a pulsar rotates with this ellipticity, the emission of gravitational waves (GWs) will cause it to lose energy in the form of angular momentum loss. The amplitude of the GW emitted scales with increasing frequency so the high frequencies of pulsars mean puts the GWs within current detector sensitivity ranges. Although no such signal has been directly observed yet, naive upper limits on the GW amplitude can be placed by assuming that all rotation energy that is lost by the star is lost through the emission of GWs (this is unlikely as a large fraction is expected to be lost through magnetic dipole radiation). We call these limits "spin-down limits".

The frequency of the GWs are also expected to be closely linked to the pulsar rotation frequency so that the GW frequency is 2x the pulsar frequency. There are some processes which can also cause emission at 1x the frequency such as free precession of the pulsar or a independently rotating superconducting core. In order to account for these possibilities, searches look for GW signals at both 1 and 2 times the pulsar rotation frequency.

## Why care? 

Unfortunately, due to their incredibly small size, pulsars are difficult to observe directly. Often, we don't know much more about them than their distance and rotation frequency. This means there are still many questions about pulsars which we haven't yet answered. For example, there are various possible theorised equations of state (EoS) for pulsars which each give different upper limits on the maximum deformation (ellipticity) allowed. So, measuring deformation through GW observation would help constrain the EoS. 

{% capture fig_img %}
![Foo]({{ "/assets/img/o3paper/rossby-wave.jpg" | relative_url }})
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Rossby waves on Earth. Image credit: <a href="[url](https://oceanservice.noaa.gov/facts/rossby-wave.html)">NASA/GSFC</a></figcaption>
</figure>

Additionally, there are other processes which may emit gravitational waves which occur beneath the crust of the star. For example, r-waves or Rossby waves are a phenomenon which occur on Earth and are similarly predicted to occur on pulsars, but have yet to be proven. An observation of a GW from one of these processes would provide strong evidence of their existance and give valuable information on the proccesses beneath pulsar crusts.

## This search

Now I hope you can see why it might be a good idea to look for these GW signals, and that is exactly what we did. We looked at data from the O2 and O3 (meaning second and third) observing runs of LIGO-Virgo in what is an updated version of a search performed on O1 and O2 data previously. There are various types of searches. A targeted search will look for gravitational waves from known pulsars. Since we know their distance and frequency for example already, there are fewer parameters which need to be searched over, leading to a less computationally expensive and more sensitive search than other methods. For example, an all-sky search looks for signals over a wide range of parameters in all sky directions while directed searches look for signals in small sky regions where it is believed likely for a pulsar to exist.

GWs from 236 pulsars were searched for, with 74 of these pulsars having not been included in the [previous search](https://iopscience.iop.org/article/10.3847/1538-4357/ab20cb) using O1 and O2 data. 168 of these pulsars are in binary systems and 161 pulsars are millisecond pulsars. Time domain Bayesian analysis was performed on all pulsars searching for signals at 2x and both 1x and 2x the rotation frequency. In the absence of a detection, we present 95% confidence upper limits for the GW amplitude or “strain”.



Here is what I presented at EAS 2022 on this project:
<object data="../assets/pdfs/EAS-2022.pdf" width="1000" height="1000" type='application/pdf'></object>
