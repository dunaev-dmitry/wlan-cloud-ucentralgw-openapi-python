# openapi_client.DevicesApi

All URIs are relative to *https://localhost:16001/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_new_device**](DevicesApi.md#create_new_device) | **POST** /device/{serialNumber} | Creating a new device
[**delete_device**](DevicesApi.md#delete_device) | **DELETE** /device/{serialNumber} | Deleting a single device
[**get_device_information**](DevicesApi.md#get_device_information) | **GET** /device/{serialNumber} | Retrieve information for a single device
[**get_device_list**](DevicesApi.md#get_device_list) | **GET** /devices | Returns a list of devices.
[**update_new_device**](DevicesApi.md#update_new_device) | **PUT** /device/{serialNumber} | Updating a new device


# **create_new_device**
> Device create_new_device(serial_number)

Creating a new device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import devices_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.device import Device
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
    api_instance = devices_api.DevicesApi(api_client)
    serial_number = "serialNumber_example" # str | 
    device = Device(
        owner="owner_example",
        location="location_example",
        serial_number="serial_number_example",
        device_type=DeviceType("AP"),
        mac_address="mac_address_example",
        manufacturer="manufacturer_example",
        uuid=1,
        configuration="configuration_example",
        notes="notes_example",
        created_timestamp=1,
        last_configuration_change=1,
        last_configuration_download=1,
        firmware="firmware_example",
        device_password="device_password_example",
    ) # Device | Information used to create the new device (optional)

    # example passing only required values which don't have defaults set
    try:
        # Creating a new device
        api_response = api_instance.create_new_device(serial_number)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling DevicesApi->create_new_device: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Creating a new device
        api_response = api_instance.create_new_device(serial_number, device=device)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling DevicesApi->create_new_device: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **device** | [**Device**](Device.md)| Information used to create the new device | [optional]

### Return type

[**Device**](Device.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful device creation will return the device record with the proper device ID |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_device**
> GenericGoodAnswer delete_device(serial_number)

Deleting a single device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import devices_api
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
    api_instance = devices_api.DevicesApi(api_client)
    serial_number = "serialNumber_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Deleting a single device
        api_response = api_instance.delete_device(serial_number)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling DevicesApi->delete_device: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |

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
**200** | The requested operation was performed. |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_device_information**
> Device get_device_information(serial_number)

Retrieve information for a single device

Retrieve all the inforamtion about a single device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import devices_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.device import Device
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
    api_instance = devices_api.DevicesApi(api_client)
    serial_number = "serialNumber_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve information for a single device
        api_response = api_instance.get_device_information(serial_number)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling DevicesApi->get_device_information: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |

### Return type

[**Device**](Device.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Device information |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_device_list**
> object get_device_list()

Returns a list of devices.

Get a list of devices.

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import devices_api
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
    api_instance = devices_api.DevicesApi(api_client)
    offset = 1 # int | Pagination start (starts at 1. If not specified, 1 is assumed) (optional)
    limit = 1 # int | Maximum number of entries to return (if absent, no limit is assumed) (optional)
    filter = "filter_example" # str | Filter the results (optional)
    select = "serial1,serial2,serial3" # str | Supply a list of devices comma separated (optional)
    serial_only = True # bool | only serial numbers of full device details (optional)
    count_only = True # bool | return the number of devices (optional)
    device_with_status = True # bool | Return extra information with the device information (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Returns a list of devices.
        api_response = api_instance.get_device_list(offset=offset, limit=limit, filter=filter, select=select, serial_only=serial_only, count_only=count_only, device_with_status=device_with_status)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling DevicesApi->get_device_list: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **offset** | **int**| Pagination start (starts at 1. If not specified, 1 is assumed) | [optional]
 **limit** | **int**| Maximum number of entries to return (if absent, no limit is assumed) | [optional]
 **filter** | **str**| Filter the results | [optional]
 **select** | **str**| Supply a list of devices comma separated | [optional]
 **serial_only** | **bool**| only serial numbers of full device details | [optional]
 **count_only** | **bool**| return the number of devices | [optional]
 **device_with_status** | **bool**| Return extra information with the device information | [optional]

### Return type

**object**

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List devices |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_new_device**
> Device update_new_device(serial_number)

Updating a new device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import devices_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.device import Device
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
    api_instance = devices_api.DevicesApi(api_client)
    serial_number = "serialNumber_example" # str | 
    device = Device(
        owner="owner_example",
        location="location_example",
        serial_number="serial_number_example",
        device_type=DeviceType("AP"),
        mac_address="mac_address_example",
        manufacturer="manufacturer_example",
        uuid=1,
        configuration="configuration_example",
        notes="notes_example",
        created_timestamp=1,
        last_configuration_change=1,
        last_configuration_download=1,
        firmware="firmware_example",
        device_password="device_password_example",
    ) # Device | Information used to create the new device (optional)

    # example passing only required values which don't have defaults set
    try:
        # Updating a new device
        api_response = api_instance.update_new_device(serial_number)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling DevicesApi->update_new_device: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Updating a new device
        api_response = api_instance.update_new_device(serial_number, device=device)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling DevicesApi->update_new_device: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **device** | [**Device**](Device.md)| Information used to create the new device | [optional]

### Return type

[**Device**](Device.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful device creation will return the device record with the proper device ID |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

