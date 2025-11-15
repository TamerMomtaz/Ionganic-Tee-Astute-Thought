# CLAUDE.md

## Project Overview

**Ionganic-Tee-Astute-Thought** is a static GitHub Pages portal site that serves as a centralized hub for all RootRise-related projects, experiments, and thought pieces. It functions as a single entry point to navigate various GitHub Pages projects under the RootRise/Tamer Momtaz ecosystem.

**Primary Purpose**: Provide a clean, professional landing page with card-based navigation to multiple project repositories.

**Technology Stack**:
- Static HTML/CSS (no JavaScript dependencies)
- Jekyll (GitHub Pages integration via `_config.yml`)
- Glass morphism design aesthetic
- Responsive grid layout

---

## Repository Structure

```
/
├── index.html          # Main portal page (core file)
├── README.md           # Brief repository description
├── _config.yml         # Jekyll configuration for GitHub Pages
├── logo.png            # Brand logo (2.2MB PNG)
└── CLAUDE.md           # This file - AI assistant guide
```

**Key Files**:

1. **`index.html`** (5.5KB) - The entire application lives here
   - Self-contained HTML with inline CSS
   - Card-based project grid
   - Template for adding new projects (see line 146-151)

2. **`_config.yml`** - Jekyll metadata
   - Theme: `jekyll-theme-cayman`
   - Title and description for GitHub Pages

3. **`logo.png`** - RootRise brand logo
   - Used as page background (with white overlay)
   - Used as clickable logo in each card
   - Should not be modified without explicit permission

---

## Design System

### Color Palette (CSS Variables in `:root`)

```css
--bg: #f7f7fb;       /* Page background (light gray-blue) */
--card: #ffffff;     /* Card background (pure white) */
--text: #1b1f24;     /* Main text (near-black) */
--accent: #2457ff;   /* Blue accent (brand color) */
--muted: #6b7280;    /* Muted text (gray) */
--border: #e5e7eb;   /* Subtle borders (light gray) */
```

### Visual Style
- **Glass morphism**: Header uses `backdrop-filter: blur(10px)` with semi-transparent white
- **Background**: Logo image with white overlay (`rgba(255,255,255,0.92)`) for readability
- **Hover effects**: Cards lift (`translateY(-5px)`) and border color changes to accent blue
- **Border radius**: 20px for header, 14px for cards, 10px for buttons, 16px for logo
- **Typography**: Segoe UI (primary), Roboto, Arial (fallbacks)

---

## Development Workflows

### Adding a New Project Card

The most common task is adding a new RootRise project to the portal. Follow this workflow:

1. **Locate the template** in `index.html` (lines 146-151):
   ```html
   <!-- TEMPLATE: copy for each new page
   <div class="card">
     <h3>Your New Page Title</h3>
     <p>1–2 line description of what's inside.</p>
     <a class="btn" target="_blank" href="https://tamermomtaz.github.io/REPO-NAME/">Open</a>
   </div>
   -->
   ```

2. **Copy the template** and paste it before the closing `</div>` of the grid (line 153)

3. **Modify the card**:
   - `<h3>`: Project title (clear, concise)
   - `<p>`: Brief description (1-2 lines max)
   - `href`: Full GitHub Pages URL following pattern `https://tamermomtaz.github.io/REPO-NAME/`
   - `target="_blank"`: Keep this - all links open in new tabs

4. **Choose button style**:
   - **Logo button** (preferred for consistency):
     ```html
     <a class="logo-link" target="_blank" href="URL">
       <img src="logo.png" alt="Open PROJECT-NAME">
     </a>
     ```
   - **Text button** (legacy style):
     ```html
     <a class="btn" target="_blank" href="URL">Open</a>
     ```

5. **Commit with clear message**:
   ```bash
   git add index.html
   git commit -m "Add [Project Name] card to portal"
   git push -u origin <branch-name>
   ```

### Modifying Existing Cards

When updating existing project cards:

