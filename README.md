# شجرۂ طیبہ سادات گیلانی — موضع داتا (مانسہرہ)

Online family tree of the Sadat Gilani of Datta, Mansehra (Hazara & Kashmir).
Live site: **https://syedmaaez.github.io/shajra-gilani-datta/** — the QR code on the printed poster points here.

- ترتیبِ اول (۲۰۰۶ء): سید شجاعت علی شاہ بن سید محمد افضل شاہ، ساکنہ داتا
- ڈیجیٹل ترتیب و نظرِ ثانی (۲۰۲۶ء): سید عدیس گیلانی ولدِ سید امداد علی شاہ، ساکنہ داتا

## Files

| File | What it is |
|---|---|
| `index.html` | The website (search, family page, lineage, tree explorer, relationship finder, add/correct form) |
| `data.json` | **All names and father→son links.** Edit this to add generations or fix names |
| `fonts/jameel-noori.woff2` | Jameel Noori Nastaleeq (loads after the page opens; Noto Nastaliq is shown until then) |
| `shajra-poster.pdf` | Print poster, 6 × 7 ft |
| `shajra-name-index.pdf` | A4 alphabetical name index with poster grid squares |

## Put it online (one time, ~5 minutes)

1. On GitHub create a **public** repository named exactly `shajra-gilani-datta` under the account `syedmaaez`.
2. Upload every file in this folder (keep the `fonts` folder).
3. Repository **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**.
4. After a minute the site is live at the address above. The QR code on the poster already points there.
5. Optional: open `index.html`, find `whatsapp: ''` near the bottom and put the maintainer's number in international format without `+` (e.g. `923001234567`). Then the WhatsApp button opens a chat with that number.

## How suggestions arrive

Anyone can press **اضافہ / اصلاح** on the site. It prepares a message with the person's ID and the new names, then:
- **GitHub پر بھیجیں** opens a new *Issue* in this repository (labels `addition` / `correction`). You get an email for each one.
- **WhatsApp پر بھیجیں** sends the same text by WhatsApp for relatives without a GitHub account.

Each suggestion includes a JSON block, e.g. `{"type":"add","target":"p477","names":["سید …"]}`.

## Adding a new generation by hand (editing `data.json`)

Every person looks like this:

```json
{ "id": "p477", "n": "امداد علی شاہ", "f": "p471", "c": ["p480","p484"], "g": 38, "s": 2 }
```

- `id` unique ID (never reuse or change an existing one) · `n` name · `f` father's ID · `c` sons' IDs (eldest first) · `g` generation counted from the Prophet ﷺ (father's `g` + 1) · `s` poster section.
- Optional: `note` short note under the name, `tag` e.g. `لاولد`, `chk: 1` marks a name whose spelling still needs checking (remove after confirming).

To add a son to `p484` (سید ماعز گیلانی):
1. Add a new entry at the end of `people`, with a new ID such as `p1001`, `"f": "p484"`, `"g": 40`, `"s": 2`, `"c": []`.
2. Add `"p1001"` to the `c` list of `p484`.
3. Change `meta.version` to today's date so visitors' browsers load the new data.
4. Commit. The site updates within a minute. (The printed poster does not change; ask for a new poster when there are enough additions.)

Use new IDs from `p1001` upward so they never clash with the IDs taken from the original chart.
