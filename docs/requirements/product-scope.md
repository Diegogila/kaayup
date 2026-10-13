# Product Scope

## Product Overview

Kaayup is a mobile application for smartphones and tablets designed to simplify music discovery from festival lineup images.

The application allows users to upload a festival poster, identify the featured artists, and explore their music through representative songs and links to external music platforms.

Its primary focus is reducing the effort required to discover unfamiliar artists. As a secondary benefit, it helps users identify artists they may be interested in seeing at a festival.

## Product Goals

- Simplify music discovery from festival lineup images.
- Reduce repetitive manual searches for individual artists.
- Help users discover unfamiliar artists and their music.
- Provide access to representative songs and external music platforms.
- Deliver a simple and accessible experience on smartphones and tablets.

## Planned Core Capabilities

The following capabilities define the intended core experience. Their inclusion in the initial release will be finalized during MVP planning.

### Lineup Image Upload

Users can select and upload an image containing a festival lineup for processing.

### Artist Name Recognition

The system processes the uploaded image using Optical Character Recognition (OCR) to extract potential artist names.

### Artist Identification and Validation

The system attempts to identify recognized artists using external music catalogs.

Users can review and correct incorrectly recognized or ambiguous artist names.

### Music Discovery

The application presents identified artists and retrieves relevant music information when available.

Up to three representative songs may be displayed for each artist, depending on the data provided by external services.

### External Music Platform Access

Users can access available links to music platforms to explore artists and songs.

Music preview playback may be supported when permitted by the provider's technical capabilities, licensing terms, and usage policies.

## Product Boundaries

Kaayup focuses on discovering music associated with artists featured in festival lineup images.

The application is not intended to:

- Replace existing music streaming platforms.
- Provide a complete music streaming service.
- Organize festival schedules or stage timetables.
- Provide navigation within festival venues.
- Manage festival ticket purchases or reservations.

## Potential Future Capabilities

The following capabilities are possible future enhancements and are not automatically part of the MVP:

- Favorite artists.
- Saved festivals.
- Playlist creation.
- Personalized music recommendations.
- Additional music platform integrations.

Their implementation will depend on future product priorities, user needs, technical feasibility, and available resources.

## External Dependencies and Limitations

Kaayup depends on image processing and external music information services.

The following limitations must be considered:

- OCR accuracy may vary depending on image quality, typography, and poster layout.
- Artist names may be ambiguous or incorrectly recognized.
- External music catalogs may contain incomplete or inconsistent information.
- Representative song availability depends on the information provided by music services.
- Music previews may be unavailable or restricted.
- External APIs may impose authentication, rate limits, licensing restrictions, or usage costs.
- The application must comply with applicable data protection requirements and provider policies.

The product should handle these limitations without assuming that every artist can be successfully identified or that music information will always be available.

## MVP Scope Status

The definitive MVP scope has not yet been approved.

The planned core capabilities describe the intended product experience, but their delivery priority and acceptance criteria will be determined during product planning.

Future capabilities listed in this document must not be treated as MVP commitments unless explicitly approved.

## Success Criteria

The product should enable users to:

- Upload a festival lineup image.
- Review artists identified from the image.
- Correct recognition errors or ambiguous artist names.
- Discover available representative songs.
- Access external music platforms.

Quantitative success metrics and performance thresholds will be defined separately after the corresponding product requirements are established.