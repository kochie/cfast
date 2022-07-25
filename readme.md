
**C**loud**F**ormation **A**bstract **S**yntax **T**ree format.

cfast is a specification for representing CloudFormation as an abstract syntax tree. It implements the unist spec.

This document may not be released. See releases for released documents. The latest released version is 0.0.0

## Nodes

### `TemplateRoot`
```idl
interface TemplateRoot <: Node {
  type: 'TemplateRoot'
  AWSTemplateFormatVersion: string
  Transform: string
  
  Description: string
  Metadata: 
  Parameters: [Parameter]
  Conditions: [Condition]
  Resources: [Resource]
}
```

### `Parameter`
```idl
interface Parameter <: Node {
  type: 'Parameter'
  parameterType: String | Number | List<Number> | CommaDelimitedList | AWSSpecificParameter | SsmParameter
  name: string
  description: string
  default: string
  allowedValues: [string]
  allowedPattern: string
  constraintDescription: string
  maxLength: number
  maxValue: number
  minLength: number
  minValue: number
  noEcho: boolean
}
```

### `Resource`
```idl
interface Resource <: Node {
  type: 'Resource'
  name: string
  resourceType: string
  properties: Properties
}
```

```idl
interface Properties <: Node {
  
}
```
