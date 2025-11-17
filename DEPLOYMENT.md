# cPanel Deployment Guide

## File Structure

The `public/` directory maps directly to cPanel's `public_html/` directory when deployed.

### Current Structure

```
public/
├── index.html                    # Main landing page (served as root)
├── team-questions.html           # Team questions guide page
├── logo-horizontal-black.png     # Logo image
├── dashboard-*.png              # Dashboard example images
├── page-example.png             # Page design example
└── favicon.svg                  # Site favicon
```

### cPanel Deployment

When uploaded to cPanel, files should be placed in:
- **Web Root:** `/home/username/public_html/` (or your cPanel account's public_html directory)

### File Mapping

| Local Path | cPanel Path | URL Access |
|------------|-------------|------------|
| `public/index.html` | `public_html/index.html` | `https://yourdomain.com/` |
| `public/team-questions.html` | `public_html/team-questions.html` | `https://yourdomain.com/team-questions.html` |
| `public/logo-horizontal-black.png` | `public_html/logo-horizontal-black.png` | `https://yourdomain.com/logo-horizontal-black.png` |
| `public/dashboard-*.png` | `public_html/dashboard-*.png` | `https://yourdomain.com/dashboard-*.png` |

### Important Notes

1. **All paths are relative** - The HTML files use relative paths (e.g., `logo-horizontal-black.png` not `/logo-horizontal-black.png`), which works correctly in cPanel's `public_html/` structure.

2. **index.html is the root** - The `index.html` file will be automatically served when users visit your domain root.

3. **Navigation links** - Both pages link to each other using relative paths:
   - From `index.html`: `<a href="team-questions.html">Team Questions</a>`
   - From `team-questions.html`: `<a href="index.html">Overview</a>`

4. **Images and assets** - All images and assets are in the same directory as the HTML files, using relative paths.

### Upload Instructions

1. Upload all files from the `public/` directory to your cPanel `public_html/` directory
2. Ensure `index.html` is in the root of `public_html/`
3. Maintain the same directory structure (all files in the same folder)
4. Verify file permissions (typically 644 for files, 755 for directories)

### Verification

After deployment, verify:
- ✅ `https://yourdomain.com/` loads `index.html`
- ✅ `https://yourdomain.com/team-questions.html` loads the team questions page
- ✅ All images load correctly
- ✅ Navigation links work between pages
