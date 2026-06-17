# Slack

Project channel: [#noevil-noevilstar](https://no-evilworkspace.slack.com/archives/C0BB1AVHSS2)
Channel ID: `C0BB1AVHSS2`

Project hub: [#noevil-projects](https://no-evilworkspace.slack.com/archives/C0BBXM5MCQG)
Hub channel ID: `C0BBXM5MCQG`

## Use

Use the project channel for deployments, bug reports, incidents, release notes, operational follow-ups, and non-sensitive project context.

Local context: Portfolio/project showcase and sync workflow.

Do not post secrets, deployment tokens, private contact details, or .env values.

## Environment

These values are not secrets. They can be copied into local env files, CI variables, bot config, runbooks, or deployment notes when a project needs to reference its Slack channel.

```dotenv
# Slack project channel metadata (non-secret)
SLACK_CHANNEL_NAME=noevil-noevilstar
SLACK_CHANNEL_ID=C0BB1AVHSS2
SLACK_CHANNEL_URL=https://no-evilworkspace.slack.com/archives/C0BB1AVHSS2
SLACK_PROJECT_HUB_CHANNEL_NAME=noevil-projects
SLACK_PROJECT_HUB_CHANNEL_ID=C0BBXM5MCQG
SLACK_PROJECT_HUB_CHANNEL_URL=https://no-evilworkspace.slack.com/archives/C0BBXM5MCQG
```

## GitHub Actions Notifications

This repo has `.github/workflows/slack-notify.yml` for manual or reusable Slack posts.

GitHub repository variables are expected to contain the non-secret channel metadata:

- `SLACK_CHANNEL_NAME`
- `SLACK_CHANNEL_ID`
- `SLACK_CHANNEL_URL`
- `SLACK_PROJECT_HUB_CHANNEL_NAME`
- `SLACK_PROJECT_HUB_CHANNEL_ID`
- `SLACK_PROJECT_HUB_CHANNEL_URL`

`SLACK_BOT_TOKEN` is configured as a GitHub Actions secret for this repo. It belongs to the No Evil Project Notifier Slack app and can post to the documented project channels.

`SLACK_WEBHOOK_URL` remains supported by the workflow as a fallback for a channel-bound incoming webhook, but it is not needed for the current setup.

Manual test: run the **Slack Notify** workflow from the GitHub Actions tab.

Reusable workflow example:

```yaml
jobs:
  notify-slack:
    needs: [test]
    if: always()
    uses: ./.github/workflows/slack-notify.yml
    secrets: inherit
    with:
      status: ${{ needs.test.result }}
      summary: "CI completed for ${{ github.ref_name }}"
      details: "See the linked workflow run for logs."
```
