# eBay\Commerce\Notification\SubscriptionApi

All URIs are relative to https://api.ebay.com/commerce/notification/v1.

Method | HTTP request | Description
------------- | ------------- | -------------
[**createSubscription()**](SubscriptionApi.md#createSubscription) | **POST** /subscription | 
[**deleteSubscription()**](SubscriptionApi.md#deleteSubscription) | **DELETE** /subscription/{subscription_id} | 
[**disableSubscription()**](SubscriptionApi.md#disableSubscription) | **POST** /subscription/{subscription_id}/disable | 
[**enableSubscription()**](SubscriptionApi.md#enableSubscription) | **POST** /subscription/{subscription_id}/enable | 
[**getSubscription()**](SubscriptionApi.md#getSubscription) | **GET** /subscription/{subscription_id} | 
[**getSubscriptions()**](SubscriptionApi.md#getSubscriptions) | **GET** /subscription | 
[**test()**](SubscriptionApi.md#test) | **POST** /subscription/{subscription_id}/test | 
[**updateSubscription()**](SubscriptionApi.md#updateSubscription) | **PUT** /subscription/{subscription_id} | 


## `createSubscription()`

```php
createSubscription($create_subscription_request): object
```



This method allows applications to create a subscription for a topic and supported schema version. Subscriptions allow applications to express interest in notifications and keep receiving the information relevant to their business. Each application and topic-schema pairing to a subscription should have a 1:1 cardinality. You can create the subscription in disabled mode, test it (see the test method), and when everything is ready, you can enable the subscription (see the enableSubscription method). Note: If an application is not authorized to subscribe to a topic, for example, if your authorization does not include the list of scopes required for the topic, an error code of 195011 is returned.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Commerce\Notification\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Commerce\Notification\Api\SubscriptionApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_subscription_request = new \eBay\Commerce\Notification\Model\CreateSubscriptionRequest(); // \eBay\Commerce\Notification\Model\CreateSubscriptionRequest | The create subscription request.

try {
    $result = $apiInstance->createSubscription($create_subscription_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionApi->createSubscription: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **create_subscription_request** | [**\eBay\Commerce\Notification\Model\CreateSubscriptionRequest**](../Model/CreateSubscriptionRequest.md)| The create subscription request. | [optional]

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

## `deleteSubscription()`

```php
deleteSubscription($subscription_id)
```



This method allows applications to delete a subscription. Subscriptions can be deleted regardless of status.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Commerce\Notification\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Commerce\Notification\Api\SubscriptionApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$subscription_id = 'subscription_id_example'; // string | The unique identifier for the subscription.

try {
    $apiInstance->deleteSubscription($subscription_id);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionApi->deleteSubscription: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **subscription_id** | **string**| The unique identifier for the subscription. |

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

## `disableSubscription()`

```php
disableSubscription($subscription_id)
```



This method disables a subscription, which prevents the subscription from providing notifications. To restart a subscription, call enableSubscription.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Commerce\Notification\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Commerce\Notification\Api\SubscriptionApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$subscription_id = 'subscription_id_example'; // string | The unique identifier for the subscription.

try {
    $apiInstance->disableSubscription($subscription_id);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionApi->disableSubscription: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **subscription_id** | **string**| The unique identifier for the subscription. |

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

## `enableSubscription()`

```php
enableSubscription($subscription_id)
```



This method allows applications to enable a disabled subscription. To pause (or disable) an enabled subscription, call disableSubscription.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Commerce\Notification\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Commerce\Notification\Api\SubscriptionApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$subscription_id = 'subscription_id_example'; // string | The unique identifier for the subscription.

try {
    $apiInstance->enableSubscription($subscription_id);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionApi->enableSubscription: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **subscription_id** | **string**| The unique identifier for the subscription. |

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

## `getSubscription()`

```php
getSubscription($subscription_id): \eBay\Commerce\Notification\Model\Subscription
```



This method allows applications to retrieve subscription details for the specified subscription. Specify the subscription to retrieve using the subscription_id. Use the getSubscriptions method to browse all subscriptions if you do not know the subscription_id. Subscriptions allow applications to express interest in notifications and keep receiving the information relevant to their business.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Commerce\Notification\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Commerce\Notification\Api\SubscriptionApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$subscription_id = 'subscription_id_example'; // string | The unique identifier for the subscription.

try {
    $result = $apiInstance->getSubscription($subscription_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionApi->getSubscription: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **subscription_id** | **string**| The unique identifier for the subscription. |

### Return type

[**\eBay\Commerce\Notification\Model\Subscription**](../Model/Subscription.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getSubscriptions()`

```php
getSubscriptions($limit, $continuation_token): \eBay\Commerce\Notification\Model\SubscriptionSearchResponse
```



This method allows applications to retrieve a list of all subscriptions. The list returned is a paginated collection of subscription resources. Subscriptions allow applications to express interest in notifications and keep receiving the information relevant to their business.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Commerce\Notification\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Commerce\Notification\Api\SubscriptionApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$limit = 'limit_example'; // string | The number of items, from the result set, returned in a single page. Range is from 10-100. If this parameter is omitted, the default value is used. Default: 20 Maximum: 100 items per page
$continuation_token = 'continuation_token_example'; // string | The continuation token for the next set of results.

try {
    $result = $apiInstance->getSubscriptions($limit, $continuation_token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionApi->getSubscriptions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **string**| The number of items, from the result set, returned in a single page. Range is from 10-100. If this parameter is omitted, the default value is used. Default: 20 Maximum: 100 items per page | [optional]
 **continuation_token** | **string**| The continuation token for the next set of results. | [optional]

### Return type

[**\eBay\Commerce\Notification\Model\SubscriptionSearchResponse**](../Model/SubscriptionSearchResponse.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `test()`

```php
test($subscription_id)
```



This method triggers a mocked test payload that includes a notification ID, publish date, and so on. Use this method to test your subscription end-to-end. You can create the subscription in disabled mode, test it using this method, and when everything is ready, you can enable the subscription (see the enableSubscription method). Note: Use the notificationId to tell the difference between a test payload and a real payload.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Commerce\Notification\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Commerce\Notification\Api\SubscriptionApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$subscription_id = 'subscription_id_example'; // string | The unique identifier for the subscription.

try {
    $apiInstance->test($subscription_id);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionApi->test: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **subscription_id** | **string**| The unique identifier for the subscription. |

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

## `updateSubscription()`

```php
updateSubscription($subscription_id, $update_subscription_request)
```



This method allows applications to update a subscription. Subscriptions allow applications to express interest in notifications and keep receiving the information relevant to their business. Note: This call returns an error if an application is not authorized to subscribe to a topic. You can pause and restart a subscription. See the disableSubscription and enableSubscription methods.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Commerce\Notification\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Commerce\Notification\Api\SubscriptionApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$subscription_id = 'subscription_id_example'; // string | The unique identifier for the subscription.
$update_subscription_request = new \eBay\Commerce\Notification\Model\UpdateSubscriptionRequest(); // \eBay\Commerce\Notification\Model\UpdateSubscriptionRequest | The create subscription request.

try {
    $apiInstance->updateSubscription($subscription_id, $update_subscription_request);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionApi->updateSubscription: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **subscription_id** | **string**| The unique identifier for the subscription. |
 **update_subscription_request** | [**\eBay\Commerce\Notification\Model\UpdateSubscriptionRequest**](../Model/UpdateSubscriptionRequest.md)| The create subscription request. | [optional]

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
