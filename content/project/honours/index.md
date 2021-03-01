---
title: "Using radio lobes to measure galaxy cluster properties (Honours thesis)"
subtitle: "A big ball of wibbly wobbly, timey wimey stuff"
summary: A brief description of the work I did in 2018 as part of my Honours thesis at the University of Tasmania.
date: "2018-12-00T00:00:00Z"
tags: ["Active Galactic Nuclei", "Jets", "Simulation", "Data Analysis", "Completed Work"]

reading_time: true  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
math: true
weight: 1

# Featured image
# To use, place an image named `featured.jpg/png` in your page's folder.
# Placement options: 1 = Full column width, 2 = Out-set, 3 = Screen-width
# Focal point options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
# Set `preview_only` to `true` to just use the image for thumbnails.
image:
  placement: 1
  caption: "**Radio galaxy Hercules A.** Image Credit: NASA, ESA, S. Baum and C. O'Dea (RIT), R. Perley and W. Cotton (NRAO/AUI/NSF), and the Hubble Heritage Team (STScI/AURA)"
  focal_point: "Center"
  preview_only: false
  alt_text: ""
---

During the 2018 calendar year, I completed my Honours thesis at the University of Tasmania, supervised by Dr Stanislav Shabala and Dr Ross Turner. My goal was to investigate whether radio lobe observables such as length, brightness, and polarisation could be used to infer the intrinsic properties of both the jets/lobes themselves and their host galaxy clusters, which I did through semi-analytic models. The most critical component of this study is the inclusion of polarisation data as the polarisation (or rotation measure, RM) of light is a function of the density (n) and magnetic field (B) of the material which the light passes through:

$$\text{RM} = 812 \int n_e B_{||}ds$$

I constructed a series of simulated galaxy clusters with a variety of masses (M), and with embedded radio lobes of differing power (P), age (t), and orientation ($\theta$) to the observer. I then simulated how these sources would appear to an observer here on Earth, collecting data on the luminosity of the radio lobes (L), the total source length (D),  the dispersion in RM across the source ($\sigma_{\text{RM}}$), and the heteroscedasticity of the RM (the variation in variations; H).

Values of M, P, t, and theta are then chosen at random to produce a sample of ‘real’ cases. The observables for these objects are simulated and the program is then asked to give its best estimate for M, P, t, and theta by comparing the observables it has obtained with the (much sparser) reference list of simulated cases performed above, under one of two conditions:

1. Only the observables L and D are available for the ‘real’ cases (i.e. no polarisation data)
2. Observables L, D, $\sigma_{\text{RM}}$, and H are all available (i.e. polarisation data)

If the program selects close to the correct e.g. mass and age, and does so with high confidence, then it has successfully measured those quantities. For both galaxy cluster mass and radio source age, the inclusion of polarisation observables does not greatly impact the _accuracy_ of those measurements, but it does greatly increase the _confidence_. 

{{< figure library="true" src="prob1.jpeg" title="The difference between the model radio source age and the estimated age when (left) only L and D observables are available, and (right) when polarisation observables sigma_RM and H are also available. The correct (x-axis = 0) source age is more confidently chosen when polarisation data is also included." >}}

{{< figure library="true" src="prob2.jpeg" title="The difference between the model galaxy cluster mass and the estimated mass when (left) only L and D observables are available, and (right) when polarisation observables sigma_RM and H are also available. The correct (x-axis = 0) cluster mass is more confidently chosen when polarisation data is also included." >}}
