# Mushin 

This repository contains the source code for my personal website and portfolio, accessible at [hugokatzer.tech](https://hugokatzer.tech/).

## Overview

The site is built using [Hugo](https://gohugo.io/) (very egotistical, I know), which allows for very fast creation of static sites. I chose this for the mentioned speed, but also because Hugo is primarily populated using markdown files, which is perfect considering I'm populating it with my personal project Readme's (also written in markdown), this consistency between Hugo and Github makes it easy to post to both with minimal changes. Also I'm not a web developer by any stretch of the imagination, so Hugo cuts down on the depth I need to go to in order to have and maintain something passable.

Main sections:
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

The site itself is hosted on a Cloudpanel VPS and updates are deployed using an automated SFTP deployment pipeline via GitHub Actions. All triggered on pushes to main.

Its a bit crude, but very simple and most importantly - works. No third party services, just Hugo and my server.

Enjoy!
