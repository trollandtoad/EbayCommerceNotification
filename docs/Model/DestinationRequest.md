# # DestinationRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | The name associated with this destination. | [optional]
**status** | **string** | The status for this destination. Note: The MARKED_DOWN value is set by eBay systems and cannot be used in a create or update call by applications. Valid values: ENABLED DISABLED MARKED_DOWN For implementation help, refer to &lt;a href&#x3D;&#39;https://developer.ebay.com/api-docs/commerce/notification/types/api:DestinationStatusEnum&#39;&gt;eBay API documentation&lt;/a&gt; | [optional]
**delivery_config** | [**\eBay\Commerce\Notification\Model\DeliveryConfig**](DeliveryConfig.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
