# Application Concept Sheet OmegaCEN

## Note Status
- Status: `working`
- Canonical Role: `template`
- Last reviewed: `2026-05-07`
- Authors: [Gijs Verdoes Kleijn](https://gijsverdoeskleijn.org), ...
- classification: this note is for [Torsten Enßlin](https://wwwmpa.mpa-garching.mpg.de/~ensslin/) and Jakob Knollmüller for circulation inside their UBIK/IFT group and for [Gijs Verdoes Kleijn](https://gijsverdoeskleijn.org) and [Eduardo Balbinot](https://balbinot.github.io/) and [Rees Williams](https://www.rug.nl/staff/o.r.williams/?lang=en) for circulation inside their [OmegaCEN group](https://gijsverdoeskleijn.wordpress.com/omegacen-astronomical-science-data-center/).
- caveat: it contains links to proprietary code repositories and documents that might currently not be accessible to some of us. These can be made available upon request: contact either Gijs or Jakob.
    
This note describes one idea for an UBIK application that the OmegaCEN Astronomical Science Data Center could pursue as a collaborative project with the [Information Field Theory Group / UBIK](https://wwwmpa.mpa-garching.mpg.de/~ensslin/) team at MPA and the [Data Science group at German Centre for Astrophysics (DZA)](https://www.deutscheszentrumastrophysik.de/en). The response is informal and bullet-point based, and does not yet answer every prompt in equal detail. We answer selectively and focus on the points that are most helpful for understanding the idea. The OmegaCEN team is happy to have a next discussion with the UBIK team to advance the idea into a concrete work package as part of the UBIK PI-ed [HORIZON-INFRA-2026-TECH-01-01](https://ec.europa.eu/info/funding-tenders/opportunities/portal/screen/opportunities/topic-details/HORIZON-INFRA-2026-TECH-01-01?isExactMatch=true&status=31094501,31094502,31094503&callIdentifier=HORIZON-INFRA-2026-01&order=DESC&pageNumber=1&pageSize=50&sortBy=startDate) funding proposal with deadline 16 June 2026. The work package would start June 2027 with a HORIZON-funded postdoctoral researcher as core member. 

## Application Snapshot
- Euclid ground- and space-based imagiging inference with [J-UBIK](https://github.com/NIFTy-PPL/J-UBIK)
- Optical and near-infrared imaging observed with RUBIN, DECam, CFHT, HSC, Pan-STARRS and Euclid VIS & NIR
- Application description: determine whether UBIK-based image inference in processing Euclid ground-based and space-based imaging observations can (i) improve the astrometric and photometric image quality and (ii) improve the efficiency in diagnosing failures in quality. It is appears worthwhile to explore the option to have the ground-based imaging inference based processing be guided by Euclid's space-based higher spatial resolution data. The ground-based observations have lower spatial resolution than VIS. The ground-based observations have narrowier passbands (Sloan griz) than VIS and are located inside Euclid's space-based VIS passband. 

## Current Research Context
- OmegaCEN's current research and development is to (i) improve the photometric quality (to few mmag) and astrometric quality (to few milliarcsecond astrometry) of Euclid's ground-based imaging and (ii) develop a Euclid+Gaia joint astrometric celestial reference frame and catalog denser and fainter than [Gaia CRF3](https://ui.adsabs.harvard.edu/abs/2022A%26A...667A.148G/abstract). The next milestone is the release (ETA December 2026) of the improved data processing algorithms and pipeline for ground-based observations for Euclid's Data Release 2. An overview of the current algorithms and pipeline can be found in the [Euclid Data Release 1: EXT ground-based imaging data paper by Corcho-Caballero et al 2026, in prep](https://drive.google.com/file/d/13EXRfZlXxP1qMA5Dl5X8KPFtSjKcwCFR/view?usp=sharing)
- This application sits within OmegaCEN's broader research direction to have OmegaCEN excel at precision astrometry and precision photometry in imaging for [science](https://ui.adsabs.harvard.edu/user/libraries/BHL-3XEeTMuiYAp4__HiFQ) and [socio-economic impact](https://ui.adsabs.harvard.edu/user/libraries/kY2PQC1-Q5-WGjzDwKsSDg). The OmegaCEN team is exploring extreme data lineage ([Begeman et al 2013](https://ui.adsabs.harvard.edu/abs/2013ExA....35....1B/abstract)) for the purpose of tracking down subtle systematic errors in astrometry and photometry, for the purpose of provenance of a [Gaia + Euclid joint astrometric reference frame](https://drive.google.com/file/d/1bfrVUKodW7PShFOc0aMWGWISj4dxdgWm/view?usp=sharing), and perfecting the extraction from images of asteroid streaks (e.g., [Saifollahi et al 2023](https://ui.adsabs.harvard.edu/abs/2023A%26A...673A..93S/abstract)) and satellite streaks (e.g., [Stoppa et al 2024](https://ui.adsabs.harvard.edu/abs/2024A%26A...692A.199S/abstract)).  

## Goal and Value
- The main questions are: can deploying J-UBIK on Euclid's ground-based and space-based imaging improve the derived (a) precision astrometry and (b) photometry and (3) to achieve this at a computational cost that is affordable?
- This matters scientifically for Euclid science in the area of cosmology, Solar System minor body astrometry, resolved stellar population photometry and astrometry galaxy evolution. Technically for improving the performance of the coaddition of both the PSF models and science pixels of Euclid's ground-based observations. This matters operationally for better and "greener" production of the ground-based surveys in Euclid's Data Release 3 and the usage of both the space-based and ground-based in the [General Open Orbital Dynamics (GOOD)](https://www.rug.nl/fse/news/awards-and-grants/open-science-platform-voor-baanberekeningen-krijgt-anderhalf-miljoen-nwo-subsidie) platform. 
- If the astrometry and photometry indeed worked substantially better with J-UBIK-based pipelines for the image survey production of CFHT, HSC, DECam, RUBIN, VIS, NIR, Pan-STARRS this would open the possibility to embed J-UBIK in the Euclid Mission Science Ground Segment imaging pipelines and in [AstroWISE](https://www.astro-wise.org/).
- This would impprove the derivation of (i) proper motions and/or orbits of stars, asteroids and satellites and (ii) photometry/redshifts of stars and galaxies. This would perhaps the most important main delivery of the broader workflow and derivation/inference chain of both survey production systems.

## Measurement and Data Context
- It is images, PSF models and their associated weight images, flag maps, passband effective wavelengths that are being measured and observed.
- Euclid's ground-based and space-based public single-epoch and coadded imaging frames and their metadata are available for the IFT/UBIK - OmegaCEN collaboration team. 
- The main steps from measurement to scientific or operational interpretation are outlined for Euclid's ground-based imaging observations in [Corcho-Caballero 2026 in pre](https://drive.google.com/file/d/13EXRfZlXxP1qMA5Dl5X8KPFtSjKcwCFR/view?usp=sharing) and for AstroWISE's imaging data in [McFarland et al 2013](https://ui.adsabs.harvard.edu/abs/2013ExA....35...45M/abstract). 
- The stacking of the individual PSF models for each source and the precision photometric and astrometric calibration are most important and difficult.
- The key interfaces, transformations, or handoffs in that chain are outlined in [Corcho-Caballero 2026 in pre](https://drive.google.com/file/d/13EXRfZlXxP1qMA5Dl5X8KPFtSjKcwCFR/view?usp=sharing) and in [McFarland et al 2013](https://ui.adsabs.harvard.edu/abs/2013ExA....35...45M/abstract). 

## Current Practice and Limits
- How the photometric and astrometric survey production is done today is outlined in in [Corcho-Caballero 2026 in pre](https://drive.google.com/file/d/13EXRfZlXxP1qMA5Dl5X8KPFtSjKcwCFR/view?usp=sharing) and in [McFarland et al 2013](https://ui.adsabs.harvard.edu/abs/2013ExA....35...45M/abstract) and in [Saifollahi et al 2023](https://ui.adsabs.harvard.edu/abs/2023A%26A...673A..93S/abstract). 
- It is the Euclid Science Ground Segment and AstroWISE methods, models, pipelines and workflows that are currently used.
- All of them already work reasonably well. The main challenge lies in achieving milliarcsecond level absolute astrometry and ~5mmag or better color homogeneity.   
- So the current approaches become limiting at the milliarcsecond level astrometry and ~5mmag color homogeneity. 
- In the Euclid Science Ground Segment the handoffs between data, models, and interpretation becomes difficult and unreliable at the interfaces of image production pipelines and image extraction pipelines. Reason: socio-organizational constraints of relatively independent (and geographically separated) teams with largely independent designs of their algorithmic and pipeline software developments.    

## Main Challenges
- The main bottlenecks, uncertainties and failure points are perceived to be in the diagnosability of the photometric and astrometric requirement non-compliances. It is a lot of human manual detective work.
- The parts that are hard to calibrate, model, infer, validate and scale are the PSF models and the spatially varying effective wavelengths of the passbands of the observatories. 
- The steps that are most manual, fragile, opaque, slow are the diagnosis of the mmag-level photometric and milliarcsecond level astrometric requirement non-compliances.
- The consistency of the survey image production pipeline and astrometric and photometric extraction pipeline seem hardest to make consistent and with trustworthy configuration control. This is perceived to be mostly due to socio-organizational constraints. 

## Proposed Advance
- We want to develop, improve, test and demonstrate that UBIK-based imaging inference in (a) VIS astrometry and (b) ground-based color homogeneity outperforms the Euclid Data Release 1 results.
- If this project went unusually well, the genuinely exciting advance would be the joint uptake by DZA and the [German](https://www.mpe.mpg.de/1270194/Data_Center) and [Netherlands Euclid Science Data Centers](https://www.rug.nl/research/kapteyn/onderzoek/euclid-netherlands-science-data-centre?lang=en) of Euclid ground-based production and the uptake of Euclid VIS astrometric platform with [INAF](https://www.aanda.org/articles/aa/abs/2025/12/aa57407-25/aa57407-25.html) DZA, INAF, OmegaCEN 
- The smallest credible demonstrator in the first `12-18` months is improved or equal color homogeneity on the Eulid Wide Surevey data of [UNIONS](https://drive.google.com/file/d/13EXRfZlXxP1qMA5Dl5X8KPFtSjKcwCFR/view?usp=sharing) in the Euclid Deep Field North and DECAM and HSC wide and deep images in the Euclid Deep Field South, Euclid Deep Field Fornax and COSMOS field.   
- A successful outcome after `3-4` years would look like UBIK-based survey production inside the three survey production platforms: AstroWISE, GOOD and Euclid Science Ground Segment.
- The main technical advance woyuld be better controlled observatory models thanks to Bayesian inference based image productions. This should be accompanied by careful design of the upgraded workflows in each of the three platforms for a better yet greener end-to-end workflow.

## Assets, Inputs, and Constraints
- Needed are imaging data. Those are provided by the Euclid Consortium and OmegaCEN), observatory models (those require collaboration from UNIONS and Dark Energy Survey and RUBIN teams. Metadata, calibration information. Those are provided by Euclid Consortium and OmegaCEN through the Euclid Science Ground Segment and AstroWISE. 
- What assets already exist: datasets, pipelines, models, software, benchmark cases: see above. 
- What technical capabilities or expertise would be needed?: Prior knowledge: exchange of domain knowledge between DZA/UBIK team and OmegaCEN team. The OmegaCEN team needs to acquire a basic knowledge of NFT. Bayesian imaging inference and J-UBIK implementation. The DZA/UBIK team needs to acquire a basic knowledge of the Euclid ground- and space-based imaging astrometry and photometry challenges.
- What external dependencies or constraints exist? Membership/access to RUBIN consortium, Euclid VIS and NIR and UNIONS data for proprietary data. But it is expected that we can start with publicly released data.  

## Resource Context
- Roughly what would a full-time research position cost in your environment over `5` years?: A postdoctoral research position starting 1 June 2027 and ending 5 years later would have a salary cost on average of 125kEuro/year. (This is a postdoc at Netherlands University scale 10 and seniority step 6.). The calculation includes the employer fees and overheads. A similar salary scale pertains to support from academic IT personnel at the University of Groningen. 
- Additional non-personnel costs that would likely be important for this application are access to sufficient compute, storage and databasing resources. These could be provided by the [Donald Smits Center for Information Technology](https://www.rug.nl/society-business/center-for-information-technology/) at the University of Groningen. And funding for in person workshops and meetings between the UBIK/DZA team and the OmegaCEN team.
- There are no further important local constraints or overheads.

## Validation
- We would evaluate whether the project succeeded by the publications on Euclid science using this project's code and other deliverables. Solar System science and Planetary Defence using those as well. And technical publications to accompany the software releases by the project. 
- What would count as a convincing result or demonstration? Achieving similar or better astrometry and photometry on Euclid ground-based and space-based imaging through UBIK-based code. In comparison to Euclid Data Release 1. 
- Are there benchmark cases, reference datasets, or comparison methods? Euclid Data Release 1, [Kilo-Degree Data Release 5](https://ui.adsabs.harvard.edu/abs/2024A%26A...686A.170W/abstract)
- What would show that the approach is not only useful in this case, but robust or transferable?: An Open Source licence availability. 

## Risks and Open Questions
- What are the biggest uncertainties or blockers?: sufficient FTE of Eduardo Balbinot and Gijs Verdoes Kleijn to pursue this very exciting project. Reason: currently they have a significant commitment to quality assessment and algorithmic development for the Euclid ground-based surveys. A Netherlands or German 0.5-1.0 FTE postdoctoral position for 2 years to perform these tasks instead of Eduardo and Gijs would be a solution.
- Which questions would need clarification early on?: (1) FTEs than can be committed inside the OmegaCEN and DZA/MPA teams to this exciting project in addition to the EU-funded postdoctoral position. Proprietary data sets from Euclid that team members without a Euclid Consortium membership would need access to. 
- What would make you hesitate to put this forward as a serious project line? No outlook on a funding plan for above's potential bottleneck. 

## Project Context
- What are your expectations going into this project? We foresee a very reasonable chance on achieving a very positive game changer in the way the Euclid Mission and AstroWISE-based and eventually ELT imagers MICADO and METIS will perform their image processing. Yielding an improved astrometric and photometric quality compared to state-of-the-art with their image processing platforms in 2026. 
- Are there aspects of the project that seem especially relevant to your application? Diagnosability of astrometric and photometric quality compromises thanks to differentiable instrument and sky models. 
- Are there parts of the project direction that still feel unclear from the perspective of this application? How well does it work in the challenging environment of kHz atmospheric variations and gravity-induced minute scale variations in instrument models? 

## Resources
- Roughly what would a full-time position cost in your environment per year? A postdoctoral research position starting 1 June 2027 and ending 5 years later would have a salary cost on average of 125kEuro/year. (This is a postdoc at Netherlands University scale 10 and seniority step 6.). The calculation includes the employer fees and overheads. For a 4year PhD starting 1 June 2027 the equivalent would be 80 Keuro per year.  
- Are there additional costs beyond the usual overhead that would be associated with the project? (regular on-site visits, hardware/tools,...): see answers in section "Resource context".


## References and Background Material
- If available, can you provide papers, notes, earlier proposals, slides, draft ideas, or internal documents that would help us understand this application better?: [OmegaCEN code repositories](https://gitlab.astro-wise.org/), [Euclid ground-based code repositories](https://gitlab.euclid-sgs.uk/PF-EXT), [OmegaCEN astro-IT papers](https://ui.adsabs.harvard.edu/user/libraries/CnQTHc69StOZTG4Zz09Hew), [OmegaCEN astro-scientific papers](https://ui.adsabs.harvard.edu/user/libraries/fnZv2q4lQIesQosSguH7Eg)

## General Notes
- Idea to have UBIK be deployed also on remote sensing. We have some contacts in the NL.  

END DOCUMENT

gijsToSelf: [UBIK mindmap](https://docs.google.com/presentation/d/1Y7P4BjCyIc-nP6L6s6xpaE0Q1GnRoe0pWDN10GTVoII/edit?slide=id.g3f79a33b93d_0_0#slide=id.g3f79a33b93d_0_0)
