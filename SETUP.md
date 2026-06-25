# Baby Tracker — Setup (Gift Copy A)

A private baby tracker (sleep, feeding, diapers, growth, notes) that syncs between
the parents' phones. It is a single `index.html` file — no app store, no accounts.

This copy is **pre-configured with its own private data path** and is ready to
personalize. The parents set the baby's name themselves on first open.

---

## 1. Personalize on first open (the parents do this)
1. Open the app (see "How to deploy" below for the link, or just open `index.html`).
2. Tap **⚙️ Settings** at the bottom.
3. Under **👶 Baby Profile**, enter the **baby's name** and **birthdate**, then it
   saves automatically. The header and app title update to the baby's name.
4. Optionally set language (EN / JP), default feed method, and reminders.

That's it — no name needs to be hard-coded. Whatever they type syncs to their
own private data store and shows on both parents' phones.

## 2. Add to Home Screen (makes it feel like a real app)
- **iPhone (Safari):** Share → *Add to Home Screen*.
- **Android (Chrome):** ⋮ menu → *Add to Home screen*.

## 3. Feeding: bottle, breastfeeding, or both
The feed screen has a **Method** selector:
- **Bottle** — volume in ml + type (formula / breast milk / mixed).
- **Breastfeed** — time on breast (minutes) + side (left / right / both).
- **Both** — logs breast time *and* a top-up bottle in one entry (hybrid feeds).

Trends/summaries adapt automatically: ml charts for bottle, a minutes chart for
breastfeeding, and both when the family does a mix.

---

## How to deploy (so both parents get a link)
Same approach as the original Niko tracker — host the file on **GitHub Pages**:
1. Create a new GitHub repo (e.g. `babyA-tracker`) and upload the contents of this
   folder (`index.html`, `serve.js`).
2. Repo → **Settings → Pages** → Source = `main` branch, root folder → Save.
3. After a minute it's live at `https://<your-username>.github.io/babyA-tracker/`.
4. Send that link to both parents; each adds it to their Home Screen.

> To preview locally first: `npx http-server . -p 8081 -c-1` then open
> `http://localhost:8081`.

---

## Privacy note (please read)
All families' data lives in **one shared Firebase database**, separated by a
secret path. This copy's path is unique (set in `index.html` near the top:
`SECRET_PATH = 'bba_...'`). Practically:
- No login is required — anyone with the link + path could read/write the data.
- **You (the gifter) are the technical custodian** of the underlying database.
- Fine for a private tracker between two parents; just know it isn't login-protected.

Do **not** change or share the `SECRET_PATH` — it's what keeps this baby's data
separate from the other families'.
