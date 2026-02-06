# GitHub Upload Guide for v1.1.0

## Files to Upload

You have **6 files** ready:
1. `index.html` - The calculator (v1.1.0)
2. `README.md` - Documentation (updated for v1.1.0)
3. `LICENSE` - MIT License (2026)
4. `CITATION.cff` - Citation helper (v1.1.0)
5. `.gitignore` - Ignore rules
6. `CHANGELOG.md` - Version history (NEW)

---

## Step-by-Step Upload Process

### Step 1: Navigate to Your Repository
1. Go to https://github.com/Boriz4k/phospho-calculator-html
2. You should see your existing files from v1.0.0

### Step 2: Update Files (One by One)

**For each file:**

#### Option A: Via Web Interface (Easiest)
1. Click on the filename (e.g., `index.html`)
2. Click the pencil icon (✏️ Edit)
3. Delete all content
4. Copy-paste new content from downloaded file
5. Scroll down to "Commit changes"
6. Commit message: `Update to v1.1.0` or specific like `Update index.html to v1.1.0`
7. Click "Commit changes"

**Repeat for:**
- `index.html`
- `README.md`
- `CITATION.cff`
- `LICENSE` (should be unchanged, but check date is 2026)
- `.gitignore` (should be unchanged)

**Add new file:**
- Click "Add file" → "Create new file"
- Name: `CHANGELOG.md`
- Paste content
- Commit

#### Option B: Upload All at Once
1. Click "Add file" → "Upload files"
2. Drag all 6 files into the box
3. **Important:** This will REPLACE existing files
4. Commit message: `Release v1.1.0`
5. Click "Commit changes"

### Step 3: Create Release v1.1.0

1. Click **"Releases"** (right sidebar on main page)
2. Click **"Create a new release"**
3. **Choose a tag:** Type `v1.1.0` and select "Create new tag: v1.1.0 on publish"
4. **Release title:** `Version 1.1.0 - Side-by-side Layout & UX Improvements`
5. **Description:**

```markdown
# Phospho Proteoform Calculator v1.1.0

## Major Improvements

### Layout Redesign
- **Side-by-side view:** Spectrum (left) + phosphorylation sites (right)
- Everything visible without scrolling on laptop screens
- Compact, professional interface

### User Experience
- **Auto-load on startup:** Random protein appears immediately
- **Guided interaction:** Hint text explains what to try
- **Better zoom:** 1 kDa range centers phosphorylation states properly
- **Fixed overlaps:** Peak labels (P3, P4, etc.) no longer collide

### Technical
- Responsive design for desktop, tablet, and mobile
- Compact site controls (50% less space)
- Improved peak label positioning algorithm
- Taller spectrum aspect ratio (65%)

## Try it now
🔗 https://Boriz4k.github.io/phospho-calculator-html

## Files
- `index.html` - Standalone calculator (download and open in browser)

## Full Changelog
See [CHANGELOG.md](https://github.com/Boriz4k/phospho-calculator-html/blob/main/CHANGELOG.md)
```

6. **Attach files (optional):** Upload `index.html` as downloadable asset
7. Click **"Publish release"**

### Step 4: Verify GitHub Pages

1. Go to **Settings** → **Pages**
2. Should say: "Your site is live at https://Boriz4k.github.io/phospho-calculator-html"
3. Wait 2-3 minutes for deployment
4. Visit the URL to test

---

## Testing Checklist

After upload, test on GitHub Pages:

**Desktop:**
- [ ] Spectrum on left, sites on right (side-by-side)
- [ ] Random protein loads automatically
- [ ] All presets work (α1, β1, γ1, Complex, Random)
- [ ] Peak shape presets work (All 50%, Gradient, Bimodal, Reset)
- [ ] Main slider adjusts phosphorylation smoothly
- [ ] Individual site sliders work
- [ ] Peak labels don't overlap
- [ ] Download spectrum (PNG)
- [ ] Export data (CSV)

**Tablet (iPad):**
- [ ] Layout stacks vertically (spectrum top, sites below)
- [ ] Controls wrap properly
- [ ] Touch scrolling works

**Phone:**
- [ ] All content visible
- [ ] Buttons are tappable
- [ ] Sliders work with touch
- [ ] No horizontal scrolling

---

## QR Code Generation (For Poster)

Once GitHub Pages is updated:

1. **Get your URL:** https://Boriz4k.github.io/phospho-calculator-html
2. **Generate QR code:** 
   - Go to https://www.qr-code-generator.com/
   - Paste URL
   - Download high-res PNG (300 DPI minimum)
   - Size for printing: 5×5 cm recommended
3. **Test:** Print on paper, scan with phone
4. **Add to poster** with text: "Try it yourself!"

---

## Troubleshooting

**Problem:** Changes don't appear on GitHub Pages
- **Solution:** Wait 5 minutes, GitHub Pages can be slow to update
- Clear browser cache (Ctrl+Shift+R or Cmd+Shift+R)
- Check if files actually updated in repository

**Problem:** "404 Not Found"
- **Solution:** Verify GitHub Pages is enabled in Settings → Pages
- Make sure file is named exactly `index.html` (lowercase)

**Problem:** JavaScript errors
- **Solution:** View browser console (F12)
- Check if Plotly.js CDN loaded
- Verify all JavaScript is present in index.html

**Problem:** Site controls not showing
- **Solution:** Check browser console for errors
- Verify initializeSiteControls() is called before loadRandomProtein()

---

## After Upload: What Changes?

### Immediate (Within 5 minutes)
- ✅ GitHub repository shows v1.1.0 files
- ✅ Release v1.1.0 appears in Releases section
- ✅ GitHub Pages updates to v1.1.0
- ✅ "Cite this repository" button shows v1.1.0

### Your URL Stays the Same
- https://Boriz4k.github.io/phospho-calculator-html
- QR codes from v1.0.0 still work!
- Users automatically get latest version

### What to Share
- GitHub repository: https://github.com/Boriz4k/phospho-calculator-html
- Live tool: https://Boriz4k.github.io/phospho-calculator-html
- Specific release: https://github.com/Boriz4k/phospho-calculator-html/releases/tag/v1.1.0

---

## Git Commands (Advanced - Optional)

If you prefer command line:

```bash
# Clone repository (first time only)
git clone https://github.com/Boriz4k/phospho-calculator-html.git
cd phospho-calculator-html

# Copy new files
cp /path/to/new/index.html .
cp /path/to/new/README.md .
cp /path/to/new/CITATION.cff .
cp /path/to/new/CHANGELOG.md .

# Commit changes
git add .
git commit -m "Release v1.1.0 - Side-by-side layout and UX improvements"

# Create tag
git tag -a v1.1.0 -m "Version 1.1.0"

# Push to GitHub
git push origin main
git push origin v1.1.0
```

Then create release on GitHub web interface.

---

## Next Steps

After successful upload:

1. **Test everything** on live site
2. **Generate QR code** for poster
3. **Share with colleagues** for feedback
4. **Monitor GitHub Issues** for bug reports
5. **Plan v1.2** features based on feedback

---

## Need Help?

- GitHub Help: https://docs.github.com/
- GitHub Pages: https://pages.github.com/
- Create issue: https://github.com/Boriz4k/phospho-calculator-html/issues

Good luck with the upload! 🚀
