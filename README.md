# personal-site-template

Created by [Jennifer Isasi](https://jenniferisasi.github.io) for a workshop on personal sites for graduate students. Last updated February 2026. AI Usage Disclosure: This document was created with minimal assistance from Claude.

You can preview the site at: https://dla-psu.github.io/personal-site-template/

GitHub provides a preview of files before committing changes. If you prefer to work locally, we recommend [Zettlr](https://www.zettlr.com) to work on the files or [Visual Studio Code](https://code.visualstudio.com) if you want to avoid the online GitHub interface. 

---

A template to create a simple, static personal site with bio, projects (bilingual in the template), and CV. It turns Markdown files into web pages automatically. No coding required for updates.

The site has four pages:

- **About** (homepage) — with visual timeline and optional PhD progress tracker
- **Projects** — in your primary language
- **Projects** — in an alternative language OR for a secondary project
- **CV/Resume**

---

## Table of Contents

- [Using This Template](#using-this-template)
- [How to Make Changes](#how-to-make-changes)
- [What's in Each Folder](#whats-in-each-folder)
- [Customizing the About Page](#customizing-the-about-page)
  - [Timeline](#timeline)
  - [PhD Progress Tracker](#phd-progress-tracker)
- [Adding a New Project](#adding-a-new-project)
- [Adding Images](#adding-images)
- [Basic Markdown Formatting](#basic-markdown-formatting)
- [Basic HTML Editing](#basic-html-editing)
- [How It Actually Works](#how-it-actually-works)
- [Troubleshooting](#troubleshooting)
- [Want to Change the Design?](#want-to-change-the-design)
- [Want to Add More Project Pages?](#want-to-add-more-project-pages)

---

## Using This Template

1. Click the green **"Use this template"** button at the top of this page
2. Choose **"Create a new repository"**
3. **Name your repository:**
   - **For a clean URL** (recommended): Name it `your-username.github.io`
     → Your site will be at `https://your-username.github.io/`
   - **For a project site**: Name it anything (e.g. `my-portfolio`)
     → Your site will be at `https://your-username.github.io/repository-name/`
     → ie. this site is `https://dla-psu.github.io/personal-site-template/` because it is a project within the DLA-PSU initiatives
4. Set it to **Public**
5. Click **"Create repository"**

GitHub will copy all files to your new repo in a couple of minutes. Then you can edit them with your own information.

**Enable GitHub Pages after copying to deploy/publish the site:**

1. Go to **Settings** in your new repository (left, on the top bar navigation)
2. Click **Pages** on the left side menu
3. Under "Source", select **GitHub Actions**
4. Your site will be live in 2–3 minutes

---

## How to Make Changes

### For Projects and CV pages:

1. Navigate to the file in the `content/` folder (e.g. `content/projects-main.md`)
2. Click the pencil icon in the top right
3. Edit using Markdown
4. Scroll to the bottom and click **"Commit changes"**
5. Wait 2–3 minutes for the site to update

### For the About page:

1. Navigate to `about.html` in the root folder
2. Click the pencil icon
3. Edit the HTML directly — it's clearly structured with comments explaining each section
4. Commit changes

### Updating the Footer

The footer appears in two places and should match on all pages.

**1. About page footer** — open `about.html` and find:

```html
<footer>
    <p>&copy; 2024 [Your Name]. All rights reserved.</p>
</footer>
```

**2. All other pages** — open `template.html` and find the same block.

Replace `[Your Name]` with your name in both files.

### Changing Navigation Language Labels

1. Open `template.html`
2. Find the `<nav>` section
3. Change "Projects" and "Proyectos" to your preferred labels (e.g. "Projets" for French, "Projekte" for German)
4. Make the same update in `about.html` to keep navigation consistent

---

## What's in Each Folder

**Root folder:**

| File | Purpose |
|------|---------|
| `about.html` | About page / homepage (timeline + optional PhD tracker) |
| `template.html` | Page layout used for all Markdown-based pages |
| `styles.css` | Colors and fonts for the entire site |
| `.github/workflows/deploy.yml` | Instructions for GitHub on how to build the site |

**`content/`** — Markdown files converted to pages:

| File | Purpose |
|------|---------|
| `projects-main.md` | Projects in your primary language |
| `projects-alt.md` | Projects in an alternative language |
| `cv.md` | Your CV/resume |

**`images/`** — All photos and screenshots:

| File | Purpose |
|------|---------|
| `photo.jpg` | Your profile photo |
| *(other files)* | Project screenshots, etc. |

---

## Customizing the About Page

The About page (`about.html`) is an HTML file with clearly labeled comment blocks. You edit it directly in GitHub by clicking the pencil icon.

### Timeline

The timeline displays your education and career history. Items are listed with the most recent at the top.

**To add a new timeline item:**

1. Open `about.html`
2. Find the timeline section
3. Copy an existing block:

```html
<div class="timeline-item">
    <div class="timeline-dot"></div>
    <div class="timeline-content">
        <div class="timeline-date">YEAR – YEAR</div>
        <h3>Position or Degree Title</h3>
        <h4>Company or Institution</h4>
        <p>Description of what you did.</p>
    </div>
</div>
```

4. Paste it in place (most recent at the top)
5. Update with your information

### PhD Progress Tracker

An optional section you can enable to display your degree progress, milestones, and expected completion.

**To enable it:**

1. Open `about.html`
2. Find the section starting with `<!-- OPTIONAL PhD PROGRESS TRACKER`
3. Delete the `<!--` line at the beginning of the section
4. Scroll down and delete the `-->` line at the end
5. Commit your changes

**To customize it, update these fields inside `about.html`:**

- **Degree title** — e.g. "PhD in History"
- **Year progress** — e.g. "Year 2 of 5"
- **Institution name**
- **Expected completion year**
- **Progress percentage** — change `60%` in two places (the displayed label and `width: 60%`)
- **Milestones** — add, remove, or reorder as needed

**Milestone status classes:**

| Class | Appearance |
|-------|-----------|
| `class="completed"` | Green with ✓ |
| `class="in-progress"` | Orange with ⚡ |
| *(no class)* | Gray with ◯ |

**To customize tracker colors in `styles.css`:**

- **Progress bar**: find `.progress-fill` and update the `background` value
- **Completed milestones**: find `.milestone.completed .milestone-title` and change the color
- **In-progress milestones**: find `.milestone.in-progress .milestone-title` and change the color
- **Tracker border**: find `.phd-progress` and change `border-left: 4px solid #3498db;`

Popular color combinations:
- Professional Blue: `#2563eb` / `#1e40af`
- Academic Purple: `#8b5cf6` / `#6d28d9`
- Success Green: `#10b981` / `#059669`

---

## Adding a New Project

1. Open `content/projects-main.md`
2. Find an existing project section
3. Copy everything from one `---` divider to the next
4. Paste it where you want the new project
5. Update the title, date, description, and any other fields
6. Commit changes

Repeat in `content/projects-alt.md` for the alternative-language version.

---

## Adding Images

1. In your repository, click **"Add file"** → **"Upload files"**
2. Upload your image to the `images/` folder
3. Reference it in a Markdown file:

```markdown
![Description of image](./images/my-image.jpg)
```

Replace `my-image.jpg` with your actual filename. Filenames are case-sensitive.

---

## Basic Markdown Formatting

```markdown
# Big heading
## Smaller heading
### Even smaller heading

**bold text**
*italic text*

- Bullet point
- Another bullet point

[Link text](https://website.com)

![Image description](./images/photo.jpg)
```

For a deeper intro, see: [Getting Started with Markdown](https://programminghistorian.org/en/lessons/getting-started-with-markdown) by Sarah Simpkin.

---

## Basic HTML Editing

The About page uses HTML. Here are the essentials:

```html
<h1>Big heading</h1>
<h2>Smaller heading</h2>
<p>This is a paragraph.</p>

<strong>bold</strong>
<em>italic</em>

<a href="https://website.com">Link text</a>
<img src="./images/photo.jpg" alt="Description">
```

The `about.html` file has comments (text between `<!--` and `-->`) explaining what each section does — you don't need to touch anything outside those labeled areas.

For more: [Viewing HTML Files](https://programminghistorian.org/en/lessons/viewing-html-files) by William J. Turkel and Adam Crymble.

---

## How It Actually Works

When you commit changes, GitHub automatically rebuilds your site:

- **Markdown files** (Projects, CV): converted to HTML using Pandoc, then wrapped in `template.html` (which adds navigation and styling)
- **`about.html`**: copied directly to the site — no conversion needed
- **Images and CSS**: copied as-is

This all happens in 2–3 minutes. You never need to trigger it manually.

---

## Troubleshooting

**Changes aren't showing up**
Wait 3–5 minutes. Then check the **Actions** tab — a red ✗ means something went wrong. Click it for details.

**Image not appearing**
Make sure the file is in the `images/` folder and the filename in your Markdown matches exactly (including the extension and capitalization).

**Timeline or progress tracker not displaying correctly**
Check that you've removed the `<!--` and `-->` comment wrappers fully, and that `styles.css` contains the timeline styles.

**Something broke**
GitHub keeps a full history of changes. Go to the file → click **History** → find the last working version → use the three-dot menu to revert.

---

## Want to Change the Design?

Edit `styles.css` to change colors or fonts. The two main colors used throughout the site are:

- `#3498db` — blue accent color
- `#2c3e50` — dark navigation bar

To change them:
1. Browse palettes at [color-hex.com/color-palettes](https://www.color-hex.com/color-palettes/)
2. Copy your preferred hex codes
3. Open `styles.css` and do a find-and-replace for the existing values
4. Commit — site updates in 2–3 minutes

---

## Want to Add More Project Pages?

### Step 1: Create the new Markdown file

1. Go to `content/`
2. Click **"Add file"** → **"Create new file"**
3. Name it (e.g. `projects-lang3.md`)
4. Copy content from `projects-main.md` and translate it
5. Commit

### Step 2: Update the workflow

1. Open `.github/workflows/deploy.yml`
2. In the Markdown conversion section, add before the CV step:

```yaml
          # Convert projects (third language)
          pandoc content/projects-lang3.md -o _site/projects-lang3.html \
            --from markdown+raw_html \
            --template=./template.html \
            --metadata title="Projects" \
            --metadata page="projects-lang3"
```

3. Commit

### Step 3: Add a navigation link

1. Open `template.html`
2. Find the `<nav>` section and add:

```html
<li><a href="./projects-lang3.html">Your Label</a></li>
```

3. Add the same link to the `<nav>` section in `about.html`
4. Commit

Your new project page will appear in the navigation on all pages.
