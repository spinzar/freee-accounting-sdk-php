# Freee\Accounting\SegmentTagsApi

All URIs are relative to *https://api.freee.co.jp*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createSegmentTag**](SegmentTagsApi.md#createSegmentTag) | **POST** /api/1/segments/{segment_id}/tags | セグメントの作成
[**destroySegmentsTag**](SegmentTagsApi.md#destroySegmentsTag) | **DELETE** /api/1/segments/{segment_id}/tags/{id} | セグメントタグの削除
[**getSegmentTags**](SegmentTagsApi.md#getSegmentTags) | **GET** /api/1/segments/{segment_id}/tags | セグメントタグ一覧の取得
[**updateSegmentTag**](SegmentTagsApi.md#updateSegmentTag) | **PUT** /api/1/segments/{segment_id}/tags/{id} | セグメントタグの更新



## createSegmentTag

> \Freee\Accounting\Model\SegmentTagResponse createSegmentTag($segment_id, $segment_tag_params)

セグメントの作成

<h2 id=\"\">概要</h2>  <p>指定した事業所のセグメントタグを作成する</p>  <h2 id=\"\">注意点</h2>  <ul>  <li>本APIは法人向けのプロフェッショナルプラン以上で利用可能です。利用可能なセグメントの数は、法人向けのプロフェッショナルプランの場合は1つ、エンタープライズプランの場合は3つです。</li>  </ul>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: oauth2
$config = Freee\Accounting\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Freee\Accounting\Api\SegmentTagsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$segment_id = 56; // int | セグメントID（1,2,3のいずれか） 該当プラン以外で参照した場合にはエラーとなります。   1: 法人向けプロフェッショナル, 法人向けエンタープライズプラン   2,3: 法人向け エンタープライズプラン
$segment_tag_params = new \Freee\Accounting\Model\SegmentTagParams(); // \Freee\Accounting\Model\SegmentTagParams | セグメントタグの作成

try {
    $result = $apiInstance->createSegmentTag($segment_id, $segment_tag_params);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SegmentTagsApi->createSegmentTag: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **segment_id** | **int**| セグメントID（1,2,3のいずれか） 該当プラン以外で参照した場合にはエラーとなります。   1: 法人向けプロフェッショナル, 法人向けエンタープライズプラン   2,3: 法人向け エンタープライズプラン |
 **segment_tag_params** | [**\Freee\Accounting\Model\SegmentTagParams**](../Model/SegmentTagParams.md)| セグメントタグの作成 |

### Return type

[**\Freee\Accounting\Model\SegmentTagResponse**](../Model/SegmentTagResponse.md)

### Authorization

[oauth2](../../README.md#oauth2)

### HTTP request headers

- **Content-Type**: application/json, application/x-www-form-urlencoded
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## destroySegmentsTag

> destroySegmentsTag($segment_id, $id, $company_id)

セグメントタグの削除

<h2 id=\"\">概要</h2>  <p>指定した事業所のセグメントタグを削除する</p>  <h2 id=\"\">注意点</h2>  <ul>  <li>本APIは法人向けのプロフェッショナルプラン以上で利用可能です。利用可能なセグメントの数は、法人向けのプロフェッショナルプランの場合は1つ、エンタープライズプランの場合は3つです。</li>  </ul>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: oauth2
$config = Freee\Accounting\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Freee\Accounting\Api\SegmentTagsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$segment_id = 56; // int | セグメントID（1,2,3のいずれか） 該当プラン以外で参照した場合にはエラーとなります。   1: 法人向けプロフェッショナル, 法人向けエンタープライズプラン   2,3: 法人向け エンタープライズプラン
$id = 56; // int | セグメントタグID
$company_id = 56; // int | 事業所ID

try {
    $apiInstance->destroySegmentsTag($segment_id, $id, $company_id);
} catch (Exception $e) {
    echo 'Exception when calling SegmentTagsApi->destroySegmentsTag: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **segment_id** | **int**| セグメントID（1,2,3のいずれか） 該当プラン以外で参照した場合にはエラーとなります。   1: 法人向けプロフェッショナル, 法人向けエンタープライズプラン   2,3: 法人向け エンタープライズプラン |
 **id** | **int**| セグメントタグID |
 **company_id** | **int**| 事業所ID |

### Return type

void (empty response body)

### Authorization

[oauth2](../../README.md#oauth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getSegmentTags

> \Freee\Accounting\Model\InlineResponse20010 getSegmentTags($company_id, $segment_id, $offset, $limit)

セグメントタグ一覧の取得

<h2 id=\"\">概要</h2>  <p>指定した事業所のセグメントタグ一覧を取得する</p>  <h2 id=\"\">注意点</h2>  <ul>  <li>本APIは法人向けのプロフェッショナルプラン以上で利用可能です。利用可能なセグメントの数は、法人向けのプロフェッショナルプランの場合は1つ、エンタープライズプランの場合は3つです。</li>  </ul>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: oauth2
$config = Freee\Accounting\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Freee\Accounting\Api\SegmentTagsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$company_id = 56; // int | 事業所ID
$segment_id = 56; // int | セグメントID（1,2,3のいずれか） 該当プラン以外で参照した場合にはエラーとなります。   1: 法人向けプロフェッショナル, 法人向けエンタープライズプラン   2,3: 法人向け エンタープライズプラン
$offset = 56; // int | 取得レコードのオフセット (デフォルト: 0)
$limit = 56; // int | 取得レコードの件数 (デフォルト: 20, 最小: 1, 最大: 500)

try {
    $result = $apiInstance->getSegmentTags($company_id, $segment_id, $offset, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SegmentTagsApi->getSegmentTags: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **company_id** | **int**| 事業所ID |
 **segment_id** | **int**| セグメントID（1,2,3のいずれか） 該当プラン以外で参照した場合にはエラーとなります。   1: 法人向けプロフェッショナル, 法人向けエンタープライズプラン   2,3: 法人向け エンタープライズプラン |
 **offset** | **int**| 取得レコードのオフセット (デフォルト: 0) | [optional]
 **limit** | **int**| 取得レコードの件数 (デフォルト: 20, 最小: 1, 最大: 500) | [optional]

### Return type

[**\Freee\Accounting\Model\InlineResponse20010**](../Model/InlineResponse20010.md)

### Authorization

[oauth2](../../README.md#oauth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## updateSegmentTag

> \Freee\Accounting\Model\SegmentTagResponse updateSegmentTag($segment_id, $id, $segment_tag_params)

セグメントタグの更新

<h2 id=\"\">概要</h2>  <p>指定した事業所のセグメントタグを更新する</p>  <h2 id=\"\">注意点</h2>  <ul>  <li>本APIは法人向けのプロフェッショナルプラン以上で利用可能です。利用可能なセグメントの数は、法人向けのプロフェッショナルプランの場合は1つ、エンタープライズプランの場合は3つです。</li>  </ul>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: oauth2
$config = Freee\Accounting\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Freee\Accounting\Api\SegmentTagsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$segment_id = 56; // int | セグメントID（1,2,3のいずれか） 該当プラン以外で参照した場合にはエラーとなります。   1: 法人向けプロフェッショナル, 法人向けエンタープライズプラン   2,3: 法人向け エンタープライズプラン
$id = 56; // int | セグメントタグID
$segment_tag_params = new \Freee\Accounting\Model\SegmentTagParams(); // \Freee\Accounting\Model\SegmentTagParams | セグメントタグの作成

try {
    $result = $apiInstance->updateSegmentTag($segment_id, $id, $segment_tag_params);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SegmentTagsApi->updateSegmentTag: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **segment_id** | **int**| セグメントID（1,2,3のいずれか） 該当プラン以外で参照した場合にはエラーとなります。   1: 法人向けプロフェッショナル, 法人向けエンタープライズプラン   2,3: 法人向け エンタープライズプラン |
 **id** | **int**| セグメントタグID |
 **segment_tag_params** | [**\Freee\Accounting\Model\SegmentTagParams**](../Model/SegmentTagParams.md)| セグメントタグの作成 |

### Return type

[**\Freee\Accounting\Model\SegmentTagResponse**](../Model/SegmentTagResponse.md)

### Authorization

[oauth2](../../README.md#oauth2)

### HTTP request headers

- **Content-Type**: application/json, application/x-www-form-urlencoded
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)

