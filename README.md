# Lingopie — The Quiz (Conversion Flow)

A high-intent quiz landing page built in partnership with **European Listings**.

Five quick questions where every answer reflects back a personalised hook. By the
final question the visitor has described their ideal product — and it's Lingopie.
The flow assembles a custom plan and rolls straight into checkout.

## Stack

Single self-contained `index.html` — HTML, CSS, and vanilla JS with **zero build
step** and no dependencies. The only external asset is the Lingopie logo in `assets/`.

## Flow

1. **Hook** — headline + promise + Start
2. **Q1 Language** — Spanish / French / Italian / German / Korean (also the `?lang=` deep-link entry)
3. **Q2 Streaming habit** — anchors Lingopie to a habit they already have
4. **Q3 Episodes / week** — drives the dynamic word-count projection
5. **Q4 Past blocker** — surfaces the objection so we can dissolve it
6. **Q5 Goal + urgency** — sets the timeline that primes checkout
7. **Building** — ~2s "Building your plan…" loader
8. **Personalised result** — plan assembled from all 5 answers
9. **Checkout** — 3 plans, Yearly highlighted

Each answer shows a reflected-back hook with a **Next** button (no auto-advance).

## Configuration

Constants at the top of the `<script>` in `index.html`:

- `CHECKOUT_URL` — destination for all "Try for free" buttons
- `LOGIN_URL` — "Log in" link on the result screen
- `LANGUAGES` — per-language recommended show + Q1 hook
- `QUESTIONS` — questions, answer options, hooks, and word-projection values

Entry deep-link: `?lang=es` (or `fr` / `it` / `de` / `ko`) pre-selects the language
and starts at Q2.

### To confirm before launch

- `WORDS_PER_EPISODE` — Q3 projections (~600 / ~1,800 / ~3,600 per month) are the
  brief's placeholder figures; replace with the real number.
- Korean recommended show is set to **Squid Game** (placeholder).
- European Listings logo is a script-font recreation; swap in the official asset when available.

## Local preview

```bash
python3 -m http.server 8080
# → http://localhost:8080
```

## Deployment

Static site — Vercel serves `index.html` at the root with no build configuration.
