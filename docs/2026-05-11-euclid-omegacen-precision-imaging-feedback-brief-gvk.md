# Euclid/OmegaCEN Precision Imaging Inference Current Proposal State

## Purpose
This brief records the current proposal-facing state of the Euclid/OmegaCEN line as of `2026-05-12`.
It is derived from proposal text only and keeps the current work-package, deliverable, and milestone wording as intact as possible while converting LaTeX syntax to Markdown.

## Feedback Requested
Please use this brief to check whether the current proposal text represents your project line accurately and usefully.

This is an informal proposal-framing check, not a final commitment of role, effort, beneficiary status, data access, or deliverable ownership.

You can either answer the questions below or add comments directly in the text using `Comment: ...`.

1. What in this description feels accurate and important to keep?
2. What feels wrong, misleading, overstated, understated, or awkwardly framed?
3. What scientific, instrumental, data, validation, or domain context is missing?
4. Are the proposed role, deliverables, milestones, and scope boundaries appropriate from your perspective?
5. What should we change, add, remove, or rephrase?

## Proposal Context
UBIK is framed as a shared inferential core developed together with application lines, not as a set of disconnected demonstrations. WP1 defines shared contracts, trust, and reference-workflow logic; WP2 develops two separate reusable framework-adapter routes, ScopeSim-JAX for observatory simulation and Pyxel-JAX for detector modeling; WP3 integrates concrete instruments and data chains; WP4 validates scientific and operational applications; WP5 makes workflows runnable and inspectable; WP6 supports coordination, onboarding, uptake, and transfer.

WP map: WP1 core; WP2 framework adapters; WP3 instrument integration; WP4 scientific and operational applications; WP5 compute; WP6 coordination/transfer.

Some WP, task, deliverable, and milestone text is cross-application by design, so this brief may include other application lines where they share the same framework adapter, instrument-integration package, validation package, execution criterion, or milestone gate.

## Short Legend
- `WP`: work package.
- `T`: task inside a work package.
- `D`: deliverable, the formal output reported to the funder.
- `M`: project month counted from month 1; for example, `M12` means month 12.
- `MS`: milestone, a project checkpoint or integration gate.

This brief concerns the Euclid/OmegaCEN precision imaging inference line. It starts in WP3 as survey-production and imaging data-chain integration and develops into WP4 color-homogeneity validation.

## Current Proposal Role
The proposal says that the current application lines are the first co-development lines for the UBIK core, not downstream demonstrations of a finished platform. Each line should be read through the same methodological card: what scientific state is inferred, which measurements constrain it, why the application matters in its own right, which application requirements it brings to UBIK, which posterior products and validation route make the result trustworthy, and which reusable reference-workflow lesson returns to the shared core.

### Euclid/OmegaCEN precision imaging inference
- This line concerns survey-production quality in which Euclid VIS/NIR and ground-based optical/NIR imaging provide complementary constraints on a shared sky or source scene.
- Its standalone value is more diagnosable precision imaging: improved or comparable color homogeneity, astrometry, photometry, or failure diagnosis with uncertainty products and provenance rather than only final image products.
- Its first demonstrator focuses on color homogeneity in one public or accessible Euclid-related field, while treating AstroWISE, GOOD, Euclid SGS, Euclid Science Data Center uptake, and proprietary survey data as maturation routes rather than starting promises.
- Its methodological pressure is spatially varying PSFs and passbands, weights, flags, masks, astrometric and photometric calibration terms, metadata handoffs, data-rights labels, recognized baseline products, and quality-failure diagnostics at the few-mmag and milliarcsecond frontier.
- Its reusable UBIK output is a reference pattern for turning survey-production handoffs into explicit model components and diagnostics that can distinguish sky structure from PSF, passband, calibration, registration, masking, or provenance problems.

### Impact framing
- Euclid/OmegaCEN precision imaging inference supports survey-production quality by making color homogeneity, PSF and passband effects, astrometric and photometric calibration, provenance, and quality-failure diagnosis more uncertainty-aware and inspectable.
- Later AstroWISE, GOOD, Euclid SGS, or Science Data Center uptake is treated as a maturation route after validation.

