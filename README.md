# Bump & Tag & Release Action

## Workflow steps

Composite action designed to help and simplify development of new GitHut Action pipelines in order to perform following steps:

**Configure GitHub Credentials** required to iteract with GitHub API
**Bump and Tag** use existing custom action which is doing version bump and cerate tag
**Build changelog** gathering information about previous commits and put them together
**Changelog publish** publish changelog to Release
**Post Slack message** post a message to Slack channel

## Future improvements

TBD

## How to use

### Example:

```yml
- name: Set repository name to variable PROJECT_SHORT_NAME
  run: |
    echo "PROJECT_SHORT_NAME=$(echo ${{ github.repository }} | cut -d '/' -f 2)" >> $GITHUB_ENV

- name: Bump & Tag & Release
  uses: propertylift/github.action.bump-tag-release@v0.3.0
  with:
    github_token: ${{ secrets.GITHUB_TOKEN }}
    project_name: ${{ env.PROJECT_SHORT_NAME }}
    slack_channel_id: ${{ secrets.SLACK_CHANNEL_NOTIFICATION }}
    slack_bot_token: ${{ secrets.SLACK_TOKEN }}
```

## Inputs

| Parameter Name | Required | Default | Description                                |
| -------------- | -------- | ------- | ------------------------------------------ |
| githubToken    | Yes      | ''      | The GitHub token to use for authentication |
| projectName    | Yes      | ''      | The name of the project                    |
| slackChannelId | Yes      | ''      | The Slack channel id to post to            |
| slackBotToken  | Yes      | ''      | The Slack bot token                        |
