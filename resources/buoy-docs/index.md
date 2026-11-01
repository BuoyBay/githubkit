---
title: "GitHubKit"
summary: "Read and update GitHub and Enterprise repository tickets with typed REST models."
category: "Overview"
order: 0
keywords: ["github", "enterprise", "issues", "rest", "pagination"]
related: ["getting-started.md", "api.md", "typed-api.md"]
---

# GitHubKit

GitHubKit is a source-only REST client for GitHub and GitHub Enterprise. It covers repositories, issues, comments, labels, milestones, and pull-request metadata using Buoy URLConnection. Models retain RawJSON as well as typed fields.

## Credentials and execution

Constructing a client makes no network request. Tokens remain in memory, and applications supply their own credential storage. Calls are synchronous; use one client on one worker for GUI operations. TLS verification and finite timeouts remain enabled, and redirects fail instead of forwarding credentials.

The API root defaults to the public service. Enterprise installations can specify an api/v3 root and a compatible API version. The current constructor default is 2026-03-10; select the version your Enterprise deployment supports.

## Scope

No OAuth/device flow, GraphQL projects, upload, issue search, webhook, or PR mutation/merge API is exposed. Responses are fully buffered without a streaming cap or cancellation. The wrapper rejects IDs outside the exact nonnegative 53-bit JSON integer range.

## Read next

- [Overview](index.md)
- [Getting started](getting-started.md)
- [API reference](api.md)
