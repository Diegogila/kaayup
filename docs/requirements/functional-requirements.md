# Functional Requirements

## Overview

This document defines the functional requirements for the Kaayup Minimum Viable Product (MVP).

The requirements describe the expected behavior of the application and are grouped by functional capability.

All requirements in this document belong to the MVP unless explicitly marked as conditional.

## Image Selection

**FR-001 — Select lineup image**

The system shall allow users to select an existing image from their device's photo gallery.

**FR-002 — Support screenshots**

The system shall accept screenshots of festival lineups selected from the device's photo gallery, provided they meet the supported image requirements.

**FR-003 — Image selection feedback**

The system shall inform users when a selected image cannot be processed and allow them to select another image.

## Artist Recognition

**FR-004 — Extract artist names**

The system shall process the selected image using Optical Character Recognition (OCR) to extract potential artist names.

**FR-005 — Identify artists**

The system shall attempt to identify extracted artist names using external music catalogs.

**FR-006 — Present recognition results**

The system shall display the artists extracted from the image, including those whose identity has not been confirmed.

**FR-007 — Default artist ordering**

The system shall display automatically recognized artists in alphabetical order by default.

**FR-008 — Unrecognizable images**

When no artist names can be reliably extracted, the system shall inform the user and provide options to select another image or enter artists manually.

## Artist Validation and Correction

**FR-009 — Resolve ambiguous matches**

When multiple candidate artists match a recognized name, the system shall allow the user to select the correct artist from the available candidates.

**FR-010 — Handle unidentified artists**

When no matching artist is found, the system shall retain the name in the results and visually indicate its unresolved status using red highlighting.

**FR-011 — Search for unidentified artists**

The system shall allow users to manually search for an artist when automatic identification fails.

**FR-012 — Correct recognized names**

The system shall allow users to edit incorrectly recognized artist names.

**FR-013 — Remove artists**

The system shall allow users to remove incorrectly recognized or unwanted artists from the results.

**FR-014 — Add artists manually**

The system shall allow users to manually add artists missing from the recognition results.

**FR-015 — Position manually added artists**

The system shall place manually added artists at the end of the artist list, after automatically recognized artists.

**FR-016 — Prevent silent ambiguity resolution**

The system shall not automatically confirm an ambiguous artist identity without an explicit user selection.

## Artist Information

**FR-017 — Display artist information**

The system shall display available information for each identified artist, including:

- Artist name.
- Musical genre.
- Country of origin.
- Additional artist information when provided by external services.

**FR-018 — Handle incomplete artist information**

The system shall display available artist information even when some fields are missing, without inventing unavailable data.

**FR-019 — Handle unavailable artist information**

When no information is available for an artist, the system shall indicate that the information is unavailable and allow the user to continue exploring other artists.

## Music Discovery

**FR-020 — Retrieve representative songs**

The system shall attempt to retrieve representative songs for each identified artist using external music services.

**FR-021 — Limit song results**

The system shall display a maximum of three representative songs per artist.

**FR-022 — Handle fewer available songs**

When fewer than three reliable song results are available, the system shall display only the available songs.

**FR-023 — Display song information**

The system shall display available identifying information for each representative song, including its title and associated artist.

**FR-024 — Open external music platforms**

The system shall allow users to open available external music platform links associated with artists or songs.

**FR-025 — Conditional audio previews**

When an external provider offers legally permitted and technically supported audio previews, the system may allow users to play them.

Audio preview playback is conditional and is not required for MVP completion.

## Error Handling and Recovery

**FR-026 — Handle external service failures**

When an external music service fails, the system shall inform the user without displaying fabricated information.

**FR-027 — Retry recoverable operations**

The system shall provide a retry option for failed operations when retrying is supported and appropriate.

**FR-028 — Preserve available results**

The system shall preserve available artist and music results when a recoverable failure affects only part of the processing flow.

**FR-029 — Continue exploring other artists**

The system shall allow users to continue exploring successfully identified artists when other artists cannot be identified or have unavailable information.

## Access and Connectivity

**FR-030 — Access without registration**

The system shall allow users to complete the core music discovery flow without creating an account or signing in.

**FR-031 — Internet connectivity requirement**

The system shall inform users when an Internet connection is unavailable and prevents the core discovery functionality from operating.

**FR-032 — Supported platforms**

The core discovery functionality shall be available on Android and iOS smartphones and tablets.

## Requirement Verification

Functional requirements shall be verified through automated tests, integration tests, or manual acceptance tests, according to the behavior being evaluated.

Features that depend on external providers shall be tested against available provider capabilities and controlled failure scenarios.

Performance thresholds, technical limits, and quality attributes shall be documented separately in the Non-Functional Requirements.

## Scope Notes

The following capabilities are excluded from these MVP requirements:

- User accounts and authentication.
- Saving favorite artists.
- Saving festivals or lineup history.
- Creating playlists.
- Personalized recommendations.
- Direct camera capture.
- Festival scheduling and navigation.
- Ticket purchasing.
- Full music streaming.

These capabilities may be evaluated for future releases.