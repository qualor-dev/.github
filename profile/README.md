# Qualor

**Quality gates for new code. No lines-of-code licence.**

Qualor is an open-source, self-hosted SonarQube alternative for GitLab and GitHub. It runs the
analyzers you already trust, tracks issues across commits and fails the merge request that makes
the code worse.

[Website](https://qualor.dev) · [Documentation](https://qualor.dev/docs) ·
[Live demo](https://review.qualor.dev)

## Start in one step

```yaml
- uses: actions/checkout@v4
  with:
    fetch-depth: 0
    persist-credentials: false
    ref: ${{ github.event.pull_request.head.sha || github.sha }}
- uses: qualor-dev/scan-action@v0.11
  with:
    server-url: ${{ vars.QUALOR_URL }}
    token: ${{ secrets.QUALOR_TOKEN }}
```

Run the server with Docker in a few minutes: [quick start](https://qualor.dev/docs/quick-start).

## What you get

- **Quality gates on new code** for every merge request and pull request, with comments and
  annotations on the changed lines.
- **Security analysis** with Qualor's own taint rules for JavaScript, TypeScript, Python, Java, Go
  and C#, plus secrets, vulnerable dependencies and licence policy.
- **Your AI agent fixes what Qualor finds**: connect Claude Code, Cursor or any MCP client with one
  URL.
- **Slack and Microsoft Teams** notifications and a weekly security digest.
- **Migrate from SonarQube** in one command.

## Repositories

| Repository | What it is |
| --- | --- |
| [qualor](https://github.com/qualor-dev/qualor) | The server, the scanner, the CLI and the web UI |
| [scan-action](https://github.com/qualor-dev/scan-action) | The GitHub Action |
| [gitlab.com/qualor/qualor](https://gitlab.com/qualor/qualor) | The GitLab CI/CD component |

Images on Docker Hub: [`qualor/server`](https://hub.docker.com/r/qualor/server),
[`qualor/scanner`](https://hub.docker.com/r/qualor/scanner),
[`qualor/scanner-dotnet`](https://hub.docker.com/r/qualor/scanner-dotnet).
