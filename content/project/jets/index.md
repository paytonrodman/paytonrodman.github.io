---
title: "Radio Jet Filament Formation in a Magnetised Medium"
subtitle: "Can simulations produce the radio filaments we observe?"
summary: A brief look at the second half of my PhD
date: "2024-02-11T00:00:00Z"
tags: ["Active Galactic Nuclei", "Jets", "Simulation", "Data Analysis", "In Progress"]

reading_time: true  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
math: true
weight: 1
draft: false

# Featured image
# To use, place an image named `featured.jpg/png` in your page's folder.
# Placement options: 1 = Full column width, 2 = Out-set, 3 = Screen-width
# Focal point options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
# Set `preview_only` to `true` to just use the image for thumbnails.
image:
  placement: 1
  caption: ""
  focal_point: "Center"
  preview_only: true
  alt_text: ""
---

At the heart of most large galaxies is a supermassive black hole, or SMBH for short. Black holes get a bit of a bad rap, and are often talked about as though they uncontrollably eat everything around them, but this isn't really true and *jets* are a good example. As material comes close to a black hole it will want to form into an orbit, much like our Earth orbits the Sun. This orbit tends to be very flat, so we call the resulting accumulation of 'stuff' an accretion *disk* (you can read a little more about accretion disks in another post [here](https://www.paytonelyce.com/project/accretion/)). From the accretion disk, material can then fall into the black hole.

**But** this isn't a done deal. Not all material will fall into the black hole. Some charged particles (electrons and protons) instead get tangled up in the strong magnetic field draping around the black hole and are launched away from the poles through the Blandford-Znajek process. As these charged particles fly away, they rotate about the magnetic field lines and emit radiation that we can observe as radio waves. When a radio telescope looks up at a galaxy in the sky, we often see something like this:

{{< figure library="true" src="HercA.jpg" style="width:48px;height:48px;" title="Radio jets from galaxy Hercules A. Visible light (stars) was collected using the Hubble Space Telescope, while the radio jets are shown with data from the Very Large Array. Image Credit: NASA (visible) / ESA (radio)" >}}

Hercules A is a slightly special case as it's pretty close to us in astronomical terms. Most galaxies we can see are much, much further away and their jets just look like nondescript smudges.

Now, this is all well and good, but in 2020 a new radio telescope called MeerKAT saw something that no one had expected: filaments.

{{< figure library="true" src="ESO137-6.png" style="width:48px;height:48px;" title="Radio threads or filaments are observed streaming from the radio jets in source ESO 137-006, observed with the MeerKAT telescope in 2020. Image Credit: Rhodes University / INAF / SARAO" >}}

The wispy, thready material we can see *inside* the jets was already well-known, but the stuff *linking* the jets? That was new. And unexplained.

We hypothesised that these threads may be bundles of magnetic field, sourced either from around the black hole or from the surrounding environment. To test our ideas, we ran a series of simulations of jets in environments with realistic magnetic fields and strong winds.

Our first simulations didn't include charged particles, so we couldn't produce images that could be directly compared to ESO 137-6, but we did observe links forming between the inner jet field and the outer environment field, which could then theoretically be loaded with charged particles to produce the images we see.

{{< figure library="true" src="jet_Bstream.png" style="width:48px;height:48px;" title="Magnetic field streamlines connecting the jet to the environment." >}}

Our next steps are to add pseudo-particles to these simulations and try to produce some pseudo-observations.
