# Project Walkthrough - NATRC Region 1 Mobile

This project is a mobile-friendly refactor of the NATRC (North American Trail Ride Conference) Region 1 website.

## Architecture

- **Static Site**: The project consists of static HTML files.
- **Mobile-First CSS**: Styles are separated into a common `styles.css` and page-specific CSS files in the `css/` directory.
- **responsive**: Navigation and layout are designed to be responsive, with breakpoints at 480px and 768px.

## File Structure

- `/index.html`: Home page (likely renamed from `natrc-region1-mobile.html`).
- `/ride-schedule.html`: Upcoming rides and events.
- `/stories-articles.html`: Member stories and educational articles.
- `/judges-corner.html`: Information for and by NATRC judges.
- `/gallery.html`: Photo gallery (currently mostly placeholders).
- `/links.html`: Helpful external links.
- `/contact.html`: Contact information and forms.
- `/css/*.css`: Page-specific styles.
- `/styles.css`: Base/common styles used across all pages.
- `/images/`: Site assets and photos.

## Recent Work

A major refactoring (Issue #3) was recently completed to:

1. Extract inline styles to external CSS files.
2. Implement a mobile-first responsive design.
3. Organize the file structure for better maintainability.

## Development

To preview the site locally, you can use any static file server:

```bash
npx -y http-server -p 8080
```

Then visit `http://127.0.0.1:8080`.
