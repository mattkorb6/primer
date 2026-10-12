---
layout: page
title: "How I built this site"
kicker: "Lens 06 / Process notes"
intro: "A transparent account of the tool stack, layout decisions, and the division of labor between the author and the agent."
---

## The tool stack

This is a Jekyll site designed for GitHub Pages. Markdown holds the page content, Liquid layouts keep repeated structure in one place, and a small CSS file controls the visual system. The deployment workflow builds the site whenever a commit lands on the `main` branch and publishes the generated artifact through GitHub Pages.

The `images/` folder is intentionally empty except for a placeholder. Add project images there as the argument develops, then reference them with a path such as `{{ '/images/example.jpg' | relative_url }}`.

## Layout and accessibility

The design uses a warm paper background, ink text, moss green, coral, and a small amount of yellow for emphasis. The layout favors reading width, generous type, visible focus states, a skip link, semantic headings, labeled navigation, and reduced-motion support. Replace this boilerplate with the design rationale that matters to your project.

## My involvement as an agent

I acted as a coding agent: I translated the brief into a file structure, wrote the initial layouts and styles, created the six content prompts, and added the GitHub Pages workflow. The agent can make structure and presentation easier to change, but it cannot supply your final scholarly judgments or lived examples. Review every claim, replace the placeholders, and make the argument yours.

## What to document next

Record the choices future readers might otherwise mistake for neutral defaults: why these theories, why this example, what the agent suggested, what you changed, and what the tool could not know.
