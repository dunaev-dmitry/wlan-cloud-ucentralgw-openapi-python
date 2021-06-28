# openapi_client.AuthenticationApi

All URIs are relative to *https://localhost:16001/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_access_token**](AuthenticationApi.md#get_access_token) | **POST** /oauth2 | Get access token - to be used as Bearer token header for all other API requests.
[**remove_access_token**](AuthenticationApi.md#remove_access_token) | **DELETE** /oauth2/{token} | Revoke a token.


# **get_access_token**
> WebTokenResult get_access_token(web_token_request)

Get access token - to be used as Bearer token header for all other API requests.

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import authentication_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.web_token_request import WebTokenRequest
from openapi_client.model.web_token_result import WebTokenResult
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
    api_instance = authentication_api.AuthenticationApi(api_client)
    web_token_request = WebTokenRequest(
        user_id="support@example.com",
        password="support",
        refresh_token="refresh_token_example",
    ) # WebTokenRequest | User id and password

    # example passing only required values which don't have defaults set
    try:
        # Get access token - to be used as Bearer token header for all other API requests.
        api_response = api_instance.get_access_token(web_token_request)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling AuthenticationApi->get_access_token: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **web_token_request** | [**WebTokenRequest**](WebTokenRequest.md)| User id and password |

### Return type

[**WebTokenResult**](WebTokenResult.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | successful operation |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **remove_access_token**
> GenericGoodAnswer remove_access_token(token)

Revoke a token.

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import authentication_api
from openapi_client.model.generic_good_answer import GenericGoodAnswer
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
    api_instance = authentication_api.AuthenticationApi(api_client)
    token = "token_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Revoke a token.
        api_response = api_instance.remove_access_token(token)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling AuthenticationApi->remove_access_token: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **token** | **str**|  |

### Return type

[**GenericGoodAnswer**](GenericGoodAnswer.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | successful operation |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

