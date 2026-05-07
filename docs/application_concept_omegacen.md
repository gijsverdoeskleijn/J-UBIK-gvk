# Application Concept Sheet OmegaCEN

## Note Status
- Status: `working`
- Canonical Role: `template`
- Last reviewed: `2026-05-05`
- Authors: [Gijs Verdoes Kleijn](https://gijsverdoeskleijn.org), ...
- classification: this note is for [Torsten Enßlin](https://wwwmpa.mpa-garching.mpg.de/~ensslin/) and Jakob Knollmüller for circulation inside their UBIK/IFT group and for [Gijs Verdoes Kleijn](https://gijsverdoeskleijn.org) and [Eduardo Balbinot](https://balbinot.github.io/) for circulation inside their [OmegaCEN group](https://gijsverdoeskleijn.wordpress.com/omegacen-astronomical-science-data-center/). Heads-up: it contains links to proprietary code repositories and documents that might currently not be accessible to some of us. These can be made available upon request, contact either Gijs or Jakob.
    
This note describes one UBIK application idea that the OmegaCEN Astronomical Science Data Center could be excited to pursue as a collaborative project with the [Information Field Theory Group / UBIK](https://wwwmpa.mpa-garching.mpg.de/~ensslin/) team at MPA and the [Data Science group at German Centre for Astrophysics](https://www.deutscheszentrumastrophysik.de/en). The response is informal and bullet-point based, and does not yet answer every prompt in equal detail. We answer selectively and focus on the points that are most helpful for understanding the idea. The OmegaCEN team is happy to have a discussion with the UBIK team seeking to advance the idea into a concrete work package.

## Application Snapshot
- Euclid ground- and space-based imagiging inference with [J-UBIK](https://github.com/NIFTy-PPL/J-UBIK)
- Optical and near-infrared imaging observed with RUBIN, DECam, CFHT, HSC, Pan-STARRS and Euclid VIS & NIR
- Application description: determine whether UBIK-based image inference of the Euclid ground-based and space-based imaging observations can improve the astrometric and photometric image quality and the efficiency in diagnosing failures in quality. Ground-based imaging inference guided by Euclid's space-based higher spatial resolution data appears an option. The ground-based observations have lower spatial resolution and smaller passbandss located inside Euclid's space-based VIS passband. 

## Current Research Context
- OmegaCEN's current research and development is to (i) improve the photometric quality (to few mmag) and astrometric quality (to few milliarcsecond astrometry) of Euclid's ground-based imaging and (ii) develop a Euclid+Gaia joint astrometric celestial reference frame and catalog denser and fainter than [Gaia CRF3](https://ui.adsabs.harvard.edu/abs/2022A%26A...667A.148G/abstract). The next milestone is the release (ETA December 2026) of the improved data processing algorithms and pipeline for ground-based observations for Euclid's Data Release 2. An overview of the current algorithms and pipeline can be found in [EXT DR1 draft paper, Corcho-Caballero et al 2026 in prep](https://drive.google.com/file/d/13EXRfZlXxP1qMA5Dl5X8KPFtSjKcwCFR/view?usp=sharing)
- This application sits within your broader research direction to have OmegaCEN excel at precision astrometry and precision photometry in imaging for scientific and socio-economic impact. We are exploring extreme data lineage for the purpose of precision astrometry and photometry systematic errors (reference to AstroWISE paper on this), Gaia + Euclid joint astrometric reference frame (Giacomo thesis about this), and perfecting the extraction from images of asteroid streaks (asteroid draft paper about it) and satellite streaks (FOTOS OPS paper? about it)  

## Goal and Value
- The main questions are: can deploying J-UBIK on Euclid's ground-based and space-based imaging improve (a) the derived precision astrometry and (b) photometry and (3) at a computational cost that is affordable?
- This matters scientifically for Euclid science in the area of cosmology, Solar System minor body astrometry, resolved stellar population photometry and astrometry galaxy evolution. Technically for improving the performance of the Euclid PSF and science pixel coaddition algorithms. This matters operationally for better yet "greener" production of the ground-based surveys in Euclid's Data Release 3 and the usage of the space-based and ground-based in the General Open Orbital Dynamics platform (reference). 
- If the astrometry and photometry indeed worked substantially better with J-UBIK-based pipelines for the image survey production of CFHT, HSC, DECam, RUBIN, VIS, NIR, Pan-STARRS this would open the possibility to embed J-UBIK in ESA's Science Ground Segment imaging pipelines and those of AstroWISE
- This would impprove the proper motions of stars and asteroids and photometry/redshifts of stars and galaxies as most important main delivery of the broader workflow and derivation/inference chain of both survey production systems.

## Measurement and Data Context
- It is images, PSF models and their associated weight images, flag maps, passband effective wavelengths that are being measured and observed.
- single-epoch and coadded imaging frames and their metadata are expected to be available for the IFT/UBIK - OmegaCEN collaboration team. 
- The main steps from measurement to scientific or operational interpretation are outlined in Pablo. 
- The stacking of the PSF models per source detection and the precision photometric and astrometric calibration are most important and difficult.
- The key interfaces, transformations, or handoffs in that chain are outlined in Pablo?

## Current Practice and Limits
- How is this is done today is outlined in Pablo + AstroWISE paper plus Teymoor asteroid paper. 
- It is the Euclid Science Ground Segment and AstroWISE methods, models, pipelines and workflows that are currently used.
- All of them already work reasonably well. The main challenge lies in achieving milliarcsecond level absolute astrometry in Euclid's ground- and space-based images and ~5mmag or better color homogeneity.   
- So the current approaches become limiting at the milliarcsecond level astrometry and ~5mmag color homogeneity. 
- In the Euclid Science Ground Segment the handoffs between data, models, and interpretation becomes difficult and unreliable at the interfaces of image production pipelines and image extraction pipelines. Reason: socio-organizational constraints of highly independent and geographically separate teams with largely independent designs of their algorithmic and pipeline software developments.    

## Main Challenges
- The main bottlenecks, uncertainties and failure points are perceived to be in the diagnosability of the photometric and astrometric requirement non-compliances. It is a lot of human manual detective work.
- The parts that are hard to calibrate, model, infer, validate and scale are the PSF models and the spatially varying effective wavelengths of the passbands of the observatories. 
- The steps that are most manual, fragile, opaque, slow are the diagnosis of the mmag-level photometric and milliarcsecond level astrometric requirement non-compliances.
- The joining of the survey image production and astrometric and photometric extractions seem hardest to make consistent and with trustworthy configuration control.

## Proposed Advance
- We would you want to develop, improve, test and demonstrate that UBIK-based imaging inference in VIS astrometry and ground-based color homogeneity outperforms the Euclid Data Release 1 results.
- If this project went unusually well, the joint uptake by DZA and the German and Netherlands Euclid Science Data Centers of Euclid ground-based production and the updatek of Euclid VIS astrometric platform with DZA+INAF+OmegaCEN ASDC would be the genuinely exciting advance.
- The smallest credible demonstrator in the first `12-18` months is improved or equal color homogeneity on the UNIONS EDFN, DECAM+HSC EDFS+EDFF+COSMOS.   
- A successful outcome after `3-4` years would look like UBIK-based survey production in the AstroWISE, GOOD and Euclid survey production platforms
- The amain advance woyuld be better controlled observatory models (reference to FGM-based calibration) thanks to Bayesian inference based image productions. This should be accompanied by careful design of the upgraded workflows in each of the three platforms for a better and greener end-to-end workflow.

## Assets, Inputs, and Constraints
- Needed are imaging data (those are provided by the Euclid SGS and AstroWISE), observatory models (those require collaboration from UNIONS and DES and RUBIN teams, metadata, calibration information and (provided by Euclid SGS and AstroWISE teams). 
- What assets already exist: datasets, pipelines, models, software, benchmark cases: see above. 
- What technical capabilities or expertise would be needed?: Prior knowledge: exchange of knowledge between UBIK team (they need to get a 101 on gory details of EXT) and OmegaCEN team (they need to get a 101 on UBIK).
- What external dependencies or constraints exist? Membership/access to RUBIN, Euclid VIS and NIR and UNIONS data for proprietary data. But it is expected that we can start with publicly released data.  

## Resource Context
- Roughly what would a full-time research position cost in your environment over `5` years?: look up scale 10.medium with SPL for EU funding. 
- Are there additional non-personnel costs that would likely be important for this application: CIT contribution
  telescope visits, instrument access, compute, storage, hardware, travel, software, data acquisition, or similar? In return provided by CIT for a hardware investment in them. 
- There are not further important local constraints or overheads we should be aware of at OmegaCEN University of Groningen.

## Validation
- How would you evaluate whether the project succeeded? GOOD-based publications. Legacy science of Pablo, Eduardo 
- What would count as a convincing result or demonstration? GOOD-based publications. Legacy science of Pablo, Eduardo 
- Are there benchmark cases, reference datasets, or comparison methods? Euclid Data Release 1, KiDS DR5. 
- What would show that the approach is not only useful in this case, but robust or transferable?: Open Source licence availability. 

## Risks and Open Questions
- What are the biggest uncertainties or blockers?: human resources for EXT quality assessment. 
- What might make this difficult in practice? Funding
- Which questions would need clarification early on? FTEs than can be committed on both sides provided the funding is there for them. 
- What would make you hesitate to put this forward as a serious project line? No outlook on a funding plan. 

## Project Context
- What are your expectations going into this project? Very positive gamechanger. 
- Are there aspects of the project that seem especially relevant to your application? Diagnosability of astrometric and photometric quality compromises thanks to differentiable instrument and sky models. 
- Are there parts of the project direction that still feel unclear from the perspective of this application? How well does it work in the challenging environment of kHz atmospheric variations and gravity-induced minute scale variations in instrument models. 

## Resources
- Roughly what would a full-time position cost in your environment per year? postdoc, PhD, senior researcher. with SPL using start date in June 2027 
- Are there additional costs beyond the usual overhead that would be associated with the project? (regular on-site visits, hardware/tools,...): no


## References and Background Material
- If available, can you provide papers, notes, earlier proposals, slides, draft ideas, or internal documents that would help us understand this application better?: Key papers, code repositories, ADS reference lists. 

## General Notes
- gijsToSelf: [UBIK mindmap](https://docs.google.com/presentation/d/1Y7P4BjCyIc-nP6L6s6xpaE0Q1GnRoe0pWDN10GTVoII/edit?slide=id.g3f79a33b93d_0_0#slide=id.g3f79a33b93d_0_0)
