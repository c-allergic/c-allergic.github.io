# Xiaofeng Li — Personal Site

Personal academic website and CV, built with the [al-folio](https://github.com/alshedivat/al-folio) template (Jekyll).

## Pages

- **Home**: `_pages/about.md` — short bio
- **CV**: `_data/cv.yaml` (RenderCV format) → rendered to `assets/rendercv/rendercv_output/Xiaofeng_Li_CV.pdf` by the `render-cv.yml` workflow
- **Publications**: `_bibliography/papers.bib`

## Update the CV

Edit `_data/cv.yaml`, then render locally (requires Python + RenderCV):

```bash
cd _data
rendercv render cv.yaml --settings ../assets/rendercv/settings.yaml
```

or just push — the `render-cv.yml` GitHub Action re-renders the PDF automatically.

## Deploy

Push to `main`; the `deploy.yml` workflow builds the site and deploys it to GitHub Pages (gh-pages branch).
