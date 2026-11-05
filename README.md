# Taskrabbit Tasker quiz: moving categories

A recruiting version of the moving calculator. It asks up to six questions about a person's vehicle, gear, and the work they enjoy, then recommends moving-related categories to sign up for. New Taskers get a Become a Tasker button; existing Taskers get steps for adding categories in the Tasker app and a Copy Category List button.

## Files

- `index.html`: the quiz. Host this in a `taskers` folder in the existing repo.
- `embed-snippet.html`: the code to paste into a blog post or landing page.

## Hosting on the existing GitHub repo

1. Open the `taskrabbit-moving` repo and click **Add file → Upload files**.
2. Drag in the whole `taskers` folder from the zip (it contains `index.html`). GitHub keeps the folder structure.
3. Commit. A minute or two later the quiz is live at `https://trseo.github.io/taskrabbit-moving/taskers/`.

The client calculator at `https://trseo.github.io/taskrabbit-moving/` is untouched.

## Before launch: check these

1. **Sign-up URLs.** `signupUrl` for each market in `CONFIG.markets`. The US and UK Become a Tasker URLs are best guesses; confirm them.
2. **Perks copy.** "Set your own rates and keep 100% of them, plus tips" matches current Tasker messaging, but confirm it holds in every market you embed in, and check with legal before launch.
3. **Category names and availability** by market, including Truck-Assisted Help Moving vs Man with a Van.
4. **App navigation.** The existing-Tasker steps say Performance tab, then Skills & Rates. Confirm that's current in each market's Tasker app.

## Brand and legal guardrails built into the copy

The copy follows the Brand Guidelines' legal guidance: it never says hire, apply, applicant, vetted, professional, licensed, or "our Taskers"; it never says a vehicle or tool is required; it makes no earnings or outcome promises; and it uses "sign up" and "background check" for registration. Keep to these when editing.

## How matching works

Each answer adds points to categories (`score` on each option; negative numbers push a category down, e.g. "I'd rather skip heavy lifting"). Categories with 4+ points are shown, highest first: one top pick plus up to five more. Each shows "Why it fits", built from the `tag` on the answers that contributed.

## Analytics

Events go to `window.dataLayer` with the `tasker_quiz_` prefix: `start`, `step_view`, `complete` (with tasker status, top pick, all categories, answers), `signup_click`, `copy_list`, `restart`. Sign-up links carry `utm_campaign=tasker_moving_quiz` and `utm_content=top_<category>` or `bottom_<category>`.
