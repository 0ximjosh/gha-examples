# Github Action Examples

Some examples of GitHub Actions paired with Planetscale (and a bonus one for
vercel)

## db-deploy-request.yml

When a PR contains `db:[branch]` in the description the gha will open a deploy
request from the given branch to main.

## db-deploy-deploy-request.yml

When a PR is merged with `db:[branch]` in the description the gha will merge the
corresponding deploy request.

## preview-vercel.yml

Combines the power of planetscale branches and vercel preview deployments. When
a PR is opened and *optionally* contains `db:[branch]`, generate new connection
strings for the given branch, or `stage` if not provided. The connection string
is then passed to vercel-cli to deploy a new preview to vercel with the selected
or default db. If stage is behind main, then stage is re-deployed to be in sync
with main.
