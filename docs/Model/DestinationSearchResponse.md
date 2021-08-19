# # DestinationSearchResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**total** | **int** | The total number of matches for the search criteria. | [optional]
**href** | **string** | The path to the call URI that produced the current page of results. | [optional]
**next** | **string** | The URL to access the next set of results. This field includes a continuation_token. No prev field is returned, but this value is persistent during the session so that you can use it to return to the next page. This field is not returned if fewer records than specified by the limit field are returned. | [optional]
**limit** | **int** | The number of records to show in the current response. Default: 20 | [optional]
**destinations** | [**\eBay\Commerce\Notification\Model\Destination[]**](Destination.md) | An array that contains the destination details. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
