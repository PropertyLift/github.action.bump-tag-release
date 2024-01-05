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
- name: Bump & Tag & Release
  uses: bricklanetech/github.action.bump-tag-release@v0.4.3
  with:
    githubToken: ${{ secrets.GITHUB_TOKEN }}
    slackChannelId: ${{ secrets.SLACK_CHANNEL_NOTIFICATION }}
    slackBotToken: ${{ secrets.SLACK_TOKEN }}
```

## Inputs

| Parameter Name | Required | Default | Description                                |
| -------------- | -------- | ------- | ------------------------------------------ |
| githubToken    | Yes      | ''      | The GitHub token to use for authentication |
| slackChannelId | Yes      | ''      | The Slack channel id to post to            |
| slackBotToken  | Yes      | ''      | The Slack bot token                        |
