# Issue / Pull request body / title regex validator
This Action checks issue and pull-request descriptions against an regular expression. This can be used to check if the description met your Github template files.

## Usage
This Action subscribes to [Pull request events](https://developer.github.com/v3/activity/events/types/#pullrequestevent) and [Issues events](https://developer.github.com/v3/activity/events/types/#issuesevent) which will fire whenever Issues or Pull requests get created.

```workflow
name: Example workflow
on: [issues, pull_request]
jobs:
  example:
    name: Example job
    runs-on: ubuntu-latest
    steps:
    - name: Run the-real-mpgames/pr-regex-validator
      uses: the-real-mpgames/pr-regex-validator@v1
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        PULL_REQUEST_PATTERN: '#(\d+)'
        PULL_REQUEST_COMMENT: 'please specify trello card number in pr body'
```

## License
The Dockerfile and associated scripts and documentation in this project are released under the [GNU General Public License v3.0](LICENSE).
