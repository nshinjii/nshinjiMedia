# Nshinji Media

Creator and website-design portfolio published at https://nshinjimedia.co.uk/.

## Website

`index.html` contains the complete website, styles, and JavaScript. Navigation uses hash links. Videos and Shorts use the public uploads for YouTube channel `UCIa-bzHuoaBa6HxGaRTyA7g`. Website enquiries use Discord `e9vg`.

## Publishing and automatic updates

GitHub Pages uses the `.github/workflows/youtube.yml` workflow. It runs on pushes to `main`, manually through Actions, and on an hourly schedule (GitHub may delay scheduled runs).

The workflow fetches the latest YouTube RSS entries, merges them with the previous published archive, and publishes `content.json` alongside the website. The browser checks for updates every five minutes while visible. Existing uploads are kept when YouTube is unavailable; views only update where the feed provides them.

To update the design, edit `index.html`, commit to `main`, and confirm the latest **Update YouTube Videos** run succeeds. Keep the `let uploads=[...],videoFilter=` seed declaration intact: the workflow reads it as its initial archive.

`CNAME` stores the custom domain. Preserve it when publishing. No secrets or API keys are needed for the public feed.