## Work Package Text
### WP3 Instrument Integration
WP3 integrates concrete instruments, sensors, detectors, archives, survey-production handoffs, reconstruction inputs, and observation chains against the WP1 contracts and the WP2 framework adapters where applicable. Its job is to make the measurement side of each application line explicit: which instrument sees which latent state, through which response, metadata, calibration, detector, mask, noise, and likelihood assumptions.

Relevant WP3 objectives:
- Integrate Euclid VIS/NIR plus ground-based optical/NIR imaging, AstroWISE/GOOD/Euclid SGS-style production handoffs, PSF, passband, weights, flags, masks, astrometric and photometric calibration terms, provenance, and data-rights labels for one public or accessible Euclid-related field.
- Provide Euclid/OmegaCEN integration evidence on calibration, provenance, metadata completeness, data access, and operational tractability, in a form that can later enter the wider WP3 readiness comparison.

`T3.1 Initial instrument-integration specifications`
- For Euclid/OmegaCEN, specify Euclid VIS/NIR and ground-based optical/NIR image products, PSF models, passband effective wavelengths, weights, flags, masks, astrometric and photometric calibration terms, metadata, data-rights labels, and recognized baseline products.
- Keep proprietary Euclid-related, AstroWISE/GOOD, Euclid SGS, or other survey-imaging data dependencies labeled as access-conditional rather than assumed public inputs.

`T3.2 Integrated instrument, sensor, detector, and archive workflows`
- Produce the first Euclid/OmegaCEN imaging integration package, starting from a reduced case that can be rerun and inspected before larger validation runs.
- For Euclid/OmegaCEN, build the first shared-scene imaging integration for one accessible field with the color-homogeneity metric as the primary target and astrometry, photometry, or failure diagnosis as secondary or later extensions.

`T3.3 Instrument-integration comparison and lessons`
- Compare Euclid/OmegaCEN integration lessons: which metadata were essential, which PSF, passband, astrometric, or photometric calibration terms had to be fixed or inferred, which data-access limits shaped validation, and which assumptions affected posterior meaning.
- Produce validation packages that distinguish survey-production handoff and instrument-integration limits from later application-validation limits.
- Feed reusable integration lessons to WP1, execution and profiling lessons to WP5, and validated onboarding material to WP6.

### WP4 Scientific and Operational Applications
WP4 turns the adapter and instrument-integration work into validated scientific and operational demonstrators. It owns the application value claims, baseline comparisons, posterior products, quality metrics, scope boundaries, and comparative evidence across the active application lines.

Relevant WP4 objectives:
- Deliver scoped application demonstrators whose value stands on its own while also proving reuse of the shared UBIK stack.
- Validate Euclid/OmegaCEN precision imaging inference as the survey-production quality application track.
- Use Euclid/OmegaCEN as a precision survey-production demonstrator focused first on color homogeneity in one public or accessible Euclid-related field, with uncertainty and quality-failure diagnostics as central outputs.
- Require each application claim to include a baseline, uncertainty or diagnostic evidence, approximation labels, provenance, scope boundary, and rerunnable workflow record.

`T4.1 Application-demonstrator scoping and validation plans`
- Define the first demonstrator scope, baseline, data route, validation metric, reusable UBIK contribution, compute need, risks, and deferred expansions for each active application line.
- For Euclid/OmegaCEN, scope one public or accessible Euclid-related field with color homogeneity as the primary metric, using recognized Euclid/OmegaCEN-relevant baselines where available and keeping proprietary data access conditional.

`T4.2 Validation-grade application workflow packages`
- Bring at least two distinct application lines to validation-grade application packages with domain validation, posterior products, uncertainty summaries, residuals, posterior-predictive checks, approximation labels, runtime records, and validation evidence.
- For Euclid/OmegaCEN, decide whether UBIK improves color homogeneity, matches baseline performance with better uncertainty, or diagnoses failure modes more clearly; do not claim automatic metric improvement before the comparison exists.

