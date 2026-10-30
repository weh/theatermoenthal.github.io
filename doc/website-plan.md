# Theatergruppe Mönthal Website Plan

**Status:** Initial planning
**Last updated:** Initial planning session

## 1. Project overview

The website is for **Theatergruppe Mönthal**, a theater group that is part of **STV Mönthal**. STV Mönthal is based in Mönthal, Aargau, Switzerland.

The website will be a statically generated site built with **Hugo**, the Go-based static site generator, and hosted on **GitHub Pages** at a GitHub-hosted domain.

## 2. Website goals

- Present Theatergruppe Mönthal and its connection to STV Mönthal.
- Promote the current theater production.
- Provide performance dates and practical visitor information.
- Allow visitors to reserve seats by telephone.
- Maintain an archive of previous productions.
- Present recurring players and other members through reusable profiles.
- Provide a photo gallery for current and previous productions.
- Keep hosting and running costs at zero where practical.

## 3. Language and audience

- The website's primary and initially only language is **German**.
- Additional languages are not currently planned because the plays are performed in German.
- The main audience is local visitors from Mönthal, Aargau, and surrounding communities.

## 4. Proposed navigation

- Startseite
- Aktuelles Stück
- Aufführungen & Reservation
- Produktionen
- Mitglieder
- Galerie
- Über uns
- Kontakt

## 5. Page requirements

### Startseite

The homepage should prominently show:

- Theatergruppe Mönthal name and branding
- Current production
- Next performance date
- Reservation telephone number
- Link to the reservation page
- Short introduction to the group
- Recent gallery images
- Link to the STV Mönthal website

### Aktuelles Stück

The current production page should contain:

- Production title and poster
- Short description and longer synopsis
- Author
- Director
- Cast
- Crew
- Performance dates
- Venue
- Link to seat reservations

### Aufführungen & Reservation

This page should contain:

- Complete performance schedule
- Venue and address
- Admission prices in CHF
- Reservation telephone number
- Reservation opening times, if applicable
- Instructions for reserving seats
- Parking and arrival information

There will be no online ticket purchase. Visitors reserve seats by phone. The page should provide a mobile-friendly telephone link using a `tel:` URL where appropriate.

Suggested call to action:

> Plätze reservieren  
> Reservieren Sie Ihre Plätze telefonisch unter **[Telefonnummer]**.

### Produktionen

This section will be an archive organized by production and year. Each production may include:

- Year
- Title
- Poster
- Description
- Performance dates
- Cast and crew
- Photo gallery
- Optional program or press material

### Mitglieder

Member profiles should be reusable across productions. A profile may include:

- Name
- Portrait
- Short biography
- Theater roles or responsibilities
- Productions in which the person participated

### Galerie

The gallery should support photos from:

- The current production
- Previous productions
- Behind-the-scenes activities
- Theater group events

Images may include captions and photographer credits.

### Über uns

This page should explain:

- The history of Theatergruppe Mönthal
- The relationship with STV Mönthal
- The group's activities and values
- Rehearsals and theater activities
- Community involvement
- How interested people can participate

### Kontakt

This page should provide:

- General email address
- Reservation contact
- Contact persons
- Postal/location information
- Social media links, if available
- Link to STV Mönthal

## 6. Photo gallery and media hosting decision

The current preference is to host the gallery directly in the Hugo/GitHub repository instead of using a paid external photo hosting service.

Recommended approach:

- Keep original camera photos outside the public website as an archive.
- Add optimized web images to the Hugo repository.
- Use Hugo image processing to generate thumbnails and responsive image sizes.
- Prefer WebP or AVIF where practical, with a suitable fallback format.
- Use thumbnails in gallery views and open larger versions when selected.
- Do not use Git LFS initially; regular optimized image files are simpler for GitHub Pages.

Suggested media structure:

```text
assets/
└── images/
    └── produktionen/
        └── 2025-stueck/
            ├── bild-01.jpg
            ├── bild-02.jpg
            └── bild-03.jpg
```

Suggested image targets:

- Gallery thumbnail: approximately 600 px wide
- Full-size image: approximately 1600–2000 px wide
- JPEG quality: approximately 75–85%, depending on the image

If the archive becomes very large, a separate media repository or another storage solution can be considered later. The website structure should remain independent of the storage implementation.

Photo permissions must be checked before publishing images, especially images of children, audience members, and photographs made by external photographers.

## 7. Initial Hugo content structure

```text
content/
├── _index.md
├── aktuelles-stueck/
│   └── _index.md
├── auffuehrungen/
│   └── _index.md
├── produktionen/
│   ├── _index.md
│   └── 2025-stueck/
│       └── index.md
├── mitglieder/
│   ├── _index.md
│   └── member-name/
│       └── index.md
├── galerie/
│   └── _index.md
├── ueber-uns/
│   └── _index.md
└── kontakt/
    └── _index.md
```

The current production may initially be maintained as a dedicated page. Later, it could be selected dynamically from the production archive using Hugo front matter.

## 8. Technical direction

- Static site generator: Hugo
- Hosting: GitHub Pages
- Source control: GitHub repository
- Primary site language: German
- Ticketing: Telephone reservations only
- Gallery: Optimized assets integrated into the repository initially
- Responsive design: Required, especially for mobile visitors reserving seats by phone
- Accessibility: Should be considered from the beginning, including readable contrast, alt text, keyboard navigation, and clear contact/reservation information

## 9. Open questions

The following information still needs to be collected:

- GitHub repository and final domain name
- Current production title and description
- Performance dates and venue
- Reservation telephone number and reservation hours
- Admission prices
- Contact email and contact persons
- STV Mönthal website URL
- Existing logo, colors, and visual identity
- Social media URLs
- Group history and founding year
- Member list and biographies
- Available photographs and usage permissions
- Preferred venue and arrival/parking information
- Whether a newsletter or social media news feed is needed
