# Artifact size per repo

## Context

In order to allow charge back (or just to monitor), we want to list the repo and their respective size


## Implementation

```bash
#!/bin/bash

# Get total size for artifacts in a GitHub Repo. To run, first create a GitHub token
# with the "repo" scope: Profile > Settings > Developer Settings > Personal access tokens
#
# Requires jq 1.6 or higher.

if [ $# -ne 1 ] || [ -z $API_TOKEN ]; then
  echo "Usage: API_TOKEN=<token> $0 <org/repo>"
  exit 1
fi

REPO_NAME=$1

ARTIFACTS_SIZE=$(curl --silent \
  -H "Authorization: token $API_TOKEN" \
  -H "Accept: application/vnd.github.v3+json" \
  "https://api.github.com/repos/$REPO_NAME/actions/artifacts" \
  | jq '[.artifacts[] | .size_in_bytes] | (add // 0) / (1024*1024) | round')

echo "Total size of artifacts in repo \"$REPO_NAME\": ${ARTIFACTS_SIZE}MB"
```