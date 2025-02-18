# README

@cloudcomponents/cdk-codepipeline-check-parameter-action

# @cloudcomponents/cdk-codepipeline-check-parameter-action

## Table of contents

### Classes

- [CheckParameterFunction](#check-parameter-function)
- [CodePipelineCheckEmailParameterAction](#code-pipeline-check-email-parameter-action)
- [CodePipelineCheckParameterAction](#code-pipeline-check-parameter-action)
- [CodePipelineCheckUrlParameterAction](#code-pipeline-check-url-parameter-action)

### Interfaces

- [CheckParamterFunctionProps](#check-paramter-function-props)
- [CodePipelineCheckEmailParameterActionProps](#code-pipeline-check-email-parameter-action-props)
- [CodePipelineCheckParameterActionProps](#code-pipeline-check-parameter-action-props)
- [CodePipelineCheckUrlParameterActionProps](#code-pipeline-check-url-parameter-action-props)
- [CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props)
- [RegExp](#reg-exp)

# Check Parameter Function

[@cloudcomponents/cdk-codepipeline-check-parameter-action](#readme) / CheckParameterFunction

# Class: CheckParameterFunction

## Hierarchy

- `Function`

  ↳ **`CheckParameterFunction`**

## Table of contents

### Constructors

- [constructor](#constructor)

### Properties

- [\_connections](#_connections)
- [\_invocationGrants](#_invocationgrants)
- [architecture](#architecture)
- [canCreatePermissions](#cancreatepermissions)
- [deadLetterQueue](#deadletterqueue)
- [env](#env)
- [functionArn](#functionarn)
- [functionName](#functionname)
- [grantPrincipal](#grantprincipal)
- [node](#node)
- [permissionsNode](#permissionsnode)
- [physicalName](#physicalname)
- [role](#role)
- [runtime](#runtime)
- [stack](#stack)
- [timeout](#timeout)
- [\_VER\_PROPS](#_ver_props)

### Accessors

- [connections](#connections)
- [currentVersion](#currentversion)
- [isBoundToVpc](#isboundtovpc)
- [latestVersion](#latestversion)
- [logGroup](#loggroup)

### Methods

- [\_checkEdgeCompatibility](#_checkedgecompatibility)
- [\_enableCrossEnvironment](#_enablecrossenvironment)
- [\_functionNode](#_functionnode)
- [\_isStackAccount](#_isstackaccount)
- [addEnvironment](#addenvironment)
- [addEventSource](#addeventsource)
- [addEventSourceMapping](#addeventsourcemapping)
- [addLayers](#addlayers)
- [addPermission](#addpermission)
- [addToRolePolicy](#addtorolepolicy)
- [addVersion](#addversion)
- [applyRemovalPolicy](#applyremovalpolicy)
- [configureAsyncInvoke](#configureasyncinvoke)
- [generatePhysicalName](#generatephysicalname)
- [getResourceArnAttribute](#getresourcearnattribute)
- [getResourceNameAttribute](#getresourcenameattribute)
- [grantInvoke](#grantinvoke)
- [metric](#metric)
- [metricDuration](#metricduration)
- [metricErrors](#metricerrors)
- [metricInvocations](#metricinvocations)
- [metricThrottles](#metricthrottles)
- [onPrepare](#onprepare)
- [onSynthesize](#onsynthesize)
- [onValidate](#onvalidate)
- [prepare](#prepare)
- [synthesize](#synthesize)
- [toString](#tostring)
- [validate](#validate)
- [classifyVersionProperty](#classifyversionproperty)
- [fromFunctionArn](#fromfunctionarn)
- [fromFunctionAttributes](#fromfunctionattributes)
- [isConstruct](#isconstruct)
- [isResource](#isresource)
- [metricAll](#metricall)
- [metricAllConcurrentExecutions](#metricallconcurrentexecutions)
- [metricAllDuration](#metricallduration)
- [metricAllErrors](#metricallerrors)
- [metricAllInvocations](#metricallinvocations)
- [metricAllThrottles](#metricallthrottles)
- [metricAllUnreservedConcurrentExecutions](#metricallunreservedconcurrentexecutions)

## Constructors

### constructor

• **new CheckParameterFunction**(`scope`, `id`, `props`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `scope` | `Construct` |
| `id` | `string` |
| `props` | [`CheckParamterFunctionProps`](#check-paramter-function-props) |

#### Overrides

Function.constructor

## Properties

### \_connections

• `Protected` `Optional` **\_connections**: `Connections`

Actual connections object for this Lambda

May be unset, in which case this Lambda is not configured use in a VPC.

**`internal`**

#### Inherited from

Function.\_connections

___

### \_invocationGrants

• `Protected` **\_invocationGrants**: `Record`<`string`, `Grant`\>

Mapping of invocation principals to grants. Used to de-dupe `grantInvoke()` calls.

**`internal`**

#### Inherited from

Function.\_invocationGrants

___

### architecture

• `Optional` `Readonly` **architecture**: `Architecture`

The architecture of this Lambda Function (this is an optional attribute and defaults to X86_64).

**`stability`** stable

#### Inherited from

Function.architecture

___

### canCreatePermissions

• `Protected` `Readonly` **canCreatePermissions**: ``true``

Whether the addPermission() call adds any permissions.

True for new Lambdas, false for version $LATEST and imported Lambdas
from different accounts.

**`stability`** stable

#### Inherited from

Function.canCreatePermissions

___

### deadLetterQueue

• `Optional` `Readonly` **deadLetterQueue**: `IQueue`

The DLQ associated with this Lambda Function (this is an optional attribute).

**`stability`** stable

#### Inherited from

Function.deadLetterQueue

___

### env

• `Readonly` **env**: `ResourceEnvironment`

The environment this resource belongs to.

For resources that are created and managed by the CDK
(generally, those created by creating new class instances like Role, Bucket, etc.),
this is always the same as the environment of the stack they belong to;
however, for imported resources
(those obtained from static methods like fromRoleArn, fromBucketName, etc.),
that might be different than the stack they were imported into.

**`stability`** stable

#### Inherited from

Function.env

___

### functionArn

• `Readonly` **functionArn**: `string`

ARN of this function.

**`stability`** stable

#### Inherited from

Function.functionArn

___

### functionName

• `Readonly` **functionName**: `string`

Name of this function.

**`stability`** stable

#### Inherited from

Function.functionName

___

### grantPrincipal

• `Readonly` **grantPrincipal**: `IPrincipal`

The principal this Lambda Function is running as.

**`stability`** stable

#### Inherited from

Function.grantPrincipal

___

### node

• `Readonly` **node**: `ConstructNode`

The construct tree node associated with this construct.

**`stability`** stable

#### Inherited from

Function.node

___

### permissionsNode

• `Readonly` **permissionsNode**: `ConstructNode`

The construct node where permissions are attached.

**`stability`** stable

#### Inherited from

Function.permissionsNode

___

### physicalName

• `Protected` `Readonly` **physicalName**: `string`

Returns a string-encoded token that resolves to the physical name that should be passed to the CloudFormation resource.

This value will resolve to one of the following:
- a concrete value (e.g. `"my-awesome-bucket"`)
- `undefined`, when a name should be generated by CloudFormation
- a concrete name generated automatically during synthesis, in
   cross-environment scenarios.

**`stability`** stable

#### Inherited from

Function.physicalName

___

### role

• `Optional` `Readonly` **role**: `IRole`

Execution role associated with this function.

**`stability`** stable

#### Inherited from

Function.role

___

### runtime

• `Readonly` **runtime**: `Runtime`

The runtime configured for this lambda.

**`stability`** stable

#### Inherited from

Function.runtime

___

### stack

• `Readonly` **stack**: `Stack`

The stack in which this resource is defined.

**`stability`** stable

#### Inherited from

Function.stack

___

### timeout

• `Optional` `Readonly` **timeout**: `Duration`

The timeout configured for this lambda.

**`stability`** stable

#### Inherited from

Function.timeout

___

### \_VER\_PROPS

▪ `Static` **\_VER\_PROPS**: `Object`

**`internal`**

#### Index signature

▪ [key: `string`]: `boolean`

#### Inherited from

Function.\_VER\_PROPS

## Accessors

### connections

• `get` **connections**(): `Connections`

Access the Connections object.

Will fail if not a VPC-enabled Lambda Function

**`stability`** stable

#### Returns

`Connections`

#### Inherited from

Function.connections

___

### currentVersion

• `get` **currentVersion**(): `Version`

Returns a `lambda.Version` which represents the current version of this Lambda function. A new version will be created every time the function's configuration changes.

You can specify options for this version using the `currentVersionOptions`
prop when initializing the `lambda.Function`.

**`stability`** stable

#### Returns

`Version`

#### Inherited from

Function.currentVersion

___

### isBoundToVpc

• `get` **isBoundToVpc**(): `boolean`

Whether or not this Lambda function was bound to a VPC.

If this is is `false`, trying to access the `connections` object will fail.

**`stability`** stable

#### Returns

`boolean`

#### Inherited from

Function.isBoundToVpc

___

### latestVersion

• `get` **latestVersion**(): `IVersion`

The `$LATEST` version of this function.

Note that this is reference to a non-specific AWS Lambda version, which
means the function this version refers to can return different results in
different invocations.

To obtain a reference to an explicit version which references the current
function configuration, use `lambdaFunction.currentVersion` instead.

**`stability`** stable

#### Returns

`IVersion`

#### Inherited from

Function.latestVersion

___

### logGroup

• `get` **logGroup**(): `ILogGroup`

The LogGroup where the Lambda function's logs are made available.

If either `logRetention` is set or this property is called, a CloudFormation custom resource is added to the stack that
pre-creates the log group as part of the stack deployment, if it already doesn't exist, and sets the correct log retention
period (never expire, by default).

Further, if the log group already exists and the `logRetention` is not set, the custom resource will reset the log retention
to never expire even if it was configured with a different value.

**`stability`** stable

#### Returns

`ILogGroup`

#### Inherited from

Function.logGroup

## Methods

### \_checkEdgeCompatibility

▸ **_checkEdgeCompatibility**(): `void`

**`internal`**

#### Returns

`void`

#### Inherited from

Function.\_checkEdgeCompatibility

___

### \_enableCrossEnvironment

▸ **_enableCrossEnvironment**(): `void`

Called when this resource is referenced across environments
(account/region) to order to request that a physical name will be generated
for this resource during synthesis, so the resource can be referenced
through it's absolute name/arn.

**`internal`**

#### Returns

`void`

#### Inherited from

Function.\_enableCrossEnvironment

___

### \_functionNode

▸ `Protected` **_functionNode**(): `ConstructNode`

Returns the construct tree node that corresponds to the lambda function.
For use internally for constructs, when the tree is set up in non-standard ways. Ex: SingletonFunction.

**`internal`**

#### Returns

`ConstructNode`

#### Inherited from

Function.\_functionNode

___

### \_isStackAccount

▸ `Protected` **_isStackAccount**(): `boolean`

Given the function arn, check if the account id matches this account

Function ARNs look like this:

  arn:aws:lambda:region:account-id:function:function-name

..which means that in order to extract the `account-id` component from the ARN, we can
split the ARN using ":" and select the component in index 4.

**`internal`**

#### Returns

`boolean`

true if account id of function matches the account specified on the stack, false otherwise.

#### Inherited from

Function.\_isStackAccount

___

### addEnvironment

▸ **addEnvironment**(`key`, `value`, `options?`): [`CheckParameterFunction`](#check-parameter-function)

Adds an environment variable to this Lambda function.

If this is a ref to a Lambda function, this operation results in a no-op.

**`stability`** stable

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `key` | `string` | The environment variable key. |
| `value` | `string` | The environment variable's value. |
| `options?` | `EnvironmentOptions` | Environment variable options. |

#### Returns

[`CheckParameterFunction`](#check-parameter-function)

#### Inherited from

Function.addEnvironment

___

### addEventSource

▸ **addEventSource**(`source`): `void`

Adds an event source to this function.

Event sources are implemented in the @aws-cdk/aws-lambda-event-sources module.

The following example adds an SQS Queue as an event source:
```
import { SqsEventSource } from '@aws-cdk/aws-lambda-event-sources';
myFunction.addEventSource(new SqsEventSource(myQueue));
```

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `source` | `IEventSource` |

#### Returns

`void`

#### Inherited from

Function.addEventSource

___

### addEventSourceMapping

▸ **addEventSourceMapping**(`id`, `options`): `EventSourceMapping`

Adds an event source that maps to this AWS Lambda function.

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `id` | `string` |
| `options` | `EventSourceMappingOptions` |

#### Returns

`EventSourceMapping`

#### Inherited from

Function.addEventSourceMapping

___

### addLayers

▸ **addLayers**(...`layers`): `void`

Adds one or more Lambda Layers to this Lambda function.

**`stability`** stable

**`throws`** if there are already 5 layers on this function, or the layer is incompatible with this function's runtime.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `...layers` | `ILayerVersion`[] | the layers to be added. |

#### Returns

`void`

#### Inherited from

Function.addLayers

___

### addPermission

▸ **addPermission**(`id`, `permission`): `void`

Adds a permission to the Lambda resource policy.

**`see`** Permission for details.

**`stability`** stable

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | The id for the permission construct. |
| `permission` | `Permission` | The permission to grant to this Lambda function. |

#### Returns

`void`

#### Inherited from

Function.addPermission

___

### addToRolePolicy

▸ **addToRolePolicy**(`statement`): `void`

Adds a statement to the IAM role assumed by the instance.

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `statement` | `PolicyStatement` |

#### Returns

`void`

#### Inherited from

Function.addToRolePolicy

___

### addVersion

▸ **addVersion**(`name`, `codeSha256?`, `description?`, `provisionedExecutions?`, `asyncInvokeConfig?`): `Version`

(deprecated) Add a new version for this Lambda.

If you want to deploy through CloudFormation and use aliases, you need to
add a new version (with a new name) to your Lambda every time you want to
deploy an update. An alias can then refer to the newly created Version.

All versions should have distinct names, and you should not delete versions
as long as your Alias needs to refer to them.

**`deprecated`** This method will create an AWS::Lambda::Version resource which
snapshots the AWS Lambda function *at the time of its creation* and it
won't get updated when the function changes. Instead, use
`this.currentVersion` to obtain a reference to a version resource that gets
automatically recreated when the function configuration (or code) changes.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `name` | `string` | A unique name for this version. |
| `codeSha256?` | `string` | The SHA-256 hash of the most recently deployed Lambda source code, or omit to skip validation. |
| `description?` | `string` | A description for this version. |
| `provisionedExecutions?` | `number` | A provisioned concurrency configuration for a function's version. |
| `asyncInvokeConfig?` | `EventInvokeConfigOptions` | configuration for this version when it is invoked asynchronously. |

#### Returns

`Version`

A new Version object.

#### Inherited from

Function.addVersion

___

### applyRemovalPolicy

▸ **applyRemovalPolicy**(`policy`): `void`

Apply the given removal policy to this resource.

The Removal Policy controls what happens to this resource when it stops
being managed by CloudFormation, either because you've removed it from the
CDK application or because you've made a change that requires the resource
to be replaced.

The resource can be deleted (`RemovalPolicy.DESTROY`), or left in your AWS
account for data recovery and cleanup later (`RemovalPolicy.RETAIN`).

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `policy` | `RemovalPolicy` |

#### Returns

`void`

#### Inherited from

Function.applyRemovalPolicy

___

### configureAsyncInvoke

▸ **configureAsyncInvoke**(`options`): `void`

Configures options for asynchronous invocation.

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `options` | `EventInvokeConfigOptions` |

#### Returns

`void`

#### Inherited from

Function.configureAsyncInvoke

___

### generatePhysicalName

▸ `Protected` **generatePhysicalName**(): `string`

**`stability`** stable

#### Returns

`string`

#### Inherited from

Function.generatePhysicalName

___

### getResourceArnAttribute

▸ `Protected` **getResourceArnAttribute**(`arnAttr`, `arnComponents`): `string`

Returns an environment-sensitive token that should be used for the resource's "ARN" attribute (e.g. `bucket.bucketArn`).

Normally, this token will resolve to `arnAttr`, but if the resource is
referenced across environments, `arnComponents` will be used to synthesize
a concrete ARN with the resource's physical name. Make sure to reference
`this.physicalName` in `arnComponents`.

**`stability`** stable

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `arnAttr` | `string` | The CFN attribute which resolves to the ARN of the resource. |
| `arnComponents` | `ArnComponents` | The format of the ARN of this resource. |

#### Returns

`string`

#### Inherited from

Function.getResourceArnAttribute

___

### getResourceNameAttribute

▸ `Protected` **getResourceNameAttribute**(`nameAttr`): `string`

Returns an environment-sensitive token that should be used for the resource's "name" attribute (e.g. `bucket.bucketName`).

Normally, this token will resolve to `nameAttr`, but if the resource is
referenced across environments, it will be resolved to `this.physicalName`,
which will be a concrete name.

**`stability`** stable

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `nameAttr` | `string` | The CFN attribute which resolves to the resource's name. |

#### Returns

`string`

#### Inherited from

Function.getResourceNameAttribute

___

### grantInvoke

▸ **grantInvoke**(`grantee`): `Grant`

Grant the given identity permissions to invoke this Lambda.

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `grantee` | `IGrantable` |

#### Returns

`Grant`

#### Inherited from

Function.grantInvoke

___

### metric

▸ **metric**(`metricName`, `props?`): `Metric`

Return the given named metric for this Function.

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `metricName` | `string` |
| `props?` | `MetricOptions` |

#### Returns

`Metric`

#### Inherited from

Function.metric

___

### metricDuration

▸ **metricDuration**(`props?`): `Metric`

How long execution of this Lambda takes.

Average over 5 minutes

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `props?` | `MetricOptions` |

#### Returns

`Metric`

#### Inherited from

Function.metricDuration

___

### metricErrors

▸ **metricErrors**(`props?`): `Metric`

How many invocations of this Lambda fail.

Sum over 5 minutes

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `props?` | `MetricOptions` |

#### Returns

`Metric`

#### Inherited from

Function.metricErrors

___

### metricInvocations

▸ **metricInvocations**(`props?`): `Metric`

How often this Lambda is invoked.

Sum over 5 minutes

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `props?` | `MetricOptions` |

#### Returns

`Metric`

#### Inherited from

Function.metricInvocations

___

### metricThrottles

▸ **metricThrottles**(`props?`): `Metric`

How often this Lambda is throttled.

Sum over 5 minutes

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `props?` | `MetricOptions` |

#### Returns

`Metric`

#### Inherited from

Function.metricThrottles

___

### onPrepare

▸ `Protected` **onPrepare**(): `void`

Perform final modifications before synthesis.

This method can be implemented by derived constructs in order to perform
final changes before synthesis. prepare() will be called after child
constructs have been prepared.

This is an advanced framework feature. Only use this if you
understand the implications.

**`stability`** stable

#### Returns

`void`

#### Inherited from

Function.onPrepare

___

### onSynthesize

▸ `Protected` **onSynthesize**(`session`): `void`

Allows this construct to emit artifacts into the cloud assembly during synthesis.

This method is usually implemented by framework-level constructs such as `Stack` and `Asset`
as they participate in synthesizing the cloud assembly.

**`stability`** stable

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `session` | `ISynthesisSession` | The synthesis session. |

#### Returns

`void`

#### Inherited from

Function.onSynthesize

___

### onValidate

▸ `Protected` **onValidate**(): `string`[]

Validate the current construct.

This method can be implemented by derived constructs in order to perform
validation logic. It is called on all constructs before synthesis.

**`stability`** stable

#### Returns

`string`[]

An array of validation error messages, or an empty array if the construct is valid.

#### Inherited from

Function.onValidate

___

### prepare

▸ `Protected` **prepare**(): `void`

Perform final modifications before synthesis.

This method can be implemented by derived constructs in order to perform
final changes before synthesis. prepare() will be called after child
constructs have been prepared.

This is an advanced framework feature. Only use this if you
understand the implications.

**`stability`** stable

#### Returns

`void`

#### Inherited from

Function.prepare

___

### synthesize

▸ `Protected` **synthesize**(`session`): `void`

Allows this construct to emit artifacts into the cloud assembly during synthesis.

This method is usually implemented by framework-level constructs such as `Stack` and `Asset`
as they participate in synthesizing the cloud assembly.

**`stability`** stable

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `session` | `ISynthesisSession` | The synthesis session. |

#### Returns

`void`

#### Inherited from

Function.synthesize

___

### toString

▸ **toString**(): `string`

Returns a string representation of this construct.

**`stability`** stable

#### Returns

`string`

#### Inherited from

Function.toString

___

### validate

▸ `Protected` **validate**(): `string`[]

Validate the current construct.

This method can be implemented by derived constructs in order to perform
validation logic. It is called on all constructs before synthesis.

**`stability`** stable

#### Returns

`string`[]

An array of validation error messages, or an empty array if the construct is valid.

#### Inherited from

Function.validate

___

### classifyVersionProperty

▸ `Static` **classifyVersionProperty**(`propertyName`, `locked`): `void`

Record whether specific properties in the `AWS::Lambda::Function` resource should also be associated to the Version resource.

See 'currentVersion' section in the module README for more details.

**`stability`** stable

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `propertyName` | `string` | The property to classify. |
| `locked` | `boolean` | whether the property should be associated to the version or not. |

#### Returns

`void`

#### Inherited from

Function.classifyVersionProperty

___

### fromFunctionArn

▸ `Static` **fromFunctionArn**(`scope`, `id`, `functionArn`): `IFunction`

Import a lambda function into the CDK using its ARN.

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `scope` | `Construct` |
| `id` | `string` |
| `functionArn` | `string` |

#### Returns

`IFunction`

#### Inherited from

Function.fromFunctionArn

___

### fromFunctionAttributes

▸ `Static` **fromFunctionAttributes**(`scope`, `id`, `attrs`): `IFunction`

Creates a Lambda function object which represents a function not defined within this stack.

**`stability`** stable

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `scope` | `Construct` | The parent construct. |
| `id` | `string` | The name of the lambda construct. |
| `attrs` | `FunctionAttributes` | the attributes of the function to import. |

#### Returns

`IFunction`

#### Inherited from

Function.fromFunctionAttributes

___

### isConstruct

▸ `Static` **isConstruct**(`x`): x is Construct

Return whether the given object is a Construct.

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `x` | `any` |

#### Returns

x is Construct

#### Inherited from

Function.isConstruct

___

### isResource

▸ `Static` **isResource**(`construct`): construct is CfnResource

Check whether the given construct is a Resource.

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `construct` | `IConstruct` |

#### Returns

construct is CfnResource

#### Inherited from

Function.isResource

___

### metricAll

▸ `Static` **metricAll**(`metricName`, `props?`): `Metric`

Return the given named metric for this Lambda.

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `metricName` | `string` |
| `props?` | `MetricOptions` |

#### Returns

`Metric`

#### Inherited from

Function.metricAll

___

### metricAllConcurrentExecutions

▸ `Static` **metricAllConcurrentExecutions**(`props?`): `Metric`

Metric for the number of concurrent executions across all Lambdas.

**`default`** max over 5 minutes

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `props?` | `MetricOptions` |

#### Returns

`Metric`

#### Inherited from

Function.metricAllConcurrentExecutions

___

### metricAllDuration

▸ `Static` **metricAllDuration**(`props?`): `Metric`

Metric for the Duration executing all Lambdas.

**`default`** average over 5 minutes

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `props?` | `MetricOptions` |

#### Returns

`Metric`

#### Inherited from

Function.metricAllDuration

___

### metricAllErrors

▸ `Static` **metricAllErrors**(`props?`): `Metric`

Metric for the number of Errors executing all Lambdas.

**`default`** sum over 5 minutes

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `props?` | `MetricOptions` |

#### Returns

`Metric`

#### Inherited from

Function.metricAllErrors

___

### metricAllInvocations

▸ `Static` **metricAllInvocations**(`props?`): `Metric`

Metric for the number of invocations of all Lambdas.

**`default`** sum over 5 minutes

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `props?` | `MetricOptions` |

#### Returns

`Metric`

#### Inherited from

Function.metricAllInvocations

___

### metricAllThrottles

▸ `Static` **metricAllThrottles**(`props?`): `Metric`

Metric for the number of throttled invocations of all Lambdas.

**`default`** sum over 5 minutes

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `props?` | `MetricOptions` |

#### Returns

`Metric`

#### Inherited from

Function.metricAllThrottles

___

### metricAllUnreservedConcurrentExecutions

▸ `Static` **metricAllUnreservedConcurrentExecutions**(`props?`): `Metric`

Metric for the number of unreserved concurrent executions across all Lambdas.

**`default`** max over 5 minutes

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `props?` | `MetricOptions` |

#### Returns

`Metric`

#### Inherited from

Function.metricAllUnreservedConcurrentExecutions

# Code Pipeline Check Email Parameter Action

[@cloudcomponents/cdk-codepipeline-check-parameter-action](#readme) / CodePipelineCheckEmailParameterAction

# Class: CodePipelineCheckEmailParameterAction

## Hierarchy

- [`CodePipelineCheckParameterAction`](#code-pipeline-check-parameter-action)

  ↳ **`CodePipelineCheckEmailParameterAction`**

## Table of contents

### Constructors

- [constructor](#constructor)

### Properties

- [providedActionProperties](#providedactionproperties)

### Accessors

- [\_pipeline](#_pipeline)
- [\_scope](#_scope)
- [\_stage](#_stage)
- [actionProperties](#actionproperties)

### Methods

- [bind](#bind)
- [bound](#bound)
- [onStateChange](#onstatechange)
- [variableExpression](#variableexpression)

## Constructors

### constructor

• **new CodePipelineCheckEmailParameterAction**(`props`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `props` | [`CodePipelineCheckEmailParameterActionProps`](#code-pipeline-check-email-parameter-action-props) |

#### Overrides

[CodePipelineCheckParameterAction](#code-pipeline-check-parameter-action).[constructor](#constructor)

## Properties

### providedActionProperties

• `Protected` `Readonly` **providedActionProperties**: `ActionProperties`

This is a renamed version of the {@link IAction.actionProperties} property.

**`stability`** stable

#### Inherited from

[CodePipelineCheckParameterAction](#code-pipeline-check-parameter-action).[providedActionProperties](#providedactionproperties)

## Accessors

### \_pipeline

• `Private` `get` **_pipeline**(): `any`

#### Returns

`any`

#### Inherited from

CodePipelineCheckParameterAction.\_pipeline

___

### \_scope

• `Private` `get` **_scope**(): `any`

Retrieves the Construct scope of this Action.
Only available after the Action has been added to a Stage,
and that Stage to a Pipeline.

#### Returns

`any`

#### Inherited from

CodePipelineCheckParameterAction.\_scope

___

### \_stage

• `Private` `get` **_stage**(): `any`

#### Returns

`any`

#### Inherited from

CodePipelineCheckParameterAction.\_stage

___

### actionProperties

• `get` **actionProperties**(): `ActionProperties`

The simple properties of the Action, like its Owner, name, etc.

Note that this accessor will be called before the [bind](#bind) callback.

**`stability`** stable

#### Returns

`ActionProperties`

#### Inherited from

CodePipelineCheckParameterAction.actionProperties

## Methods

### bind

▸ **bind**(`scope`, `stage`, `options`): `ActionConfig`

The callback invoked when this Action is added to a Pipeline.

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `scope` | `Construct` |
| `stage` | `IStage` |
| `options` | `ActionBindOptions` |

#### Returns

`ActionConfig`

#### Inherited from

[CodePipelineCheckParameterAction](#code-pipeline-check-parameter-action).[bind](#bind)

___

### bound

▸ `Protected` **bound**(`scope`, `_stage`, `options`): `ActionConfig`

#### Parameters

| Name | Type |
| :------ | :------ |
| `scope` | `Construct` |
| `_stage` | `IStage` |
| `options` | `ActionBindOptions` |

#### Returns

`ActionConfig`

#### Inherited from

[CodePipelineCheckParameterAction](#code-pipeline-check-parameter-action).[bound](#bound)

___

### onStateChange

▸ **onStateChange**(`name`, `target?`, `options?`): `Rule`

Creates an Event that will be triggered whenever the state of this Action changes.

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `name` | `string` |
| `target?` | `IRuleTarget` |
| `options?` | `RuleProps` |

#### Returns

`Rule`

#### Inherited from

[CodePipelineCheckParameterAction](#code-pipeline-check-parameter-action).[onStateChange](#onstatechange)

___

### variableExpression

▸ `Protected` **variableExpression**(`variableName`): `string`

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `variableName` | `string` |

#### Returns

`string`

#### Inherited from

[CodePipelineCheckParameterAction](#code-pipeline-check-parameter-action).[variableExpression](#variableexpression)

# Code Pipeline Check Parameter Action

[@cloudcomponents/cdk-codepipeline-check-parameter-action](#readme) / CodePipelineCheckParameterAction

# Class: CodePipelineCheckParameterAction

Represents a reference to a CodePipelineCheckParameterAction.

## Hierarchy

- `Action`

  ↳ **`CodePipelineCheckParameterAction`**

  ↳↳ [`CodePipelineCheckUrlParameterAction`](#code-pipeline-check-url-parameter-action)

  ↳↳ [`CodePipelineCheckEmailParameterAction`](#code-pipeline-check-email-parameter-action)

## Table of contents

### Constructors

- [constructor](#constructor)

### Properties

- [props](#props)
- [providedActionProperties](#providedactionproperties)

### Accessors

- [\_pipeline](#_pipeline)
- [\_scope](#_scope)
- [\_stage](#_stage)
- [actionProperties](#actionproperties)

### Methods

- [bind](#bind)
- [bound](#bound)
- [onStateChange](#onstatechange)
- [variableExpression](#variableexpression)

## Constructors

### constructor

• **new CodePipelineCheckParameterAction**(`props`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `props` | [`CodePipelineCheckParameterActionProps`](#code-pipeline-check-parameter-action-props) |

#### Overrides

Action.constructor

## Properties

### props

• `Private` `Readonly` **props**: [`CodePipelineCheckParameterActionProps`](#code-pipeline-check-parameter-action-props)

___

### providedActionProperties

• `Protected` `Readonly` **providedActionProperties**: `ActionProperties`

This is a renamed version of the {@link IAction.actionProperties} property.

**`stability`** stable

#### Inherited from

Action.providedActionProperties

## Accessors

### \_pipeline

• `Private` `get` **_pipeline**(): `any`

#### Returns

`any`

#### Inherited from

Action.\_pipeline

___

### \_scope

• `Private` `get` **_scope**(): `any`

Retrieves the Construct scope of this Action.
Only available after the Action has been added to a Stage,
and that Stage to a Pipeline.

#### Returns

`any`

#### Inherited from

Action.\_scope

___

### \_stage

• `Private` `get` **_stage**(): `any`

#### Returns

`any`

#### Inherited from

Action.\_stage

___

### actionProperties

• `get` **actionProperties**(): `ActionProperties`

The simple properties of the Action, like its Owner, name, etc.

Note that this accessor will be called before the [bind](#bind) callback.

**`stability`** stable

#### Returns

`ActionProperties`

#### Inherited from

Action.actionProperties

## Methods

### bind

▸ **bind**(`scope`, `stage`, `options`): `ActionConfig`

The callback invoked when this Action is added to a Pipeline.

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `scope` | `Construct` |
| `stage` | `IStage` |
| `options` | `ActionBindOptions` |

#### Returns

`ActionConfig`

#### Inherited from

Action.bind

___

### bound

▸ `Protected` **bound**(`scope`, `_stage`, `options`): `ActionConfig`

#### Parameters

| Name | Type |
| :------ | :------ |
| `scope` | `Construct` |
| `_stage` | `IStage` |
| `options` | `ActionBindOptions` |

#### Returns

`ActionConfig`

#### Overrides

Action.bound

___

### onStateChange

▸ **onStateChange**(`name`, `target?`, `options?`): `Rule`

Creates an Event that will be triggered whenever the state of this Action changes.

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `name` | `string` |
| `target?` | `IRuleTarget` |
| `options?` | `RuleProps` |

#### Returns

`Rule`

#### Inherited from

Action.onStateChange

___

### variableExpression

▸ `Protected` **variableExpression**(`variableName`): `string`

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `variableName` | `string` |

#### Returns

`string`

#### Inherited from

Action.variableExpression

# Code Pipeline Check Url Parameter Action

[@cloudcomponents/cdk-codepipeline-check-parameter-action](#readme) / CodePipelineCheckUrlParameterAction

# Class: CodePipelineCheckUrlParameterAction

## Hierarchy

- [`CodePipelineCheckParameterAction`](#code-pipeline-check-parameter-action)

  ↳ **`CodePipelineCheckUrlParameterAction`**

## Table of contents

### Constructors

- [constructor](#constructor)

### Properties

- [providedActionProperties](#providedactionproperties)

### Accessors

- [\_pipeline](#_pipeline)
- [\_scope](#_scope)
- [\_stage](#_stage)
- [actionProperties](#actionproperties)

### Methods

- [bind](#bind)
- [bound](#bound)
- [onStateChange](#onstatechange)
- [variableExpression](#variableexpression)

## Constructors

### constructor

• **new CodePipelineCheckUrlParameterAction**(`props`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `props` | [`CodePipelineCheckUrlParameterActionProps`](#code-pipeline-check-url-parameter-action-props) |

#### Overrides

[CodePipelineCheckParameterAction](#code-pipeline-check-parameter-action).[constructor](#constructor)

## Properties

### providedActionProperties

• `Protected` `Readonly` **providedActionProperties**: `ActionProperties`

This is a renamed version of the {@link IAction.actionProperties} property.

**`stability`** stable

#### Inherited from

[CodePipelineCheckParameterAction](#code-pipeline-check-parameter-action).[providedActionProperties](#providedactionproperties)

## Accessors

### \_pipeline

• `Private` `get` **_pipeline**(): `any`

#### Returns

`any`

#### Inherited from

CodePipelineCheckParameterAction.\_pipeline

___

### \_scope

• `Private` `get` **_scope**(): `any`

Retrieves the Construct scope of this Action.
Only available after the Action has been added to a Stage,
and that Stage to a Pipeline.

#### Returns

`any`

#### Inherited from

CodePipelineCheckParameterAction.\_scope

___

### \_stage

• `Private` `get` **_stage**(): `any`

#### Returns

`any`

#### Inherited from

CodePipelineCheckParameterAction.\_stage

___

### actionProperties

• `get` **actionProperties**(): `ActionProperties`

The simple properties of the Action, like its Owner, name, etc.

Note that this accessor will be called before the [bind](#bind) callback.

**`stability`** stable

#### Returns

`ActionProperties`

#### Inherited from

CodePipelineCheckParameterAction.actionProperties

## Methods

### bind

▸ **bind**(`scope`, `stage`, `options`): `ActionConfig`

The callback invoked when this Action is added to a Pipeline.

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `scope` | `Construct` |
| `stage` | `IStage` |
| `options` | `ActionBindOptions` |

#### Returns

`ActionConfig`

#### Inherited from

[CodePipelineCheckParameterAction](#code-pipeline-check-parameter-action).[bind](#bind)

___

### bound

▸ `Protected` **bound**(`scope`, `_stage`, `options`): `ActionConfig`

#### Parameters

| Name | Type |
| :------ | :------ |
| `scope` | `Construct` |
| `_stage` | `IStage` |
| `options` | `ActionBindOptions` |

#### Returns

`ActionConfig`

#### Inherited from

[CodePipelineCheckParameterAction](#code-pipeline-check-parameter-action).[bound](#bound)

___

### onStateChange

▸ **onStateChange**(`name`, `target?`, `options?`): `Rule`

Creates an Event that will be triggered whenever the state of this Action changes.

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `name` | `string` |
| `target?` | `IRuleTarget` |
| `options?` | `RuleProps` |

#### Returns

`Rule`

#### Inherited from

[CodePipelineCheckParameterAction](#code-pipeline-check-parameter-action).[onStateChange](#onstatechange)

___

### variableExpression

▸ `Protected` **variableExpression**(`variableName`): `string`

**`stability`** stable

#### Parameters

| Name | Type |
| :------ | :------ |
| `variableName` | `string` |

#### Returns

`string`

#### Inherited from

[CodePipelineCheckParameterAction](#code-pipeline-check-parameter-action).[variableExpression](#variableexpression)

# Check Paramter Function Props

[@cloudcomponents/cdk-codepipeline-check-parameter-action](#readme) / CheckParamterFunctionProps

# Interface: CheckParamterFunctionProps

## Table of contents

### Properties

- [crossAccountRole](#crossaccountrole)
- [parameterName](#parametername)

## Properties

### crossAccountRole

• `Optional` `Readonly` **crossAccountRole**: `IRole`

Role for crossAccount permission

___

### parameterName

• `Readonly` **parameterName**: `string`

The name of the parameter.

# Code Pipeline Check Email Parameter Action Props

[@cloudcomponents/cdk-codepipeline-check-parameter-action](#readme) / CodePipelineCheckEmailParameterActionProps

# Interface: CodePipelineCheckEmailParameterActionProps

## Hierarchy

- [`CommonCodePipelineCheckParameterActionProps`](#common-code-pipeline-check-parameter-action-props)

  ↳ **`CodePipelineCheckEmailParameterActionProps`**

## Table of contents

### Properties

- [actionName](#actionname)
- [crossAccountRole](#crossaccountrole)
- [exact](#exact)
- [logParameter](#logparameter)
- [parameterName](#parametername)
- [role](#role)
- [runOrder](#runorder)
- [variablesNamespace](#variablesnamespace)

## Properties

### actionName

• `Readonly` **actionName**: `string`

The physical, human-readable name of the Action.

Note that Action names must be unique within a single Stage.

**`stability`** stable

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[actionName](#actionname)

___

### crossAccountRole

• `Optional` `Readonly` **crossAccountRole**: `IRole`

Role for crossAccount permission

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[crossAccountRole](#crossaccountrole)

___

### exact

• `Optional` `Readonly` **exact**: `boolean`

Only match an exact string

**`default`** true

___

### logParameter

• `Optional` `Readonly` **logParameter**: `boolean`

Parameter is logged after successful check

**`default`** false The parameter is not logged

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[logParameter](#logparameter)

___

### parameterName

• `Readonly` **parameterName**: `string`

The name of the parameter.

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[parameterName](#parametername)

___

### role

• `Optional` `Readonly` **role**: `IRole`

The Role in which context's this Action will be executing in.

The Pipeline's Role will assume this Role
(the required permissions for that will be granted automatically)
right before executing this Action.
This Action will be passed into your {@link IAction.bind}
method in the {@link ActionBindOptions.role} property.

**`default`** a new Role will be generated

**`stability`** stable

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[role](#role)

___

### runOrder

• `Optional` `Readonly` **runOrder**: `number`

The runOrder property for this Action.

RunOrder determines the relative order in which multiple Actions in the same Stage execute.

**`default`** 1

**`see`** https://docs.aws.amazon.com/codepipeline/latest/userguide/reference-pipeline-structure.html

**`stability`** stable

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[runOrder](#runorder)

___

### variablesNamespace

• `Optional` `Readonly` **variablesNamespace**: `string`

The name of the namespace to use for variables emitted by this action.

**`default`** - a name will be generated, based on the stage and action names,
if any of the action's variables were referenced - otherwise,
no namespace will be set

**`stability`** stable

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[variablesNamespace](#variablesnamespace)

# Code Pipeline Check Parameter Action Props

[@cloudcomponents/cdk-codepipeline-check-parameter-action](#readme) / CodePipelineCheckParameterActionProps

# Interface: CodePipelineCheckParameterActionProps

## Hierarchy

- [`CommonCodePipelineCheckParameterActionProps`](#common-code-pipeline-check-parameter-action-props)

  ↳ **`CodePipelineCheckParameterActionProps`**

## Table of contents

### Properties

- [actionName](#actionname)
- [crossAccountRole](#crossaccountrole)
- [logParameter](#logparameter)
- [parameterName](#parametername)
- [regExp](#regexp)
- [role](#role)
- [runOrder](#runorder)
- [variablesNamespace](#variablesnamespace)

## Properties

### actionName

• `Readonly` **actionName**: `string`

The physical, human-readable name of the Action.

Note that Action names must be unique within a single Stage.

**`stability`** stable

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[actionName](#actionname)

___

### crossAccountRole

• `Optional` `Readonly` **crossAccountRole**: `IRole`

Role for crossAccount permission

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[crossAccountRole](#crossaccountrole)

___

### logParameter

• `Optional` `Readonly` **logParameter**: `boolean`

Parameter is logged after successful check

**`default`** false The parameter is not logged

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[logParameter](#logparameter)

___

### parameterName

• `Readonly` **parameterName**: `string`

The name of the parameter.

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[parameterName](#parametername)

___

### regExp

• `Optional` `Readonly` **regExp**: [`RegExp`](#reg-exp)

Regular expression to validate the parameter.

___

### role

• `Optional` `Readonly` **role**: `IRole`

The Role in which context's this Action will be executing in.

The Pipeline's Role will assume this Role
(the required permissions for that will be granted automatically)
right before executing this Action.
This Action will be passed into your {@link IAction.bind}
method in the {@link ActionBindOptions.role} property.

**`default`** a new Role will be generated

**`stability`** stable

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[role](#role)

___

### runOrder

• `Optional` `Readonly` **runOrder**: `number`

The runOrder property for this Action.

RunOrder determines the relative order in which multiple Actions in the same Stage execute.

**`default`** 1

**`see`** https://docs.aws.amazon.com/codepipeline/latest/userguide/reference-pipeline-structure.html

**`stability`** stable

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[runOrder](#runorder)

___

### variablesNamespace

• `Optional` `Readonly` **variablesNamespace**: `string`

The name of the namespace to use for variables emitted by this action.

**`default`** - a name will be generated, based on the stage and action names,
if any of the action's variables were referenced - otherwise,
no namespace will be set

**`stability`** stable

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[variablesNamespace](#variablesnamespace)

# Code Pipeline Check Url Parameter Action Props

[@cloudcomponents/cdk-codepipeline-check-parameter-action](#readme) / CodePipelineCheckUrlParameterActionProps

# Interface: CodePipelineCheckUrlParameterActionProps

## Hierarchy

- [`CommonCodePipelineCheckParameterActionProps`](#common-code-pipeline-check-parameter-action-props)

  ↳ **`CodePipelineCheckUrlParameterActionProps`**

## Table of contents

### Properties

- [actionName](#actionname)
- [crossAccountRole](#crossaccountrole)
- [exact](#exact)
- [logParameter](#logparameter)
- [parameterName](#parametername)
- [role](#role)
- [runOrder](#runorder)
- [strict](#strict)
- [variablesNamespace](#variablesnamespace)

## Properties

### actionName

• `Readonly` **actionName**: `string`

The physical, human-readable name of the Action.

Note that Action names must be unique within a single Stage.

**`stability`** stable

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[actionName](#actionname)

___

### crossAccountRole

• `Optional` `Readonly` **crossAccountRole**: `IRole`

Role for crossAccount permission

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[crossAccountRole](#crossaccountrole)

___

### exact

• `Optional` `Readonly` **exact**: `boolean`

Only match an exact string

**`default`** true

___

### logParameter

• `Optional` `Readonly` **logParameter**: `boolean`

Parameter is logged after successful check

**`default`** false The parameter is not logged

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[logParameter](#logparameter)

___

### parameterName

• `Readonly` **parameterName**: `string`

The name of the parameter.

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[parameterName](#parametername)

___

### role

• `Optional` `Readonly` **role**: `IRole`

The Role in which context's this Action will be executing in.

The Pipeline's Role will assume this Role
(the required permissions for that will be granted automatically)
right before executing this Action.
This Action will be passed into your {@link IAction.bind}
method in the {@link ActionBindOptions.role} property.

**`default`** a new Role will be generated

**`stability`** stable

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[role](#role)

___

### runOrder

• `Optional` `Readonly` **runOrder**: `number`

The runOrder property for this Action.

RunOrder determines the relative order in which multiple Actions in the same Stage execute.

**`default`** 1

**`see`** https://docs.aws.amazon.com/codepipeline/latest/userguide/reference-pipeline-structure.html

**`stability`** stable

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[runOrder](#runorder)

___

### strict

• `Optional` `Readonly` **strict**: `boolean`

Force URLs to start with a valid protocol or www

___

### variablesNamespace

• `Optional` `Readonly` **variablesNamespace**: `string`

The name of the namespace to use for variables emitted by this action.

**`default`** - a name will be generated, based on the stage and action names,
if any of the action's variables were referenced - otherwise,
no namespace will be set

**`stability`** stable

#### Inherited from

[CommonCodePipelineCheckParameterActionProps](#common-code-pipeline-check-parameter-action-props).[variablesNamespace](#variablesnamespace)

# Common Code Pipeline Check Parameter Action Props

[@cloudcomponents/cdk-codepipeline-check-parameter-action](#readme) / CommonCodePipelineCheckParameterActionProps

# Interface: CommonCodePipelineCheckParameterActionProps

## Hierarchy

- `CommonAwsActionProps`

  ↳ **`CommonCodePipelineCheckParameterActionProps`**

  ↳↳ [`CodePipelineCheckParameterActionProps`](#code-pipeline-check-parameter-action-props)

  ↳↳ [`CodePipelineCheckUrlParameterActionProps`](#code-pipeline-check-url-parameter-action-props)

  ↳↳ [`CodePipelineCheckEmailParameterActionProps`](#code-pipeline-check-email-parameter-action-props)

## Table of contents

### Properties

- [actionName](#actionname)
- [crossAccountRole](#crossaccountrole)
- [logParameter](#logparameter)
- [parameterName](#parametername)
- [role](#role)
- [runOrder](#runorder)
- [variablesNamespace](#variablesnamespace)

## Properties

### actionName

• `Readonly` **actionName**: `string`

The physical, human-readable name of the Action.

Note that Action names must be unique within a single Stage.

**`stability`** stable

#### Inherited from

CommonAwsActionProps.actionName

___

### crossAccountRole

• `Optional` `Readonly` **crossAccountRole**: `IRole`

Role for crossAccount permission

___

### logParameter

• `Optional` `Readonly` **logParameter**: `boolean`

Parameter is logged after successful check

**`default`** false The parameter is not logged

___

### parameterName

• `Readonly` **parameterName**: `string`

The name of the parameter.

___

### role

• `Optional` `Readonly` **role**: `IRole`

The Role in which context's this Action will be executing in.

The Pipeline's Role will assume this Role
(the required permissions for that will be granted automatically)
right before executing this Action.
This Action will be passed into your {@link IAction.bind}
method in the {@link ActionBindOptions.role} property.

**`default`** a new Role will be generated

**`stability`** stable

#### Inherited from

CommonAwsActionProps.role

___

### runOrder

• `Optional` `Readonly` **runOrder**: `number`

The runOrder property for this Action.

RunOrder determines the relative order in which multiple Actions in the same Stage execute.

**`default`** 1

**`see`** https://docs.aws.amazon.com/codepipeline/latest/userguide/reference-pipeline-structure.html

**`stability`** stable

#### Inherited from

CommonAwsActionProps.runOrder

___

### variablesNamespace

• `Optional` `Readonly` **variablesNamespace**: `string`

The name of the namespace to use for variables emitted by this action.

**`default`** - a name will be generated, based on the stage and action names,
if any of the action's variables were referenced - otherwise,
no namespace will be set

**`stability`** stable

#### Inherited from

CommonAwsActionProps.variablesNamespace

# Reg Exp

[@cloudcomponents/cdk-codepipeline-check-parameter-action](#readme) / RegExp

# Interface: RegExp

## Table of contents

### Properties

- [source](#source)

## Properties

### source

• `Readonly` **source**: `string`
