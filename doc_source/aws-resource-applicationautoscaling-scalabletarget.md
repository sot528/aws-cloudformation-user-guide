# AWS::ApplicationAutoScaling::ScalableTarget<a name="aws-resource-applicationautoscaling-scalabletarget"></a>

The `AWS::ApplicationAutoScaling::ScalableTarget` resource specifies a resource that Application Auto Scaling can scale\. 

For more information, see [RegisterScalableTarget](https://docs.aws.amazon.com/autoscaling/application/APIReference/API_RegisterScalableTarget.html) in the *Application Auto Scaling API Reference*\.

For introductory exercises for scaling specific resources, see [Getting Started](https://docs.aws.amazon.com/autoscaling/application/userguide/getting-started.html) in the *Application Auto Scaling User Guide*\.

## Syntax<a name="aws-resource-applicationautoscaling-scalabletarget-syntax"></a>

To declare this entity in your AWS CloudFormation template, use the following syntax:

### JSON<a name="aws-resource-applicationautoscaling-scalabletarget-syntax.json"></a>

```
{
  "Type" : "AWS::ApplicationAutoScaling::ScalableTarget",
  "Properties" : {
      "[MaxCapacity](#cfn-applicationautoscaling-scalabletarget-maxcapacity)" : Integer,
      "[MinCapacity](#cfn-applicationautoscaling-scalabletarget-mincapacity)" : Integer,
      "[ResourceId](#cfn-applicationautoscaling-scalabletarget-resourceid)" : String,
      "[RoleARN](#cfn-applicationautoscaling-scalabletarget-rolearn)" : String,
      "[ScalableDimension](#cfn-applicationautoscaling-scalabletarget-scalabledimension)" : String,
      "[ScheduledActions](#cfn-applicationautoscaling-scalabletarget-scheduledactions)" : [ ScheduledAction, ... ],
      "[ServiceNamespace](#cfn-applicationautoscaling-scalabletarget-servicenamespace)" : String,
      "[SuspendedState](#cfn-applicationautoscaling-scalabletarget-suspendedstate)" : SuspendedState
    }
}
```

### YAML<a name="aws-resource-applicationautoscaling-scalabletarget-syntax.yaml"></a>

```
Type: AWS::ApplicationAutoScaling::ScalableTarget
Properties: 
  [MaxCapacity](#cfn-applicationautoscaling-scalabletarget-maxcapacity): Integer
  [MinCapacity](#cfn-applicationautoscaling-scalabletarget-mincapacity): Integer
  [ResourceId](#cfn-applicationautoscaling-scalabletarget-resourceid): String
  [RoleARN](#cfn-applicationautoscaling-scalabletarget-rolearn): String
  [ScalableDimension](#cfn-applicationautoscaling-scalabletarget-scalabledimension): String
  [ScheduledActions](#cfn-applicationautoscaling-scalabletarget-scheduledactions): 
    - ScheduledAction
  [ServiceNamespace](#cfn-applicationautoscaling-scalabletarget-servicenamespace): String
  [SuspendedState](#cfn-applicationautoscaling-scalabletarget-suspendedstate): 
    SuspendedState
```

## Properties<a name="aws-resource-applicationautoscaling-scalabletarget-properties"></a>

`MaxCapacity`  <a name="cfn-applicationautoscaling-scalabletarget-maxcapacity"></a>
The maximum value that you plan to scale out to\. When a scaling policy is in effect, Application Auto Scaling can scale out \(expand\) as needed to the maximum capacity limit in response to changing demand\.  
*Required*: Yes  
*Type*: Integer  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`MinCapacity`  <a name="cfn-applicationautoscaling-scalabletarget-mincapacity"></a>
The minimum value that you plan to scale in to\. When a scaling policy is in effect, Application Auto Scaling can scale in \(contract\) as needed to the minimum capacity limit in response to changing demand\.   
*Required*: Yes  
*Type*: Integer  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`ResourceId`  <a name="cfn-applicationautoscaling-scalabletarget-resourceid"></a>
The resource identifier to associate with this scalable target\. This string consists of the resource type and unique identifier\. For valid values, see the `ResourceId` parameter for [RegisterScalableTarget](https://docs.aws.amazon.com/autoscaling/application/APIReference/API_RegisterScalableTarget.html) in the *Application Auto Scaling API Reference*\.  
*Required*: Yes  
*Type*: String  
*Update requires*: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

`RoleARN`  <a name="cfn-applicationautoscaling-scalabletarget-rolearn"></a>
Specify the Amazon Resource Name \(ARN\) of an AWS Identity and Access Management \(IAM\) role that allows Application Auto Scaling to modify the scalable target on your behalf\. This can be either an IAM service role that Application Auto Scaling can assume to make calls to other AWS resources on your behalf, or a service\-linked role for the specified service\. For more information, see [How Application Auto Scaling Works with IAM](https://docs.aws.amazon.com/autoscaling/application/userguide/security_iam_service-with-iam.html) in the *Application Auto Scaling User Guide*\.  
To automatically create a service\-linked role, specify the full ARN of the service\-linked role in your stack template\. For examples of the ARN format and more information, see [Service\-Linked Roles](https://docs.aws.amazon.com/autoscaling/application/userguide/application-auto-scaling-service-linked-roles.html) in the *Application Auto Scaling User Guide*\.  
*Required*: Yes  
*Type*: String  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`ScalableDimension`  <a name="cfn-applicationautoscaling-scalabletarget-scalabledimension"></a>
The scalable dimension that is associated with the scalable target\. Specify the service namespace, resource type, and scaling property, for example, `ecs:service:DesiredCount` for the desired task count of an Amazon ECS service\. For valid values, see the `ScalableDimension` parameter for [RegisterScalableTarget](https://docs.aws.amazon.com/autoscaling/application/APIReference/API_RegisterScalableTarget.html) in the *Application Auto Scaling API Reference*\.  
*Required*: Yes  
*Type*: String  
*Update requires*: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

`ScheduledActions`  <a name="cfn-applicationautoscaling-scalabletarget-scheduledactions"></a>
The scheduled actions for the scalable target\. Duplicates aren't allowed\.  
For more information about using scheduled scaling, see [Scheduled Scaling](https://docs.aws.amazon.com/autoscaling/application/userguide/application-auto-scaling-scheduled-scaling.html) in the *Application Auto Scaling User Guide*\.  
*Required*: No  
*Type*: List of [ScheduledAction](aws-properties-applicationautoscaling-scalabletarget-scheduledaction.md)  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

`ServiceNamespace`  <a name="cfn-applicationautoscaling-scalabletarget-servicenamespace"></a>
The namespace of the AWS service that provides the resource or `custom-resource` for a resource provided by your own application or service\. For valid values, see the `ServiceNamespace` parameter for [RegisterScalableTarget](https://docs.aws.amazon.com/autoscaling/application/APIReference/API_RegisterScalableTarget.html) in the *Application Auto Scaling API Reference*\.  
*Required*: Yes  
*Type*: String  
*Update requires*: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

`SuspendedState`  <a name="cfn-applicationautoscaling-scalabletarget-suspendedstate"></a>
An embedded object that contains attributes and attribute values that are used to suspend and resume automatic scaling\. Setting the value of an attribute to `true` suspends the specified scaling activities\. Setting it to `false` \(default\) resumes the specified scaling activities\.   
**Suspension Outcomes**  
+ For `DynamicScalingInSuspended`, while a suspension is in effect, all scale\-in activities that are triggered by a scaling policy are suspended\.
+ For `DynamicScalingOutSuspended`, while a suspension is in effect, all scale\-out activities that are triggered by a scaling policy are suspended\.
+ For `ScheduledScalingSuspended`, while a suspension is in effect, all scaling activities that involve scheduled actions are suspended\. 
For more information, see [Suspending and Resuming Scaling](https://docs.aws.amazon.com/autoscaling/application/userguide/application-auto-scaling-suspend-resume-scaling.html) in the *Application Auto Scaling User Guide*\.  
*Required*: No  
*Type*: [SuspendedState](aws-properties-applicationautoscaling-scalabletarget-suspendedstate.md)  
*Update requires*: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

## Return values<a name="aws-resource-applicationautoscaling-scalabletarget-return-values"></a>

### Ref<a name="aws-resource-applicationautoscaling-scalabletarget-return-values-ref"></a>

When the logical ID of this resource is provided to the `Ref` intrinsic function, `Ref` returns the AWS CloudFormation\-generated ID of the resource\. For example: `service/ecsStack-MyECSCluster-AB12CDE3F4GH/ecsStack-MyECSService-AB12CDE3F4GH|ecs:service:DesiredCount|ecs`\. 

AWS CloudFormation uses the following format to generate the ID: `service/resource_ID|scalable_dimension|service_namespace `\.

For more information about using the `Ref` function, see [Ref](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference-ref.html)\. 

## Examples<a name="aws-resource-applicationautoscaling-scalabletarget--examples"></a>

Each scalable target has a service namespace, scalable dimension, and resource ID, as well as values for minimum and maximum capacity\. 

### Register a Scalable Target<a name="aws-resource-applicationautoscaling-scalabletarget--examples--Register_a_Scalable_Target"></a>

The following example creates a scalable target for an Amazon Keyspaces \(for Apache Cassandra\) table \([AWS::Cassandra::Table](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-cassandra-table.html)\)\. Application Auto Scaling can scale the write capacity throughput at a minimum of 1 capacity unit and a maximum of 20\. For more information about scaling Amazon Keyspaces tables, see [Managing Amazon Keyspaces Throughput Capacity with Application Auto Scaling](https://docs.aws.amazon.com/keyspaces/latest/devguide/autoscaling.html) in the *Amazon Keyspaces \(for Apache Cassandra\) Developer Guide*\.

To register a different resource supported by Application Auto Scaling, specify its namespace in `ServiceNamespace`, its scalable dimension in `ScalableDimension`, its resource ID in `ResourceId`, and its service\-linked role in `RoleARN`\.

#### JSON<a name="aws-resource-applicationautoscaling-scalabletarget--examples--Register_a_Scalable_Target--json"></a>

```
{
  "ScalableTarget":{
    "Type":"AWS::ApplicationAutoScaling::ScalableTarget",
    "Properties":{
      "MaxCapacity":20,
      "MinCapacity":1,
      "RoleARN":{
        "Fn::Sub":"arn:aws:iam::${AWS::AccountId}:role/aws-service-role/cassandra.application-autoscaling.amazonaws.com/AWSServiceRoleForApplicationAutoScaling_CassandraTable"
      },
      "ServiceNamespace":"cassandra",
      "ScalableDimension":"cassandra:table:WriteCapacityUnits",
      "ResourceId":"keyspace/mykeyspace/table/mytable"
    }
  }
}
```

#### YAML<a name="aws-resource-applicationautoscaling-scalabletarget--examples--Register_a_Scalable_Target--yaml"></a>

```
ScalableTarget:
  Type: AWS::ApplicationAutoScaling::ScalableTarget
  Properties:
    MaxCapacity: 20
    MinCapacity: 1
    RoleARN: 
      Fn::Sub: 'arn:aws:iam::${AWS::AccountId}:role/aws-service-role/cassandra.application-autoscaling.amazonaws.com/AWSServiceRoleForApplicationAutoScaling_CassandraTable'
    ServiceNamespace: cassandra
    ScalableDimension: cassandra:table:WriteCapacityUnits
    ResourceId: keyspace/mykeyspace/table/mytable
```

### Lambda with a Scheduled Action<a name="aws-resource-applicationautoscaling-scalabletarget--examples--Lambda_with_a_Scheduled_Action"></a>

The following example registers the provisioned concurrency for a function alias \([AWS::Lambda::Alias](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-lambda-alias.html)\) called BLUE, with a minimum capacity of 1 and a maximum capacity of 100\. It also creates a scheduled action with a recurring schedule using a cron expression\.

This example uses the [Fn::Join](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference-join.html) and [Ref](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference-ref.html) intrinsic functions in the `RoleARN` property to specify the ARN of the service\-linked role\. It uses the [Fn::Sub](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference-sub.html) intrinsic function to construct the `ResourceId` property\. 

Note: You can't allocate provisioned concurrency on an alias that points to the unpublished version \($LATEST\)\. 

#### JSON<a name="aws-resource-applicationautoscaling-scalabletarget--examples--Lambda_with_a_Scheduled_Action--json"></a>

```
{
  "ScalableTarget":{
    "Type":"AWS::ApplicationAutoScaling::ScalableTarget",
    "Properties":{
      "MaxCapacity":100,
      "MinCapacity":1,
      "RoleARN":{
        "Fn::Join":[
          ":",
          [
            "arn:aws:iam:",
            {
              "Ref":"AWS::AccountId"
            },
            "role/aws-service-role/lambda.application-autoscaling.amazonaws.com/AWSServiceRoleForApplicationAutoScaling_LambdaConcurrency"
          ]
        ]
      },
      "ServiceNamespace":"lambda",
      "ScalableDimension":"lambda:function:ProvisionedConcurrency",
      "ResourceId":{
        "Fn::Sub":"function:${MyFunction}:BLUE"
      },
      "ScheduledActions":[
        {
          "EndTime":"2019-12-31T12:00:00.000Z",
          "ScalableTargetAction":{
            "MaxCapacity":"500",
            "MinCapacity":"50"
          },
          "ScheduledActionName":"First",
          "StartTime":"2019-12-25T12:00:00.000Z",
          "Schedule":"cron(0 18 * * ? *)"
        }
      ]
    }
  }
}
```

#### YAML<a name="aws-resource-applicationautoscaling-scalabletarget--examples--Lambda_with_a_Scheduled_Action--yaml"></a>

```
ScalableTarget:
  Type: AWS::ApplicationAutoScaling::ScalableTarget
  Properties:
    MaxCapacity: 100
    MinCapacity: 1
    RoleARN: !Join 
      - ':'
      - - 'arn:aws:iam:'
        - !Ref 'AWS::AccountId'
        - role/aws-service-role/lambda.application-autoscaling.amazonaws.com/AWSServiceRoleForApplicationAutoScaling_LambdaConcurrency
    ServiceNamespace: lambda
    ScalableDimension: lambda:function:ProvisionedConcurrency
    ResourceId: !Sub function:${MyFunction}:BLUE
    ScheduledActions:
      - EndTime: '2019-12-31T12:00:00.000Z'
        ScalableTargetAction:
          MaxCapacity: '500'
          MinCapacity: '50'
        ScheduledActionName: First
        StartTime: '2019-12-25T12:00:00.000Z'
        Schedule: 'cron(0 18 * * ? *)'
```

### Amazon DynamoDB<a name="aws-resource-applicationautoscaling-scalabletarget--examples--Amazon_DynamoDB"></a>

This example registers the read and write capacity throughput of a DynamoDB table \([AWS::DynamoDB::Table](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-dynamodb-table.html)\) and its global secondary index as scalable targets\. It uses the [Fn::Sub](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference-sub.html) intrinsic function to construct the `ResourceId` properties\. 

#### JSON<a name="aws-resource-applicationautoscaling-scalabletarget--examples--Amazon_DynamoDB--json"></a>

```
{
  "Resources" : {
    "DDBTable" : {
      "Type" : "AWS::DynamoDB::Table",
      "Properties" : {
        "AttributeDefinitions" : [
          {
            "AttributeName" : "id",
            "AttributeType" : "S"   
          }
        ],
        "KeySchema" : [
          {
            "AttributeName" : "id",
            "KeyType" : "HASH"
          }
        ],
        "ProvisionedThroughput" : {
          "ReadCapacityUnits" : "5",
          "WriteCapacityUnits" : "5"
        },
        "GlobalSecondaryIndexes" : [{
          "IndexName" : "GSI",
          "KeySchema" : [
            {
              "AttributeName" : "id",
              "KeyType" : "HASH"
            }
          ],                         
          "Projection" : {
            "ProjectionType" : "KEYS_ONLY"
          },
          "ProvisionedThroughput" : {
            "ReadCapacityUnits" : "5",
            "WriteCapacityUnits" : "5"
          }
        }]
      }
    },
    "WriteCapacityScalableTarget":{
      "Type":"AWS::ApplicationAutoScaling::ScalableTarget",
      "Properties":{
        "MaxCapacity":100,
        "MinCapacity":5,
        "RoleARN":{
          "Fn::Sub":"arn:aws:iam::${AWS::AccountId}:role/aws-service-role/dynamodb.application-autoscaling.amazonaws.com/AWSServiceRoleForApplicationAutoScaling_DynamoDBTable"
        },
        "ServiceNamespace":"dynamodb",
        "ScalableDimension":"dynamodb:table:WriteCapacityUnits",
        "ResourceId":{
          "Fn::Sub":"table/${DDBTable}"
        }
      }
    },
    "ReadCapacityScalableTarget":{
      "Type":"AWS::ApplicationAutoScaling::ScalableTarget",
      "Properties":{
        "MaxCapacity":100,
        "MinCapacity":5,
        "RoleARN":{
          "Fn::Sub":"arn:aws:iam::${AWS::AccountId}:role/aws-service-role/dynamodb.application-autoscaling.amazonaws.com/AWSServiceRoleForApplicationAutoScaling_DynamoDBTable"
        },
        "ServiceNamespace":"dynamodb",
        "ScalableDimension":"dynamodb:table:ReadCapacityUnits",
        "ResourceId":{
          "Fn::Sub":"table/${DDBTable}"
        }
      }
    },
    "WriteCapacityScalableTargetGSI":{
      "Type":"AWS::ApplicationAutoScaling::ScalableTarget",
      "Properties":{
        "MaxCapacity":100,
        "MinCapacity":5,
        "RoleARN":{
          "Fn::Sub":"arn:aws:iam::${AWS::AccountId}:role/aws-service-role/dynamodb.application-autoscaling.amazonaws.com/AWSServiceRoleForApplicationAutoScaling_DynamoDBTable"
        },
        "ServiceNamespace":"dynamodb",
        "ScalableDimension":"dynamodb:index:WriteCapacityUnits",
        "ResourceId":{
          "Fn::Sub":"table/${DDBTable}/index/GSI"
        }
      }
    },
    "ReadCapacityScalableTargetGSI":{
      "Type":"AWS::ApplicationAutoScaling::ScalableTarget",
      "Properties":{
        "MaxCapacity":100,
        "MinCapacity":5,
        "RoleARN":{
          "Fn::Sub":"arn:aws:iam::${AWS::AccountId}:role/aws-service-role/dynamodb.application-autoscaling.amazonaws.com/AWSServiceRoleForApplicationAutoScaling_DynamoDBTable"
        },
        "ServiceNamespace":"dynamodb",
        "ScalableDimension":"dynamodb:index:ReadCapacityUnits",
        "ResourceId":{
          "Fn::Sub":"table/${DDBTable}/index/GSI"
        }
      }
    }
  }
}
```

#### YAML<a name="aws-resource-applicationautoscaling-scalabletarget--examples--Amazon_DynamoDB--yaml"></a>

```
Resources:
  DDBTable:
    Type: AWS::DynamoDB::Table
    Properties:
      AttributeDefinitions:
        - AttributeName: "id"
          AttributeType: "S"
      KeySchema:
        - AttributeName: "id"
          KeyType: "HASH"
      ProvisionedThroughput:
        ReadCapacityUnits: 5
        WriteCapacityUnits: 5  
      GlobalSecondaryIndexes:
        - IndexName: "GSI"
          KeySchema:
            - AttributeName: "id"
              KeyType: "HASH"
          Projection:
            ProjectionType: "KEYS_ONLY"
          ProvisionedThroughput:
            ReadCapacityUnits: 5
            WriteCapacityUnits: 5    
  WriteCapacityScalableTarget:
    Type: AWS::ApplicationAutoScaling::ScalableTarget
    Properties:
      MaxCapacity: 100
      MinCapacity: 5
      RoleARN: 
        Fn::Sub: 'arn:aws:iam::${AWS::AccountId}:role/aws-service-role/dynamodb.application-autoscaling.amazonaws.com/AWSServiceRoleForApplicationAutoScaling_DynamoDBTable'
      ServiceNamespace: dynamodb
      ScalableDimension: dynamodb:table:WriteCapacityUnits
      ResourceId: !Sub table/${DDBTable} 
  ReadCapacityScalableTarget:
    Type: AWS::ApplicationAutoScaling::ScalableTarget
    Properties:
      MaxCapacity: 100
      MinCapacity: 5
      RoleARN: 
        Fn::Sub: 'arn:aws:iam::${AWS::AccountId}:role/aws-service-role/dynamodb.application-autoscaling.amazonaws.com/AWSServiceRoleForApplicationAutoScaling_DynamoDBTable'
      ServiceNamespace: dynamodb
      ScalableDimension: dynamodb:table:ReadCapacityUnits
      ResourceId: !Sub table/${DDBTable}
  WriteCapacityScalableTargetGSI:
    Type: AWS::ApplicationAutoScaling::ScalableTarget
    Properties:
      MaxCapacity: 100
      MinCapacity: 5
      RoleARN:
        Fn::Sub: 'arn:aws:iam::${AWS::AccountId}:role/aws-service-role/dynamodb.application-autoscaling.amazonaws.com/AWSServiceRoleForApplicationAutoScaling_DynamoDBTable'
      ServiceNamespace: dynamodb
      ScalableDimension: dynamodb:index:WriteCapacityUnits
      ResourceId: !Sub table/${DDBTable}/index/GSI
  ReadCapacityScalableTargetGSI:
    Type: AWS::ApplicationAutoScaling::ScalableTarget
    Properties:
      MaxCapacity: 100
      MinCapacity: 5
      RoleARN: 
        Fn::Sub: 'arn:aws:iam::${AWS::AccountId}:role/aws-service-role/dynamodb.application-autoscaling.amazonaws.com/AWSServiceRoleForApplicationAutoScaling_DynamoDBTable'
      ServiceNamespace: dynamodb
      ScalableDimension: dynamodb:index:ReadCapacityUnits
      ResourceId: !Sub table/${DDBTable}/index/GSI
```

## See also<a name="aws-resource-applicationautoscaling-scalabletarget--seealso"></a>
+ [Application Auto Scaling User Guide](https://docs.aws.amazon.com/autoscaling/application/userguide/what-is-application-auto-scaling.html) 
+ [Examples](https://docs.aws.amazon.com/cli/latest/reference/application-autoscaling/register-scalable-target.html#examples) of Application Auto Scaling scalable targets in the * AWS CLI Command Reference*