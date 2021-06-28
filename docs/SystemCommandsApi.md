# openapi_client.SystemCommandsApi

All URIs are relative to *https://localhost:16001/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**system_command**](SystemCommandsApi.md#system_command) | **POST** /system | Perform some systeme wide commands


# **system_command**
> SystemCommandResults system_command()

Perform some systeme wide commands

### Example

* Api Key Authentication (ApiKeyAuth):
* Bearer (JWT) Authentication (bearerAuth):
```python
import time
import openapi_client
from openapi_client.api import system_commands_api
from openapi_client.model.system_command_details import SystemCommandDetails
from openapi_client.model.generic_error_response import GenericErrorResponse
from openapi_client.model.system_command_results import SystemCommandResults
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
    api_instance = system_commands_api.SystemCommandsApi(api_client)
    system_command_details = SystemCommandDetails(
        command="setloglevels",
        parameters=,
    ) # SystemCommandDetails | Command details (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Perform some systeme wide commands
        api_response = api_instance.system_command(system_command_details=system_command_details)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling SystemCommandsApi->system_command: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **system_command_details** | [**SystemCommandDetails**](SystemCommandDetails.md)| Command details | [optional]

### Return type

[**SystemCommandResults**](SystemCommandResults.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successfull command execution |  -  |
**403** | The requested does not have sufficient rights to perform the operation. |  -  |
**404** | The specified resource was not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

