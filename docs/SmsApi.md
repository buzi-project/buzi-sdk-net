# Io.Gitlab.Buziproject.V1.Api.SmsApi

All URIs are relative to *https://petstore3.swagger.io*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CancelMessage**](SmsApi.md#cancelmessage) | **POST** /v1/sms/messages/{messageId}/cancel | Cancel a message |
| [**CreateMessage**](SmsApi.md#createmessage) | **POST** /v1/sms/messages | Create Message |
| [**CreatePricing**](SmsApi.md#createpricing) | **PUT** /v1/sms/networks/{networkId}/pricing | Create network price |
| [**DeleteMessage**](SmsApi.md#deletemessage) | **DELETE** /v1/sms/messages/{messageId} | Deletes a message |
| [**GetMessage**](SmsApi.md#getmessage) | **GET** /v1/sms/messages/{messageId} | Get message |
| [**GetNetwork**](SmsApi.md#getnetwork) | **GET** /v1/sms/networks/{networkId} | Get network |
| [**GetPricing**](SmsApi.md#getpricing) | **GET** /v1/sms/networks/{networkId}/pricing | List network rates |
| [**ListMessages**](SmsApi.md#listmessages) | **GET** /v1/sms/messages | List messages |
| [**ListNetworks**](SmsApi.md#listnetworks) | **GET** /v1/sms/networks | List networks |
| [**SendMessage**](SmsApi.md#sendmessage) | **POST** /v1/sms/messages/{messageId}/send | Sends a message |

<a name="cancelmessage"></a>
# **CancelMessage**
> Message CancelMessage (long messageId)

Cancel a message

Returns a single pet

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Io.Gitlab.Buziproject.V1.Api;
using Io.Gitlab.Buziproject.V1.Client;
using Io.Gitlab.Buziproject.V1.Model;

namespace Example
{
    public class CancelMessageExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BaseUrl = "https://petstore3.swagger.io";
            // Configure API key authorization: ApiKeyAuth
            config.AddApiKey("X-API-Key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-API-Key", "Bearer");
            // Configure HTTP basic authorization: BasicAuth
            config.Username = "YOUR_USERNAME";
            config.Password = "YOUR_PASSWORD";
            // Configure Bearer token for authorization: BearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new SmsApi(config);
            var messageId = 789L;  // long | ID of pet to return

            try
            {
                // Cancel a message
                Message result = apiInstance.CancelMessage(messageId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SmsApi.CancelMessage: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CancelMessageWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Cancel a message
    ApiResponse<Message> response = apiInstance.CancelMessageWithHttpInfo(messageId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SmsApi.CancelMessageWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **messageId** | **long** | ID of pet to return |  |

### Return type

[**Message**](Message.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | successful operation |  -  |
| **400** | Invalid ID supplied |  -  |
| **404** | Pet not found |  -  |
| **0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a name="createmessage"></a>
# **CreateMessage**
> Message CreateMessage (CreateMessageInput createMessageInput)

Create Message

Update an existing pet by Id

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Io.Gitlab.Buziproject.V1.Api;
using Io.Gitlab.Buziproject.V1.Client;
using Io.Gitlab.Buziproject.V1.Model;

namespace Example
{
    public class CreateMessageExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BaseUrl = "https://petstore3.swagger.io";
            // Configure API key authorization: ApiKeyAuth
            config.AddApiKey("X-API-Key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-API-Key", "Bearer");
            // Configure HTTP basic authorization: BasicAuth
            config.Username = "YOUR_USERNAME";
            config.Password = "YOUR_PASSWORD";
            // Configure Bearer token for authorization: BearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new SmsApi(config);
            var createMessageInput = new CreateMessageInput(); // CreateMessageInput | Update an existent pet in the store

            try
            {
                // Create Message
                Message result = apiInstance.CreateMessage(createMessageInput);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SmsApi.CreateMessage: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateMessageWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create Message
    ApiResponse<Message> response = apiInstance.CreateMessageWithHttpInfo(createMessageInput);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SmsApi.CreateMessageWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createMessageInput** | [**CreateMessageInput**](CreateMessageInput.md) | Update an existent pet in the store |  |

### Return type

[**Message**](Message.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successful operation |  -  |
| **400** | Invalid ID supplied |  -  |
| **404** | Pet not found |  -  |
| **405** | Validation exception |  -  |
| **0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a name="createpricing"></a>
# **CreatePricing**
> Message CreatePricing (int networkId)

Create network price

Returns a single pet

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Io.Gitlab.Buziproject.V1.Api;
using Io.Gitlab.Buziproject.V1.Client;
using Io.Gitlab.Buziproject.V1.Model;

namespace Example
{
    public class CreatePricingExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BaseUrl = "https://petstore3.swagger.io";
            // Configure API key authorization: ApiKeyAuth
            config.AddApiKey("X-API-Key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-API-Key", "Bearer");
            // Configure HTTP basic authorization: BasicAuth
            config.Username = "YOUR_USERNAME";
            config.Password = "YOUR_PASSWORD";
            // Configure Bearer token for authorization: BearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new SmsApi(config);
            var networkId = 56;  // int | 

            try
            {
                // Create network price
                Message result = apiInstance.CreatePricing(networkId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SmsApi.CreatePricing: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreatePricingWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create network price
    ApiResponse<Message> response = apiInstance.CreatePricingWithHttpInfo(networkId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SmsApi.CreatePricingWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **networkId** | **int** |  |  |

### Return type

[**Message**](Message.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | successful operation |  -  |
| **400** | Invalid ID supplied |  -  |
| **404** | Pet not found |  -  |
| **0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a name="deletemessage"></a>
# **DeleteMessage**
> Error DeleteMessage (long messageId, string apiKey = null)

Deletes a message

delete a message

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Io.Gitlab.Buziproject.V1.Api;
using Io.Gitlab.Buziproject.V1.Client;
using Io.Gitlab.Buziproject.V1.Model;

namespace Example
{
    public class DeleteMessageExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BaseUrl = "https://petstore3.swagger.io";
            // Configure API key authorization: ApiKeyAuth
            config.AddApiKey("X-API-Key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-API-Key", "Bearer");
            // Configure HTTP basic authorization: BasicAuth
            config.Username = "YOUR_USERNAME";
            config.Password = "YOUR_PASSWORD";
            // Configure Bearer token for authorization: BearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new SmsApi(config);
            var messageId = 789L;  // long | Pet id to delete
            var apiKey = "apiKey_example";  // string |  (optional) 

            try
            {
                // Deletes a message
                Error result = apiInstance.DeleteMessage(messageId, apiKey);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SmsApi.DeleteMessage: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteMessageWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Deletes a message
    ApiResponse<Error> response = apiInstance.DeleteMessageWithHttpInfo(messageId, apiKey);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SmsApi.DeleteMessageWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **messageId** | **long** | Pet id to delete |  |
| **apiKey** | **string** |  | [optional]  |

### Return type

[**Error**](Error.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Invalid pet value |  -  |
| **0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a name="getmessage"></a>
# **GetMessage**
> Message GetMessage (long messageId)

Get message

Returns a single pet

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Io.Gitlab.Buziproject.V1.Api;
using Io.Gitlab.Buziproject.V1.Client;
using Io.Gitlab.Buziproject.V1.Model;

namespace Example
{
    public class GetMessageExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BaseUrl = "https://petstore3.swagger.io";
            // Configure API key authorization: ApiKeyAuth
            config.AddApiKey("X-API-Key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-API-Key", "Bearer");
            // Configure HTTP basic authorization: BasicAuth
            config.Username = "YOUR_USERNAME";
            config.Password = "YOUR_PASSWORD";
            // Configure Bearer token for authorization: BearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new SmsApi(config);
            var messageId = 789L;  // long | ID of pet to return

            try
            {
                // Get message
                Message result = apiInstance.GetMessage(messageId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SmsApi.GetMessage: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetMessageWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get message
    ApiResponse<Message> response = apiInstance.GetMessageWithHttpInfo(messageId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SmsApi.GetMessageWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **messageId** | **long** | ID of pet to return |  |

### Return type

[**Message**](Message.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | successful operation |  -  |
| **400** | Invalid ID supplied |  -  |
| **404** | Pet not found |  -  |
| **0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a name="getnetwork"></a>
# **GetNetwork**
> Network GetNetwork (int networkId, long? countryCode = null)

Get network

Returns a single pet

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Io.Gitlab.Buziproject.V1.Api;
using Io.Gitlab.Buziproject.V1.Client;
using Io.Gitlab.Buziproject.V1.Model;

namespace Example
{
    public class GetNetworkExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BaseUrl = "https://petstore3.swagger.io";
            // Configure API key authorization: ApiKeyAuth
            config.AddApiKey("X-API-Key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-API-Key", "Bearer");
            // Configure HTTP basic authorization: BasicAuth
            config.Username = "YOUR_USERNAME";
            config.Password = "YOUR_PASSWORD";
            // Configure Bearer token for authorization: BearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new SmsApi(config);
            var networkId = 56;  // int | 
            var countryCode = 789L;  // long? | ID of pet to return (optional) 

            try
            {
                // Get network
                Network result = apiInstance.GetNetwork(networkId, countryCode);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SmsApi.GetNetwork: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetNetworkWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get network
    ApiResponse<Network> response = apiInstance.GetNetworkWithHttpInfo(networkId, countryCode);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SmsApi.GetNetworkWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **networkId** | **int** |  |  |
| **countryCode** | **long?** | ID of pet to return | [optional]  |

### Return type

[**Network**](Network.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | successful operation |  -  |
| **400** | Invalid ID supplied |  -  |
| **404** | Pet not found |  -  |
| **0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a name="getpricing"></a>
# **GetPricing**
> List&lt;Pricing&gt; GetPricing (int networkId)

List network rates

Returns a single pet

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Io.Gitlab.Buziproject.V1.Api;
using Io.Gitlab.Buziproject.V1.Client;
using Io.Gitlab.Buziproject.V1.Model;

namespace Example
{
    public class GetPricingExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BaseUrl = "https://petstore3.swagger.io";
            // Configure API key authorization: ApiKeyAuth
            config.AddApiKey("X-API-Key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-API-Key", "Bearer");
            // Configure HTTP basic authorization: BasicAuth
            config.Username = "YOUR_USERNAME";
            config.Password = "YOUR_PASSWORD";
            // Configure Bearer token for authorization: BearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new SmsApi(config);
            var networkId = 56;  // int | 

            try
            {
                // List network rates
                List<Pricing> result = apiInstance.GetPricing(networkId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SmsApi.GetPricing: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetPricingWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List network rates
    ApiResponse<List<Pricing>> response = apiInstance.GetPricingWithHttpInfo(networkId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SmsApi.GetPricingWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **networkId** | **int** |  |  |

### Return type

[**List&lt;Pricing&gt;**](Pricing.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | successful operation |  -  |
| **400** | Invalid ID supplied |  -  |
| **404** | Pet not found |  -  |
| **0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a name="listmessages"></a>
# **ListMessages**
> List&lt;Message&gt; ListMessages (string inbox = null, string status = null)

List messages

Update an existing pet by Id

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Io.Gitlab.Buziproject.V1.Api;
using Io.Gitlab.Buziproject.V1.Client;
using Io.Gitlab.Buziproject.V1.Model;

namespace Example
{
    public class ListMessagesExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BaseUrl = "https://petstore3.swagger.io";
            // Configure API key authorization: ApiKeyAuth
            config.AddApiKey("X-API-Key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-API-Key", "Bearer");
            // Configure HTTP basic authorization: BasicAuth
            config.Username = "YOUR_USERNAME";
            config.Password = "YOUR_PASSWORD";
            // Configure Bearer token for authorization: BearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new SmsApi(config);
            var inbox = "inbox_example";  // string |  (optional) 
            var status = "status_example";  // string |  (optional) 

            try
            {
                // List messages
                List<Message> result = apiInstance.ListMessages(inbox, status);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SmsApi.ListMessages: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListMessagesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List messages
    ApiResponse<List<Message>> response = apiInstance.ListMessagesWithHttpInfo(inbox, status);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SmsApi.ListMessagesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **inbox** | **string** |  | [optional]  |
| **status** | **string** |  | [optional]  |

### Return type

[**List&lt;Message&gt;**](Message.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successful operation |  -  |
| **400** | Invalid ID supplied |  -  |
| **404** | Pet not found |  -  |
| **405** | Validation exception |  -  |
| **0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a name="listnetworks"></a>
# **ListNetworks**
> List&lt;Network&gt; ListNetworks (string countryCode = null)

List networks

Returns a single pet

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Io.Gitlab.Buziproject.V1.Api;
using Io.Gitlab.Buziproject.V1.Client;
using Io.Gitlab.Buziproject.V1.Model;

namespace Example
{
    public class ListNetworksExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BaseUrl = "https://petstore3.swagger.io";
            // Configure API key authorization: ApiKeyAuth
            config.AddApiKey("X-API-Key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-API-Key", "Bearer");
            // Configure HTTP basic authorization: BasicAuth
            config.Username = "YOUR_USERNAME";
            config.Password = "YOUR_PASSWORD";
            // Configure Bearer token for authorization: BearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new SmsApi(config);
            var countryCode = "countryCode_example";  // string | ID of pet to return (optional) 

            try
            {
                // List networks
                List<Network> result = apiInstance.ListNetworks(countryCode);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SmsApi.ListNetworks: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListNetworksWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List networks
    ApiResponse<List<Network>> response = apiInstance.ListNetworksWithHttpInfo(countryCode);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SmsApi.ListNetworksWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **countryCode** | **string** | ID of pet to return | [optional]  |

### Return type

[**List&lt;Network&gt;**](Network.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | successful operation |  -  |
| **400** | Invalid ID supplied |  -  |
| **404** | Pet not found |  -  |
| **0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a name="sendmessage"></a>
# **SendMessage**
> Message SendMessage (long messageId)

Sends a message

Returns a single pet

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Io.Gitlab.Buziproject.V1.Api;
using Io.Gitlab.Buziproject.V1.Client;
using Io.Gitlab.Buziproject.V1.Model;

namespace Example
{
    public class SendMessageExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BaseUrl = "https://petstore3.swagger.io";
            // Configure API key authorization: ApiKeyAuth
            config.AddApiKey("X-API-Key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-API-Key", "Bearer");
            // Configure HTTP basic authorization: BasicAuth
            config.Username = "YOUR_USERNAME";
            config.Password = "YOUR_PASSWORD";
            // Configure Bearer token for authorization: BearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new SmsApi(config);
            var messageId = 789L;  // long | ID of pet to return

            try
            {
                // Sends a message
                Message result = apiInstance.SendMessage(messageId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SmsApi.SendMessage: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SendMessageWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Sends a message
    ApiResponse<Message> response = apiInstance.SendMessageWithHttpInfo(messageId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SmsApi.SendMessageWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **messageId** | **long** | ID of pet to return |  |

### Return type

[**Message**](Message.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [BasicAuth](../README.md#BasicAuth), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | successful operation |  -  |
| **400** | Invalid ID supplied |  -  |
| **404** | Pet not found |  -  |
| **0** | Unexpected Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

