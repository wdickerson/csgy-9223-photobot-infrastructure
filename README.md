## Photobot Infrastructure

CloudFormation resource definitions for the Photobot app, created in the final project of CS-GY 9223 at NYU.

### Standing up Photobot

First, place a secret in secrets manager named `github_pat` of this format:

```
{
    "token": <a github access token with repo and repo_hook access>
}
```

This allows CodePipeline to register a webhook with Github for the three repositories referenced in the CloudFormation template.

Then, create a CloudFormation stack from `template.yml`.

### Other notes

`swagger.yml` is included for reference, but all of the API definitions are included in the cloudformation template.

`template-subset.yml` is a subset of `template.yml` and it includes the OpenSearch domain and the Lex bot. These resources take the longest to create. You can create a stack with `template-subset.yml` and update it with `template.yml` if, for example, you want to show most of the CloudFormation events happen in real-time without waiting for OpenSearch or Lex.

Many things in the template are prefixed with `cfx`. This is so you can find-and-replace `cfx` with `cfy`, `cfz`, etc, and stand up two identical stacks.

