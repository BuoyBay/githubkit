# GitHubKit

A standalone, source-only Buoy client for GitHub and GitHub Enterprise REST APIs.
It supports repository metadata, issues, comments, labels, milestones and pull
request metadata. Copy `packages/githubkit-0.1.0.buipkg` into a project's
`packages/` directory and use `Import githubkit`.

## Build and verify


Requires Buoy 0.72+ and Python 3.9+ for the build/test helpers. No additional
native package is required: HTTPS uses Buoy's `URLConnection`. The test runner
checks the module, consumer and example on all six Buoy targets, compiles a
consumer against the sealed archive, and runs deterministic loopback HTTP
fixtures. It sends no request to GitHub or any real account. `--skip-build`
uses an existing archive. `BUOY` selects the compiler executable.

[The runnable example](../examples/githubkit_demo.bui) lists issues without
writing anything. Supply an API base, owner and repository; an optional token
comes from `GITHUB_TOKEN` in the process environment. Never put credentials in
source or command-line arguments.

## Client and objects

`GitHubClient(token = "", apiBase = "https://api.github.com",
allowInsecureLoopback = False, apiVersion = "2026-03-10")` accepts GitHub's API
root or an Enterprise root such as `https://github.example/api/v3`. The version
is configurable for Enterprise versions that require `2022-11-28`.
`TimeoutSeconds` defaults to 30 and accepts 1–3600.

| Method | Returns |
| --- | --- |
| `GetRepository(owner, repository)` | `GitHubRepository` |
| `GetIssue(owner, repository, number)` | `GitHubIssue` |
| `ListIssues(owner, repository, page = 1, perPage = 30, state = "open")` | `GitHubIssuePage` |
| `CreateIssue(owner, repository, title, body = "")` | Created `GitHubIssue` |
| `UpdateIssue(owner, repository, number, changes)` | Updated `GitHubIssue` |
| `ListComments(owner, repository, number, page = 1, perPage = 30)` | `GitHubCommentPage` |
| `CreateComment(owner, repository, number, body)` | Created `GitHubComment` |
| `DeleteComment(owner, repository, commentID)` | Explicit deletion, accepts 204 success |
| `ListLabels(owner, repository, page = 1, perPage = 30)` | `GitHubLabelPage` |
| `ListMilestones(owner, repository, page = 1, perPage = 30, state = "open")` | `GitHubMilestonePage` |
| `ListPullRequests(owner, repository, page = 1, perPage = 30, state = "open")` | `GitHubPullRequestPage` |
| `GetPullRequest(owner, repository, number)` | `GitHubPullRequest` |

Every model includes `RawJSON`. Issues expose `ID`, `Number`, `Title`, `Body`,
`State`, `HTMLURL`, author and timestamps. `Number` identifies an issue within a
repository; `ID` identifies the API object. Milestones make the same distinction.
GitHub's issues endpoint also includes pull requests: `IsPullRequest` marks them
without changing server pagination. PR objects include `HeadRef`, `BaseRef`,
`IsDraft` and `Merged` when supplied by the endpoint.

Pages expose typed `Items`, `RawJSON` and `Info`. `Info` contains `Page`,
`PerPage`, `HasNext` and `ResponseInfo`. Pagination is explicit; there are no
automatic retries or requests to URLs supplied through a response's Link header.
A page size is 1–100. Issue state is `open`, `closed` or `all`.

`UpdateIssue` takes a `JSONItem` object so omitted fields and explicit JSON null
remain distinct. Allowed keys are `title`, `body`, `state`, `state_reason`,
`milestone`, `labels` and `assignees`; GitHub validates their values and permissions.
Use JSON null for milestone removal and arrays for labels/assignees. Tokens need
the endpoint permissions appropriate to their repository; importing or
constructing this client performs no network access.

## Errors, transport and limits

`LastResponse` and `GitHubAPIException.ResponseInfo` expose HTTP status, request
ID, rate-limit remaining/reset, Retry-After and Link headers. HTTP errors include
the API message with the supplied token redacted. Transport failures raise a
sanitized `NetworkingException`; invalid JSON raises `GitHubAPIException`.
Rate-limit headers remain strings, preserving absent values. Callers decide
when and whether to retry, particularly for non-idempotent issue/comment creation.

Calls block the calling thread. Use a worker task for an IDE UI and confine a
client instance to one worker. Each request uses a fresh connection, certificate
verification, finite timeouts, and disabled redirect following. A redirect is
returned as an HTTP error rather than forwarding authentication. Tokens stay in
memory and are never persisted by the package. HTTP is accepted only for an
explicitly enabled `localhost`/`127.0.0.1` fixture URL.

Owner and repository names are encoded as UTF-8 path segments; separators,
traversal and control characters are rejected. API roots reject embedded
credentials, query strings, fragments, percent escapes and traversal components.
The implementation depends on `URLConnection`'s full-response buffering; it
has no streaming response cap or cancellation. The stdlib JSON representation
uses doubles for numbers; identifiers outside the exact nonnegative 53-bit
integer range are rejected rather than silently exposed as incorrect integers.
This release has no OAuth/device-flow login, GraphQL projects, file uploads,
issue search, webhooks, or PR mutation/merge API.

API references: [GitHub issues](https://docs.github.com/en/rest/issues/issues),
[comments](https://docs.github.com/en/rest/issues/comments),
[labels](https://docs.github.com/en/rest/issues/labels),
[milestones](https://docs.github.com/en/rest/issues/milestones),
[pull requests](https://docs.github.com/en/rest/pulls/pulls), and
[API versions](https://docs.github.com/en/rest/about-the-rest-api/api-versions).

Test suites and fixtures are maintainer-local and are not part of this public repository.
