# OzReady Content

This repo hosts the live content and website for the **OzReady** app.

## Structure

```
data/
  questions.json        ← quiz questions (app fetches this on launch)
  chapters.json         ← chapter content
  content_version.json  ← version manifest (bump this to trigger an update)
docs/
  index.html            ← GitHub Pages landing page
  privacy.html          ← Privacy Policy
  terms.html            ← Terms of Use
```

## How to update questions (no app update needed)

1. Edit `data/questions.json` — add, edit, or fix questions
2. Open `data/content_version.json` and increment `"version"` by 1
3. Update `"questions_count"` and `"updated_at"` 
4. Commit and push to `main`

```json
{
  "version": 2,
  "questions_count": 225,
  "updated_at": "2026-06-14"
}
```

On their **next app launch**, all users silently receive the updated questions. No app store update required.

## Question format

```json
{
  "id": 221,
  "chapter_id": 1,
  "text": "Question text here?",
  "options": ["Option A", "Option B", "Option C", "Option D"],
  "correct_index": 0,
  "explanation": "Why A is correct...",
  "difficulty": "easy",
  "is_values_question": false,
  "tags": ["tag1", "tag2"]
}
```

- `id` must be unique and never reused
- `correct_index` is 0-based (0 = first option)
- `is_values_question: true` for Australian Values questions (Chapter 4)

## GitHub Pages

The site is live at: `https://ssharmaa1.github.io/ozready-content/`

To enable: **Settings → Pages → Source → Deploy from branch → main → /docs**
