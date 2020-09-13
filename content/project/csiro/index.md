---
title: "The spectral signature of interstellar scintillation"
subtitle: "Twinkle twinkle little black hole"
summary: A project I undertook in the summer of 2016/2017 with CSIRO in Perth, WA.
date: "2016-11-00T00:00:00Z"
#tags: ["Active Galactic Nuclei", "Quasars"]

reading_time: true  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
math: true

# Featured image
# To use, place an image named `featured.jpg/png` in your page's folder.
# Placement options: 1 = Full column width, 2 = Out-set, 3 = Screen-width
# Focal point options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
# Set `preview_only` to `true` to just use the image for thumbnails.
image:
  placement: 1
  caption: ""
  focal_point: "Center"
  preview_only: false
  alt_text: ""
---

When the light from stars passes through the Earth’s atmosphere, the light waves are distorted and result in the “twinkling” affect we see at night. Analogously, when the radio light from a quasar passes through a cloud of dust in the interstellar medium, these radio waves are distorted and produce a highly variable signal over days to months that we can observe on Earth. By studying this variability, we can learn more about the material in the interstellar medium.

{{< figure library="true" src="scintillate.png" title="From left to right: (a) light is emitted from the AGN as plane-parallel waves. (b) This light passes through a cloud of material in the interstellar medium. (c) The light waves emerge from the cloud twisted and distorted, both in space and time. (d) These distorted waves are detected by a radio observatory, and are seen in the form of a highly variable lightcurve as in this example from source PKS 1257-326 (Bignell et al. 2003)." >}}

During the Summer of 2016—2017, I undertook a project at the CSIRO Astronomy and Space Science (CASS) office in Perth, Australia with Dr Cormac Reynolds to study this kind of quasar variability. The properties of scintillation vary depending on the properties of the medium and the frequency you observe at, and can be primarily characterised by a number called the _modulation index_, alongside the _structure function_:

$$ M = \frac{\sqrt{\langle F^2 \rangle}}{\langle F \rangle}$$

$$ SF = \sqrt{|F(T_i) - F(T_j)|^2}$$

where F is the flux at the given wavelength and T is the timescale of variability. Together these give both the typical strength and timescale of the variation. 

We used a sample of 2232 quasars from the Australian Telescope Extreme Scattering Events Survey (ATESE) pipeline observed from 2014—2016, across a frequency range of 2—12 GHz and covering a wide range on the sky. Limiting ourselves to those sources which had >1% variation on a timescale of 50 days, we found a slight bias towards greater variation in the galactic plane (b=0).

{{< figure library="true" src="structurefunction.png" title="The strength of variability as a function of distance from the galactic plane, where b=0 denotes the line of the galactic plane. There is a slight, but not statistically significant, preference towards more variability at b=0." >}}

## For more information:
 - [CSIRO Astronomy and Space Science (CASS)](https://www.csiro.au/en/Research/Astronomy)
 - [CASS Undergraduate Vacation Program](https://www.atnf.csiro.au/research/summer_vacation/index.html)
