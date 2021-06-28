# openapi_client.CallbackApi

All URIs are relative to *https://localhost:16001/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**post_callback**](CallbackApi.md#post_callback) | **POST** /callbackChannel | Generic callback hook


# **post_callback**
> GenericGoodAnswer post_callback(any_payload)

Generic callback hook

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import callback_api
from openapi_client.model.generic_good_answer import GenericGoodAnswer
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.any_payload import AnyPayload
from pprint import pprint
# Defining the host is optional and defaults to https://localhost:16001/api/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = openapi_client.Configuration(
    host = "https://localhost:16001/api/v1"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure API key authorization: ApiKeyAuth
configuration.api_key['ApiKeyAuth'] = 'YOUR_API_KEY'

# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['ApiKeyAuth'] = 'Bearer'

# Configure Bearer authorization (JWT): bearerAuth
configuration = openapi_client.Configuration(
    access_token = 'YOUR_BEARER_TOKEN'
)

# Enter a context with an instance of the API client
with openapi_client.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = callback_api.CallbackApi(api_client)
    any_payload = AnyPayload(
        document="document_example",
    ) # AnyPayload | A generic JSONDocument, may be empty too {}
    subscribe = True # bool |  (optional)
    uri = "uri_example" # str |  (optional)
    key = "key_example" # str |  (optional)
    topics = "topics_example" # str |  (optional)
    id = "id_example" # str |  (optional)
    topic = "topic_example" # str |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Generic callback hook
        api_response = api_instance.post_callback(any_payload)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CallbackApi->post_callback: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Generic callback hook
        api_response = api_instance.post_callback(any_payload, subscribe=subscribe, uri=uri, key=key, topics=topics, id=id, topic=topic)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CallbackApi->post_callback: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **any_payload** | [**AnyPayload**](AnyPayload.md)| A generic JSONDocument, may be empty too {} |
 **subscribe** | **bool**|  | [optional]
 **uri** | **str**|  | [optional]
 **key** | **str**|  | [optional]
 **topics** | **str**|  | [optional]
 **id** | **str**|  | [optional]
 **topic** | **str**|  | [optional]

### Return type

[**GenericGoodAnswer**](GenericGoodAnswer.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | The requested operation was performed. |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

