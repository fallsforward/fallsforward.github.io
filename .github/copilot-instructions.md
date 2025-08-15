# Copilot Instructions for Falls Forward Website

## Repository Overview

This is the **Falls Forward** website repository (`fallsforward/fallsforward.github.io`), a static GitHub Pages site for an educational advocacy organization in Sheboygan Falls, Wisconsin. The organization focuses on educational excellence, fiscal responsibility, and student safety in local schools.

**Repository Details:**
- **Type:** Static website deployed via GitHub Pages
- **Size:** ~16MB, ~2,000 lines of code
- **Languages:** HTML, CSS, JavaScript (vanilla)
- **Framework:** Bootstrap 5.3.3 with BootstrapMade "Append" template
- **Domain:** https://fallsforward.org (via CNAME)
- **Main Pages:** `index.html` (455 lines), `past-issues.html` (109 lines)

## Build and Validation Instructions

### Prerequisites
- **Python 3.x** (for local testing)
- **Node.js/npm** (for linting with webhint)
- **Web browser** (for testing)

### Local Development Setup
1. **Clone and navigate:**
   ```bash
   cd /path/to/fallsforward.github.io
   ```

2. **Start local development server:**
   ```bash
   python -m http.server 8000 --directory .
   ```
   - Access site at `http://localhost:8000`
   - **Always test locally** before committing changes
   - Server starts instantly, no build process required

### Linting and Validation

**Primary Linter - webhint (.hintrc configuration):**
```bash
npx --yes hint . --config .hintrc
```
- **Expected output:** 26 errors, 42 warnings, 44 hints (mostly CSS compatibility issues)
- **Focus on:** New errors/warnings introduced by your changes
- **Note:** Existing CSS compatibility warnings are known and acceptable
- **Runtime:** ~30-60 seconds (includes npm install)

**Code Style - EditorConfig:**
- **Indentation:** 2 spaces for .js, .ts, .html, .css, .json
- **Always** respect existing formatting patterns
- VSCode settings in `.vscode/settings.json` include spell check dictionary

### Deployment Process

**Automatic GitHub Pages Deployment:**
- **Trigger:** Any push to `main` branch
- **Workflow:** "pages-build-deployment" (GitHub native)
- **No manual deployment steps required**
- **Validation:** Site auto-deploys to https://fallsforward.org

### Testing Checklist

Before committing changes:
1. **Start local server** and verify pages load correctly
2. **Run webhint linter** and ensure no new errors
3. **Test responsive design** (mobile/desktop)
4. **Verify all links work** (especially external links to Substack, social media)
5. **Check images load** (some hosted on external CDNs)

## Project Layout and Architecture

### Directory Structure
```
.
├── index.html                 # Main landing page (455 lines)
├── past-issues.html          # Secondary page (109 lines)
├── assets/
│   ├── css/
│   │   └── main.css          # Custom styles (1,257 lines)
│   ├── js/
│   │   └── main.js           # Custom JavaScript (151 lines)
│   ├── img/                  # Images and graphics
│   └── vendor/               # Third-party libraries
│       ├── bootstrap/        # Bootstrap 5.3.3
│       ├── bootstrap-icons/  # Icon font
│       ├── aos/             # Animate On Scroll
│       ├── swiper/          # Image slider
│       ├── boxicons/        # Icon font
│       └── imagesloaded/    # Image loading utility
├── .editorconfig            # Code formatting rules
├── .hintrc                  # webhint linting configuration
├── .gitignore              # Git ignore patterns
├── .vscode/settings.json   # VSCode configuration
└── CNAME                   # Domain configuration
```

### Key Architecture Elements

**HTML Structure:**
- **Bootstrap 5.3.3** grid system and components
- **Semantic HTML5** with proper heading hierarchy
- **AOS (Animate On Scroll)** for scroll animations
- **Swiper.js** for image carousels
- **Single-page application** design with hash navigation

**CSS Architecture:**
- **Custom CSS** in `assets/css/main.css` extends Bootstrap
- **CSS custom properties** for theme colors (`:root` variables)
- **Responsive design** with Bootstrap breakpoints
- **Component-based** styling (`.hero`, `.features`, `.candidates`, etc.)

**JavaScript Features:**
- **Vanilla JavaScript** (no frameworks) in `assets/js/main.js`
- **Mobile navigation** toggle functionality
- **Scroll spy** for navigation highlighting
- **Smooth scrolling** to anchor links
- **AOS initialization** for animations

### Validation Pipelines

**GitHub Actions Workflows:**
1. **pages-build-deployment:** Standard GitHub Pages deployment
2. **Copilot:** Copilot-related automation

**Pre-commit Validation:**
- **webhint linting** catches HTML/CSS issues
- **EditorConfig** enforces consistent formatting
- **Local testing** required before pushing

### Content Management

**External Dependencies:**
- **Images:** Some hosted on Substack CDN
- **Google Fonts:** Open Sans, Lora, Poppins
- **Google Analytics:** gtag.js with ID G-08D54Y5W4H
- **Social links:** Facebook, X (Twitter) sharing

**Content Sections in index.html:**
- Header with navigation (`#header`)
- Hero section (`#hero`)
- About section (`#about`) 
- Issues section (`#issues`)
- Stats section (`#stats`)
- Get Involved section (`#get-involved`)
- Footer with contact info

### Common File Patterns

**Root Directory Files:**
- `index.html` - Main landing page
- `past-issues.html` - Secondary content page
- `CNAME` - Domain configuration (fallsforward.org)
- `.editorconfig` - Code formatting (2-space indentation)
- `.hintrc` - webhint configuration
- `.gitignore` - Excludes .DS_Store, hint-report/

**Development Guidelines:**
- **Minimal changes only** - this is a small, focused site
- **Test locally first** - always use `python -m http.server`
- **Preserve existing structure** - don't reorganize without reason
- **Maintain accessibility** - use semantic HTML and proper alt text
- **Mobile-first** - test responsive design changes
- **Performance** - keep images optimized, vendor assets unchanged

**Trust these instructions** - they're comprehensive and tested. Only search for additional information if these instructions are incomplete or incorrect.