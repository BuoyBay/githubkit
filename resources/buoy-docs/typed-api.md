---
title: "githubkit typed API"
summary: "Source-derived public signatures, properties, parameters, defaults, and return values."
category: "Reference"
order: 21
types: ["GitHubAPIException", "GitHubClient", "GitHubComment", "GitHubCommentPage", "GitHubIssue", "GitHubIssuePage", "GitHubLabel", "GitHubLabelPage", "GitHubMilestone", "GitHubMilestonePage", "GitHubPageInfo", "GitHubPullRequest", "GitHubPullRequestPage", "GitHubRepository", "GitHubResponseInfo"]
dependencies: []
symbols: ["GitHubAPIException", "GitHubClient", "GitHubComment", "GitHubCommentPage", "GitHubIssue", "GitHubIssuePage", "GitHubLabel", "GitHubLabelPage", "GitHubMilestone", "GitHubMilestonePage", "GitHubPageInfo", "GitHubPullRequest", "GitHubPullRequestPage", "GitHubRepository", "GitHubResponseInfo"]
related: ["api.md", "getting-started.md", "index.md"]
---

# githubkit typed API

Generated from the package source declarations. Platform guards are shown where present; inherited members are documented on the base type. See the [API contracts](api.md) for behavior and limitations.

## GitHubResponseInfo

`Public Class GitHubResponseInfo`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `Status` | `Integer` | No | No | — | — |
| `RequestID` | `String` | No | No | — | — |
| `RateLimitRemaining` | `String` | No | No | — | — |
| `RateLimitReset` | `String` | No | No | — | — |
| `RetryAfter` | `String` | No | No | — | — |
| `Link` | `String` | No | No | — | — |

## GitHubAPIException

`Public Class GitHubAPIException Inherits Exception`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `ResponseInfo` | `GitHubResponseInfo` | No | No | — | — |

## GitHubPageInfo

`Public Class GitHubPageInfo`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `Page` | `Integer` | No | No | — | — |
| `PerPage` | `Integer` | No | No | — | — |
| `HasNext` | `Boolean` | No | No | — | — |
| `ResponseInfo` | `GitHubResponseInfo` | No | No | — | — |

## GitHubRepository

`Public Class GitHubRepository`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `RawJSON` | `JSONItem` | No | No | — | — |
| `ID` | `Integer` | No | No | — | — |
| `Name` | `String` | No | No | — | — |
| `FullName` | `String` | No | No | — | — |
| `HTMLURL` | `String` | No | No | — | — |
| `Description` | `String` | No | No | — | — |
| `DefaultBranch` | `String` | No | No | — | — |
| `IsPrivate` | `Boolean` | No | No | — | — |

## GitHubIssue

`Public Class GitHubIssue`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `RawJSON` | `JSONItem` | No | No | — | — |
| `ID` | `Integer` | No | No | — | — |
| `Number` | `Integer` | No | No | — | — |
| `Title` | `String` | No | No | — | — |
| `Body` | `String` | No | No | — | — |
| `State` | `String` | No | No | — | — |
| `HTMLURL` | `String` | No | No | — | — |
| `CreatedAt` | `String` | No | No | — | — |
| `UpdatedAt` | `String` | No | No | — | — |
| `Author` | `String` | No | No | — | — |
| `IsPullRequest` | `Boolean` | No | No | — | — |

## GitHubIssuePage

`Public Class GitHubIssuePage`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `Items` | `Array Of GitHubIssue` | No | No | — | — |
| `Info` | `GitHubPageInfo` | No | No | — | — |
| `RawJSON` | `JSONItem` | No | No | — | — |

## GitHubComment

`Public Class GitHubComment`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `RawJSON` | `JSONItem` | No | No | — | — |
| `ID` | `Integer` | No | No | — | — |
| `Body` | `String` | No | No | — | — |
| `HTMLURL` | `String` | No | No | — | — |
| `CreatedAt` | `String` | No | No | — | — |
| `UpdatedAt` | `String` | No | No | — | — |
| `Author` | `String` | No | No | — | — |

