# Profile setup

## Publish the profile

1. Sign in as **huseyingocek** and create a **public** repository named **huseyingocek**. GitHub displays its root `README.md` on your profile.
2. Copy `README.md`, the complete `assets/` folder, and `.github/workflows/snake.yml` into that repository. Preserve the folder structure. When using the website, create the workflow through **Add file → Create new file**, entering `.github/workflows/snake.yml` as its name; hidden folders can be missed by upload tools.
3. Commit the files to your default branch. The README and local SVG images work immediately. `SETUP.md` is optional; do not upload the ZIP into the repository as a substitute for its contents.
4. Open **Actions → Generate contribution snake → Run workflow** and choose the default branch. The first successful run replaces the clearly labelled placeholder with your real contribution animation.
5. Reopen your profile at <https://github.com/huseyingocek>. GitHub image caching may delay the updated snake briefly.

## How the animation works

The workflow runs daily at **03:23 UTC / 06:23 Istanbul**, on manual request, and when the workflow itself changes. GitHub scheduled runs may be delayed. Schedules run from the default branch and may be disabled after 60 days of repository inactivity in public repositories; re-enable them in Actions if needed.

It uses the repository's automatic `GITHUB_TOKEN`; no personal token or external secret is required. The token is granted `contents: write` to save only the generated SVG through an explicit `git add`. The two actions are pinned to the commit IDs resolved from upstream `actions/checkout@v4` and `Platane/snk@v3` during preparation. Review upstream releases before changing these pins.

There is no output branch to create and no GitHub Pages dependency. Generated commits do not retrigger this workflow because its push filter only includes the workflow file.

If a run fails, the previous SVG stays available. Open its failed step in Actions:

- **Actions disabled:** enable Actions for the repository and allow the two referenced actions under your repository or organization policy.
- **Push denied:** confirm repository rules allow the Actions bot to update the default branch. Branch protection may require an approved pull request approach instead; do not disable protections merely for this image.
- **Push rejected after another commit:** rerun the workflow to start with a fresh checkout.
- **No visible activity:** the image reflects data returned by GitHub. It does not synthesize contributions or expose private repository names. An empty graph is valid.

## Content and verification

Checked on **16 October 2026** using the public GitHub profile and unauthenticated GitHub repositories API. Both showed no public repositories at the time of checking. The profile identifies Hüseyin Göçek, Istanbul, DevSecOps / Cloud Security, network automation, cybersecurity, Raspberry Pi, and Arduino; its LinkedIn link is used in the README.

AWS, Python automation, RiskCore, ThreatGraph, and CASY were supplied in the request. AWS and Python are presented as interests; the three project names have no guessed descriptions, maturity claims, or repository links. Their implementation details and visibility could not be independently verified. Update the project section when you have descriptions and links you are ready to publish.

The console is decorative, not a live security dashboard. There are no uptime claims, skill percentages, star counts, visitor counters, or external statistics widgets. All README images are local; only the scheduled snake generation depends on an external action and GitHub data.

## Customize

- Edit the text in `README.md`; keep important information as text for accessibility and mobile reading.
- Edit `assets/header.svg` to change the banner. Palette: midnight `#0b101b`, cyan `#45f3d0`, blue `#7cc9ff`, magenta `#eaa0f4`.
- Add public project links only after verifying that each URL is accessible while signed out.
- To remove the snake, remove section 04 from the README and delete the workflow. The static banner needs no automation.

## References

- Public profile: <https://github.com/huseyingocek>
- Public repository API: <https://api.github.com/users/huseyingocek/repos?per_page=100&type=owner>
- Profile README rules: <https://docs.github.com/en/account-and-profile/how-tos/profile-customization/managing-your-profile-readme>
- Snake action and color options: <https://github.com/Platane/snk>
- Scheduled workflow behavior: <https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#schedule>
