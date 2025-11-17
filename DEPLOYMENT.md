# Deployment Guide for cPanel

## File Structure for cPanel

For cPanel hosting, upload all files from the `public/` directory to your `public_html/` directory on the server.

### Required Files to Upload:

```
public_html/
├── index.html          (Main landing page)
├── team-questions.html (Team questions page)
├── .htaccess          (Apache configuration)
├── logo-horizontal-black.png
├── favicon.svg
└── [all image files]
```

## Steps:

1. **Upload all files from `public/` to `public_html/`**
   - Use cPanel File Manager or FTP client
   - Ensure `.htaccess` is uploaded (it may be hidden)

2. **Verify `.htaccess` is working**
   - The `.htaccess` file sets `DirectoryIndex index.html`
   - This ensures `index.html` is served as the default page

3. **Check file permissions**
   - Files: 644
   - Directories: 755
   - `.htaccess`: 644

4. **Test the site**
   - Visit your domain - it should show `index.html`
   - If you see cPanel default page, check:
     - Files are in `public_html/` (not a subdirectory)
     - `index.html` exists in `public_html/`
     - `.htaccess` is present and readable

## Troubleshooting

**If you see cPanel default page instead of index.html:**
1. Make sure `index.html` is in `public_html/` (root of web directory)
2. Check that `.htaccess` file exists and has `DirectoryIndex index.html`
3. In cPanel, go to "Indexes" and ensure "Default" is set to use `index.html`
4. Clear browser cache and try again

**If images don't load:**
- Check that all image files are uploaded
- Verify file paths in HTML are correct (relative paths should work)
- Check file permissions (644 for files)

## Notes

- The `.htaccess` file handles:
  - Setting `index.html` as the default page
  - Clean URLs (removing .html extension)
  - Caching for static assets
  - Security headers

