# Constraints & Assumptions

## Overview

This document identifies the confirmed constraints and unvalidated assumptions that influence the development of Kaayup's Minimum Viable Product (MVP).

Constraints establish boundaries that must be respected during implementation. Assumptions identify conditions that require validation and may influence future product or technical decisions.

## Product Constraints

**CON-001 — Target platforms**

The MVP must support Android and iOS smartphones and tablets.

**CON-002 — Image input**

Users must select existing lineup images from the device's photo gallery. Direct camera capture and other image input methods are excluded from the MVP.

**CON-003 — Internet connectivity**

Core music discovery functionality requires an active Internet connection. Offline operation is outside the MVP scope.

**CON-004 — User registration**

The core discovery experience must be accessible without requiring users to create an account or sign in.

**CON-005 — MVP scope**

Favorites, saved festivals, playlists, personalized recommendations, and other explicitly excluded features must not be included in the MVP without an approved scope change.

## Technical Constraints

**CON-006 — Established technology stack**

The project will use:

- React Native, Expo, and TypeScript for the frontend.
- Python, Django, and Django REST Framework for the backend.
- PostgreSQL for persistent data when required.
- OCR and image processing technologies for artist name extraction.

Specific OCR libraries, music providers, and infrastructure services have not yet been selected.

**CON-007 — Architecture**

The backend must follow the established modular monolith architecture, organized through Feature-Based Design and pragmatic Clean Architecture principles.

Microservices and full tactical Domain-Driven Design are excluded from the initial architecture.

**CON-008 — External music providers**

Kaayup must not depend exclusively on Spotify.

The application must respect the technical capabilities, authentication requirements, rate limits, licensing terms, and usage policies of the selected providers.

**CON-009 — Music availability**

The application cannot guarantee that every artist will have complete information, three representative songs, or available audio previews.

Audio preview playback must only be offered when supported and permitted by the provider.

**CON-010 — Recognition limitations**

OCR and artist matching cannot be assumed to produce accurate results for every lineup.

The application must allow users to review and correct recognition errors and ambiguous artist matches.

## Operational and Resource Constraints

**CON-011 — Infrastructure budget**

The anticipated monthly operational budget for the MVP is between MXN 0 and MXN 250.

Infrastructure and external services must be evaluated against this budget before adoption.

The budget refers to recurring operational expenses and does not automatically include one-time costs such as developer accounts or publication fees.

**CON-012 — Development resources**

Kaayup is initially developed by one person. Technical decisions should favor maintainability, simplicity, and manageable operational complexity.

**CON-013 — Data protection**

User data and uploaded images must be handled securely, with collection and retention limited to what is necessary for the application's functionality.

**CON-014 — Intellectual property and provider compliance**

The application must respect applicable copyright, licensing, data protection requirements, and third-party service policies.

## Product Assumptions

**ASM-001 — User interest in music discovery**

People considering attending a festival are interested in discovering music from unfamiliar artists before deciding whether to attend.

**Status:** Unvalidated.

**ASM-002 — Reduced search effort**

Exploring multiple artists through a consolidated experience requires less effort than searching for each artist individually.

**Status:** Unvalidated.

**ASM-003 — Image-based interaction**

Selecting a festival lineup image is a convenient and understandable starting point for music discovery.

**Status:** Unvalidated.

**ASM-004 — Representative song usefulness**

Up to three representative songs per artist provide sufficient initial information for users to decide whether they want to explore an artist further.

**Status:** Unvalidated.

**ASM-005 — Manual correction acceptance**

Users are willing to correct recognition errors or resolve ambiguous matches when necessary.

**Status:** Unvalidated.

## Technical and Operational Assumptions

**ASM-006 — OCR feasibility**

An OCR solution can extract a useful proportion of artist names from representative festival posters.

**Status:** Requires technical validation.

**ASM-007 — Music catalog coverage**

At least one suitable external music provider can supply useful artist information and song references for the intended discovery experience.

**Status:** Requires provider evaluation.

**ASM-008 — Budget feasibility**

The core MVP can operate within the anticipated monthly infrastructure budget under an initially limited workload.

**Status:** Requires cost estimation and testing.

**ASM-009 — Platform compatibility**

The selected frontend technologies can support the required core experience on the targeted Android and iOS devices.

**Status:** Requires device testing.

## Assumption Validation

Assumptions should be evaluated through user research, technical prototypes, provider reviews, and controlled testing, as appropriate.

Validation should prioritize assumptions whose failure would significantly affect the product's viability.

| Assumption | Suggested Validation Method |
|---|---|
| ASM-001 | User interviews or usability research |
| ASM-002 | Comparative discovery tasks |
| ASM-003 | Image selection usability testing |
| ASM-004 | User feedback after exploring representative songs |
| ASM-005 | Observation of manual correction tasks |
| ASM-006 | OCR testing with real festival posters |
| ASM-007 | External API capability and coverage evaluation |
| ASM-008 | Infrastructure cost estimates and usage tests |
| ASM-009 | Android and iOS device testing |

## Open Constraints and Decisions

The following details remain unresolved:

- Selection of OCR technology.
- Selection and verification of music data providers.
- Infrastructure and hosting configuration.
- Minimum supported operating system versions.
- Supported image formats and upload size limits.
- Temporary image retention limits.
- Quantitative processing performance thresholds.

These items must be resolved through the corresponding product or technical decision-making process.

## Document Maintenance

Confirmed constraints should be updated only when the underlying decisions change.

Assumptions should be marked as validated, rejected, or revised when supporting evidence becomes available.

Changes affecting product scope, architecture, or external provider usage must be reflected in the corresponding requirements and architecture documentation.