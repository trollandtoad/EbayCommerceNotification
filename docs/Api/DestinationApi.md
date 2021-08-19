# eBay\Commerce\Notification\DestinationApi

All URIs are relative to https://api.ebay.com/commerce/notification/v1.

Method | HTTP request | Description
------------- | ------------- | -------------
[**createDestination()**](DestinationApi.md#createDestination) | **POST** /destination | 
[**deleteDestination()**](DestinationApi.md#deleteDestination) | **DELETE** /destination/{destination_id} | 
[**getDestination()**](DestinationApi.md#getDestination) | **GET** /destination/{destination_id} | 
[**getDestinations()**](DestinationApi.md#getDestinations) | **GET** /destination | 
[**updateDestination()**](DestinationApi.md#updateDestination) | **PUT** /destination/{destination_id} | 


## `createDestination()`

```php
createDestination($destination_request): object
```



This method allows applications to create a destination. A destination is an endpoint that receives HTTP push notifications. A single destination for all topics is valid, as is individual destinations for each topic. To update a destination, use the updateDestination call. The destination created will need to be referenced while creating or updating a subscription to a topic. Note: The destination should be created and ready to respond with the expected challengeResponse for the endpoint to be registered successfully. Refer to the Notification API overview for more information.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Commerce\Notification\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Commerce\Notification\Api\DestinationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$destination_request = new \eBay\Commerce\Notification\Model\DestinationRequest(); // \eBay\Commerce\Notification\Model\DestinationRequest | The create destination request.

try {
    $result = $apiInstance->createDestination($destination_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DestinationApi->createDestination: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **destination_request** | [**\eBay\Commerce\Notification\Model\DestinationRequest**](../Model/DestinationRequest.md)| The create destination request. | [optional]

### Return type

**object**

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteDestination()`

```php
deleteDestination($destination_id)
```



This method provides applications a way to delete a destination. The same destination ID can be used by many destinations. Trying to delete an active destination results in an error. You can disable a subscription, and when the destination is no longer in use, you can delete it.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Commerce\Notification\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Commerce\Notification\Api\DestinationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$destination_id = 'destination_id_example'; // string | The unique identifier for the destination.

try {
    $apiInstance->deleteDestination($destination_id);
} catch (Exception $e) {
    echo 'Exception when calling DestinationApi->deleteDestination: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **destination_id** | **string**| The unique identifier for the destination. |

### Return type

void (empty response body)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getDestination()`

```php
getDestination($destination_id): \eBay\Commerce\Notification\Model\Destination
```



This method allows applications to fetch the details for a destination. The details include the destination name, status, and configuration, including the endpoint and verification token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Commerce\Notification\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Commerce\Notification\Api\DestinationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$destination_id = 'destination_id_example'; // string | The unique identifier for the destination.

try {
    $result = $apiInstance->getDestination($destination_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DestinationApi->getDestination: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **destination_id** | **string**| The unique identifier for the destination. |

### Return type

[**\eBay\Commerce\Notification\Model\Destination**](../Model/Destination.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getDestinations()`

```php
getDestinations($limit, $continuation_token): \eBay\Commerce\Notification\Model\DestinationSearchResponse
```



This method allows applications to retrieve a paginated collection of destination resources and related details. The details include the destination names, statuses, and configurations, including the endpoints and verification tokens.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Commerce\Notification\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Commerce\Notification\Api\DestinationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$limit = 'limit_example'; // string | The number of items, from the result set, returned in a single page. Range is from 10-100. If this parameter is omitted, the default value is used. Default: 20 Maximum: 100 items per page
$continuation_token = 'continuation_token_example'; // string | The continuation token for the next set of results.

try {
    $result = $apiInstance->getDestinations($limit, $continuation_token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DestinationApi->getDestinations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **string**| The number of items, from the result set, returned in a single page. Range is from 10-100. If this parameter is omitted, the default value is used. Default: 20 Maximum: 100 items per page | [optional]
 **continuation_token** | **string**| The continuation token for the next set of results. | [optional]

### Return type

[**\eBay\Commerce\Notification\Model\DestinationSearchResponse**](../Model/DestinationSearchResponse.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateDestination()`

```php
updateDestination($destination_id, $destination_request)
```



This method allows applications to update a destination. Note: The destination should be created and ready to respond with the expected challengeResponse for the endpoint to be registered successfully. Refer to the Notification API overview for more information.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Commerce\Notification\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Commerce\Notification\Api\DestinationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$destination_id = 'destination_id_example'; // string | The unique identifier for the destination.
$destination_request = new \eBay\Commerce\Notification\Model\DestinationRequest(); // \eBay\Commerce\Notification\Model\DestinationRequest | The create subscription request.

try {
    $apiInstance->updateDestination($destination_id, $destination_request);
} catch (Exception $e) {
    echo 'Exception when calling DestinationApi->updateDestination: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **destination_id** | **string**| The unique identifier for the destination. |
 **destination_request** | [**\eBay\Commerce\Notification\Model\DestinationRequest**](../Model/DestinationRequest.md)| The create subscription request. | [optional]

### Return type

void (empty response body)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
