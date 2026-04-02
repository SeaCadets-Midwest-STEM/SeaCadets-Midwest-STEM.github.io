# Contributing to Sea Cadets Midwest STEM

Thank you for contributing! This guide explains how to add and edit content on the site. No coding experience is required — all content is written in Markdown, a simple text formatting language.

---

## Table of Contents

- [How the Site Works](#how-the-site-works)
- [Adding Content via GitHub](#adding-content-via-github)
- [Content Types](#content-types)
  - [Adding an Event](#adding-an-event)
  - [Adding a News Post](#adding-a-news-post)
  - [Adding a Program](#adding-a-program)
  - [Adding a Resource](#adding-a-resource)
  - [Adding Photos to the Gallery](#adding-photos-to-the-gallery)
- [Front Matter Reference](#front-matter-reference)
- [Markdown Cheat Sheet](#markdown-cheat-sheet)
- [Previewing Changes Locally](#previewing-changes-locally)

---

## How the Site Works

The site is built with **Hugo**, a tool that converts Markdown files into web pages. When changes are pushed to the `main` branch on GitHub, the site is automatically rebuilt and published.

Each page on the site corresponds to a `.md` (Markdown) file in the `content/` folder.

---

## Adding Content via GitHub

The easiest way to add content without installing anything:

1. Go to the repository on GitHub
2. Navigate to the appropriate folder in `content/` (e.g., `content/events/`)
3. Click **Add file** → **Create new file**
4. Name your file (e.g., `2026-fall-robotics-day.md`)
5. Paste in the template for that content type (see below)
6. Fill in the details
7. Scroll down and click **Commit new file** (commit directly to `main` or create a pull request for review)

The site will automatically rebuild within a few minutes.

---

## Content Types

### Adding an Event

Create a new `.md` file in `content/events/`. Use a descriptive filename like `EC-IN-2601-Invention-Lab.md`.

**Template:**

```markdown
---
title: "Fall Robotics Day"
date: 2026-09-15
draft: false
description: "A one-day robotics workshop for cadets."

event_date: 2026-10-12
event_end_date: 2026-10-12
location: "Great Lakes NTC, IL"
training_code: "ER-IL-2602"
status: "upcoming"

hero_title: "Fall Robotics Day"
hero_subtitle: "October 12, 2026 — Great Lakes, IL"
---

Write your event description here.

## What to Expect

Describe the event activities.

## Requirements

List any prerequisites.
```

**Important fields:**
- `training_code` — The code cadets use to register via **Quarterdeck** (e.g., "ER-IL-2602")
- `status` — Set to `"upcoming"` for future events, `"past"` for completed events, or `"cancelled"`
- `event_date` — The actual date of the event (separate from `date`, which is the publish date)

### Adding a News Post

Create a new `.md` file in `content/news/`.

**Template:**

```markdown
---
title: "Your News Title"
date: 2026-09-15
draft: false
description: "A brief summary of the news."
author: "Your Name"
tags: ["announcement"]
categories: ["General"]
---

Write your news content here.
```

### Adding a Program

Create a new `.md` file in `content/programs/`.

**Template:**

```markdown
---
title: "Program Name"
date: 2026-09-15
draft: false
description: "Brief description of the program."
weight: 30
age_range: "10-18"
featured: false
---

Describe the program here.

## Overview

What is this program about?

## What You'll Learn

- Skill 1
- Skill 2

## How to Participate

How cadets can get involved.
```

Set `featured: true` to display the program on the homepage.

### Adding a Resource

Create a new `.md` file in `content/resources/`.

**Template:**

```markdown
---
title: "Resource Name"
date: 2026-09-15
draft: false
description: "Brief description of the resource."
weight: 20
---

Resource content here.
```

### Adding Photos to the Gallery

Edit `content/gallery/_index.md` and add entries to the `images` list in the front matter:

```yaml
images:
  - src: "/images/gallery/photo1.jpg"
    alt: "Cadets building a robot"
    caption: "Summer STEM Camp 2026 — Robotics team"
  - src: "/images/gallery/photo2.jpg"
    alt: "Cybersecurity lab"
    caption: "Cadets working through a CTF challenge"
```

Upload the actual image files to the `static/images/gallery/` directory.

---

## Front Matter Reference

Front matter is the section between `---` marks at the top of each Markdown file. Here's what each field means:

| Field | Used In | Description |
|-------|---------|-------------|
| `title` | All | Page title displayed on the site |
| `date` | All | Publish date (YYYY-MM-DD format) |
| `draft` | All | Set to `true` to hide from the live site; `false` to publish |
| `description` | All | Short summary used in search engines and social sharing |
| `weight` | Programs, Resources | Controls display order (lower numbers appear first) |
| `hero_title` | All | Custom title for the hero banner (optional) |
| `hero_subtitle` | All | Subtitle text in the hero banner (optional) |
| `hero_image` | All | Path to a hero background image (optional) |
| `event_date` | Events | Actual event start date |
| `event_end_date` | Events | Event end date (if multi-day) |
| `location` | Events | Event location |
| `training_code` | Events | Quarterdeck registration code (e.g., "ER-MW-2601") |
| `status` | Events | `"upcoming"`, `"past"`, or `"cancelled"` |
| `age_range` | Programs | Eligible age range (e.g., "10-18") |
| `featured` | Programs | Set to `true` to show on the homepage |
| `author` | News | Author name |
| `tags` | News | List of tags (e.g., `["robotics", "announcement"]`) |
| `categories` | News | List of categories (e.g., `["General"]`) |

---

## Markdown Cheat Sheet

Markdown is a simple way to format text. Here are the basics:

```markdown
# Heading 1
## Heading 2
### Heading 3

**Bold text**
*Italic text*

- Bullet point
- Another point

1. Numbered item
2. Another item

[Link text](https://example.com)

![Image description](/images/photo.jpg)

> This is a blockquote
```

For more details, see the [Markdown Guide](https://www.markdownguide.org/basic-syntax/).

---

## Previewing Changes Locally

If you have Hugo installed, you can preview the site on your computer:

```bash
cd SeaCadets-Midwest-STEM
hugo server -D
```

Then open `http://localhost:1313/` in your browser. The `-D` flag includes draft content. Changes you make to files will automatically refresh in the browser.

### Installing Hugo

Follow the [official Hugo installation guide](https://gohugo.io/installation/) for your operating system. Make sure to install the **extended** version (needed for the site's stylesheets).
