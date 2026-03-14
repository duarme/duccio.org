# duccio.org — Personal Website Plan

**Status:** Idea
**Domain:** duccio.org (registered)
**Format:** Static single-page site (HTML + CSS, JS only if needed)

---

## Purpose

A personal landing page that does three things:
1. Tells visitors who Duccio is and what he offers (in 10 seconds).
2. Funnels them to the right platform (X, YouTube, LinkedIn, GitHub, uCV).
3. Proves credibility through a Wall of Love (screenshots and videos from people he helped).

This is not a blog. Not a portfolio. It's a conversion page for anyone who googles "Duccio Armenise" or clicks a link from a bio.

---

## Sections (top to bottom)

### 1. Hero / Value Proposition
One sentence that explains what Duccio does and who it's for. A subtitle with the backstory (laid off, now out-earning his former boss). Primary CTA (follow on X) and secondary CTA (YouTube).

### 2. My Story
The opening of Duccio's story: how he got laid off, became an indie dev, and ended up making more than his former boss. Show the first few lines on the page, then a "continue reading" link that leads to the full story (either a separate page on duccio.org or a published X/blog post). The goal is to hook the visitor without making the landing page too long. The full story is the conversion tool. The landing page is the teaser.

### 3. Links
Flat list of links: X, YouTube, GitHub, LinkedIn, uCV. Visible, not buried in a footer.

### 4. Portfolio
Three products: Corsidia, uCV, Esmerise. For each: name, one-line description, link. Optionally a screenshot. Keep it tight. This section answers "what has this guy actually built?" without turning the page into a case study gallery. No dead projects, no side experiments. Only things that are live and prove competence.

### 5. Wall of Love
Grid of testimonials from people Duccio already helped. Mix of screenshot images and video clips. This is the proof section. The most important part of the page after the hero.

### 6. Footer
Name, domain. Nothing else.

---

## Design Principles

- Single column, max 720px wide. No sidebar, no nav bar.
- System font stack. No custom fonts to load.
- Black and white with minimal accent color. The content is the design.
- Mobile-first. Most visitors will come from X on their phone.
- No animations, no parallax, no hero image. Fast and clean.

---

## Technical Decisions

- **Static HTML + CSS.** No framework, no build step, no CMS. Edit the file, push, done.
- **No JavaScript** unless a lightbox for screenshots or a "show more" toggle for the Wall of Love becomes necessary. Even then, keep it under 3KB.
- **Video testimonials:** two options depending on scale.
  - **Option A (launch):** Self-hosted with native `<video>`, `preload="none"`. Simplest, no tracking, no clutter. Works fine for 3-5 short clips.
  - **Option B (growth):** Upload to YouTube, embed on the page. Solves bandwidth, drives traffic to the YouTube channel, and the videos become discoverable content on their own. Tradeoff: YouTube branding on the player, slower embed load, tracking.
  - Start with A. Switch to B when the video count or file sizes justify it, or when driving YouTube traffic becomes a priority.
- **Lazy loading** on all images. Wall of Love will be the heaviest section.

---

## Hosting

- **GitHub Pages** (free tier). More than enough for a static single-page site.
- Custom domain: `duccio.org` via CNAME record pointing to `<username>.github.io`.
- HTTPS: automatic via Let's Encrypt, no configuration needed.
- Deployment: push to `main` branch, site updates in seconds.
- **Limits (none that matter):**
  - 1 GB repo size. This page will be a few MB.
  - 100 GB/month bandwidth. Would need hundreds of thousands of visitors to hit this.
  - Static only, no server-side code. That's the plan already.
- **DNS setup at registrar:**
  - A records pointing to GitHub's IPs: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`.
  - CNAME for `www` pointing to `<username>.github.io`.
  - Add a `CNAME` file in the repo root containing `duccio.org`.
- **If self-hosted videos get heavy:** move video files to Cloudflare R2 (free tier: 10 GB storage, 10 million reads/month) and link from the static page. Or switch to YouTube embeds (see Technical Decisions above).

---

## Content to Prepare Before Building

1. **Hero headline.** Needs to be sharp. Current candidate: "I help developers escape the hamster wheel and build profitable indie products."
2. **Portfolio entries.** For each of Corsidia, uCV, and Esmerise: one-line description, URL, and optionally a clean screenshot (browser frame, no clutter). Write descriptions from the user's perspective, not the developer's.
3. **Wall of Love material.** Collect screenshots of tweets/messages from people thanking Duccio. Record or request short video testimonials. Aim for 6 to 8 strong ones at launch, add more over time.
4. **Profile photo.** Optional but helps. A real face builds trust faster than a logo.
5. **Meta description.** For SEO and social previews when the link is shared.
6. **Open Graph image.** So the link looks good when shared on X, LinkedIn, WhatsApp.

---

## What This Is Not

- Not a blog. If Duccio wants to write long-form, it goes on X or a separate platform.
- Not a deep-dive portfolio with case studies and tech stacks. The portfolio section shows what Duccio built. If people want details, they can click through to each product.
- Not a lead capture page with email signups. If that becomes relevant, it can be added later. For now, X is the funnel.

---

## Open Questions

- Should the Wall of Love have a cap (e.g., show 6, "see all" expands the rest)? Depends on how many testimonials exist at launch.
- Should there be an "as seen in" or "featured" section? Only if there are real mentions worth showing. Don't fake social proof.
- Should the uCV link go to an external service or a self-hosted page under duccio.org/cv? Depends on what uCV already provides.
