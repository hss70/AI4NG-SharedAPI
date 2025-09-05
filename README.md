# AI4NG Shared API Gateway

Shared API Gateway for all AI4NG services. Deploy this first before other services.

## Deployment

**Method**: AWS CodePipeline (see [CODEPIPELINE.md](CODEPIPELINE.md))

## Exports

This stack exports:
- `SharedApiId-dev/prod` - API Gateway ID
- `SharedApiAuthorizerId-dev/prod` - Cognito Authorizer ID

## Usage in Other Services

Import in your CloudFormation templates:
```yaml
Parameters:
  SharedApiId:
    Type: String
    Default: !ImportValue SharedApiId-dev
```

## Environments

- **Dev**: `AI4NG-dev` API Gateway
- **Prod**: `AI4NG-prod` API Gateway