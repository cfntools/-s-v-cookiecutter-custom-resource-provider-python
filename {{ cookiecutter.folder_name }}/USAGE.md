# Usage

This Custom Resource Provider follows https://github.com/cfntools/custom-resource-provider-spec and can be made available in your AWS account by buidling and deploying template.yaml

It is recommended to do this as a nested stack, so you can export the `ServiceToken` output.

## Syntax
```yaml
Type: AWS::CloudFormation::Stack
Properties:
  [See AWS Documentation]
  Parameters:
    LogLevel: String
    LogRetentionInDays: Integer
    PermissionsBoundary: String
    RoleName: String
    RolePath: String
    {%- if cookiecutter.include_optional_parameters == "y" %}
    DeleteAction: String
    UpdateReplaceAction: String
    {%- endif %}
    
```
## Properties
See https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-stack.html#aws-properties-stack-properties and https://github.com/cfntools/custom-resource-provider-spec

## Return Values
### Ref
See https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-stack.html#aws-properties-stack-return-values

## GetAtt

- `Outputs`: A map containing the outputs defined in https://github.com/cfntools/custom-resource-provider-spec

## Examples
### Minimal configuration
```yaml
{{ cookiecutter.resource_type }}:
  Type: AWS::CloudFormation::Stack
  Properties:
    TemplateURL: "https://s3.amazonaws.com/bucket-in-same-region/example_custom_resource/template-v1.0.yaml"
``` 

### Setting the LogLevel to DEBUG
```yaml
{{ cookiecutter.resource_type }}:
  Type: AWS::CloudFormation::Stack
  Properties:
    Parameters:
      LogLevel: DEBUG
``` 