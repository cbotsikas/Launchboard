# Launchboard

Launchboard is a lightweight offline start page for quick access to work links and personal task tracking.

## Why It Exists

This project was built for a constrained browser environment where:

- browser plugins are not allowed by company IT policies
- the browser home and new-tab experience cannot be customized enough
- the new tab's shortcut limit (10) is too small for day-to-day work needs

The goal was to build something lightweight, fast, offline-capable, and private by default. The page runs as a local `file://` page, stores its state in the browser profile, and does not depend on third-party hosted services. That keeps sensitive internal URLs out of external bookmark tools or online dashboards.

It was also a hands-on experiment in collaborating with AI agents to iteratively design and refine a small utility.

## What It Does

- Organizes links into sections
- Supports drag-and-drop reordering and moving links across sections
- Lets you manage lightweight tasks with completion tracking
- Persists data locally in the browser with `localStorage`
- Works as a local `file://` page with no backend or extension

## Usage

1. Open `index.html` in your browser.
2. Bookmark the local file if you want to use it as your landing page.
3. Add sections, links, and tasks from the UI.

## Notes

- Data is stored in the current browser profile.
- The default state is empty.
- This project is intentionally dependency-free and build-free.
- It is designed for local use first, not for shared multi-user deployment.
