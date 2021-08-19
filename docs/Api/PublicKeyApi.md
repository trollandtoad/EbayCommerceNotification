# eBay\Commerce\Notification\PublicKeyApi

All URIs are relative to https://api.ebay.com/commerce/notification/v1.

Method | HTTP request | Description
------------- | ------------- | -------------
[**getPublicKey()**](PublicKeyApi.md#getPublicKey) | **GET** /public_key/{public_key_id} | 


## `getPublicKey()`

```php
getPublicKey($public_key_id): \eBay\Commerce\Notification\Model\PublicKey
```



This method allows users to retrieve a public key using a specified key ID. The public key that is returned in the response payload is used to process and validate eBay notifications. The public key ID, which is a required request parameter for this method, is retrieved from the Base64-encoded X-EBAY-SIGNATURE header that is included in the eBay notification. Note: For more details about how to process eBay push notifications and validate notification message payloads, see the Notification API overview.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Commerce\Notification\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Commerce\Notification\Api\PublicKeyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$public_key_id = 'public_key_id_example'; // string | The unique key ID that is used to retrieve the public key. Note: This is retrieved from the X-EBAY-SIGNATURE header that is included with the push notification.

try {
    $result = $apiInstance->getPublicKey($public_key_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PublicKeyApi->getPublicKey: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **public_key_id** | **string**| The unique key ID that is used to retrieve the public key. Note: This is retrieved from the X-EBAY-SIGNATURE header that is included with the push notification. |

### Return type

[**\eBay\Commerce\Notification\Model\PublicKey**](../Model/PublicKey.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
