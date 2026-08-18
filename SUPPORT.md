# Support

GitHub issues in this organization are for bugs and feature requests in the open source
repositories: the SDK, the examples and the docs. They are not a support channel for the
hosted service, and they are not private.

## Account, billing and API problems

Use [bundle.social/contact](https://bundle.social/contact). That reaches the team that can
actually look at your organization, and it does not publish your account details to the
internet.

Bring the request id if you have one, the endpoint, and the timestamp. That turns a long
thread into one lookup.

## Check these first

| | |
| --- | --- |
| Is the API up? Is one platform degraded? | [status page](https://bundlesocial.betteruptime.com) and `GET /api/v1`, which returns live per-platform health |
| Why did my post fail on one platform? | [Platform limits](https://info.bundle.social/api-reference/limits) and the platform's own page under [Platforms](https://info.bundle.social/api-reference/platforms/index) |
| What does this error mean? | [Errors](https://info.bundle.social/api-reference/errors) |
| Am I being rate limited? | [Rate limits](https://info.bundle.social/api-reference/rate-limits) |
| What fields does this platform take? | [Platform parameters](https://info.bundle.social/api-reference/platform-parameters) |
| How do I connect an account? | [Connect social accounts](https://info.bundle.social/api-reference/connect-social-accounts) |
| Full docs | [info.bundle.social](https://info.bundle.social/welcome) |

Most "the API is broken" reports turn out to be a platform-specific rule listed on one of
those pages. The health endpoint is worth calling before you send users into a connect flow.

## Never post a key

Do not paste an API key into an issue, a discussion, or a pull request. If you already
have, rotate it from the **API Keys** section of your dashboard right away. Keys are
org-level and reach every team in the organization.

## Security issues

Report those privately. See [SECURITY.md](https://github.com/bundleglobal/.github/blob/main/SECURITY.md).
