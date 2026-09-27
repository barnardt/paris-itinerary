# paris-itinerary

Eight days from one apartment in Bagneux. One serious visit each morning, lunch as the meal you book, home before the late-afternoon crash.

Single-file site: `index.html`. No build step.

## Preview locally

```sh
python3 -m http.server 8000
# open http://localhost:8000/
```

## Publish to GitHub Pages

Suggested repo name: `paris-itinerary`.

```sh
git init
git add index.html .nojekyll README.md
git commit -m "Paris itinerary: eight days from Bagneux"
gh repo create paris-itinerary --public --source=. --push
```

Then enable Pages:

1. GitHub repo → Settings → Pages
2. Source: Deploy from a branch (or GitHub Actions if you add the workflow below)
3. Branch: `main`, folder: `/ (root)`
4. URL will be `https://<you>.github.io/paris-itinerary/`

A static Actions workflow is included at `.github/workflows/pages.yml` if you prefer Actions-based deploys. With that file present, choose Source: GitHub Actions instead.

## Edit

Edit `index.html` directly. All styling is inline in `<style>`. Sections are `day1`…`day8`, plus `before`, `arrival`, `if-wrong`, `notes`.
