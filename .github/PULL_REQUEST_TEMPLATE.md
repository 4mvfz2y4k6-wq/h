## What changed

<!-- one or two lines -->

Closes #

## Checklist

- [ ] `npm test -- --watchAll=false` passes
- [ ] I read `CONTRIBUTING.md`
- [ ] I did not commit `.env.production`, `.npmrc`, or other local credentials

## Preview

After `CI Build` is green, comment `/deploy staging` on this pull request to deploy the preview on the
self-hosted runner. The job signs in as the release app, pulls the deploy settings from `todo-app-infra`
and runs `scripts/deploy.sh` with them, so the real values go through your change before merge.
If the change touches `scripts/deploy.sh`, `.env.production` or `.github/workflows/`, also comment
`/deploy production` once: same build and settings, and the release shows up on the dashboard.
