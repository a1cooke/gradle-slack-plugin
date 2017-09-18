# gradle-slack-plugin
Slack plugin for Gradle

# Usage
This plugin supports whole message structure of current slack. You can find full docs here: https://api.slack.com/docs/messages

The below is an example usage

```
slack {
  webhookUrl 'https://hooks.slack.com/services/TXXXXXXXX/BX/xxxxxxxx'
  message {
    text = "Project is built newly and deployed into *${deployMode.toUpperCase()}*"
    channel = '#channel-name'
    attachment {
      authorName = gitUsername
      color = 'good'
      title = "Branch: ${gitBranchName}(${gitCommitHash})"
      titleLink = "https://github.com/link/i/want/to/redirect"
      field {
        title = 'Built'
        value = 'Success'
        shortValue = true
      }
      field {
        title = 'Deployed'
        value = 'Success'
        shortValue = true
      }
    }
  }
}
```
