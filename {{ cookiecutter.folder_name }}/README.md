# {{ cookiecutter.resource_type }}
{{ cookiecutter.resource_description }}
  
See USAGE.md to for how to deploy the Custom Resource provider. 

## Syntax
```yaml
Type: Custom::{{ cookiecutter.resource_type }}
Properties:
  ServiceToken: String
  SomeProperty: String
```

## Properties
- `ServiceToken`: see the [AWS Documentation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-cfn-customresource.html#cfn-customresource-servicetoken)
  - Required: Yes
  - Type: String
  - Update requires: Updates are not supported    
- `SomeProperty`: A  property of the Custom Resource
  - Required: No 
  - Type: Integer
  - Update requires: No interuption

## Return Values
### Ref
`Ref` returns the Physical Resource Id

### GetAtt

- `Arn`: The ARN of the resource.

## Examples
### A simple example
```yaml
My{{ cookiecutter.resource_type }}:
  Type: Custom::{{ cookiecutter.resource_type }}
  Properties:
    ServiceToken: arn:aws:lambda:eu-west-1:123456789012:function:ResourceProviderFunctionName
    SomeProperty: 42
```
