# Deployment Instructions

## Overview
This guide explains how to deploy the refactored CSS changes to your repository.

## Prerequisites
- Git installed and configured
- Access to the repository (push permissions)
- Branch `wstidolph/issue3` checked out locally

## Step-by-Step Deployment

### 1. Create the CSS Directory
```bash
# In your repository root
mkdir -p css
```

### 2. Add the CSS Files
Copy all files from the `css/` folder in the deliverable to your repository's `css/` directory:
- contact.css
- gallery.css
- home.css
- judges-corner.css
- links.css
- ride-schedule.css
- stories-articles.css

### 3. Replace the HTML Files
Replace the following HTML files with the refactored versions:
- natrc-region1-mobile.html
- contact.html
- gallery.html
- judges-corner.html
- links.html
- ride-schedule.html
- stories-articles.html

**Note:** The `styles.css` file remains unchanged, but is included for completeness.

### 4. Add Files to Git
```bash
# Add the new CSS directory
git add css/

# Add all modified HTML files
git add *.html

# Optional: Add documentation
git add REFACTORING_README.md
```

### 5. Commit the Changes
```bash
git commit -m "Extract per-page styles into mobile-friendly CSS files

- Created dedicated CSS files for each page in css/ directory
- Removed inline <style> blocks from all HTML files
- Implemented mobile-first responsive design approach
- Improved code organization and maintainability

Closes #3"
```

### 6. Push to the Branch
```bash
git push origin wstidolph/issue3
```

### 7. Create the Pull Request
1. Go to: https://github.com/wstidolph/NATRCR1-MOBILE/pull/new/wstidolph/issue3
2. Use the content from `PR_DESCRIPTION.md` as your PR description
3. Assign reviewers if needed
4. Submit the PR

## Verification Steps

After deployment, verify the following:

### Local Testing
1. Open each HTML file in a browser
2. Check that styles are loading correctly
3. Test responsive behavior at different viewport sizes:
   - Mobile: 375px width
   - Tablet: 768px width
   - Desktop: 1200px+ width

### Browser DevTools Check
1. Open DevTools (F12)
2. Check the Network tab
3. Verify all CSS files load successfully (200 status)
4. Check for any 404 errors

### Responsive Testing
1. Use browser DevTools responsive mode
2. Test at breakpoints: 320px, 480px, 768px, 1024px, 1440px
3. Verify layouts adapt properly
4. Check that all interactive elements are accessible

## File Structure After Deployment

```
NATRCR1-MOBILE/
├── css/                          # NEW directory
│   ├── contact.css
│   ├── gallery.css
│   ├── home.css
│   ├── judges-corner.css
│   ├── links.css
│   ├── ride-schedule.css
│   └── stories-articles.css
├── styles.css                    # Existing file (unchanged)
├── natrc-region1-mobile.html     # Modified
├── contact.html                  # Modified
├── gallery.html                  # Modified
├── judges-corner.html            # Modified
├── links.html                    # Modified
├── ride-schedule.html            # Modified
├── stories-articles.html         # Modified
└── REFACTORING_README.md         # Optional: Documentation
```

## Rollback Plan

If issues are discovered after deployment:

### Option 1: Revert the Commit
```bash
git revert HEAD
git push origin wstidolph/issue3
```

### Option 2: Reset to Previous State
```bash
git reset --hard HEAD~1
git push --force origin wstidolph/issue3
```

## Common Issues and Solutions

### CSS Files Not Loading
**Problem:** 404 errors for CSS files  
**Solution:** Verify the `css/` directory is in the correct location relative to HTML files

### Styles Look Broken
**Problem:** Some styles not applying correctly  
**Solution:** Clear browser cache and hard refresh (Ctrl+Shift+R or Cmd+Shift+R)

### Mobile Layout Issues
**Problem:** Layout doesn't adapt on mobile  
**Solution:** Check viewport meta tag is present: `<meta name="viewport" content="width=device-width, initial-scale=1.0">`

### Path Issues on Server
**Problem:** CSS paths work locally but not on server  
**Solution:** Verify case sensitivity of filenames (Linux servers are case-sensitive)

## Production Deployment

If deploying to production:

1. **Test thoroughly** on the branch first
2. **Get PR approval** before merging
3. **Merge to main/master** only after testing
4. **Deploy to production** following your normal deployment process
5. **Monitor** for any issues after deployment
6. **Cache busting**: Consider adding version query strings if needed
   ```html
   <link rel="stylesheet" href="css/home.css?v=1.0">
   ```

## Performance Considerations

### Browser Caching
- CSS files will be cached by browsers
- Users will get faster page loads on subsequent visits
- Update cache-control headers if needed on your server

### File Size Impact
- HTML files are now smaller (removed inline styles)
- CSS files are cached separately
- Overall page weight may be slightly higher on first load but better for repeat visits

## Need Help?

If you encounter any issues:
1. Check the `REFACTORING_README.md` for detailed information
2. Review the `PR_DESCRIPTION.md` for testing steps
3. Verify file paths are correct
4. Check browser console for errors
5. Test in an incognito/private window to avoid cache issues

## Success Criteria

Deployment is successful when:
- ✅ All HTML pages render correctly
- ✅ All CSS files load without 404 errors
- ✅ Responsive behavior works at all breakpoints
- ✅ No console errors in browser DevTools
- ✅ Visual appearance matches original design
- ✅ All interactive elements function properly
