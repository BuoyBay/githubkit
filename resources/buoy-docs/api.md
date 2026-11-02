---
title: "GitHubKit API"
summary: "Public types, operations, error behavior, and limits for GitHubKit."
category: "Reference"
order: 20
keywords: ["github", "enterprise", "issues", "rest", "pagination"]
symbols: ["GitHubClient", "GitHubIssue", "GitHubIssuePage", "GitHubPageInfo", "GitHubResponseInfo", "GitHubAPIException", "GitHubClient.ListIssues", "GitHubClient.UpdateIssue"]
related: ["index.md", "getting-started.md", "typed-api.md"]
---

# GitHubKit API

| API | Contract |
| --- | --- |
| GitHubClient(token, apiBase, allowInsecureLoopback, apiVersion) | Optional credentials/root/version; HTTP only with explicit loopback opt-in. |
| TimeoutSeconds, LastResponse | Configurable 1–3600-second deadline and latest response metadata. |
| GetRepository, GetIssue, GetPullRequest | Typed repository, issue, or PR metadata. |
| ListIssues, ListComments, ListLabels, ListMilestones, ListPullRequests | Typed Items with Info and RawJSON; explicit page/perPage parameters. |
| CreateIssue, UpdateIssue, CreateComment, DeleteComment | Explicit mutations; deletion accepts 204 success. |
| GitHubRepository, GitHubIssue, GitHubComment, GitHubLabel, GitHubMilestone, GitHubPullRequest | Typed server snapshots plus RawJSON. |
| GitHubPageInfo | Page, PerPage, HasNext, ResponseInfo. |
| GitHubResponseInfo | Status, RequestID, RateLimitRemaining, RateLimitReset, RetryAfter, Link. |

## Errors and update fields

GitHubAPIException.ResponseInfo exposes HTTP/rate-limit metadata; malformed successful JSON also becomes an API exception. NetworkingException is sanitized for transport errors. The configured token is redacted from server error messages. Callers own rate-limit scheduling and retry decisions.

UpdateIssue allows title, body, state, state_reason, milestone, labels, and assignees. Use JSON null to remove a milestone and arrays for labels/assignees. Server permissions and field values remain subject to GitHub validation.

## Read next

- [Overview](index.md)
- [Getting started](getting-started.md)
- [API reference](api.md)

[Full typed API: properties, parameters, defaults, and returns](typed-api.md)
