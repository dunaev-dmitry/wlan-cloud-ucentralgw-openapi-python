# openapi_client.OUIsApi

All URIs are relative to *https://localhost:16001/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_ouis**](OUIsApi.md#get_ouis) | **GET** /ouis | Get a list of OUIs


# **get_ouis**
> get_ouis(mac_list)

Get a list of OUIs

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import ouis_api
from openapi_client.model.generic_error_response import GenericErrorResponse
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
    api_instance = ouis_api.OUIsApi(api_client)
    mac_list = "macList_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get a list of OUIs
        api_instance.get_ouis(mac_list)
    except openapi_client.ApiException as e:
        print("Exception when calling OUIsApi->get_ouis: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mac_list** | **str**|  |

### Return type

void (empty response body)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