1. **Read `index.html`** first to see current state
2. **Use the Edit tool** to modify specific card content
3. **Preserve formatting**: Maintain indentation (2 spaces per level)
4. **Test descriptions**: Keep them under 100 characters for visual consistency
5. **Verify URLs**: Ensure they point to live GitHub Pages sites

### Git Commit Conventions

Based on repository history:
- **Pattern**: Most commits are `Update index.html`
- **Recommendation for AI assistants**: Be more descriptive
  - Good: `Add LinkedIn Strategy card to portal`
  - Good: `Update DBA Program card description`
  - Avoid: `Update index.html` (too generic)

---

## Key Conventions for AI Assistants

### 1. File Modification Rules

**DO**:
- Read `index.html` before making any changes
- Use the Edit tool for precise modifications
- Preserve exact indentation and spacing
- Keep the template comment intact for future reference
- Maintain alphabetical or chronological card ordering

**DON'T**:
- Modify `logo.png` without explicit permission
- Remove existing cards without confirmation
- Change CSS variables without understanding impact
- Add JavaScript unless absolutely necessary (keep it static)
- Create new files unless specifically requested

### 2. Content Guidelines

**Card Titles**:
- Use title case: "LinkedIn Content Strategy for RootRise"
- Be specific and descriptive
- Match the actual repository/page name when possible

**Card Descriptions**:
- 1-2 concise sentences (max 2 lines when rendered)
- Explain the purpose or content
- Use sentence case
- End with a period

**URLs**:
- Always use full `https://tamermomtaz.github.io/REPO-NAME/` format
- Include trailing slash for consistency
- For anchor links: `https://tamermomtaz.github.io/REPO/#anchor-name`
- Always set `target="_blank"` to open in new tab

### 3. Design Consistency

**Grid Layout**:
- Cards automatically wrap based on screen size
- Minimum card width: 260px
- Grid gap: 20px
- Don't manually control card positioning

**Logo Usage**:
- Current standard: Logo-based links (`<a class="logo-link">`)
- Logo should be 80x80px with border-radius 16px
- Hover effect: 10% scale increase with blue shadow
- Alt text format: `"Open [Project Name]"`

**Accessibility**:
- Always include descriptive alt text for logo links
- Maintain semantic HTML structure
- Ensure sufficient color contrast (already compliant)

### 4. Testing Checklist

Before committing changes:
- [ ] Cards render correctly in grid layout
- [ ] All links open in new tabs (`target="_blank"`)
- [ ] Descriptions are concise (1-2 lines)
- [ ] Logo images load correctly
- [ ] Hover effects work on cards and logos
- [ ] No broken links (verify GitHub Pages URLs exist)
- [ ] HTML is valid (no unclosed tags)
- [ ] Indentation is consistent (2 spaces)

### 5. Common Tasks

**Task: Add a new RootRise project**
```html
<div class="card">
  <h3>Project Name Here</h3>
  <p>Brief description of what this project contains or does.</p>
  <a class="logo-link" target="_blank" href="https://tamermomtaz.github.io/REPO-NAME/">
    <img src="logo.png" alt="Open Project Name Here">
  </a>
</div>
```

**Task: Update a project description**
- Use Edit tool to replace the `<p>` content only
- Keep it under 100 characters
- Maintain sentence case and ending punctuation

**Task: Update a project URL**
- Use Edit tool to replace the `href` value
- Verify the new URL is live before committing
- Keep `target="_blank"` attribute

**Task: Reorder cards**
- Read entire grid section
- Use Edit tool to move entire `<div class="card">...</div>` blocks
- Maintain consistent formatting

---

## Project Context

### RootRise Ecosystem

This portal connects to the **RootRise** brand and related projects:

1. **Before & After (RootRise)** - Comparative project snapshots
2. **RootRise Main Page** - Core product/service information
3. **Alaa Thinks** - Personal reflections and notes
4. **LinkedIn Content Strategy** - Marketing and brand building
5. **DBA Program Integration** - Academic/business integration
6. **Diagnostic Report Assessment** - First-layer analysis

