# Architecture

How the todo frontend is built and released. The diagram is kept with the infrastructure code in `todo-app-infra`
and is embedded here so that both repositories show the same picture.

![Deployment architecture](https://media.githubusercontent.com/media/BinaryBaconLabs/todo-app-infra/main/docs/img/architecture-b6f85775eb5c.png)

If the diagram does not load, you are not signed in to an account that can read `todo-app-infra`. Ask in
#frontend-deploys for access.

## Components

| Component | Where it runs | Notes |
|---|---|---|
| Todo frontend (this repository) | Static hosting behind the CDN | Built by `CI Build`, released by `Post Build Deploy` |
| Internal npm registry | Build network | Serves the `@acme-internal` scope, see `docs/DEPLOY.md` |
| Preview image registry | Build network | Credentials in `deploy/docker-config.json` |
| Release automation | GitHub Actions | Signs in as the `bbl-release-bot` GitHub App |

## Environments

- `staging`: deployed on every successful `CI Build` on `main`.
- `production`: deployed from a `vX.Y.Z` tag. Runtime settings are in `.env.production`.
