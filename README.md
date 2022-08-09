## Photobot Infrastructure

CloudFormation resource definitions.

### Prerequisites

A secret in secrets manager named `github_pat` of this format:

```
{
    "token": <a github access token with repo and repo_hook access>
}
```

