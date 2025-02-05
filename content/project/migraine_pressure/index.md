---
title: "Comparing daily pressure variation across the globe"
subtitle: "The best and worst places to live with barometric pressure migraine"
summary: A personal project exploring worldwide pressure variation data.
date: "2024-01-00T00:00:00Z"
tags: ["Data Analysis", "In Progress"]

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
  caption: ""
  focal_point: "Center"
  preview_only: false
  alt_text: ""
---

<iframe title="Fraction of days with high pressure variation" aria-label="Map" id="datawrapper-chart-f0TbC" src="https://datawrapper.dwcdn.net/f0TbC/2/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="674" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(a){if(void 0!==a.data["datawrapper-height"]){var e=document.querySelectorAll("iframe");for(var t in a.data["datawrapper-height"])for(var r=0;r<e.length;r++)if(e[r].contentWindow===a.source){var i=a.data["datawrapper-height"][t]+"px";e[r].style.height=i}}}))}();
</script>

Growing up, I often had to watch as my mother and grandmother suffered attacks of migraine, a neurological disorder characterised by episodes of moderate-severe headache, along with nausea and vomiting, photophobia (light aversion) and phonophobia (sound aversion), plus a raft of other strange neurological symptoms like aphasia (garbled speech), weakness, fatigue, loss of vision/sensation, vertigo and dizziness, and more. Migraine is very common, affecting up to 33% of women and 18% of men [[1](https://www.nature.com/articles/s41572-021-00328-4)], peaking in early adulthood. As a result, migraine is often extremely debilitating for its sufferers: it is the leading cause of disability in the 15--49 age group and costs employers in Europe €27 billion in lost productivity annually [[2](https://journals.sagepub.com/doi/10.1177/0333102420977852)].

Migraine attacks can be brought on by many different things, most commonly stress, disturbed/changed sleep, alcohol, and weather changes. While many triggers can be avoided or controlled, the weather cannot be, and so I was motivated to explore which places on Earth would be better or worse for migraine sufferers with weather triggers.

The initial data is sourced from the [meteostat](https://meteostat.net/en/) python library, which provides station and weather data compiled from a number of sources. Although the data has been precompiled into dataframes, it still needs to be cleaned and outliers removed. Identifying outliers in a time series can be a tricky business, primarily because the data may be sparse. To manage issues of data availability, I first select stations that meet the following criteria:

1. At least half of all hourly pressure records are valid (non-NaN).
2. At least half of the recorded days have 6+ pressure measurements.

These requirements may seem quite lenient, but this is based on careful consideration of the data. Many stations in underdeveloped areas and deprived areas will lack the necessary staff or access to equipment to take air pressure measurements every hour of every day. Implementing stricter data requirements could improve data quality somewhat, but it comes at the expense of great swathes of the globe. The two requirements above that I eventually settled on balanced the need for inclusive data while also removing the more obvious outlier stations.

The primary concern with barometric air pressure re triggering migraines is a high rate of change, and so I calculate hourly variation. I then identified outlier pressure change measurements using a variation on the interquartile range (IQR),

$$IQR = Q_3 - Q_1$$

where $Q_1$ and $Q_3$ are the 25th and 75th percentiles of the data for a given day. It is standard to define outliers as any value $>Q_3 + 1.5IQR$ or $<Q_1 - 1.5IQR$, however, based on a series of tests I settled on a higher value of $3IQR$ as it performed better (was more tolerant) when faced with sparse data. Additionally, some locations experience a high degree of pressure variation naturally, on top of extreme weather events that we really want to retain. In the search for high pressure variations, we don't want to accidentally penalise locations for having true high variation. Days with two or more points outside of $3IQR$ (indicative of an outlier spike) are removed.

With the data cleaned, the number of days with a pressure variation $>=10$ hPa is then recorded for each station, and the results plotted!

We see a clear overall trend with smaller latitudes (closer to the equator) having fewer high pressure variations per year compared to higher latitudes. We can also see a region of high variation in the west-midwestern US, where continental and subtropical climate regions meet the colder and semi-arid climates of the Rocky Mountains.
