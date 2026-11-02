---
title: "GitHubKit getting started"
summary: "Install and use GitHubKit with explicit configuration and resource ownership."
category: "Guides"
order: 10
keywords: ["github", "enterprise", "issues", "rest", "pagination"]
related: ["index.md", "api.md", "typed-api.md"]
---

# GitHubKit getting started

Copy the githubkit archive into packages. The example reads one page of public issues and filters pull requests from display. Replace the illustrative repository before running. Obtain any required token from your credential provider or environment, rather than embedding it in source or command-line arguments.

```basic
Import githubkit

Sub Main()
    Dim client As New GitHubClient()
    client.TimeoutSeconds = 10
    Try
        Dim page As GitHubIssuePage = client.ListIssues("example", "project")
        For Each issue As GitHubIssue In page.Items
            If Not issue.IsPullRequest Then Print issue.Title
        Next
    Catch e As GitHubAPIException
        Print e.Message
    End Try
End Sub
```

## Explicit pagination

A list returns one page. Inspect page.Info.HasNext, increment page, and request again when the caller wants more. perPage accepts 1 through 100. Link headers are preserved as response metadata and never followed automatically.

The issues endpoint includes pull requests; IsPullRequest distinguishes them without changing pagination. Use Number for repository-local routes and ID for object identity. Milestones make the same distinction.

## Mutations

CreateIssue, UpdateIssue, CreateComment, and DeleteComment perform explicit writes. UpdateIssue sends only supplied allowed fields; omitted fields and explicit JSON null have different meanings. There are no retries, so a caller must decide whether a failed write can safely be repeated.

## Read next

- [Overview](index.md)
- [Getting started](getting-started.md)
- [API reference](api.md)