## GitHubCommentPage

`Public Class GitHubCommentPage`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `Items` | `Array Of GitHubComment` | No | No | — | — |
| `Info` | `GitHubPageInfo` | No | No | — | — |
| `RawJSON` | `JSONItem` | No | No | — | — |

## GitHubLabel

`Public Class GitHubLabel`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `RawJSON` | `JSONItem` | No | No | — | — |
| `ID` | `Integer` | No | No | — | — |
| `Name` | `String` | No | No | — | — |
| `Color` | `String` | No | No | — | — |
| `Description` | `String` | No | No | — | — |

## GitHubLabelPage

`Public Class GitHubLabelPage`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `Items` | `Array Of GitHubLabel` | No | No | — | — |
| `Info` | `GitHubPageInfo` | No | No | — | — |
| `RawJSON` | `JSONItem` | No | No | — | — |

## GitHubMilestone

`Public Class GitHubMilestone`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `RawJSON` | `JSONItem` | No | No | — | — |
| `ID` | `Integer` | No | No | — | — |
| `Number` | `Integer` | No | No | — | — |
| `Title` | `String` | No | No | — | — |
| `State` | `String` | No | No | — | — |
| `Description` | `String` | No | No | — | — |
| `DueOn` | `String` | No | No | — | — |

## GitHubMilestonePage

`Public Class GitHubMilestonePage`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `Items` | `Array Of GitHubMilestone` | No | No | — | — |
| `Info` | `GitHubPageInfo` | No | No | — | — |
| `RawJSON` | `JSONItem` | No | No | — | — |

## GitHubPullRequest

`Public Class GitHubPullRequest`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `RawJSON` | `JSONItem` | No | No | — | — |
| `ID` | `Integer` | No | No | — | — |
| `Number` | `Integer` | No | No | — | — |
| `Title` | `String` | No | No | — | — |
| `Body` | `String` | No | No | — | — |
| `State` | `String` | No | No | — | — |
| `HTMLURL` | `String` | No | No | — | — |
| `IsDraft` | `Boolean` | No | No | — | — |
| `Merged` | `Boolean` | No | No | — | — |
| `Author` | `String` | No | No | — | — |
| `HeadRef` | `String` | No | No | — | — |
| `BaseRef` | `String` | No | No | — | — |

## GitHubPullRequestPage

`Public Class GitHubPullRequestPage`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `Items` | `Array Of GitHubPullRequest` | No | No | — | — |
| `Info` | `GitHubPageInfo` | No | No | — | — |
| `RawJSON` | `JSONItem` | No | No | — | — |

## GitHubClient

`Public Class GitHubClient`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `LastResponse` | `GitHubResponseInfo` | No | No | — | — |
| `TimeoutSeconds` | `Integer` | No | No | — | — |

### Constructor

`Public Sub Constructor(token As String = "", apiBase As String = "https://api.github.com", allowInsecureLoopback As Boolean = False, apiVersion As String = "2026-03-10")`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `token` | `String` | `ByVal` | `""` |
| `apiBase` | `String` | `ByVal` | `"https://api.github.com"` |
| `allowInsecureLoopback` | `Boolean` | `ByVal` | `False` |
| `apiVersion` | `String` | `ByVal` | `"2026-03-10"` |

Returns: no value.

### GetRepository

`Public Function GetRepository(owner As String, repository As String) As GitHubRepository`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `owner` | `String` | `ByVal` | Required |
| `repository` | `String` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `GitHubRepository` |

### GetIssue

`Public Function GetIssue(owner As String, repository As String, number As Integer) As GitHubIssue`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `owner` | `String` | `ByVal` | Required |
| `repository` | `String` | `ByVal` | Required |
| `number` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `GitHubIssue` |

### ListIssues

