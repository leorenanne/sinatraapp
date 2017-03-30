# Simple Sinatra App

My take on the rea-cruitment practical task - Simple Sinatra App:<br/>
https://github.com/rea-cruitment/simple-sinatra-app

**Prerequisites**
* Must have awscli installed
* Must have an AWS Account

**How to run**
* Clone this repository
* Edit the `sinatra-cfn-params.json` file. Use your AWS account's existing VPN's ID and Subnet IDs.

```json
 {
    "ParameterKey": "InstanceType",
    "ParameterValue": "t2.small"
  },
  {
    "ParameterKey": "KeyName",
    "ParameterValue": "stack-key" 
  },
  {
    "ParameterKey": "VpcID",
    "ParameterValue": "vpc1234"
  },
  {
    "ParameterKey": "SubnetElb",
    "ParameterValue": "subnetPub123"
  },
  {
    "ParameterKey": "SubnetInstance",
    "ParameterValue": "subnetPriv123" 
  },
  {
    "ParameterKey": "PublicSubnetCidrIP",
    "ParameterValue": "10.0.0.0/16"
  }
  ```
* Run aws createstack <br/>
`aws cloudformation create-stack --stack-name leoren-stack --template-body file://sinatra-cfn.json --parameters file://sinatra-cfn-params.json`
