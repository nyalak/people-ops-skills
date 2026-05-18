# peoplestudio.ai — site structure

Deployed on Vercel from this repo. Static HTML, no build step.

## File structure

```
index.html                                        ← homepage (skill cards)
consulting/index.html                             ← work with me
skills/
  work-experience-and-interview/index.html        ← Talent Acquisition skill page
  people-ops-coach/index.html                     ← Coaching skill page
  [new-skill]/index.html                          ← add future skills here
vercel.json                                       ← URL routing + redirects
```

## URLs

| Page | URL |
|---|---|
| Home | peoplestudio.ai |
| Work with me | peoplestudio.ai/consulting |
| Talent Acquisition skill | peoplestudio.ai/skills/work-experience-and-interview |
| People Ops Coach skill | peoplestudio.ai/skills/people-ops-coach |

Old URLs (`/skill`, `/skill.html`, `/framework`, `/framework.html`, `/consulting.html`) all redirect via `vercel.json`.

## Adding a new skill

1. Create `skills/[your-skill-slug]/index.html` — copy an existing skill page as your template
2. Update the slug, title, description, badge color, framework section, and use cases
3. Add a card to `index.html` in the `.skills-grid` section
4. Add a rewrite to `vercel.json` if needed (Vercel usually handles `index.html` automatically)
5. Drop the `SKILL.md` file in `skills/[your-skill-slug]/SKILL.md` so the download button works
6. Push — Vercel deploys automatically

## Download links

Each skill page links to its SKILL.md like:
```
/skills/[slug]/SKILL.md
```

Just place the file at that path in the repo and the download button works with no other changes.

## Skill page template

Copy `skills/people-ops-coach/index.html` as the base for new skills. Key things to change:
- `<title>` and `<meta name="description">`
- `.skill-badge` color class (`.badge-live`, `.badge-new`, or add your own)
- `h1` title and `.hero-sub` description
- Download link `href` pointing to the correct SKILL.md path
- Framework section content
- Use cases grid
- How-to-use step 3 prompt example
