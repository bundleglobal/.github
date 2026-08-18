# Contributing

Thanks for helping improve bundle.social. This applies to every repository in the
[@bundleglobal](https://github.com/bundleglobal) organization unless a repo ships its own
`CONTRIBUTING.md`.

## Where does this belong?

The bundle.social API itself is closed source, so there is no repository to send an API
patch to. Almost everything else has a home:

| You want to | Go to |
| --- | --- |
| Report an SDK bug, or fix one | [bundlesocial-node](https://github.com/bundleglobal/bundlesocial-node) |
| Fix or add an example | [bundlesocial-examples](https://github.com/bundleglobal/bundlesocial-examples) |
| Fix a typo or a wrong snippet in the docs | [bundlesocial-docs](https://github.com/bundleglobal/bundlesocial-docs) |
| Report an API bug, or request an endpoint | [bundle.social/contact](https://bundle.social/contact) |
| Report a security issue | [SECURITY.md](https://github.com/bundleglobal/.github/blob/main/SECURITY.md), privately, never a public issue |
| Ask how to do something | [SUPPORT.md](https://github.com/bundleglobal/.github/blob/main/SUPPORT.md) |

## Before you open a pull request

Open an issue first for anything beyond a typo or a small fix. It is cheaper for both of
us to agree on the approach before you write the code.

Keep pull requests focused on one thing. A PR that fixes a bug and reformats 400 lines is
a PR we cannot review.

## Commit messages are load-bearing

We use [Conventional Commits](https://www.conventionalcommits.org). This is not a style
preference: `bundlesocial-node` releases through semantic-release on `main`, so the commit
type decides whether a release happens and which number it gets.

```
fix: retry uploads on 502 from the media endpoint     -> patch release
feat: add referenceKey to postCreate                  -> minor release
chore: bump eslint                                    -> no release
```

A breaking change needs `!` after the type, or a `BREAKING CHANGE:` footer, and it will cut
a major. Do not use one without discussing it in an issue first.

## Never hand-edit generated code

In `bundlesocial-node`, everything under `client/` is generated from the published OpenAPI
spec by `npm run generate`, which fetches
[`api.bundle.social/swagger-json`](https://api.bundle.social/swagger-json) and runs
`openapi-ts`. `client/services.gen.ts`, `client/types.gen.ts` and `openapi/` are all build
output. Edits there are overwritten on the next generation and will not be merged.

If the generated client is wrong, the spec is wrong. Say so in the issue and we will fix it
at the source, where it also fixes every other generated client.

Hand-written code lives in `src/`. That is where wrappers, the webhook helper and tests belong.

## Running the checks

Each repository documents its own setup in its README. For the SDK:

```bash
npm install
npm run generate   # refresh client/ from the live spec
npm run build
npm test
```

Please make sure the tests pass before you open the PR.

## Secrets

Never commit an API key, a team id from a real organization, or a webhook secret. Examples
should read them from the environment, and use `<TEAM_ID>` or `<UPLOAD_ID>` placeholders in
documentation snippets. Every id in the API is a UUID v4.

If you leak a key, rotate it from the **API Keys** section of your dashboard immediately.
Keys are org-level and reach every team in the organization.

## Licence

Contributions are accepted under the MIT licence carried by the repository you are
contributing to.