`T4.3 Final comparative scientific and operational evidence`
- Assemble cross-line comparison evidence across validated applications, separating application performance from adapter readiness, instrument-integration quality, and compute constraints.
- Keep AstroWISE, GOOD, Euclid SGS, and Euclid Science Data Center uptake as maturation routes unless formal commitments and validation evidence support stronger claims.

## Deliverable Text
- `D3.1`: Instrument-integration readiness matrix. Instrument-integration specification and readiness matrix with line-specific cards for ALMA, Euclid/OmegaCEN, the shared Sentinel-first EO layer with DBFZ and SatRev application tracks, ScopeSim-JAX, Pyxel-JAX, and BCDI. WP3, report, public, month 12.
- `D3.2`: Integrated instrument workflow package. Integrated instrument/sensor/detector workflow package with validation evidence for selected current integrations and readiness labels for deferred or access-conditional routes. WP3, demonstrator, public, month 30.
- `D3.3`: Instrument-integration evidence package. Instrument-integration comparative evidence package, including calibration, provenance, metadata, data-access, approximation-label lessons, and readiness status across current integration lines. WP3, report, public, month 48.
- `D4.1`: Application-demonstrator readiness matrix. Application-demonstrator scope and readiness matrix with line-specific validation routes, baselines, data access, readiness status, and scope boundaries. WP4, report, public, month 18.
- `D4.2`: Validation-grade application workflows. Validation-grade application workflow package from at least two distinct application lines, with baseline comparisons, uncertainty products, diagnostics, and execution records. WP4, demonstrator, public, month 36.
- `D4.3`: Final comparative application evidence. Final scientific and operational comparative evidence package across validated application lines, with partial, deferred, and access-conditional evidence labelled. WP4, report, public, month 54.

## Milestone Text
- `MS2`, `M6`: Workplans and interface draft complete. ScopeSim-JAX and Pyxel-JAX have scoped separate framework-adapter routes; each active instrument or application line has an integration route, application target, validation route, main risks, and interface needs; WP1 has the first UBIK interface draft; WP5 has reviewed basic execution assumptions.
- `MS3`, `M12`: Initial adapter-interface handoff and integration scopes delivered. WP2 delivers the ScopeSim-JAX and Pyxel-JAX architecture, interface, and coverage baseline as the first handoff to WP3; WP3 delivers the first instrument-integration specification and readiness matrix for ALMA, Euclid/OmegaCEN, the shared Sentinel-first EO layer with DBFZ and SatRev application tracks, ScopeSim-JAX, Pyxel-JAX, and BCDI.
- `MS4`, `M18`: Shared validation and execution criteria operational. WP1 and WP5 publish the validation, uncertainty, provenance, approximation-label, and execution-record criteria to be used by application deliverables; at least one reduced demonstrator or reference-workflow candidate has been checked against them.
- `MS6`, `M36`: Validation-grade application packages delivered. At least two scientific or operational application lines, not the ScopeSim-JAX or Pyxel-JAX adapter tracks themselves, reach validation-grade readiness with domain validation, diagnostics, uncertainty products, approximation labels, and execution records.
- `MS7`, `M48`: Cross-line comparison and adapter-readiness evidence assembled. At least two validated application lines have validation packages, while WP2 delivers consolidated ScopeSim-JAX and Pyxel-JAX adapter-readiness evidence summarizing WP3 feedback, stable interfaces, approximations, deferred coverage, execution records, failure modes, and reusable interface or workflow lessons.
- `MS8`, `M60`: Final workflow suite and uptake package complete. Final UBIK specification, ScopeSim-JAX and Pyxel-JAX framework-adapter readiness packages, instrument-integration packages, application workflow packages, validation and execution evidence, documentation, training or onboarding material, and transfer guidance are complete.

## Source Trace
- `proposal/sections/01-excellence.tex`: application-line co-development framing and Euclid/OmegaCEN role text.
- `proposal/sections/02-impact.tex`: survey-production impact and uptake-route framing.
- `proposal/sections/04-work-packages.tex`: WP3 and WP4 objectives, Euclid/OmegaCEN-specific tasks, and outputs.
- `proposal/sections/05-implementation-tables.tex`: `D3.1-D3.3`, `D4.1-D4.3`, and `MS2-MS8`.
