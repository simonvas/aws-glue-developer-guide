# User\-Defined Function API<a name="aws-glue-api-catalog-functions"></a>

## Data Types<a name="aws-glue-api-catalog-functions-objects"></a>
+ [UserDefinedFunction Structure](#aws-glue-api-catalog-functions-UserDefinedFunction)
+ [UserDefinedFunctionInput Structure](#aws-glue-api-catalog-functions-UserDefinedFunctionInput)

## UserDefinedFunction Structure<a name="aws-glue-api-catalog-functions-UserDefinedFunction"></a>

Represents the equivalent of a Hive user\-defined function \(`UDF`\) definition\.

**Fields**
+ `FunctionName` – String, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\.

  The name of the function\.
+ `ClassName` – String, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\.

  The Java class that contains the function code\.
+ `OwnerName` – String, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\.

  The owner of the function\.
+ `OwnerType` – String \(valid values: `USER` \| `ROLE` \| `GROUP`\)\.

  The owner type\.
+ `CreateTime` – Timestamp\.

  The time at which the function was created\.
+ `ResourceUris` – An array of [ResourceUri](aws-glue-api-common.md#aws-glue-api-common-ResourceUri)s\.

  The resource URIs for the function\.

## UserDefinedFunctionInput Structure<a name="aws-glue-api-catalog-functions-UserDefinedFunctionInput"></a>

A structure used to create or updata a user\-defined function\.

**Fields**
+ `FunctionName` – String, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\.

  The name of the function\.
+ `ClassName` – String, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\.

  The Java class that contains the function code\.
+ `OwnerName` – String, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\.

  The owner of the function\.
+ `OwnerType` – String \(valid values: `USER` \| `ROLE` \| `GROUP`\)\.

  The owner type\.
+ `ResourceUris` – An array of [ResourceUri](aws-glue-api-common.md#aws-glue-api-common-ResourceUri)s\.

  The resource URIs for the function\.

## Operations<a name="aws-glue-api-catalog-functions-actions"></a>
+ [CreateUserDefinedFunction Action \(Python: create\_user\_defined\_function\)](#aws-glue-api-catalog-functions-CreateUserDefinedFunction)
+ [UpdateUserDefinedFunction Action \(Python: update\_user\_defined\_function\)](#aws-glue-api-catalog-functions-UpdateUserDefinedFunction)
+ [DeleteUserDefinedFunction Action \(Python: delete\_user\_defined\_function\)](#aws-glue-api-catalog-functions-DeleteUserDefinedFunction)
+ [GetUserDefinedFunction Action \(Python: get\_user\_defined\_function\)](#aws-glue-api-catalog-functions-GetUserDefinedFunction)
+ [GetUserDefinedFunctions Action \(Python: get\_user\_defined\_functions\)](#aws-glue-api-catalog-functions-GetUserDefinedFunctions)

## CreateUserDefinedFunction Action \(Python: create\_user\_defined\_function\)<a name="aws-glue-api-catalog-functions-CreateUserDefinedFunction"></a>

Creates a new function definition in the Data Catalog\.

**Request**
+ `CatalogId` – Catalog id string, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\.

  The ID of the Data Catalog in which to create the function\. If none is supplied, the AWS account ID is used by default\.
+ `DatabaseName` – String, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\. Required\.

  The name of the catalog database in which to create the function\.
+ `FunctionInput` – An UserDefinedFunctionInput object\. Required\.

  A `FunctionInput` object that defines the function to create in the Data Catalog\.

**Response**
+ *No Response parameters\.*

**Errors**
+ `AlreadyExistsException`
+ `InvalidInputException`
+ `InternalServiceException`
+ `EntityNotFoundException`
+ `OperationTimeoutException`
+ `ResourceNumberLimitExceededException`

## UpdateUserDefinedFunction Action \(Python: update\_user\_defined\_function\)<a name="aws-glue-api-catalog-functions-UpdateUserDefinedFunction"></a>

Updates an existing function definition in the Data Catalog\.

**Request**
+ `CatalogId` – Catalog id string, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\.

  The ID of the Data Catalog where the function to be updated is located\. If none is supplied, the AWS account ID is used by default\.
+ `DatabaseName` – String, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\. Required\.

  The name of the catalog database where the function to be updated is located\.
+ `FunctionName` – String, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\. Required\.

  The name of the function\.
+ `FunctionInput` – An UserDefinedFunctionInput object\. Required\.

  A `FunctionInput` object that re\-defines the function in the Data Catalog\.

**Response**
+ *No Response parameters\.*

**Errors**
+ `EntityNotFoundException`
+ `InvalidInputException`
+ `InternalServiceException`
+ `OperationTimeoutException`

## DeleteUserDefinedFunction Action \(Python: delete\_user\_defined\_function\)<a name="aws-glue-api-catalog-functions-DeleteUserDefinedFunction"></a>

Deletes an existing function definition from the Data Catalog\.

**Request**
+ `CatalogId` – Catalog id string, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\.

  The ID of the Data Catalog where the function to be deleted is located\. If none is supplied, the AWS account ID is used by default\.
+ `DatabaseName` – String, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\. Required\.

  The name of the catalog database where the function is located\.
+ `FunctionName` – String, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\. Required\.

  The name of the function definition to be deleted\.

**Response**
+ *No Response parameters\.*

**Errors**
+ `EntityNotFoundException`
+ `InvalidInputException`
+ `InternalServiceException`
+ `OperationTimeoutException`

## GetUserDefinedFunction Action \(Python: get\_user\_defined\_function\)<a name="aws-glue-api-catalog-functions-GetUserDefinedFunction"></a>

Retrieves a specified function definition from the Data Catalog\.

**Request**
+ `CatalogId` – Catalog id string, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\.

  The ID of the Data Catalog where the function to be retrieved is located\. If none is supplied, the AWS account ID is used by default\.
+ `DatabaseName` – String, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\. Required\.

  The name of the catalog database where the function is located\.
+ `FunctionName` – String, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\. Required\.

  The name of the function\.

**Response**
+ `UserDefinedFunction` – An UserDefinedFunction object\.

  The requested function definition\.

**Errors**
+ `EntityNotFoundException`
+ `InvalidInputException`
+ `InternalServiceException`
+ `OperationTimeoutException`

## GetUserDefinedFunctions Action \(Python: get\_user\_defined\_functions\)<a name="aws-glue-api-catalog-functions-GetUserDefinedFunctions"></a>

Retrieves a multiple function definitions from the Data Catalog\.

**Request**
+ `CatalogId` – Catalog id string, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\.

  The ID of the Data Catalog where the functions to be retrieved are located\. If none is supplied, the AWS account ID is used by default\.
+ `DatabaseName` – String, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\. Required\.

  The name of the catalog database where the functions are located\.
+ `Pattern` – String, matching the [Single-line string pattern](aws-glue-api-common.md#aws-glue-api-regex-oneLine)\. Required\.

  An optional function\-name pattern string that filters the function definitions returned\.
+ `NextToken` – String\.

  A continuation token, if this is a continuation call\.
+ `MaxResults` – Number \(integer\)\.

  The maximum number of functions to return in one response\.

**Response**
+ `UserDefinedFunctions` – An array of [UserDefinedFunction](#aws-glue-api-catalog-functions-UserDefinedFunction)s\.

  A list of requested function definitions\.
+ `NextToken` – String\.

  A continuation token, if the list of functions returned does not include the last requested function\.

**Errors**
+ `EntityNotFoundException`
+ `InvalidInputException`
+ `OperationTimeoutException`
+ `InternalServiceException`