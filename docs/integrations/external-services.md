# External Integrations

## Overview

Kaayup relies on Optical Character Recognition (OCR) and external music services to identify artists from festival lineup images and provide music discovery information.

External integrations must support the core discovery experience while respecting provider limitations, licensing requirements, and the project's operational budget.

Specific technologies and providers remain subject to technical evaluation.

## Integration Categories

| Integration | Responsibility | Selection Status |
|---|---|---|
| OCR service or library | Extract text from festival lineup images | Pending |
| Music metadata providers | Identify artists and retrieve available information | Pending |
| Music platform links | Allow users to explore artists and songs externally | Provider-dependent |
| Audio preview sources | Provide permitted song previews when available | Optional |

## OCR Integration

### Responsibility

The OCR integration extracts potential artist names from uploaded festival lineup images.

### Input

- Image selected from the device's photo gallery.

### Expected Output

- Text extracted from the image.
- Potential artist names for subsequent identification.

### Limitations

Recognition accuracy may be affected by:

- Image resolution and quality.
- Typography and decorative text.
- Artist name size and placement.
- Complex layouts and visual elements.
- Text unrelated to artist names.

Extracted text must not automatically be considered a verified artist identity.

### Error Handling

When recognition fails or produces insufficient results, the application must inform the user and allow manual artist entry or selection of another image.

### Pending Decisions

- OCR technology or provider.
- Local versus server-side processing.
- Supported image formats and file size limits.
- Recognition evaluation methodology and acceptable quality thresholds.

## Music Metadata Integrations

### Responsibility

Music metadata providers are responsible for supplying available information used to identify artists and support music discovery.

### Required Information

The application will attempt to retrieve:

- Artist identity and name.
- Musical genre.
- Country of origin.
- Additional artist information when available.
- Representative songs, up to three per artist.
- Available external music platform links.

The availability of individual fields depends on provider capabilities.

### Provider Strategy

Kaayup will use a primary provider with secondary providers acting as fallbacks.

The expected strategy is:

1. Query the primary provider for artist identification or music information.
2. Evaluate whether the returned information is sufficient for the requested operation.
3. Consult an available secondary provider when required information cannot be obtained from the primary provider.
4. Use reliable available information without fabricating missing fields.
5. Clearly indicate unresolved artists or unavailable information.

Provider fallback must not automatically resolve ambiguous identities without the user's confirmation.

The exact fallback conditions and provider order will be defined during technical integration design.

### Artist Matching

External catalog results may include multiple artists with identical or similar names.

The application must distinguish:

- Identified artists.
- Ambiguous matches requiring user selection.
- Artists without a reliable match.

Uncertain matches must not be presented as verified.

### Representative Songs

The application will attempt to obtain up to three representative songs per artist.

Selection depends on the data and capabilities of the chosen providers.

The system must not assume that all providers supply popularity rankings or that the available rankings predict festival performances.

### Error Handling

The integration must account for:

- No matching artist.
- Ambiguous matches.
- Missing or incomplete metadata.
- Provider authentication failures.
- Rate limits.
- Timeouts and temporary service unavailability.
- Inconsistent results between providers.

Failures affecting one artist should not unnecessarily prevent the display of valid results for other artists.

## External Music Platform Links

### Responsibility

Allow users to continue exploring artists and songs on supported music platforms.

### Expected Behavior

- Display available external links associated with artists or songs.
- Open the selected link using the device's supported navigation behavior.
- Avoid displaying unavailable or invalid links as usable destinations.

Kaayup must not depend exclusively on Spotify.

Supported destinations will depend on the selected providers and their available data.

## Audio Preview Integration

### Responsibility

Enable playback of short song previews only when a selected provider explicitly supports and permits such usage.

### Constraints

- Preview availability is not guaranteed.
- Playback must comply with provider licensing and usage policies.
- Preview URLs must not be assumed to be available for every song.
- Audio previews are optional and are not required for MVP completion.

When a preview is unavailable, the application should retain any available external music platform links.

## Security and Compliance

External integrations must:

- Protect API credentials and authentication tokens.
- Use secure network communication.
- Validate external data before use.
- Respect provider authentication and rate limits.
- Comply with copyright, licensing, attribution, and data usage restrictions.
- Avoid retaining uploaded images and provider data beyond what is necessary or permitted.

Specific retention and caching policies remain subject to technical and legal evaluation.

## Cost and Operational Considerations

The anticipated monthly infrastructure and external service budget for the MVP is MXN 0–250.

Provider selection must consider:

- Free-tier availability and restrictions.
- Request quotas and rate limits.
- Pricing under expected usage.
- Authentication and maintenance complexity.
- Commercial application eligibility.
- Data coverage and reliability.
- Licensing and attribution requirements.

Free access does not automatically imply permission for production or commercial use.

## Provider Evaluation

Before selecting an integration, candidate providers should be evaluated against the following criteria:

| Criterion | Evaluation |
|---|---|
| Functional coverage | Does the provider supply the information required by the MVP? |
| Data quality | Can artist identities and associated songs be identified reliably? |
| Licensing | Are the intended uses permitted? |
| Pricing | Can expected usage remain within the project budget? |
| Rate limits | Can the provider support the expected request volume? |
| Reliability | How does the provider handle failures and unavailable data? |
| Integration complexity | Is implementation and maintenance manageable? |
| Fallback suitability | Can the provider complement other selected services? |

## Pending Decisions

- OCR solution selection.
- Primary music metadata provider.
- Secondary music metadata providers and fallback order.
- Minimum information required to consider a provider response sufficient.
- Artist matching and ambiguity resolution rules.
- Representative song selection methodology.
- Available music platform destinations.
- Audio preview feasibility and licensing.
- Provider caching and data retention policies.
- Expected API request volume and operational cost estimates.

## Documentation Maintenance

Provider-specific details should be added after an integration has been selected and its current API documentation and usage terms have been verified.

Relevant architectural decisions should be recorded in Architecture Decision Records (ADRs) when they have a significant impact on the system.

Changes in provider capabilities, pricing, or licensing must be reflected in this document and in any affected requirements.