**Pattern**: Most projects are separate GitHub repositories with their own GitHub Pages sites.

### Naming Conventions

- **Repository names**: Kebab-case with descriptive names (e.g., `LinkedIn-Content-Strategy-for-RootRise`)
- **Card titles**: Title case with proper spacing
- **Git branches**: Use `claude/claude-md-<session-id>` pattern for AI assistant work
- **Commits**: Descriptive present tense (e.g., "Add X card", "Update Y description")

---

## Maintenance Notes

### Regular Maintenance Tasks

1. **Verify Links**: Periodically check that all GitHub Pages URLs are still live
2. **Update Descriptions**: Refresh descriptions if project scope changes
3. **Logo Updates**: If brand logo changes, update `logo.png` and test rendering
4. **Accessibility Audit**: Ensure alt text is accurate and descriptive

### Performance Considerations

- **Logo file size**: Current logo.png is 2.2MB - consider optimization if page load is slow
- **Image format**: Consider WebP format for better compression
- **Background image**: Already optimized with fixed attachment for performance

### Browser Compatibility

- **Backdrop filter**: Modern browsers only (Safari 14+, Chrome 76+, Firefox 103+)
- **CSS Grid**: Widely supported (all modern browsers)
- **Fallbacks**: Page degrades gracefully in older browsers

---

## Quick Reference

### File Locations
- Main content: `index.html` lines 91-153 (grid section)
- Template: `index.html` lines 146-151
- CSS: `index.html` lines 7-78 (inline styles)
- Footer: `index.html` line 155

### Important Line Numbers in index.html
- Line 10-15: Color theme variables
- Line 23-27: Background logo configuration
- Line 49: Grid container with auto-fit responsive layout
- Line 50-61: Card styles and button styles
- Line 64-76: Logo link styles
- Line 91-153: Card grid content (main work area)
- Line 146-151: Template for new cards

### Git Workflow
```bash
# Create branch if needed
git checkout -b claude/claude-md-<session-id>

# Make changes to index.html
# Read file first, then Edit

# Commit with descriptive message
git add index.html
git commit -m "Add [specific change] to portal"

# Push to remote
git push -u origin claude/claude-md-<session-id>
```

---

## Questions & Troubleshooting

### Q: Should I add JavaScript functionality?
**A**: No, unless explicitly requested. Keep the site static for simplicity and performance.

### Q: Can I change the color scheme?
**A**: Only if requested by the user. The current palette is part of the RootRise brand identity.

### Q: How do I know if a GitHub Pages URL is correct?
**A**: Ask the user to confirm, or verify the pattern matches `https://tamermomtaz.github.io/[REPO-NAME]/`

### Q: Should I create a separate CSS file?
**A**: No, the inline CSS keeps the project simple and self-contained (single HTML file deployment).

### Q: What if the logo image needs to change?
**A**: Confirm with the user first. Logo is central to brand identity and used throughout the page.

### Q: Can I reorganize the card order?
**A**: Yes, but maintain logical grouping (e.g., keep related RootRise projects together).

---

## AI Assistant Best Practices

1. **Always read before editing**: Use Read tool on `index.html` before making changes
2. **Use Edit tool for precision**: Don't rewrite entire file for small changes
3. **Preserve formatting**: Match existing indentation (2 spaces) and structure
4. **Verify URLs**: Confirm GitHub Pages links are correct before committing
5. **Descriptive commits**: Use clear commit messages that explain what changed
6. **Test before commit**: Mentally verify HTML structure and attribute completeness
7. **Ask when uncertain**: If user request is ambiguous, ask for clarification
8. **Respect the template**: Keep the commented template for future use
9. **Maintain consistency**: Match the style and format of existing cards
10. **One task, one commit**: Don't batch unrelated changes together

---

## Last Updated

This CLAUDE.md was created on 2025-11-15 based on repository state at commit `61344b0`.

**Current branch**: `claude/claude-md-mi0fp7qc8sykcnd3-01GEUHXiXugA46jKuirDVSwi`

When updating this file, change the date and commit hash above.
