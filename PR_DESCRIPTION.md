# Pull Request: Extract Per-Page Styles into Mobile-Friendly CSS Files

## Issue
Closes #3

## Description
This PR refactors all page-specific inline styles from HTML files into separate, mobile-friendly CSS stylesheets. This improves code organization, maintainability, and follows responsive web design best practices.

## Changes Made

### New Files Created
- `css/home.css` - Home page styles (natrc-region1-mobile.html)
- `css/contact.css` - Contact page styles
- `css/gallery.css` - Gallery page styles
- `css/judges-corner.css` - Judge's Corner page styles
- `css/links.css` - Links & Resources page styles
- `css/ride-schedule.css` - Ride Schedule page styles
- `css/stories-articles.css` - Stories & Articles page styles

### Files Modified
- All 7 HTML files updated to remove inline `<style>` blocks
- All HTML files now reference their respective page-specific CSS files
- Common `styles.css` remains unchanged

## Key Features

### Mobile-First Design
✅ All CSS files follow mobile-first responsive approach
✅ Base styles optimized for mobile devices (320px+)
✅ Progressive enhancement for tablets (@768px) and desktop
✅ Flexible grid layouts using CSS Grid with `auto-fit`/`auto-fill`

### Code Organization
✅ Clear separation of concerns (structure vs. presentation)
✅ Page-specific styles isolated in dedicated files
✅ Consistent naming conventions across all files
✅ Well-organized file structure with dedicated `css/` directory

### Performance Benefits
✅ Smaller HTML file sizes
✅ Better browser caching of CSS resources
✅ Parallel loading of stylesheets
✅ Reduced code duplication

### Responsive Features
✅ Responsive grids with automatic column adjustment
✅ Flexible images (max-width: 100%, height: auto)
✅ Touch-friendly interactive elements
✅ Optimized breakpoints: Mobile (<480px), Tablet (768px), Desktop (>768px)

## Testing

### Tested On
- ✅ Mobile viewports: 375x667, 414x896
- ✅ Tablet viewports: 768x1024
- ✅ Desktop viewports: 1200x800, 1920x1080
- ✅ All pages maintain visual consistency
- ✅ No broken layouts or styling issues

### Browser Compatibility
Compatible with:
- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## File Structure
```
NATRCR1-MOBILE/
├── css/                          # NEW: Page-specific stylesheets
│   ├── contact.css
│   ├── gallery.css
│   ├── home.css
│   ├── judges-corner.css
│   ├── links.css
│   ├── ride-schedule.css
│   └── stories-articles.css
├── styles.css                    # Unchanged: Common styles
├── natrc-region1-mobile.html     # Modified: Inline styles removed
├── contact.html                  # Modified: Inline styles removed
├── gallery.html                  # Modified: Inline styles removed
├── judges-corner.html            # Modified: Inline styles removed
├── links.html                    # Modified: Inline styles removed
├── ride-schedule.html            # Modified: Inline styles removed
└── stories-articles.html         # Modified: Inline styles removed
```

## Before/After Comparison

### Before
```html
<head>
    <link rel="stylesheet" href="styles.css">
    <style>
        /* 200+ lines of page-specific CSS */
    </style>
</head>
```

### After
```html
<head>
    <link rel="stylesheet" href="styles.css">
    <link rel="stylesheet" href="css/page-name.css">
</head>
```

## Documentation
- Included `REFACTORING_README.md` with complete documentation
- Detailed explanation of responsive design approach
- Browser compatibility information
- Testing recommendations
- Future enhancement suggestions

## Benefits

### For Developers
- ✅ Easier to maintain and update styles
- ✅ Better code organization and readability
- ✅ Clear separation of concerns
- ✅ Reduced merge conflicts
- ✅ Easier to add new pages

### For Users
- ✅ Improved page load performance
- ✅ Better mobile experience
- ✅ Consistent responsive behavior
- ✅ Faster subsequent page loads (cached CSS)

### For the Project
- ✅ Follows modern web development best practices
- ✅ Scalable architecture for future growth
- ✅ Better maintainability
- ✅ Professional code organization

## Breaking Changes
None - This is a refactoring that maintains existing functionality and appearance.

## Migration Notes
To use these changes:
1. Ensure the `css/` directory is deployed alongside HTML files
2. All relative paths remain the same (e.g., `href="styles.css"`)
3. No changes needed to existing functionality or JavaScript

## Checklist
- [x] All inline styles extracted to external CSS files
- [x] Mobile-first responsive design implemented
- [x] All pages tested at multiple viewport sizes
- [x] File structure properly organized
- [x] Documentation provided
- [x] No breaking changes to existing functionality
- [x] Code follows project conventions
- [x] Browser compatibility verified

## Screenshots
(Add screenshots showing before/after or responsive behavior if desired)

## Additional Notes
- All existing brand colors and design language preserved
- CSS uses rem units for better accessibility
- Consistent spacing scale maintained (0.5rem, 1rem, 1.5rem, 2rem)
- Smooth transitions for interactive elements

## Reviewer Notes
Please verify:
1. All pages render correctly on mobile devices
2. CSS files are properly linked in HTML files
3. Responsive behavior works as expected across breakpoints
4. No visual regressions from the original design
