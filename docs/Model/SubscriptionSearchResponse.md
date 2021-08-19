# # SubscriptionSearchResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**total** | **int** | The total number of matches for the search criteria. | [optional]
**href** | **string** | The path to the call URI that produced the current page of results. | [optional]
**next** | **string** | The URL to access the next set of results. This field includes a continuation_token. No prev field is returned, but this value is persistent during the session so that you can use it to return to the next page. This field is not returned if fewer records than specified by the limit field are returned. | [optional]
**limit** | **int** | The value of the limit parameter submitted in the request, which is the maximum number of items to return per page, from the result set. A result set is the complete set of results returned by the method. Note: Though this parameter is not required to be submitted in the request, the parameter defaults to 20 if omitted. Default: 20 | [optional]
**subscriptions** | [**\eBay\Commerce\Notification\Model\Subscription[]**](Subscription.md) | The subscriptions that match the search criteria. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
