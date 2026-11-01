# Access GitHub and GitHub Enterprise repository APIs

A standalone, source-only Buoy client for GitHub and GitHub Enterprise REST APIs.
It supports repository metadata, issues, comments, labels, milestones and pull
request metadata. Copy `packages/githubkit-0.1.0.buipkg` into a project's
`packages/` directory and use `Import githubkit`.

## Install

From a Buoy consumer project with BPM installed:

```sh
bpm add githubkit --git https://github.com/BuoyBay/githubkit.git --rev refs/heads/main
```

BPM records the resolved commit in its lockfile. Keep that lockfile with the
consumer project for reproducible installs.

## Example

```buoy
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

## Build from source

With the native `build-packages` driver from [devtools](https://github.com/BuoyBay/devtools)
on your `PATH`, run from this checkout:

```sh
build-packages --root "$PWD" --compile-consumer githubkit
```

The driver checks source targets and compiles an import consumer. See the
[API guide](docs/API.md) for behavior, limits and any host prerequisites.

## Local Buoy setup

On your own machine, install Buoy and run:

```sh
buoy ai init --both
```

The generated agent files and editor settings stay local and are ignored by Git.

## Contributing

[Contributing](CONTRIBUTING.md) · [License](LICENSE)
