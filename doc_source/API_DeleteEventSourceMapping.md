# DeleteEventSourceMapping<a name="API_DeleteEventSourceMapping"></a>

Removes an event source mapping\. This means AWS Lambda will no longer invoke the function for events in the associated source\.

This operation requires permission for the `lambda:DeleteEventSourceMapping` action\.

## Request Syntax<a name="API_DeleteEventSourceMapping_RequestSyntax"></a>

```
DELETE /2015-03-31/event-source-mappings/UUID HTTP/1.1
```

## URI Request Parameters<a name="API_DeleteEventSourceMapping_RequestParameters"></a>

The request requires the following URI parameters\.

 ** UUID **   
The event source mapping ID\.

## Request Body<a name="API_DeleteEventSourceMapping_RequestBody"></a>

The request does not have a request body\.

## Response Syntax<a name="API_DeleteEventSourceMapping_ResponseSyntax"></a>

```
HTTP/1.1 202
Content-type: application/json

{
   "BatchSize": number,
   "EventSourceArn": "string",
   "FunctionArn": "string",
   "LastModified": number,
   "LastProcessingResult": "string",
   "State": "string",
   "StateTransitionReason": "string",
   "UUID": "string"
}
```

## Response Elements<a name="API_DeleteEventSourceMapping_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 202 response\.

The following data is returned in JSON format by the service\.

 ** BatchSize **   
The largest number of records that AWS Lambda will retrieve from your event source at the time of invoking your function\. Your function receives an event with all the retrieved records\.  
Type: Integer  
Valid Range: Minimum value of 1\. Maximum value of 10000\.

 ** EventSourceArn **   
The Amazon Resource Name \(ARN\) of the Amazon Kinesis stream that is the source of events\.  
Type: String  
Pattern: `arn:aws:([a-zA-Z0-9\-])+:([a-z]{2}-[a-z]+-\d{1})?:(\d{12})?:(.*)` 

 ** FunctionArn **   
The Lambda function to invoke when AWS Lambda detects an event on the stream\.  
Type: String  
Pattern: `arn:aws:lambda:[a-z]{2}-[a-z]+-\d{1}:\d{12}:function:[a-zA-Z0-9-_]+(:(\$LATEST|[a-zA-Z0-9-_]+))?` 

 ** LastModified **   
The UTC time string indicating the last time the event mapping was updated\.  
Type: Timestamp

 ** LastProcessingResult **   
The result of the last AWS Lambda invocation of your Lambda function\.  
Type: String

 ** State **   
The state of the event source mapping\. It can be `Creating`, `Enabled`, `Disabled`, `Enabling`, `Disabling`, `Updating`, or `Deleting`\.  
Type: String

 ** StateTransitionReason **   
The reason the event source mapping is in its current state\. It is either user\-requested or an AWS Lambda\-initiated state transition\.  
Type: String

 ** UUID **   
The AWS Lambda assigned opaque identifier for the mapping\.  
Type: String

## Errors<a name="API_DeleteEventSourceMapping_Errors"></a>

 **InvalidParameterValueException**   
One of the parameters in the request is invalid\. For example, if you provided an IAM role for AWS Lambda to assume in the `CreateFunction` or the `UpdateFunctionConfiguration` API, that AWS Lambda is unable to assume you will get this exception\.  
HTTP Status Code: 400

 **ResourceNotFoundException**   
The resource \(for example, a Lambda function or access policy statement\) specified in the request does not exist\.  
HTTP Status Code: 404

 **ServiceException**   
The AWS Lambda service encountered an internal error\.  
HTTP Status Code: 500

 **TooManyRequestsException**   
   
HTTP Status Code: 429

## See Also<a name="API_DeleteEventSourceMapping_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:

+  [AWS Command Line Interface](http://docs.aws.amazon.com/goto/aws-cli/lambda-2015-03-31/DeleteEventSourceMapping) 

+  [AWS SDK for \.NET](http://docs.aws.amazon.com/goto/DotNetSDKV3/lambda-2015-03-31/DeleteEventSourceMapping) 

+  [AWS SDK for C\+\+](http://docs.aws.amazon.com/goto/SdkForCpp/lambda-2015-03-31/DeleteEventSourceMapping) 

+  [AWS SDK for Go](http://docs.aws.amazon.com/goto/SdkForGoV1/lambda-2015-03-31/DeleteEventSourceMapping) 

+  [AWS SDK for Java](http://docs.aws.amazon.com/goto/SdkForJava/lambda-2015-03-31/DeleteEventSourceMapping) 

+  [AWS SDK for JavaScript](http://docs.aws.amazon.com/goto/AWSJavaScriptSDK/lambda-2015-03-31/DeleteEventSourceMapping) 

+  [AWS SDK for PHP V3](http://docs.aws.amazon.com/goto/SdkForPHPV3/lambda-2015-03-31/DeleteEventSourceMapping) 

+  [AWS SDK for Python](http://docs.aws.amazon.com/goto/boto3/lambda-2015-03-31/DeleteEventSourceMapping) 

+  [AWS SDK for Ruby V2](http://docs.aws.amazon.com/goto/SdkForRubyV2/lambda-2015-03-31/DeleteEventSourceMapping) 