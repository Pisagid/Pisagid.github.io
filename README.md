# isaacgideonpoku.com — Isaac Gideon Poku

The personal website of Isaac Gideon Poku. It is a single page with no build step.

```
index.html                 the whole site (styles and script included)
assets/isaac.webp          portrait with the background removed
assets/og.png              preview image shown when the link is shared (1200×630)
assets/badges/             Microsoft Certified Associate and Expert badges, taken from your certificates
assets/flags.webp          all country flags for the phone country picker, in one small image (no outside service needed)
assets/apple-touch-icon.png
assets/logo/               logo files (see below)
404.html                   friendly "not found" page; also sends isaacgideonpoku.com/works etc. to the right section
robots.txt, sitemap.xml    help search engines find and index the site
```

## 1. Put it on GitHub Pages

1. Create a public repository on the `Pisagid` account. Any name works, for example `isaacgideonpoku.com` or `Pisagid.github.io`.
2. Upload everything in this folder, keeping the `assets` folder structure, to the main branch.
3. Open **Settings → Pages**. Under **Source**, choose **Deploy from a branch**, then select **main** and **/ (root)**.
4. The site is live at **https://pisagid.github.io**. Once you own isaacgideonpoku.com and have added the DNS records below, enter `isaacgideonpoku.com` under **Settings → Pages → Custom domain** and save. GitHub then serves the site on your domain and redirects the github.io address to it.

## 2. Point isaacgideonpoku.com at GitHub

Add these DNS records at your domain registrar:

| Type | Name / Host | Value |
| --- | --- | --- |
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | pisagid.github.io |

DNS changes can take a few hours to spread. Once GitHub shows the domain as verified, tick **Enforce HTTPS** under **Settings → Pages**. Check GitHub's "Managing a custom domain for your GitHub Pages site" page in case these addresses have changed.

## 3. Activate the contact form (one time)

The **Send message** button emails every enquiry to **pisagid@gmail.com** through FormSubmit (formsubmit.co), a free service made for static sites like this one. No account is needed, but it has to be activated once:

1. Open the live site and send yourself a test message from the form.
2. FormSubmit emails an **activation link** to pisagid@gmail.com. Open it and click **Activate form**.
3. From then on, every message arrives in your inbox as a neat table. Hit **Reply** to answer the visitor directly.

Until the form is activated, or if FormSubmit is ever unreachable, visitors are offered WhatsApp, their email app or Gmail instead, so no enquiry is lost.

Optional: after activation, FormSubmit's email shows a random address for your form (like `https://formsubmit.co/ajax/a1b2c3…`). Paste it into `const FORM_ENDPOINT` in `index.html` to keep your email address out of the page source.

To use something else (Formspree, or a Power Automate flow that saves enquiries to SharePoint), replace `FORM_ENDPOINT` with that service's address. The form sends JSON with `name`, `email`, `organisation`, `phone`, `needs`, `start`, `message` and `_subject`.

## Logo

The logo is the name **pisagid**: **P**oku, **isa** for Isaac, **gid** for Gideon. The **a** and **g** are joined into one symbol: the a's arch and bowl sit on top, and its stem drops into the g's tail, joining Isaac and Gideon. The dots of the two i's are linked, a nod to networks and connected systems.

| File | Use |
| --- | --- |
| `pisagid-wordmark.svg` / `-2000.png` | on light backgrounds |
| `pisagid-wordmark-white.svg` / `-2000.png` | on dark backgrounds |
| `pisagid-icon.svg` / `-1024.png` | favicon, app icon, profile pictures (navy) |
| `pisagid-icon-blue.svg` / `-1024.png` | profile pictures (blue) |

Colours: navy `#0E1B3D` and blue `#1F6FEB`. Typeface: Bricolage Grotesque ExtraBold, converted to outlines so the logo looks the same everywhere.

## Layout

The site opens with a loading screen, then shows one scrolling page. The top menu jumps to each section, and a small menu bar stays at the top once you scroll past the opening section. Each section also has its own link you can share:

| Section | Link |
| --- | --- |
| Home | isaacgideonpoku.com/ |
| About me | isaacgideonpoku.com/#about |
| Services | isaacgideonpoku.com/#services |
| Works | isaacgideonpoku.com/#works |
| Credentials | isaacgideonpoku.com/#credentials |
| Hire me | isaacgideonpoku.com/#hire |

## Updating content

| What | Where in `index.html` |
| --- | --- |
| Certifications (the orbiting badges and the Credentials page) | the `certs` list at the top of the `<script>`. Set `lvl` to `"associate"` or `"expert"`. |
| Projects (the Works carousel) | the `projects` list just below it |
| Real screenshots | put an image in `assets/work/` and add `image:"assets/work/name.png"` to that project. It replaces the illustration. |
| About me, Services | the `#about` and `#services` sections |
| Contact details and social links | the hero and the `#hire` section (each contact is a link with its own icon) |
| Colours and fonts | the `:root` block at the top of `<style>` |

A moon button in the header switches to dark mode.

## Extras built in

- **Loading screen:** the logo draws itself while the photo and badges load, then wipes away to the home section.
- **Orbiting badges:** your certifications circle your photo. Hover or tap one to see its name.
- **Music staff:** the "Off the clock" section shows the opening phrase of *Amazing Grace* (public domain) on a treble staff. **Play the phrase** plays it with notes lighting up in time, and any single note can be tapped. Sound only starts when a visitor presses a button.
- **Google-friendly:** the page includes structured data describing you, your job, your certifications and your social profiles, which helps search results show your name properly.
- **Accessibility:** works with a keyboard, respects "reduce motion" settings, and every image has a description.
