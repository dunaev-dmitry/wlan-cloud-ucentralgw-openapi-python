# openapi_client.CommandsApi

All URIs are relative to *https://localhost:16001/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_a_command**](CommandsApi.md#delete_a_command) | **DELETE** /command/{commandUUID} | Delete a specific command
[**delete_commands**](CommandsApi.md#delete_commands) | **DELETE** /commands | Delete some commands
[**delete_device_capabilities**](CommandsApi.md#delete_device_capabilities) | **DELETE** /device/{serialNumber}/capabilities | Delete the capabilities for a given device
[**delete_device_health_checks**](CommandsApi.md#delete_device_health_checks) | **DELETE** /device/{serialNumber}/healthchecks | Delete some device health checks
[**delete_device_logs**](CommandsApi.md#delete_device_logs) | **DELETE** /device/{serialNumber}/logs | Delete some device logs
[**delete_device_stats**](CommandsApi.md#delete_device_stats) | **DELETE** /device/{serialNumber}/statistics | Get the latest statistics for a given device
[**event_queue_request**](CommandsApi.md#event_queue_request) | **POST** /device/{serialNumber}/eventrequest | Request a list of queued events
[**execute_command**](CommandsApi.md#execute_command) | **POST** /device/{serialNumber}/command | Post a command to a device
[**factory_reset**](CommandsApi.md#factory_reset) | **POST** /device/{serialNumber}/factory | Factory reset a device a device
[**get_a_command_details**](CommandsApi.md#get_a_command_details) | **GET** /command/{commandUUID} | Returns a specific command
[**get_command_list**](CommandsApi.md#get_command_list) | **GET** /commands | Returns a list of commands.
[**get_device_capabilities**](CommandsApi.md#get_device_capabilities) | **GET** /device/{serialNumber}/capabilities | Get the latest capabilities for a given device
[**get_device_health_checks**](CommandsApi.md#get_device_health_checks) | **GET** /device/{serialNumber}/healthchecks | Get the latest health checks for a given device
[**get_device_logs**](CommandsApi.md#get_device_logs) | **GET** /device/{serialNumber}/logs | Get the latest logs for a given device
[**get_device_stats**](CommandsApi.md#get_device_stats) | **GET** /device/{serialNumber}/statistics | Get the latest statistics for a given device
[**get_device_status**](CommandsApi.md#get_device_status) | **GET** /device/{serialNumber}/status | Get the latest status for a given device
[**get_rtty_session_info**](CommandsApi.md#get_rtty_session_info) | **GET** /device/{serialNumber}/rtty | Get the rtty parameters to initiate a session
[**leds_request**](CommandsApi.md#leds_request) | **POST** /device/{serialNumber}/leds | Blink the LEDs on a device
[**message_request**](CommandsApi.md#message_request) | **POST** /device/{serialNumber}/request | Request a specific message
[**reboot_device**](CommandsApi.md#reboot_device) | **POST** /device/{serialNumber}/reboot | Upgrade a device
[**trace_request**](CommandsApi.md#trace_request) | **POST** /device/{serialNumber}/trace | Launch a trace for a device
[**update_configuration_for_a_device**](CommandsApi.md#update_configuration_for_a_device) | **POST** /device/{serialNumber}/configure | Configura a device
[**upgrade_device_firmware**](CommandsApi.md#upgrade_device_firmware) | **POST** /device/{serialNumber}/upgrade | Upgrade a device
[**wifiscan_request**](CommandsApi.md#wifiscan_request) | **POST** /device/{serialNumber}/wifiscan | Launch a wifi scan for a device


# **delete_a_command**
> GenericGoodAnswer delete_a_command(command_uuid)

Delete a specific command

Delete a specific command

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
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
    api_instance = commands_api.CommandsApi(api_client)
    command_uuid = "commandUUID_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Delete a specific command
        api_response = api_instance.delete_a_command(command_uuid)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->delete_a_command: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **command_uuid** | **str**|  |

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
**200** | Delete command success |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_commands**
> GenericGoodAnswer delete_commands(serial_number)

Delete some commands

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    start_date = 1 # int |  (optional)
    end_date = 1 # int |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Delete some commands
        api_response = api_instance.delete_commands(serial_number)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->delete_commands: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Delete some commands
        api_response = api_instance.delete_commands(serial_number, start_date=start_date, end_date=end_date)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->delete_commands: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **start_date** | **int**|  | [optional]
 **end_date** | **int**|  | [optional]

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
**200** | Successfully deleted commands for the device. |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_device_capabilities**
> GenericGoodAnswer delete_device_capabilities(serial_number)

Delete the capabilities for a given device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Delete the capabilities for a given device
        api_response = api_instance.delete_device_capabilities(serial_number)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->delete_device_capabilities: %s\n" % e)
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
**200** | List of logs for this device |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_device_health_checks**
> GenericGoodAnswer delete_device_health_checks(serial_number)

Delete some device health checks

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    start_date = 1 # int |  (optional)
    end_date = 1 # int |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Delete some device health checks
        api_response = api_instance.delete_device_health_checks(serial_number)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->delete_device_health_checks: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Delete some device health checks
        api_response = api_instance.delete_device_health_checks(serial_number, start_date=start_date, end_date=end_date)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->delete_device_health_checks: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **start_date** | **int**|  | [optional]
 **end_date** | **int**|  | [optional]

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
**200** | Successfully deleted health checks for the device. |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_device_logs**
> GenericGoodAnswer delete_device_logs(serial_number)

Delete some device logs

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    start_date = 1 # int |  (optional)
    end_date = 1 # int |  (optional)
    log_type = 1 # int | 0=any kind of logs (default) 1=normal logs only 2=crash logs only (optional)

    # example passing only required values which don't have defaults set
    try:
        # Delete some device logs
        api_response = api_instance.delete_device_logs(serial_number)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->delete_device_logs: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Delete some device logs
        api_response = api_instance.delete_device_logs(serial_number, start_date=start_date, end_date=end_date, log_type=log_type)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->delete_device_logs: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **start_date** | **int**|  | [optional]
 **end_date** | **int**|  | [optional]
 **log_type** | **int**| 0&#x3D;any kind of logs (default) 1&#x3D;normal logs only 2&#x3D;crash logs only | [optional]

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
**200** | Successfully deleted logs for the device. |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_device_stats**
> GenericGoodAnswer delete_device_stats(serial_number)

Get the latest statistics for a given device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    start_date = 1 # int |  (optional)
    end_date = 1 # int |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Get the latest statistics for a given device
        api_response = api_instance.delete_device_stats(serial_number)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->delete_device_stats: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Get the latest statistics for a given device
        api_response = api_instance.delete_device_stats(serial_number, start_date=start_date, end_date=end_date)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->delete_device_stats: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **start_date** | **int**|  | [optional]
 **end_date** | **int**|  | [optional]

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
**200** | Array of statistics for this device |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **event_queue_request**
> event_queue_request(serial_number)

Request a list of queued events

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.event_queue_request import EventQueueRequest
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    event_queue_request = EventQueueRequest(
        serial_number="serial_number_example",
        types=[
            "dhcp",
        ],
    ) # EventQueueRequest | Message request details (optional)

    # example passing only required values which don't have defaults set
    try:
        # Request a list of queued events
        api_instance.event_queue_request(serial_number)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->event_queue_request: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Request a list of queued events
        api_instance.event_queue_request(serial_number, event_queue_request=event_queue_request)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->event_queue_request: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **event_queue_request** | [**EventQueueRequest**](EventQueueRequest.md)| Message request details | [optional]

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

# **execute_command**
> execute_command(serial_number)

Post a command to a device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.command_details import CommandDetails
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    command_details = CommandDetails(
        command="command_example",
        payload="payload_example",
        when=1,
        serial_number="serial_number_example",
    ) # CommandDetails | Command details (optional)

    # example passing only required values which don't have defaults set
    try:
        # Post a command to a device
        api_instance.execute_command(serial_number)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->execute_command: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Post a command to a device
        api_instance.execute_command(serial_number, command_details=command_details)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->execute_command: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **command_details** | [**CommandDetails**](CommandDetails.md)| Command details | [optional]

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

# **factory_reset**
> factory_reset(serial_number)

Factory reset a device a device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.factory_request import FactoryRequest
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    factory_request = FactoryRequest(
        serial_number="serial_number_example",
        when=1,
        keep_redirector=True,
    ) # FactoryRequest | Command details (optional)

    # example passing only required values which don't have defaults set
    try:
        # Factory reset a device a device
        api_instance.factory_reset(serial_number)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->factory_reset: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Factory reset a device a device
        api_instance.factory_reset(serial_number, factory_request=factory_request)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->factory_reset: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **factory_request** | [**FactoryRequest**](FactoryRequest.md)| Command details | [optional]

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

# **get_a_command_details**
> CommandInfo get_a_command_details(command_uuid)

Returns a specific command

Returns a specific command

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.command_info import CommandInfo
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
    api_instance = commands_api.CommandsApi(api_client)
    command_uuid = "commandUUID_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Returns a specific command
        api_response = api_instance.get_a_command_details(command_uuid)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->get_a_command_details: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **command_uuid** | **str**|  |

### Return type

[**CommandInfo**](CommandInfo.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List commands |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_command_list**
> CommandInfoList get_command_list()

Returns a list of commands.

Get a list of commands.

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.command_info_list import CommandInfoList
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str |  (optional)
    start_date = 1 # int |  (optional)
    end_date = 1 # int |  (optional)
    offset = 1 # int |  (optional)
    limit = 1 # int |  (optional)
    newest = True # bool | Selecting this option means the newest record will be returned. Use limit to select how many. (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Returns a list of commands.
        api_response = api_instance.get_command_list(serial_number=serial_number, start_date=start_date, end_date=end_date, offset=offset, limit=limit, newest=newest)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->get_command_list: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  | [optional]
 **start_date** | **int**|  | [optional]
 **end_date** | **int**|  | [optional]
 **offset** | **int**|  | [optional]
 **limit** | **int**|  | [optional]
 **newest** | **bool**| Selecting this option means the newest record will be returned. Use limit to select how many. | [optional]

### Return type

[**CommandInfoList**](CommandInfoList.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List commands |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_device_capabilities**
> DeviceCapabilities get_device_capabilities(serial_number)

Get the latest capabilities for a given device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.device_capabilities import DeviceCapabilities
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get the latest capabilities for a given device
        api_response = api_instance.get_device_capabilities(serial_number)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->get_device_capabilities: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |

### Return type

[**DeviceCapabilities**](DeviceCapabilities.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List of logs for this device |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_device_health_checks**
> HealthCheckList get_device_health_checks(serial_number)

Get the latest health checks for a given device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.health_check_list import HealthCheckList
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    start_date = 1 # int |  (optional)
    end_date = 1 # int |  (optional)
    offset = 1 # int |  (optional)
    limit = 1 # int |  (optional)
    newest = True # bool | Selecting this option means the newest record will be returned. Use limit to select how many. (optional)
    last_only = True # bool | Selecting this option means the last healthcheck will be returned. All other parameters will be ignored. (optional)

    # example passing only required values which don't have defaults set
    try:
        # Get the latest health checks for a given device
        api_response = api_instance.get_device_health_checks(serial_number)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->get_device_health_checks: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Get the latest health checks for a given device
        api_response = api_instance.get_device_health_checks(serial_number, start_date=start_date, end_date=end_date, offset=offset, limit=limit, newest=newest, last_only=last_only)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->get_device_health_checks: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **start_date** | **int**|  | [optional]
 **end_date** | **int**|  | [optional]
 **offset** | **int**|  | [optional]
 **limit** | **int**|  | [optional]
 **newest** | **bool**| Selecting this option means the newest record will be returned. Use limit to select how many. | [optional]
 **last_only** | **bool**| Selecting this option means the last healthcheck will be returned. All other parameters will be ignored. | [optional]

### Return type

[**HealthCheckList**](HealthCheckList.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Array of device health checks  for this device |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_device_logs**
> DeviceLogList get_device_logs(serial_number)

Get the latest logs for a given device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.device_log_list import DeviceLogList
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    start_date = 1 # int |  (optional)
    end_date = 1 # int |  (optional)
    offset = 1 # int |  (optional)
    limit = 1 # int |  (optional)
    log_type = 1 # int | 0=any kind of logs (default) 0=normal logs only 1=crash logs only (optional)
    newest = True # bool | Selecting this option means the newest record will be returned. Use limit to select how many. (optional)

    # example passing only required values which don't have defaults set
    try:
        # Get the latest logs for a given device
        api_response = api_instance.get_device_logs(serial_number)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->get_device_logs: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Get the latest logs for a given device
        api_response = api_instance.get_device_logs(serial_number, start_date=start_date, end_date=end_date, offset=offset, limit=limit, log_type=log_type, newest=newest)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->get_device_logs: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **start_date** | **int**|  | [optional]
 **end_date** | **int**|  | [optional]
 **offset** | **int**|  | [optional]
 **limit** | **int**|  | [optional]
 **log_type** | **int**| 0&#x3D;any kind of logs (default) 0&#x3D;normal logs only 1&#x3D;crash logs only | [optional]
 **newest** | **bool**| Selecting this option means the newest record will be returned. Use limit to select how many. | [optional]

### Return type

[**DeviceLogList**](DeviceLogList.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Array of device logs for this device |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_device_stats**
> object get_device_stats(serial_number)

Get the latest statistics for a given device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    start_date = 1 # int |  (optional)
    end_date = 1 # int |  (optional)
    offset = 1 # int |  (optional)
    limit = 1 # int |  (optional)
    lifetime = True # bool | Selecting this option means the LifetimeStatistics will be returned. All other parameters will be ignored. (optional)
    last_only = True # bool | Selecting this option means the LifetimeStatistics will be returned. All other parameters will be ignored. (optional)
    newest = True # bool | Selecting this option means the newest record will be returned. Use limit to select how many. (optional)

    # example passing only required values which don't have defaults set
    try:
        # Get the latest statistics for a given device
        api_response = api_instance.get_device_stats(serial_number)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->get_device_stats: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Get the latest statistics for a given device
        api_response = api_instance.get_device_stats(serial_number, start_date=start_date, end_date=end_date, offset=offset, limit=limit, lifetime=lifetime, last_only=last_only, newest=newest)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->get_device_stats: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **start_date** | **int**|  | [optional]
 **end_date** | **int**|  | [optional]
 **offset** | **int**|  | [optional]
 **limit** | **int**|  | [optional]
 **lifetime** | **bool**| Selecting this option means the LifetimeStatistics will be returned. All other parameters will be ignored. | [optional]
 **last_only** | **bool**| Selecting this option means the LifetimeStatistics will be returned. All other parameters will be ignored. | [optional]
 **newest** | **bool**| Selecting this option means the newest record will be returned. Use limit to select how many. | [optional]

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
**200** | Array of statistics for this device |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_device_status**
> DeviceStatus get_device_status(serial_number)

Get the latest status for a given device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.device_status import DeviceStatus
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get the latest status for a given device
        api_response = api_instance.get_device_status(serial_number)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->get_device_status: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |

### Return type

[**DeviceStatus**](DeviceStatus.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Status for the given device |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_rtty_session_info**
> RttySessionDetails get_rtty_session_info(serial_number)

Get the rtty parameters to initiate a session

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.rtty_session_details import RttySessionDetails
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get the rtty parameters to initiate a session
        api_response = api_instance.get_rtty_session_info(serial_number)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->get_rtty_session_info: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |

### Return type

[**RttySessionDetails**](RttySessionDetails.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Session information |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **leds_request**
> leds_request(serial_number)

Blink the LEDs on a device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.leds_request import LEDsRequest
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    leds_request = LEDsRequest(
        serial_number="serial_number_example",
        when=1,
        duration=1,
        pattern="true",
    ) # LEDsRequest | Command details (optional)

    # example passing only required values which don't have defaults set
    try:
        # Blink the LEDs on a device
        api_instance.leds_request(serial_number)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->leds_request: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Blink the LEDs on a device
        api_instance.leds_request(serial_number, leds_request=leds_request)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->leds_request: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **leds_request** | [**LEDsRequest**](LEDsRequest.md)| Command details | [optional]

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

# **message_request**
> object message_request(serial_number)

Request a specific message

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.message_request import MessageRequest
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    message_request = MessageRequest(
        serial_number="serial_number_example",
        when=1,
        message="state",
    ) # MessageRequest | Message request details (optional)

    # example passing only required values which don't have defaults set
    try:
        # Request a specific message
        api_response = api_instance.message_request(serial_number)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->message_request: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Request a specific message
        api_response = api_instance.message_request(serial_number, message_request=message_request)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->message_request: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **message_request** | [**MessageRequest**](MessageRequest.md)| Message request details | [optional]

### Return type

**object**

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | The command was submitted succesfully. |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **reboot_device**
> reboot_device(serial_number)

Upgrade a device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.reboot_request import RebootRequest
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    reboot_request = RebootRequest(
        serial_number="serial_number_example",
        when=1,
    ) # RebootRequest | Command details (optional)

    # example passing only required values which don't have defaults set
    try:
        # Upgrade a device
        api_instance.reboot_device(serial_number)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->reboot_device: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Upgrade a device
        api_instance.reboot_device(serial_number, reboot_request=reboot_request)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->reboot_device: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **reboot_request** | [**RebootRequest**](RebootRequest.md)| Command details | [optional]

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

# **trace_request**
> trace_request(serial_number)

Launch a trace for a device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.trace_request import TraceRequest
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    trace_request = TraceRequest(
        serial_number="serial_number_example",
        when=1,
        duration=1,
        number_of_packets=1,
        network="network_example",
        interface="interface_example",
    ) # TraceRequest | Command details (optional)

    # example passing only required values which don't have defaults set
    try:
        # Launch a trace for a device
        api_instance.trace_request(serial_number)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->trace_request: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Launch a trace for a device
        api_instance.trace_request(serial_number, trace_request=trace_request)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->trace_request: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **trace_request** | [**TraceRequest**](TraceRequest.md)| Command details | [optional]

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

# **update_configuration_for_a_device**
> update_configuration_for_a_device(serial_number)

Configura a device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.device_configure_request import DeviceConfigureRequest
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    device_configure_request = DeviceConfigureRequest(
        serial_number="serial_number_example",
        uuid=1,
        configuration="configuration_example",
        when=1,
    ) # DeviceConfigureRequest | Command details (optional)

    # example passing only required values which don't have defaults set
    try:
        # Configura a device
        api_instance.update_configuration_for_a_device(serial_number)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->update_configuration_for_a_device: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Configura a device
        api_instance.update_configuration_for_a_device(serial_number, device_configure_request=device_configure_request)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->update_configuration_for_a_device: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **device_configure_request** | [**DeviceConfigureRequest**](DeviceConfigureRequest.md)| Command details | [optional]

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

# **upgrade_device_firmware**
> upgrade_device_firmware(serial_number)

Upgrade a device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.upgrade_request import UpgradeRequest
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    upgrade_request = UpgradeRequest(
        uri="uri_example",
        serial_number="serial_number_example",
        when=1,
    ) # UpgradeRequest | Command details (optional)

    # example passing only required values which don't have defaults set
    try:
        # Upgrade a device
        api_instance.upgrade_device_firmware(serial_number)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->upgrade_device_firmware: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Upgrade a device
        api_instance.upgrade_device_firmware(serial_number, upgrade_request=upgrade_request)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->upgrade_device_firmware: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **upgrade_request** | [**UpgradeRequest**](UpgradeRequest.md)| Command details | [optional]

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

# **wifiscan_request**
> wifiscan_request(serial_number)

Launch a wifi scan for a device

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import commands_api
from openapi_client.model.wifi_scan_request import WifiScanRequest
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
    api_instance = commands_api.CommandsApi(api_client)
    serial_number = "serialNumber_example" # str | 
    wifi_scan_request = WifiScanRequest(
        serial_number="serial_number_example",
        verbose=True,
        active_scan=True,
        selector=,
    ) # WifiScanRequest | Scan details (optional)

    # example passing only required values which don't have defaults set
    try:
        # Launch a wifi scan for a device
        api_instance.wifiscan_request(serial_number)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->wifiscan_request: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Launch a wifi scan for a device
        api_instance.wifiscan_request(serial_number, wifi_scan_request=wifi_scan_request)
    except openapi_client.ApiException as e:
        print("Exception when calling CommandsApi->wifiscan_request: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serial_number** | **str**|  |
 **wifi_scan_request** | [**WifiScanRequest**](WifiScanRequest.md)| Scan details | [optional]

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

