# Mushin (Hugo Sokołowski-Katzer's Personal Site)

This repository contains the source code for my personal website and portfolio, accessible at [hugokatzer.tech](https://hugokatzer.tech/).

## Overview

The site is built using [Hugo](https://gohugo.io/), a fast and flexible static site generator, and generally uses the [FixIt](https://github.com/hugo-fixit/FixIt) theme. 
It features multiple sections including:
- **Home**: A brief introduction and profile.
- **Projects**: A showcase of my work and research (e.g., MSc AI projects, theses).
- **Devlog**: Ongoing development logs and updates.
- **About me**: Detailed background information.

## Usage / Local Development

To run this site locally, make sure you have [Hugo installed](https://gohugo.io/installation/).

1. **Clone the repository (if you haven't already):**
   ```bash
   git clone https://github.com/RAGNAROS-HS/Mushin.git
   cd Mushin
   ```

2. **Run the local development server:**
   ```bash
   hugo server -D
   ```
   The `-D` flag ensures that content marked as `draft: true` is also rendered. The site should now be available at `http://localhost:1313`.

3. **Build the site for production:**
   ```bash
   hugo
   ```
   This command generates the static HTML/CSS/JS files into the `public/` directory, which can then be deployed.

4. **Create new content:**
   ```bash
   hugo new content/devlog/my-new-post.md
   hugo new content/projects/my-new-project.md
   ```
