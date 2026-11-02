# GymBuddy

A phone-first gym tracker. No build step and no backend, just static files.

- `plan.md`: your training plan (blocks → days → exercise tables). Edit it here, or paste a new version in the app under **Plan → Paste / edit plan**.
- `seed-history.json`: your weeks 1–5 from the old Excel. It's imported once, the first time the app opens. Delete it if you don't want it online.
- `index.html`: the whole app. Logs are saved on the device (localStorage). Use **Plan → Backup** now and then.

## Plan format

```markdown
## Block 1 — Build (weeks 1-6)
> Optional note shown at the top of every workout in this block.

### Day A
| # | Exercise | Sets | Reps | Rest | Start |
|---|----------|------|------|------|-------|
| 1 | Leg Press | 3 | 8-10 | 2-3 min | 12x 140kg |
```

Only the `Exercise` column is required. `## Rules` (a heading without weeks) and its bullet list show up in the Plan tab.
History follows the exercise **name**. If you rename an exercise, the new name starts a fresh history.

## Run locally

```bash
python -m http.server 8765
```

## Put it on your phone

Host the folder on any static host with HTTPS, for example GitHub Pages: push the folder to a repo, then Settings → Pages → deploy from `main`.
Open the URL on your phone, then **Add to Home Screen**. It runs full-screen and works offline in the gym.
