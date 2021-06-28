# openapi_client.BlacklistApi

All URIs are relative to *https://localhost:16001/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_to_black_list**](BlacklistApi.md#add_to_black_list) | **POST** /blacklist | Adds to the blacklist
[**delete_from_black_list**](BlacklistApi.md#delete_from_black_list) | **DELETE** /blacklist | Delete from the blacklist
[**get_blacklist_device_list**](BlacklistApi.md#get_blacklist_device_list) | **GET** /blacklist | Returns a list blacklisted devices.


# **add_to_black_list**
> add_to_black_list()

Adds to the blacklist

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import blacklist_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.black_device_list import BlackDeviceList
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
    api_instance = blacklist_api.BlacklistApi(api_client)
    black_device_list = BlackDeviceList(
        devices=[
            BlackDeviceInfo(
                serial_number="serial_number_example",
                reason="reason_example",
            ),
        ],
    ) # BlackDeviceList | Add blacklisted devices (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Adds to the blacklist
        api_instance.add_to_black_list(black_device_list=black_device_list)
    except openapi_client.ApiException as e:
        print("Exception when calling BlacklistApi->add_to_black_list: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **black_device_list** | [**BlackDeviceList**](BlackDeviceList.md)| Add blacklisted devices | [optional]

### Return type

void (empty response body)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_from_black_list**
> delete_from_black_list(serial_number)

Delete from the blacklist

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import blacklist_api
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
    api_instance = blacklist_api.BlacklistApi(api_client)
    serial_number = "serialNumber_example" # str | Serial Number

    # example passing only required values which don't have defaults set
    try:
        # Delete from the blacklist
        api_instance.delete_from_black_list(serial_number)
    except openapi_client.ApiException as e:
        print("Exception when calling BlacklistApi->delete_from_black_list: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**| Serial Number |

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

# **get_blacklist_device_list**
> BlackDeviceList get_blacklist_device_list()

Returns a list blacklisted devices.

Get a list of blacklisteddevices.

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import blacklist_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.black_device_list import BlackDeviceList
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
    api_instance = blacklist_api.BlacklistApi(api_client)
    offset = 1 # int | Pagination start (starts at 1. If not specified, 1 is assumed) (optional)
    limit = 1 # int | Maximum number of entries to return (if absent, no limit is assumed) (optional)
    filter = "filter_example" # str | Filter the results (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Returns a list blacklisted devices.
        api_response = api_instance.get_blacklist_device_list(offset=offset, limit=limit, filter=filter)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling BlacklistApi->get_blacklist_device_list: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **offset** | **int**| Pagination start (starts at 1. If not specified, 1 is assumed) | [optional]
 **limit** | **int**| Maximum number of entries to return (if absent, no limit is assumed) | [optional]
 **filter** | **str**| Filter the results | [optional]

### Return type

[**BlackDeviceList**](BlackDeviceList.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List blacklisted devices |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

