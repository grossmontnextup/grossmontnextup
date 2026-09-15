# NextUp landing page — notes

Plain-English notes for whoever works on this next, including future-us.

## What this is

The landing page for Grossmont NextUp, at **grossmontnextup.com**. Plain HTML —
one file, no build step, no framework. It replaces the earlier Carrd version.

## Files

```
index.html              the whole page
404.html                shown for any bad URL
assets/images/          the four student photos
NOTES.md                this file
```

Folder names become URL paths. `assessment/index.html` would appear at
`grossmontnextup.com/assessment`. That's how to add pages later.

## Hosting

Cloudflare Pages, free tier, connected to the GitHub repo
`grossmontnextup/grossmontnextup`. Any commit to `main` auto-publishes in about
a minute. Cloudflare keeps every past deploy, so rollback is one click.

Build settings, for reference — there is **no build step**:

- Framework preset: None
- Build command: *(empty)*
- Output directory: `/`

Domain is registered at Hover, with DNS delegated to Cloudflare.

## How to make small edits

Open `index.html` on github.com, click the pencil icon, change the text, and
commit. Live in about a minute. No tools to install.

## The form

Posts to **Formspree** at `https://formspree.io/f/mwlpebdw`. Cloudflare can't
receive form submissions itself, and Tally has no endpoint for hand-coded HTML
forms, so Formspree sits behind our own form markup — the page keeps its own
design, labels and focus states.

Sam gets an email per submission with all fields laid out; no dashboard login
needed. Spam protection is a setting inside Formspree — keep it on. The free
tier caps monthly submissions (roughly 50), so watch the count if outreach
ramps up.

## Still to do

1. **Student photos are placeholders.** The four faces in "Students speak" and
   the hero are stand-ins until real student photos arrive. Names, quotes and
   alt text are correct and should stay with their current files.
2. **One photo placeholder remains** — the striped boxes in the "Who you'll
   actually talk to" section and the green form section. Drop real images in and
   replace the `<div class="ph">` blocks with `<img>` tags.
3. **Verify the eligibility sentence** in the hero against the program's actual
   rules. It currently reads: in foster care any time since your 13th birthday,
   and under 26.

## Design decisions worth not re-litigating

- **Colors** come from the Grossmont College brand guidelines: Grossmont Green
  `#00685E`, Grossmont Gold `#EA9610`. The mint `#D9E9E5` and sand `#EDE6DC` are
  carried over from the Carrd site. Near-black ink is `#0B0503`.
- **Font** is Montserrat, the college's primary recommended typeface. Loaded
  from Google Fonts.
- **The audience is named in the first screen on purpose.** The old page never
  said "foster youth" until roughly 85% of the way down, so a prospective
  student couldn't tell the program was for them.
- **The benefit checklist sits above the testimonials on purpose.** The benefits
  are the argument; the testimonials are corroboration. The old page had it the
  other way around, which only works for a visitor who already knows the
  program.
- **The checklist is ordered money-first.** The old order led with "do they have
  your major" and "housing within 21 miles" — the two most generic items.
- **The "Yes" tags** exist because every question is phrased about *another*
  college, so without them the reader has to mentally translate twelve times.
- **The form band is Grossmont Green** so that it reads as the destination.
  Everything else is white, mint, or sand.
- **Accessibility was a specific goal**, since it's part of the brand promise:
  one `<h1>`, one `<h2>` per section, the twelve questions are list items rather
  than headings, every form field has a real associated `<label>`, tap targets
  are 44px or larger, focus rings are visible, and there's a skip link. Please
  don't undo these — the old Carrd page failed most of them, and a California
  community college program is subject to public-entity accessibility rules.

## Design source

The working design lives alongside this as a Design Component file
(`NextUp Landing Page.dc.html`) in the Omelette project. `index.html` is the
deployable copy of it. If the design changes substantially, it's worth changing
both so they don't drift.
