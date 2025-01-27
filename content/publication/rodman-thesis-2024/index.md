---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: 'Magnetic Field Evolution in Black Hole Accretion Disks and Relativistic Jets'
subtitle: ''
summary: ''
authors:
- P E Rodman
tags: []
categories: []
date: '2024-07-29'
lastmod: 2024-07-29T00:00:00+00:00
featured: true
draft: false
math: true

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ''
  focal_point: ''
  preview_only: true

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: ["accretion","jets"]
publishDate: '2024-11-29T00:00:00.000000Z'
publication_types:
- 7
abstract: Supermassive black holes (SMBHs) catalyse change in their host galaxies, mediated through the inflow and subsequent outflow of material through the massive body. While an SMBH does not—indeed, cannot—hold its own magnetic field, the material it interacts with, feeds upon, and expels outwards is naturally magnetic, and this embedded magnetic field is expected to have a complex effect upon these processes. Due to the inherent difficulties in studying magnetic fields there is still much to learn about their role around SMBHs generally, and in accretion and the launching of relativistic jets in particular. This thesis aims to tackle both topics using three-dimensional magnetohydrodynamics (MHD) and relativistic magnetohydrodynamics (RMHD) simulations.

In the first half (Chapters 2 and 3), I focus on the role of magnetic fields in simulations of thick accretion disks. At stake is a core question within the field of disk simulations: can a simulated accretion disk self-generate the strong, large-scale poloidal field needed to launch relativistic jets? To assess this question, I simulate disks with initially toroidal fields of both high (plasma beta $\beta = P_{\rm gas} /P_{\rm mag} = 5$) and low ($\beta = 200$) field strength and at high and moderate resolution, using the code Athena++. I find that both weak and strong initially toroidal field disks can generate a poloidal field, with the initially strong case producing a more ordered and large-scale field. These findings are tempered by caution on the resolution, as an $m = 1$ mode overdensity is created at the crossroads of a weak field, moderate resolution, and resolution step-change. I additionally perform a minor study of the disk dynamo, covered in Chapter 3. Using mean-field dynamo theory, I calculate the diagonal, symmetric $\alpha_{ij}$ components under both a global azimuthal average and a local Gaussian filter average, finding that local averaging returns more robust numerical signals. We retrieve a northern hemisphere $\alpha_{\phi\phi}$ sign that is consistent with previous works and is in line with expectations of an $\alpha\Omega$-type dynamo. The mean-field formalism returns a better fit later in the disk evolution, suggesting that additional dynamo factors are present in the early phases of field evolution and growth.

In the second half of the thesis, in Chapter 4, I move my focus to relativistic jets and investigate whether magnetised head-tail (HT) jets launched in a realistic turbulent magnetised background can form magnetic linkages between the lobes as have been observed in recent high-resolution radio images. To assess this, I simulate a suite of low density (density ratio $\eta = \rho_{\rm jet} /\rho_{\rm amb} = 10^{−3}$), pressure-matched jets at both low ($v_j = 0.24c$) and high ($0.94c$) velocity into pre-evolved turbulent backgrounds generated using the PLUTO code and subject them to strong, transonic crosswinds. I find that magnetic linkages do occur, but are between the jet lobes and the ambient medium, with the region between lobes being too turbulent to support long filaments. I additionally find that the location and direction of the existing filaments depend on the particular turbulent background realisation, implying that observations of filaments could be used to constrain the ICM field.
publication:
url_pdf: https://www.repository.cam.ac.uk/handle/1810/376585
doi: 10.17863/CAM.113765
---
