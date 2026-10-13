# MVP Definition

## Overview

The Kaayup Minimum Viable Product (MVP) is the first functional version of the application, designed to validate its core value: simplifying music discovery from festival lineup images.

The MVP will allow users to select an existing image from their device, identify featured artists, review recognition results, and explore artist information and representative songs through external music services.

The initial release will support Android and iOS without requiring user registration.

## MVP Objectives

- Enable music discovery directly from festival lineup images.
- Reduce the effort required to search for unfamiliar artists individually.
- Provide reliable artist identification with manual correction options.
- Present relevant artist information and up to three representative songs.
- Allow users to continue exploring artists on external music platforms.
- Deliver a functional and usable experience on Android and iOS.

## Target Platforms

| Platform | MVP Support |
|---|---|
| Android smartphones | Included |
| iOS smartphones | Included |
| Android tablets | Included |
| iPad | Included |

The interface should adapt to supported screen sizes.

## Included Features

### Image Selection

- Users can select existing images from their device's photo gallery.
- Screenshots of festival lineups are supported.
- The selected image is submitted for artist recognition.

Direct camera capture and image selection from other file sources are not included in the MVP.

### Artist Recognition

- The system uses Optical Character Recognition (OCR) to extract potential artist names.
- Recognized names are checked against external music catalogs.
- The application presents potential artist matches for user review.
- Uncertain or incorrect results must not be silently treated as confirmed matches.

### Artist Review and Correction

Before exploring music information, users can:

- Review recognized artists.
- Correct incorrectly recognized names.
- Remove unwanted or incorrectly identified artists.
- Manually add artists missing from the recognition results.
- Select the correct artist from available candidate matches when identification is ambiguous.

Uncertain artist matches must not be silently confirmed.

### Artist Information

For identified artists, the application displays available information, including:

- Artist name.
- Musical genre.
- Country of origin.
- Additional relevant artist information when provided by the selected music services.

Unavailable information must not be fabricated.

### Representative Songs

- The application displays up to three representative songs per artist.
- Fewer than three songs may be displayed when insufficient reliable information is available.
- Song selection depends on the capabilities and information provided by external music services.
- Songs must not be invented or associated with unreliable artist matches.
- Audio previews are available only when technically supported and permitted by the provider.

The MVP does not guarantee that every artist will have three available songs or playable previews.

### External Music Platform Links

- Users can open available artist or song links in supported external music platforms.
- The application must not depend exclusively on Spotify.
- Link availability depends on the external services and their data.

### Error Handling and Recovery

The MVP must support recovery from common recognition and integration failures.

**Unrecognizable image:**
- Inform the user that artists could not be reliably identified.
- Allow another image to be selected.
- Allow artists to be entered manually.

**Incorrect or ambiguous recognition:**
- Present results for review.
- Allow manual correction, removal, or addition.
- Avoid automatically confirming uncertain matches.

**Missing artist information:**
- Keep the artist in the results.
- Inform the user that information is unavailable.
- Allow the artist name to be corrected.
- Let the user continue exploring other artists.

**External service failure:**
- Explain the failure without presenting fabricated results.
- Offer a retry when appropriate.
- Preserve available session data and previously retrieved results during recoverable failures.

## Core User Flow

1. The user selects an existing festival lineup image.
2. The system extracts potential artist names using OCR.
3. The user reviews the recognized artists and corrects, removes, or adds names as needed.
4. The system identifies artists and retrieves available music information.
5. The user explores artist details and up to three representative songs.
6. The user can open available links to external music platforms.

No registration or account creation is required to complete this flow.

## Excluded Features

The following features are outside the initial MVP:

- Saving favorite artists, including local favorites.
- Saving festival lineups or maintaining a festival history.
- Creating or exporting playlists.
- Personalized music recommendations.
- User accounts and authentication.
- Synchronization across devices.
- Direct camera capture within the application.
- Festival schedules and stage planning.
- Festival ticket purchases.
- Full music streaming functionality.

These exclusions do not prevent the features from being considered in future releases.

## Dependencies and Constraints

- An active Internet connection is required to use the core discovery functionality. Offline operation is not supported.
- OCR results depend on image quality, typography, and poster layout.
- Music information depends on the availability and accuracy of external providers.
- Ambiguous artist matches must support manual selection when candidate matches are available.
- External API usage must respect provider policies, licensing, authentication requirements, and rate limits.
- Audio playback depends on provider permissions and technical availability.
- The application must protect user data and avoid unnecessary storage of uploaded images.
- Infrastructure and external service costs must remain manageable.
- Recognition and matching quality take priority over processing speed.

## MVP Completion Criteria

The MVP can be considered functionally complete when:

- Users can select lineup images, including screenshots, on Android and iOS.
- The system can extract potential artist names from supported images.
- Users can review, correct, remove, and manually add artists.
- The application can identify artists using external music information.
- Available artist genre, country, and relevant information can be displayed.
- Up to three representative songs can be displayed per artist when reliable data is available.
- Users can open available external music platform links.
- Missing information, recognition failures, and external service errors are handled without blocking unrelated results.
- Users can recover from supported failures without unnecessarily losing their current results.
- The core discovery flow works without registration.
- The application is tested on Android and iOS.
- Artist recognition and matching results are validated using real festival lineups and manually verified reference results before release.

## Open Decisions

The following details require further definition before their corresponding requirements and acceptance criteria can be finalized:

- Rules for resolving ambiguous artist matches.
- Music provider selection and representative song selection criteria.
- Availability and licensing conditions for audio previews.
- Detailed performance and reliability thresholds.
- Supported image formats, file sizes, and processing limits.