`Public Function ListIssues(owner As String, repository As String, page As Integer = 1, perPage As Integer = 30, state As String = "open") As GitHubIssuePage`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `owner` | `String` | `ByVal` | Required |
| `repository` | `String` | `ByVal` | Required |
| `page` | `Integer` | `ByVal` | `1` |
| `perPage` | `Integer` | `ByVal` | `30` |
| `state` | `String` | `ByVal` | `"open"` |

#### Returns

| Type |
| --- |
| `GitHubIssuePage` |

### CreateIssue

`Public Function CreateIssue(owner As String, repository As String, title As String, body As String = "") As GitHubIssue`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `owner` | `String` | `ByVal` | Required |
| `repository` | `String` | `ByVal` | Required |
| `title` | `String` | `ByVal` | Required |
| `body` | `String` | `ByVal` | `""` |

#### Returns

| Type |
| --- |
| `GitHubIssue` |

### UpdateIssue

`Public Function UpdateIssue(owner As String, repository As String, number As Integer, changes As JSONItem) As GitHubIssue`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `owner` | `String` | `ByVal` | Required |
| `repository` | `String` | `ByVal` | Required |
| `number` | `Integer` | `ByVal` | Required |
| `changes` | `JSONItem` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `GitHubIssue` |

### ListComments

`Public Function ListComments(owner As String, repository As String, number As Integer, page As Integer = 1, perPage As Integer = 30) As GitHubCommentPage`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `owner` | `String` | `ByVal` | Required |
| `repository` | `String` | `ByVal` | Required |
| `number` | `Integer` | `ByVal` | Required |
| `page` | `Integer` | `ByVal` | `1` |
| `perPage` | `Integer` | `ByVal` | `30` |

#### Returns

| Type |
| --- |
| `GitHubCommentPage` |

### CreateComment

`Public Function CreateComment(owner As String, repository As String, number As Integer, body As String) As GitHubComment`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `owner` | `String` | `ByVal` | Required |
| `repository` | `String` | `ByVal` | Required |
| `number` | `Integer` | `ByVal` | Required |
| `body` | `String` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `GitHubComment` |

### DeleteComment

`Public Sub DeleteComment(owner As String, repository As String, commentID As Integer)`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `owner` | `String` | `ByVal` | Required |
| `repository` | `String` | `ByVal` | Required |
| `commentID` | `Integer` | `ByVal` | Required |

Returns: no value.

### ListLabels

`Public Function ListLabels(owner As String, repository As String, page As Integer = 1, perPage As Integer = 30) As GitHubLabelPage`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `owner` | `String` | `ByVal` | Required |
| `repository` | `String` | `ByVal` | Required |
| `page` | `Integer` | `ByVal` | `1` |
| `perPage` | `Integer` | `ByVal` | `30` |

#### Returns

| Type |
| --- |
| `GitHubLabelPage` |

### ListMilestones

`Public Function ListMilestones(owner As String, repository As String, page As Integer = 1, perPage As Integer = 30, state As String = "open") As GitHubMilestonePage`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `owner` | `String` | `ByVal` | Required |
| `repository` | `String` | `ByVal` | Required |
| `page` | `Integer` | `ByVal` | `1` |
| `perPage` | `Integer` | `ByVal` | `30` |
| `state` | `String` | `ByVal` | `"open"` |

#### Returns

| Type |
| --- |
| `GitHubMilestonePage` |

### ListPullRequests

`Public Function ListPullRequests(owner As String, repository As String, page As Integer = 1, perPage As Integer = 30, state As String = "open") As GitHubPullRequestPage`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `owner` | `String` | `ByVal` | Required |
| `repository` | `String` | `ByVal` | Required |
| `page` | `Integer` | `ByVal` | `1` |
| `perPage` | `Integer` | `ByVal` | `30` |
| `state` | `String` | `ByVal` | `"open"` |

#### Returns

| Type |
| --- |
| `GitHubPullRequestPage` |

### GetPullRequest

`Public Function GetPullRequest(owner As String, repository As String, number As Integer) As GitHubPullRequest`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `owner` | `String` | `ByVal` | Required |
| `repository` | `String` | `ByVal` | Required |
| `number` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `GitHubPullRequest` |
