# t(:unified_margin_account_data)
t(:unified_margin_account_para)

## t(:order)
### t(:dv_placeOrder)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/unified/v3/private/order/create' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 27ecc5cca2aec6a779c9f5ef828275a3e9ccaf392a030820911c52d6085c34db' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657871228347' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol": "BTCUSDT",
    "orderType": "Limit",
    "side": "Buy",
    "qty": "0.01",
    "price": "20002",
    "timeInForce": "GoodTillCancel",
    "category": "linear"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "orderId": "e10b0716-7c91-4091-b98a-1fa0f401c7d5",
        "orderLinkId": "test0000003"
    },
    "retExtInfo": {},
    "time": 1664441344238
}
```

t(:account_para_placeActive_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/unified/v3/private/order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side_v3)    |
|positionIdx |false |string |t(:row_comment_positionIdx_um)   |
|<a href="#order-type-ordertype">orderType</a> |<b>true</b> |string |t(:row_comment_orderType_v3)   |
|t(:row_parameter_quantity) |<b>true</b> |string |t(:row_comment_qty_v3) |
|t(:row_parameter_price) |false |string |t(:row_comment_resp_price) |
|basePrice |false |string |t(:row_comment_basePrice_v3) |
|triggerPrice |false |string |t(:row_comment_triggerPrice) |
|<a href="#trigger-price-type-triggerby">triggerBy</a> |false |string |t(:row_comment_triggerBy_v3) |
|orderIv |false |string |t(:row_comment_iv_v3) |
|<a href="#time-in-force-timeinforce">timeInForce</a> |<b>true</b> |string |t(:row_comment_timeInForce_v3) |
|orderLinkId |false |string |t(:row_comment_orderLinkId_um) |
|takeProfit |false |string |t(:row_comment_takeProfit_v3) |
|stopLoss |false |string |t(:row_comment_stopLoss_v3) |
|tpTriggerBy |false |string |t(:account_row_comment_tp_trigger_by_v3) |
|slTriggerBy |false |string |t(:account_row_comment_sl_trigger_by_v3) |
|reduceOnly |false |bool |t(:row_comment_reduceOnly_v3) |
|closeOnTrigger |false |bool |t(:row_comment_closeOnTrigger_v3) |
|mmp |false |bool |t(:row_comment_mmp_v3) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments) |
|:----- |:-----|----- |
|orderId |string |t(:row_comment_order_id) |
|orderLinkId |string |t(:row_comment_orderLinkId_response_v3) |


### t(:dv_replaceOrder)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/unified/v3/private/order/replace' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 27ecc5cca2aec6a779c9f5ef828275a3e9ccaf392a030820911c52d6085c34db' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657871228347' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "category": "linear",
    "symbol":"BTCUSDT",
    "orderId":"1a1ae001-2034-4a6b-8b25-45aa9100b1ec",
    "price":"35000"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
    "orderId": "42c86d66331e41998d12c2440ce90c1a", 
    "orderLinkId": "e80d558e-ed"
  }
}
```

t(:account_para_replaceActive_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoReplace>/unified/v3/private/order/replace</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|orderId |false |string |t(:row_comment_orderId_replace) |
|orderLinkId |false |string |t(:row_comment_orderLinkId_replace) |
|<a href="#order-filter-orderfilter">orderFilter</a> |false |string |t(:row_comment_orderFilter_v3)   |
|orderIv |false |string |t(:row_comment_iv_v3) |
|triggerPrice |false |string |t(:row_comment_triggerPrice_replace_v3) |
|t(:row_parameter_quantity) |false |string |t(:row_comment_qty_replace_v3) |
|t(:row_parameter_price) |false |string |t(:row_comment_price_replace_v3) |
|takeProfit |false |string |t(:row_comment_takeProfit_replace_v3) |
|stopLoss |false |string |t(:row_comment_stopLoss_replace_v3) |
|tpTriggerBy |false |string |t(:account_row_comment_tp_trigger_by_v3) |
|slTriggerBy |false |string |t(:account_row_comment_sl_trigger_by_v3) |
|<a href="#trigger-price-type-triggerby">triggerBy</a> |false |string |t(:row_comment_triggerBy_v3) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId |string |t(:row_comment_order_id) |
|orderLinkId |string |t(:row_comment_orderLinkId_response_v3) |


### t(:dv_cancelOrder)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/unified/v3/private/order/cancel' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 27ecc5cca2aec6a779c9f5ef828275a3e9ccaf392a030820911c52d6085c34db' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657871228347' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
  "category": "linear",
  "orderId": "4c51a45f-7795-4b38-9b66-3c306b73f112",
  "symbol": "BTCUSDT"
}'
```

```python--pybit

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "orderId": "42c86d66331e41998d12c2440ce90c1a",
        "orderLinkId": "e80d558e-ed"
    }
}
```

t(:account_para_cancelActive_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCancel>/unified/v3/private/order/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|orderId |false |string |t(:row_comment_orderId_v3_post) |
|orderLinkId |false |string |t(:row_comment_orderLinkId_v3_post) |
|<a href="#order-filter-orderfilter">orderFilter</a> |false |string |t(:row_comment_orderFilter_v3)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId |string |t(:row_comment_order_id) |
|orderLinkId |string |t(:row_comment_orderLinkId_response_v3) |


### t(:dv_queryOrderRealtime)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/unified/v3/private/order/unfilled-orders?category=linear' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 27ecc5cca2aec6a779c9f5ef828275a3e9ccaf392a030820911c52d6085c34db' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657871228347' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw ''
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "Success",
    "result": {
        "nextPageCursor": "135ccc0d-8136-4e1b-8af3-07b11ee158d1%3A1665565610526%2C135ccc0d-8136-4e1b-8af3-07b11ee158d1%3A1665565610526",
        "category": "linear",
        "list": [
            {
                "symbol": "ETHUSDT",
                "orderType": "Limit",
                "orderLinkId": "test0000005",
                "orderId": "135ccc0d-8136-4e1b-8af3-07b11ee158d1",
                "stopOrderType": "UNKNOWN",
                "orderStatus": "New",
                "takeProfit": "",
                "cumExecValue": "0.00000000",
                "blockTradeId": "",
                "price": "700.00000000",
                "createdTime": 1665565610526,
                "tpTriggerBy": "UNKNOWN",
                "timeInForce": "GoodTillCancel",
                "basePrice": "",
                "updatedTime": 1665565610533,
                "side": "Buy",
                "triggerPrice": "",
                "cumExecFee": "0.00000000",
                "slTriggerBy": "UNKNOWN",
                "leavesQty": "0.1000",
                "closeOnTrigger": false,
                "cumExecQty": "0.00000000",
                "reduceOnly": false,
                "qty": "0.1000",
                "stopLoss": "",
                "triggerBy": "UNKNOWN",
                "orderIM": ""
            }
        ]
    },
    "retExtInfo": {},
    "time": 1665565614320
}
```
t(:account_para_queryActive_v3)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpOrder>/unified/v3/private/order/unfilled-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |false |string |t(:row_comment_symbol_v3)   |
|baseCoin |false |string |t(:unified_baseCoin_param)   |
|orderId |false |string |t(:row_comment_query_orderId_v3) |
|orderLinkId |false |string |t(:row_comment_query_orderLinkId_v3) |
|<a href="#order-filter-orderfilter">orderFilter</a> |false |string |t(:row_comment_orderFilter_v3)   |
|direction |false |string |t(:row_comment_direction_v3)   |
|limit |false |number |t(:row_comment_limit_v3)   |
|cursor |false |string |t(:row_comment_cursor_v3)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3)    |
|list> symbol |string |t(:row_comment_symbol_v3)   |
|list> orderType |string |t(:row_comment_query_orderType_v3)  |
|list> orderLinkId |string |t(:row_comment_query_orderLinkId_v3)  |
|list> orderId |string |t(:row_comment_query_orderId_v3) |
|list> stopOrderType |string |t(:row_comment_query_stopOrderType_v3)  |
|list > orderStatus |string |t(:row_comment_query_orderStatus_v3)  |
|list > takeProfit |string |t(:row_comment_query_takeProfit_v3)  |
|list > cumExecValue |string |t(:cumExecValue)  |
|list > blockTradeId |string |t(:blockTradeId)  |
|list> price |string |t(:row_comment_query_price_v3)  |
|list > createdTime |number |t(:row_comment_query_createdTime_v3)  |
|list > tpTriggerBy |string |t(:row_comment_query_tpTriggerBy_v3)  |
|list > timeInForce |string |t(:row_comment_query_timeInForce_v3)  |
|list > basePrice |string |t(:row_comment_query_basePrice_v3)  |
|list > updatedTime |number |t(:row_comment_query_updatedTime_v3)  |
|list> side |string |t(:row_comment_query_side_v3)  |
|list > triggerPrice |string |t(:row_comment_query_triggerPrice_v3)  |
|list > cumExecFee |string |t(:cumExecFee)  |
|list > slTriggerBy |string |t(:row_comment_query_slTriggerBy_v3)  |
|list > leavesQty |string |t(:leavesQty)  |
|list > closeOnTrigger |bool |t(:row_comment_query_closeOnTrigger_v3)  |
|list > cumExecQty |string |t(:cumExecQty)  |
|list > reduceOnly |bool |t(:row_comment_query_reduceOnly_v3)  |
|list> qty |string |t(:row_comment_query_qty_v3)  |
|list > stopLoss |string |t(:row_comment_query_stopLoss_v3)  |
|list > triggerBy |string |t(:row_comment_query_triggerBy_v3)  |
|list > orderIM |string |t(:row_comment_query_orderIM_v3)  |
|list> iv |string |t(:row_comment_query_iv_v3)  |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |


### t(:dv_getOrder)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/unified/v3/private/order/list?category=linear&symbol=BTCUSDT&limit=10' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 27ecc5cca2aec6a779c9f5ef828275a3e9ccaf392a030820911c52d6085c34db' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657871228347' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw ''
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

{
  "retCode": 0,
  "retMsg": "Success",
  "result": {
  "nextPageCursor": "7d17d359-4e38-4d3a-9a31-29791ef2dfd7%3A1657711949928%2C7d17d359-4e38-4d3a-9a31-29791ef2dfd7%3A1657711949928",
    "category": "linear",
    "list": [
    {
      "symbol": "ETHUSDT",
      "orderType": "Market",
      "orderLinkId": "",
      "orderId": "7d17d359-4e38-4d3a-9a31-29791ef2dfd7",
      "stopOrderType": "UNKNOWN",
      "orderStatus": "Filled",
      "takeProfit": "",
      "cumExecValue": "536.92500000",
      "blockTradeId": "",
      "rejectReason": "EC_NoError",
      "price": "1127.10000000",
      "createdTime": 1657711949928,
      "tpTriggerBy": "UNKNOWN",
      "timeInForce": "ImmediateOrCancel",
      "basePrice": "",
      "leavesValue": "0.00000000",
      "updatedTime": 1657711949945,
      "side": "Buy",
      "triggerPrice": "",
      "cumExecFee": "0.32215500",
      "slTriggerBy": "UNKNOWN",
      "leavesQty": "0.0000",
      "closeOnTrigger": false,
      "cumExecQty": "0.5000",
      "reduceOnly": false,
      "qty": "0.5000",
      "stopLoss": "",
      "triggerBy": "UNKNOWN",
      "orderIM": ""
    }
  ]
},
  "time": 1657713451741
}

```

t(:account_para_getActive_v3)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoList>/unified/v3/private/order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |false |string |t(:row_comment_symbol_v3)   |
|baseCoin |false |string |t(:unified_baseCoin_param_2)   |
|orderId |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|orderStatus |false |string |t(:orderStatus_v3)   |
|<a href="#order-filter-orderfilter">orderFilter</a> |false |string |t(:row_comment_orderFilter_v3)   |
|direction |false |string |t(:row_comment_direction_v3)   |
|limit |false |number |t(:row_comment_limit_v3)   |
|cursor |false |string |t(:row_comment_cursor_v3)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3)    |
|list> symbol |string |t(:row_comment_symbol_v3)   |
|list> side |string |t(:row_comment_query_side_v3)  |
|list> orderType |string |t(:row_comment_query_orderType_v3)  |
|list> price |string |t(:row_comment_query_price_v3)  |
|list> qty |string |t(:row_comment_query_qty_v3)  |
|list> iv |string |t(:row_comment_query_iv_v3)  |
|list > orderIM |string |t(:row_comment_query_orderIM_v3)  |
|list > reduceOnly |bool |t(:row_comment_query_reduceOnly_v3)  |
|list > timeInForce |string |t(:row_comment_query_timeInForce_v3)  |
|list > orderStatus |string |t(:row_comment_query_orderStatus_v3)  |
|list > leavesQty |string |t(:row_comment_query_leavesQty_v3)  |
|list > leavesValue |string |t(:row_comment_query_leavesValue_v3)  |
|list > cumExecQty |string |t(:row_comment_query_cumExecQty_v3)  |
|list > cumExecValue |string |t(:row_comment_query_cumExecValue_v3)  |
|list > cumExecFee |string |t(:row_comment_query_cumExecFee_v3)  |
|list > basePrice |string |t(:row_comment_query_basePrice_v3)  |
|list > rejectReason |string |t(:row_comment_query_rejectReason_v3)  |
|list > orderLinkId |string |t(:row_comment_query_orderLinkId_v3)  |
|list > createdTime |number |t(:row_comment_query_createdTime_v3)  |
|list > updatedTime |number |t(:row_comment_query_updatedTime_v3)  |
|list> orderId |string |t(:row_comment_query_orderId_v3) |
|list> stopOrderType |string |t(:row_comment_query_stopOrderType_v3)  |
|list > takeProfit |string |t(:row_comment_query_takeProfit_v3)  |
|list > stopLoss |string |t(:row_comment_query_stopLoss_v3)  |
|list > triggerPrice |string |t(:row_comment_query_triggerPrice_v3)  |
|list > tpTriggerBy |string |t(:row_comment_query_tpTriggerBy_v3)  |
|list > slTriggerBy |string |t(:row_comment_query_slTriggerBy_v3)  |
|list > closeOnTrigger |bool |t(:row_comment_query_closeOnTrigger_v3)  |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |

### t(:dv_batchPlaceOrder)

```console
curl --location --request POST 'https://api-testnet.bybit.com/unified/v3/private/order/create-batch' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: c5cab33771ca6ccfcddb27e1cd41ffd355929b1a5025a4fc218030decca8f9b9' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1658210743423' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json \
--data-raw '{
    "category": "option",
    "request": [
        {
            "symbol": "BTC-19JUL22-25000-C",
            "orderType": "Limit",
            "side": "Buy",
            "qty": "0.01",
            "price": "5",
            "timeInForce": "GoodTillCancel",
            "orderLinkId": "316732a14",
            "reduceOnly": false
        },
        {
            "symbol": "BTC-19JUL22-25000-C",
            "orderType": "Limit",
            "side": "Buy",
            "qty": "0.01",
            "price": "5",
            "timeInForce": "GoodTillCancel",
            "orderLinkId": "316732a15",
            "reduceOnly": false
        }
    ]
}'
```

```python

```

> t(:codequote_responseExample)

```javascript

{
    "retCode": 0, 
    "retMsg": "OK",
    "result": {
    "list": [{
      "category": "option",
      "symbol": "BTC-24JUN22-45000-P",
      "orderId": "",
      "orderLinkId": "ac4e3b34-d64d-4b60-8188-438fbea4c552",
      "createAt": "0"
      }, {
      "category": "option",
      "symbol": "BTC-26AUG22-44000-C",
      "orderId": "",
      "orderLinkId": "5cee727a-2af8-430e-a293-42895e594d18",
      "createAt": "0"
      }]
    },
     "retExtInfo": {
     "list": [{
        "code": 10001,
        "msg": "BTC-24JUN22-45000-P does not exist."
      }, {
        "code": 10001,
        "msg": "Invalid order direction."
      }]
      },
     "time": 1657200736570
}

```

t(:usdcBatchOrdersDescV3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvBatchPlace>/unified/v3/private/order/create-batch</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvBatchPlace"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:dv_category)t(:dv_categorySuffix_4)    |
|request |<b>true</b> |array |    |
|list> symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|list> t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side_v3)    |
|list> positionIdx |false |string |t(:row_comment_positionIdx_um)   |
|list> <a href="#order-type-ordertype">orderType</a> |<b>true</b> |string |t(:row_comment_orderType_v3)   |
|list> t(:row_parameter_quantity) |<b>true</b> |string |t(:row_comment_qty_v3) |
|list> t(:row_parameter_price) |false |string |t(:row_comment_resp_price) |
|list> orderIv |false |string |t(:row_comment_iv_v3) |
|list> <a href="#time-in-force-timeinforce">timeInForce</a> |<b>true</b> |string |t(:row_comment_timeInForce_v3) |
|list> orderLinkId |false |string |t(:row_comment_orderLinkId_um) |
|list> reduceOnly |false |bool |t(:row_comment_reduceOnly_v3) |
|list> closeOnTrigger |false |bool |t(:row_comment_closeOnTrigger_v3) |
|list> mmp |false |bool |t(:row_comment_mmp_v3) |


<p class="fake_header">t(:responseparameters)</p>
<p>result：</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> category |string |t(:dv_category)t(:dv_categorySuffix_4) |
|list> symbol |string |t(:row_comment_symbol_v3) |
|list> orderId |string |t(:row_comment_query_orderId_v3) |
|list> orderLinkId |string |t(:row_comment_orderLinkId_response_v3) |
|list> createAt |string |t(:row_comment_createAt_response_v3) |

<p>retExtInfo：</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> code |string |t(:row_comment_code_response_v3) |
|list> msg |string |t(:row_comment_msg_response_v3) |



### t(:dv_batchReplaceOrders)

t(:usdcBatchReplaceOrdersDescV3)

```console
curl --location --request POST 'https://api-testnet.bybit.com/unified/v3/private/order/replace-batch' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 27ecc5cca2aec6a779c9f5ef828275a3e9ccaf392a030820911c52d6085c34db' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657871228347' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "category": "option",
    "request": [
        {
            "symbol": "BTC-24JUN22-45000-P",
            "orderId": "bd5f3b34-d64d-4b60-8188-438fbea4c552",
            "orderIv": "0.2",
            "qty": 5,
            "price": "25000"
        },
        {
            "symbol": "BTC-26AUG22-44000-C",
            "orderId": "4ddd727a-2af8-430e-a293-42895e594d18",
            "orderIv": "0.3",
            "qty": 4,
            "price": "24000"
        }
    ]
}'
```

```python

```

> t(:codequote_responseExample)

```javascript

{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
    "list": [{
      "category": "option",
      "symbol": "BTC-24JUN22-45000-P",
      "orderId": "bd5f3b34-d64d-4b60-8188-438fbea4c552",
      "orderLinkId": "ac4e3b34-d64d-4b60-8188-438fbea4c552",
      }, {
      "category": "option",
      "symbol": "BTC-26AUG22-44000-C",
      "orderId": "4ddd727a-2af8-430e-a293-42895e594d18",
      "orderLinkId": "5cee727a-2af8-430e-a293-42895e594d18",
      }]
    },
    "retExtInfo": {
      "list": [{
        "code": 0,
        "msg": "OK"
      }, {
        "code": 0,
        "msg": "OK"
      }]
    },
    "time": 1657200736570
}

```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvBatchReplace>/unified/v3/private/order/replace-batch</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvBatchReplace"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:dv_category)t(:dv_categorySuffix_4)    |
|request |<b>true</b> |array |    |
|list> symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|list> orderId |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|list> orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|list> orderIv |false |string |t(:row_comment_iv_v3) |
|list> t(:row_parameter_quantity) |false |string |t(:row_comment_qty_replace_v3) |
|list> t(:row_parameter_price) |false |string |t(:row_comment_price_replace_v3) |


<p class="fake_header">t(:responseparameters)</p>
<p>result：</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> category |string |t(:dv_category)t(:dv_categorySuffix_4) |
|list> symbol |string |t(:row_comment_symbol_v3) |
|list> orderId |string |t(:row_comment_query_orderId_v3) |
|list> orderLinkId |string |t(:row_comment_orderLinkId_response_v3) |

<p>retExtInfo：</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> code |string |t(:row_comment_code_response_v3) |
|list> msg |string |t(:row_comment_msg_response_v3) |

### t(:dv_batchCancelOrders)

t(:usdcBatchCancelOrdersDescV3)

```console
curl --location --request POST 'https://api-testnet.bybit.com/unified/v3/private/order/cancel-batch' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 27ecc5cca2aec6a779c9f5ef828275a3e9ccaf392a030820911c52d6085c34db' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657871228347' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "category": "option",
    "request": [
        {
            "symbol": "BTC-24JUN22-45000-P",
            "orderId": "bd5f3b34-d64d-4b60-8188-438fbea4c552"
        },
        {
            "symbol": "BTC-26AUG22-44000-C",
            "orderId": "4ddd727a-2af8-430e-a293-42895e594d18"
        }
    ]
}'
```

```python

```


> t(:codequote_responseExample)

```javascript

{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
    "list": [{
      "category": "option",
      "symbol": "BTC-24JUN22-45000-P",
      "orderId": "bd5f3b34-d64d-4b60-8188-438fbea4c552",
      "orderLinkId": "ac4e3b34-d64d-4b60-8188-438fbea4c552",
      }, {
      "category": "option",
      "symbol": "BTC-26AUG22-44000-C",
      "orderId": "4ddd727a-2af8-430e-a293-42895e594d18",
      "orderLinkId": "5cee727a-2af8-430e-a293-42895e594d18",
      }]
     },
    "retExtInfo": {
      "list": [{
        "code": 0,
        "msg": "OK"
      }, {
        "code": 0,
        "msg": "OK"
      }]
    },
    "time": 1657200736570
}

```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvBatchCancel>/unified/v3/private/order/cancel-batch</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvBatchCancel"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:dv_category)t(:dv_categorySuffix_4)    |
|request |<b>true</b> |array |    |
|list> symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|list> orderId |false |string |t(:row_comment_orderId_v3_post) |
|list> orderLinkId |false |string |t(:row_comment_orderLinkId_v3_post) |


<p class="fake_header">t(:responseparameters)</p>
<p>result：</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> category |string |t(:dv_category)t(:dv_categorySuffix_4) |
|list> symbol |string |t(:row_comment_symbol_v3) |
|list> orderId |string |t(:row_comment_query_orderId_v3) |
|list> orderLinkId |string |t(:row_comment_orderLinkId_response_v3) |

<p>retExtInfo：</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> code |string |t(:row_comment_code_response_v3) |
|list> msg |string |t(:row_comment_msg_response_v3) |


### t(:dv_cancelAllOrders)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/unified/v3/private/order/cancel-all' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 27ecc5cca2aec6a779c9f5ef828275a3e9ccaf392a030820911c52d6085c34db' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657871228347' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
  "category": "option"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
    "list": [{
      "category": "option",
      "symbol": "BTC-24JUN22-45000-P",
      "orderId": "bd5f3b34-d64d-4b60-8188-438fbea4c552",
      "orderLinkId": "ac4e3b34-d64d-4b60-8188-438fbea4c552",
      }, {
      "category": "option",
      "symbol": "BTC-24JUN22-45000-P",
      "orderId": "4ddd727a-2af8-430e-a293-42895e594d18",
      "orderLinkId": "5cee727a-2af8-430e-a293-42895e594d18",
      }]
    },
    "retExtInfo": {
      "list": [{
        "code": 0,
        "msg": "OK"
      }, {
        "code": 0,
        "msg": "OK"
      }]
    },
    "time": 1657200736570
}

```

t(:account_para_cancelAllActive_v3)

<aside class="notice">
t(:account_para_cancelAllActive_v3_notice)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCancelAll>/unified/v3/private/order/cancel-all</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:dv_category)t(:dv_categorySuffix_4)    |
|baseCoin |false |string |t(:row_comment_cancelAll_baseCoin_v3)   |
|settleCoin |false |string |t(:row_comment_settleCoin_v3) |
|symbol |false |string |t(:row_comment_symbol_v3) |
|<a href="#order-filter-orderfilter">orderFilter</a> |false |string |t(:row_comment_cancelAll_orderFilter_v3) |

<p class="fake_header">t(:responseparameters)</p>
<p>result：</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:dv_category)t(:dv_categorySuffix_4)    |
|list> symbol |string |t(:row_comment_symbol_v3) |
|list> orderId |string |t(:row_comment_query_orderId_v3) |
|list> orderLinkId |string |t(:row_comment_orderLinkId_response_v3) |

<p>retExtInfo：</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> code |string |t(:row_comment_code_response_v3) |
|list> msg |string |t(:row_comment_msg_response_v3) |


## t(:position)
### t(:dv_myposition)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/unified/v3/private/position/list?category=linear&symbol=BTCUSDT' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 1793ee8a0d7b077550faef8d6676565f817302cbdc4dece80e263f78927212ea' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657872232349' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw ''
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

{
    "retCode": 0,
    "retMsg": "Success",
    "result": {
        "nextPageCursor": "0%3A1657711949945%2C0%3A1657711949945",
        "category": "linear",
        "list": [
            {
                "symbol": "ETHUSDT",
                "leverage": "10",
                "updatedTime": 1657711949945,
                "side": "Buy",
                "positionValue": "536.92500000",
                "takeProfit": "",
                "tpslMode": "Full",
                "riskId": 11,
                "trailingStop": "",
                "entryPrice": "1073.85000000",
                "unrealisedPnl": "",
                "markPrice": "1080.65000000",
                "size": "0.5000",
                "positionStatus": "normal",
                "stopLoss": "",
                "cumRealisedPnl": "-0.32215500",
                "positionMM": "2.97456450",
                "createdTime": 1657711949928,
                "positionIdx": 0,
                "positionIM": "53.98243950"
            }
        ]
    },
    "time": 1657713693182
}

```

t(:account_para_myPosition_v3)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pList>/unified/v3/private/position/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |false |string |t(:row_comment_symbol_v3)   |
|baseCoin |false |string |t(:unified_baseCoin_param_3)   |
|direction |false |string |t(:row_comment_direction_v3)   |
|limit |false |number |t(:unified_position_limit)   |
|cursor |false |string |t(:row_comment_cursor_v3)   |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3)    |
|list> positionIdx |string |t(:row_comment_query_positionIdx_v3)   |
|list> riskId |integer |t(:unified_position_riskId)   |
|list> symbol |string |t(:row_comment_symbol_v3)   |
|list> side |string |t(:row_comment_query_side_v3)  |
|list> size |string |t(:row_comment_query_size_v3)  |
|list> entryPrice |string |t(:row_comment_query_entryPrice_v3)  |
|list> sessionAvgPrice |string |t(:row_comment_query_sessionAvgPrice_v3)  |
|list> leverage |string |t(:unified_position_leverage)  |
|list> markPrice |string |t(:row_comment_query_markPrice_v3)  |
|list> positionIM |string |t(:unified_position_positionIM)  |
|list> positionMM |string |t(:unified_position_positionMM)  |
|list > takeProfit |string |t(:row_comment_query_takeProfit_v3)  |
|list > stopLoss |string |t(:row_comment_query_stopLoss_v3)  |
|list > trailingStop |string |t(:row_comment_query_trailingStop_v3)  |
|list > positionStatus |string |t(:row_comment_query_positionStatus_v3)  |
|list > positionValue |string |t(:row_comment_query_positionValue_v3)  |
|list > unrealisedPnl |string |t(:row_comment_query_unrealisedPnl_v3)  |
|list > cumRealisedPnl |string |t(:row_comment_query_cumRealisedPnl_v3)  |
|list > createdTime |number |t(:row_comment_query_createdTime_v3)  |
|list > updatedTime |number |t(:row_comment_query_updatedTime_v3)  |
|list > tpslMode |string |t(:row_comment_query_tpslMode_v3)  |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |


### t(:dv_setleverage)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/unified/v3/private/position/set-leverage' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 1793ee8a0d7b077550faef8d6676565f817302cbdc4dece80e263f78927212ea' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657872232349' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "category": "linear",
    "symbol":"BTCUSDT",
    "buyLeverage":"11",
    "sellLeverage":"11"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

{
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "time": 1657720329368
}

```

t(:linear_account_para_setLeverage_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ulSaveNew>/unified/v3/private/position/set-leverage</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSaveNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|buyLeverage |<b>true</b> |string |t(:row_comment_buyLeverage_v3)    |
|sellLeverage |<b>true</b> |string |t(:row_comment_sellLeverage_v3)   |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:dv_switchmode)

> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/unified/v3/private/position/tpsl/switch-mode' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 1793ee8a0d7b077550faef8d6676565f817302cbdc4dece80e263f78927212ea' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657872232349' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "category": "linear",
    "symbol":"BCHUSDT",
    "tpSlMode":"Full"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

{
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "time": 1657720268433
}

```

t(:linear_private_switchmode_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vptSwitchMode>/unified/v3/private/position/tpsl/switch-mode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vptSwitchMode"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:dv_category)t(:dv_categorySuffix_7)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|<a href="#tp-sl-mode-tpslmode">tpSlMode</a> |<b>true</b> |string |t(:row_comment_tpSlMode_v3)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:dv_setrisklimit)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/unified/v3/private/position/set-risk-limit' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 1793ee8a0d7b077550faef8d6676565f817302cbdc4dece80e263f78927212ea' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657872232349' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "category": "linear",
    "symbol":"BTCUSDT",
    "riskId":2,
    "positionIdx":0
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

{
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "time": 1657720329368
}

```

t(:linear_private_setrisklimit_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oawrlList>/unified/v3/private/position/set-risk-limit</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawrlList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|riskId |<b>true</b> |number |t(:row_comment_riskId_v3)  |
|positionIdx |false |string |t(:row_comment_positionIdx_um)  |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:dv_tradingstop)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/unified/v3/private/position/trading-stop' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 1793ee8a0d7b077550faef8d6676565f817302cbdc4dece80e263f78927212ea' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657872232349' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "category": "linear",
    "symbol":"BTCUSDT",
    "takeProfit":"45000",
    "stopLoss":"40000",
    "tpTriggerBy":"LastPrice",
    "slTriggerBy":"LastPrice",
    "trailingStop":"",
    "activePrice":"",
    "slSize":"",
    "tpSize":"",
    "positionIdx":0
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

{
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "time": 1657720116299
}

```

t(:account_para_tradingStop_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oapTradingStopNew>/unified/v3/private/position/trading-stop</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oapTradingStopNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:dv_category)t(:dv_categorySuffix_7)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|takeProfit |false |string |t(:account_row_comment_takeProfit_v3) |
|stopLoss |false |string |t(:account_row_comment_stopLoss_v3) |
|trailingStop |false |string |t(:account_row_comment_trailingStop_v3) |
|tpTriggerBy |false |string |t(:account_row_comment_tpTriggerBy_v3) |
|slTriggerBy |false |string |t(:account_row_comment_slTriggerBy_v3) |
|activePrice |false |string |t(:account_row_comment_activePrice_v3) |
|slSize |false |string |t(:account_row_comment_slSize_v3) |
|tpSize |false |string |t(:row_comment_tpSize_v3) |
|positionIdx |false |string |t(:row_comment_positionIdx_um) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:dv_userTradeRecords7Day)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/unified/v3/private/execution/list?category=linear&orderFilter=order' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 1793ee8a0d7b077550faef8d6676565f817302cbdc4dece80e263f78927212ea' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657872232349' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw ''
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

{
  "retCode": 0,
    "retMsg": "Success",
    "result": {
    "nextPageCursor": "1565%3A0%2C1565%3A0",
      "category": "option",
      "list": [
      {
        "orderType": "Limit",
        "symbol": "BTC-14JUL22-17500-C",
        "orderLinkId": "188889689-yuanzhen-558998998898",
        "side": "Buy",
        "orderId": "09c5836f-81ef-4208-a5b4-43135d3e02a2",
        "leavesQty": "0.0000",
        "execTime": 1657714122417,
        "execFee": "0.11897082",
        "feeRate": "0.000300",
        "execId": "6e492560-78b4-5d2b-b331-22921d3173c9",
        "blockTradeId": "",
        "execPrice": "2360.00000000",
        "lastLiquidityInd": "TAKER",
        "orderQty": "0.0200",
        "orderPrice": "2360.00000000",
        "execValue": "47.20000000",
        "execType": "Trade",
        "execQty": "0.0200"
      }
    ]
  },
  "time": 1657714292783
}

```

t(:wallet_para_tradeRecords_v3)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpeList>/unified/v3/private/execution/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpeList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |false |string |t(:row_comment_symbol_v3)   |
|baseCoin |false |string |t(:unified_baseCoin_param_3)   |
|orderId |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|<a href="#order-filter-orderfilter">orderFilter</a> |false |string |t(:row_comment_orderFilter_v3)   |
|startTime |false |number |t(:row_comment_startTime_v3)   |
|endTime |false |number |t(:row_comment_endTime_v3)   |
|direction |false |string |t(:row_comment_direction_v3)   |
|limit |false |number |t(:row_comment_limit_100_50)   |
|cursor |false |string |t(:row_comment_cursor_v3)   |
|<a href="#exec-type-exectype">execType</a> |false |string |t(:row_comment_query_execType_v3)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3)    |
|list> symbol |string |t(:row_comment_symbol_v3)   |
|list> execFee |string |t(:row_comment_query_execFee_v3)  |
|list> execId |string |t(:row_comment_query_execId_v3)  |
|list> execPrice |string |t(:row_comment_query_execPrice_v3)  |
|list> execQty |string |t(:row_comment_query_execQty_v3)  |
|list> execType |string |t(:row_comment_query_execType_v3)  |
|list> execValue |string |t(:row_comment_query_execValue_v3)  |
|list> feeRate |string |t(:row_comment_query_feeRate_v3)  |
|list> lastLiquidityInd |string |t(:row_comment_query_lastLiquidityInd_v3)  |
|list > leavesQty |string |t(:row_comment_query_leavesQty_v3)  |
|list> orderId |string |t(:row_comment_query_orderId_v3) |
|list > orderLinkId |string |t(:row_comment_query_orderLinkId_v3)  |
|list> orderPrice |string |t(:row_comment_query_price_v3)  |
|list> orderQty |string |t(:row_comment_query_qty_v3)  |
|list> orderType |string |t(:row_comment_query_orderType_v3)  |
|list> <a href="#stop-order-type-stopordertype">stopOrderType</a> |string |t(:row_comment_query_stopOrderType_v3)  |
|list> side |string |t(:row_comment_query_side_v3)  |
|list> execTime |number |t(:row_comment_query_execTime_v3)  |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |

### t(:dv_queryOptionDeliveryLog)

> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/unified/v3/private/delivery-record?category=option&limit=10' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 1793ee8a0d7b077550faef8d6676565f817302cbdc4dece80e263f78927212ea' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657872232349' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json'```
```

``` python--pybit

```

> t(:codequote_responseExample)

```javascript

{
  "retCode": 0,
    "retMsg": "Success",
    "result": {
    "nextPageCursor": "784%3A0%2C784%3A0",
      "category": "option",
      "list": [
      {
        "symbol": "BTC-23JUN22-18500-P",
        "side": "Sell",
        "deliveryTime": 1655971201376,
        "strike": "18500",
        "fee": "0.00000000",
        "position": "15.0000",
        "deliveryPrice": "20454.54294250",
        "deliveryRpl": "0.00000000"
      }
    ]
  },
  "time": 1657716373514
}

```

t(:wallet_para_delivery_record_v3)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=uopvQueryDelivery>/unified/v3/private/delivery-record</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvQueryDelivery"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:dv_category)t(:dv_categorySuffix_8)    |
|symbol |false |string |t(:row_comment_symbol_v3)   |
|expDate |false |string |t(:row_comment_expDate_v3)   |
|direction |false |string |t(:row_comment_direction_v3)   |
|limit |false |number |t(:row_comment_limit_v3)   |
|cursor |false |string |t(:row_comment_cursor_v3)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3)    |
|list> deliveryTime |number |t(:row_comment_deliveryTime_v3)   |
|list> symbol |string |t(:row_comment_symbol_v3)   |
|list> side |string |t(:row_comment_query_side_v3)  |
|list> position |string |t(:row_comment_query_position_v3)  |
|list> deliveryPrice |string |t(:row_comment_query_deliveryPrice_v3)  |
|list> strike |string |t(:row_comment_query_strike_v3)  |
|list> fee |string |t(:row_comment_query_fee_v3)  |
|list> deliveryRpl |string |t(:row_comment_query_deliveryRpl_v3)  |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |


### t(:dv_querySettleLogs)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/unified/v3/private/settlement-record?category=linear' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 1793ee8a0d7b077550faef8d6676565f817302cbdc4dece80e263f78927212ea' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657872232349' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json'
```

```python--pybit

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "Success",
    "result": {
        "nextPageCursor": "110%3A0%2C110%3A0",
        "category": "linear",
        "list": [
            {
                "realisedPnl": "2.45000000",
                "symbol": "BTCPERP",
                "side": "None",
                "markPrice": "24354.81000000",
                "size": "",
                "time": "1660233600000",
                "sessionAvgPrice": "24354.81000000"
            }
        ]
    },
    "retExtInfo": {},
    "time": 1661326904055
}
```

t(:wallet_para_settlement_record_v3)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=upovSession>/unified/v3/private/settlement-record</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#upovSession"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:dv_category)t(:dv_categorySuffix_9)    |
|symbol |false |string |t(:row_comment_symbol_v3)   |
|direction |false |string |t(:row_comment_direction_v3)   |
|limit |false |number |t(:row_comment_limit_v3)   |
|cursor |false |string |t(:row_comment_cursor_v3)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3)    |
|list> symbol |string |t(:row_comment_symbol_v3)   |
|list> realisedPnl |string |t(:row_comment_realisedPnl_v3)   |
|list> side |string |t(:row_comment_query_side_v3)  |
|list> size |string |t(:row_comment_query_size_v3)  |
|list> sessionAvgPrice |string |t(:row_comment_query_sessionAvgPrice_v3)  |
|list> markPrice |string |t(:row_comment_query_markPrice_v3)  |
|list> time |string |t(:settlementTime)  |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |


## t(:account)
t(:wallet_para)


### t(:dv_balance)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/unified/v3/private/account/wallet/balance' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 1793ee8a0d7b077550faef8d6676565f817302cbdc4dece80e263f78927212ea' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657872232349' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw ''
```


```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "totalEquity": "445.20695266",
        "accountIMRate": "0.1195",
        "totalMarginBalance": "445.20695266",
        "totalInitialMargin": "53.20940585",
        "totalAvailableBalance": "391.99754682",
        "accountMMRate": "0.0129",
        "totalPerpUPL": "-13.12779308",
        "totalWalletBalance": "458.33474574",
        "totalMaintenanceMargin": "5.74823205",
        "coin": [
            {
                "currencyCoin": "USDC",
                "availableToBorrow": "1500000",
                "borrowSize": "0",
                "bonus": "",
                "accruedInterest": "0",
                "availableBalanceWithoutConvert": "500",
                "totalOrderIM": "0",
                "equity": "500",
                "totalPositionMM": "0",
                "usdValue": "500",
                "availableBalance": "391.99754682",
                "unrealisedPnl": "",
                "totalPositionIM": "0",
                "marginBalanceWithoutConvert": "500",
                "walletBalance": "500",
                "cumRealisedPnl": "",
                "marginBalance": "445.20695266"
            },
            {
                "currencyCoin": "USDT",
                "availableToBorrow": "2499945.20850984",
                "borrowSize": "54.79149016",
                "bonus": "",
                "accruedInterest": "0.0003021",
                "availableBalanceWithoutConvert": "-107.99938383",
                "totalOrderIM": "0",
                "equity": "-54.79149016",
                "totalPositionMM": "4.10432398",
                "usdValue": "-54.79304733",
                "availableBalance": "391.98640657",
                "unrealisedPnl": "-13.12741999",
                "totalPositionIM": "42.24959564",
                "marginBalanceWithoutConvert": "-54.79149016",
                "walletBalance": "-41.66407016",
                "cumRealisedPnl": "-41.66407016",
                "marginBalance": "445.19430024"
            }
        ]
    },
    "retExtInfo": {},
    "time": 1673266182240
}
```

t(:wallet_para_walletBalance_v3)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpwBalance>/unified/v3/private/account/wallet/balance</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpwBalance"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|coin |false |string |t(:row_comment_coin_v3)    |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|accountIMRate |string |t(:row_comment_query_accountIMRate_v3)    |
|accountMMRate |string |t(:row_comment_query_accountMMRate_v3)    |
|totalEquity |string |t(:row_comment_query_totalEquity_v3)    |
|totalWalletBalance |string |t(:row_comment_query_totalWalletBalance_v3)    |
|totalMarginBalance |string |t(:row_comment_query_totalMarginBalance_v3)    |
|totalAvailableBalance |string |t(:row_comment_query_totalAvailableBalance_v3)    |
|totalPerpUPL |string |t(:row_comment_query_totalPerpUPL_v3)    |
|totalInitialMargin |string |t(:row_comment_query_totalInitialMargin_v3)    |
|totalMaintenanceMargin |string |t(:row_comment_query_totalMaintenanceMargin_v3)    |
|Coin> coin |string |t(:row_comment_query_coin_coin_v3)    |
|Coin> equity |string |t(:row_comment_query_coin_equity_v3)    |
|Coin> usdValue |string |t(:row_comment_query_coin_usdValue_v3)    |
|Coin> walletBalance |string |t(:row_comment_query_coin_walletBalance_v3)    |
|Coin> marginBalance |string |t(:row_comment_query_coin_marginBalance_v3)    |
|Coin> availableBalance |string |t(:row_comment_query_coin_availableBalance_v3)    |
|Coin> marginBalanceWithoutConvert |string |t(:row_comment_query_coin_marginBalanceWithoutConvert_v3)    |
|Coin> availableBalanceWithoutConvert |string |t(:row_comment_query_coin_availableBalanceWithoutConvert_v3)    |
|Coin> borrowSize |string |t(:row_comment_query_coin_borrowSize_v3)    |
|Coin> availableToBorrow |string |t(:row_comment_query_coin_availableToBorrow_v3)    |
|Coin> accruedInterest |string |t(:row_comment_query_coin_accruedInterest_v3)    |
|Coin> totalOrderIM |string |t(:row_comment_query_coin_totalOrderIM_v3)    |
|Coin> totalPositionIM |string |t(:row_comment_query_coin_totalPositionIM_v3)    |
|Coin> totalPositionMM |string |t(:row_comment_query_coin_totalPositionMM_v3)    |
|Coin> unrealisedPnl |string |t(:row_comment_query_coin_unrealisedPnl_v3)    |
|Coin> cumRealisedPnl |string |t(:row_comment_query_coin_cumRealisedPnl_v3)    |


### t(:dv_upgradeUnifiedAccount)

> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/unified/v3/private/account/upgrade-unified-account' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 1793ee8a0d7b077550faef8d6676565f817302cbdc4dece80e263f78927212ea' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657872232349' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "SUCCESS",
    "result": {
    "status": "SUCCESS",
      "relieveLimitBizResponse": []
  },
  "time": 1657716101461
}
```


t(:wallet_para_upgradeUnifiedMarginAccount_v3)


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpeOrder>/unified/v3/private/account/upgrade-unified-account</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpeOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|<a href="#upgrade-result-result">result</a> |string |t(:row_comment_query_result_v3) |
|msg |string |t(:row_comment_query_msg_v3)  |

<p class="fake_header">t(:resonoferror)</p>
|t(:resonoferror)|t(:comments_v3)|
|:----- |:-----|----- |
|t(:row_comment_query_ThereisUSDCbeingtransferred_v3_code) |t(:row_comment_query_ThereisUSDCbeingtransferred_v3) |
|t(:row_comment_query_ThereisUSDTbeingtransferred_v3_code) |t(:row_comment_query_ThereisUSDTbeingtransferred_v3) |
|t(:row_comment_query_ThereareUSDCperpetualpositionholdings_v3_code) |t(:row_comment_query_ThereareUSDCperpetualpositionholdings_v3) |
|t(:row_comment_query_ThereareUSDCoptionspositionholdings_v3_code) |t(:row_comment_query_ThereareUSDCoptionspositionholdings_v3) |
|t(:row_comment_query_ThereareUSDTperpetualpositionholdings_v3_code) |t(:row_comment_query_ThereareUSDTperpetualpositionholdings_v3) |
|t(:row_comment_query_ThereareUSDCperpetualorders_v3_code) |t(:row_comment_query_ThereareUSDCperpetualorders_v3) |
|t(:row_comment_query_ThereareUSDCoptionorders_v3_code) |t(:row_comment_query_ThereareUSDCoptionorders_v3) |
|t(:row_comment_query_ThereareUSDTperpetualorders_v3_code) |t(:row_comment_query_ThereareUSDTperpetualorders_v3) |

### t(:dv_queryTransactionLogs)
t(:wallet_para_tradingHistory_v3)

> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/private/account/transaction-log?category=linear&type=&currency=USDT&baseCoin=&limit=10' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 1793ee8a0d7b077550faef8d6676565f817302cbdc4dece80e263f78927212ea' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657872232349' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw ''
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "Success",
    "result": {
    "nextPageCursor": "1563%3A0%2C1563%3A0",
      "currency": "USDT",
      "category": "linear",
      "list": [
      {
        "symbol": "ETHUSDT",
        "side": "Buy",
        "funding": "",
        "orderLinkId": "",
        "orderId": "7d17d359-4e38-4d3a-9a31-29791ef2dfd7",
        "fee": "0.32215500",
        "change": "-0.32215500",
        "cashFlow": "0.00000000",
        "transactionTime": 1657711949931,
        "type": "TRADE",
        "feeRate": "0.000600",
        "size": "0.5000",
        "qty": "0.5000",
        "cashBalance": "-0.32215500",
        "tradePrice": "1073.85000000",
        "tradeId": "f306ca09-de6b-56a1-8893-71f0fecd2384"
      }
    ]
  },
  "time": 1657714367010
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpTranLog>/unified/v3/private/account/transaction-log</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpTranLog"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|currency |<b>true</b> |string |t(:row_comment_query_currency_v3)   |
|baseCoin |false |string |t(:usdcBaseCoinUM_transLog)   |
|t(:row_comment_query_transType_v3) |false |string |t(:row_comment_type_v3)   |
|startTime |false |number |t(:row_comment_startTime_v3)   |
|endTime |false |number |t(:row_comment_endTime_v3)   |
|direction |false |string |t(:row_comment_direction_v3)   |
|limit |false |number |t(:row_comment_limit_v3)   |
|cursor |false |string |t(:row_comment_cursor_v3)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3)    |
|currency |string |t(:row_comment_query_currency_v3)    |
|list> transactionTime |number |t(:row_comment_query_transactionTime_v3)   |
|list> type |string |t(:row_comment_query_type_v3)  |
|list> symbol |string |t(:row_comment_query_symbol_v3)  |
|list> side |string |t(:row_comment_query_side_v3)  |
|list> qty |string |t(:row_comment_query_qty_v3)  |
|list> size |string |t(:row_comment_query_size_v3)  |
|list> tradePrice |string |t(:row_comment_query_tradePrice_v3)  |
|list> funding |string |t(:row_comment_query_funding_v3)  |
|list> fee |string |t(:row_comment_query_fee_v3)  |
|list> cashFlow |string |t(:row_comment_query_cashFlow_v3)  |
|list> change |string |t(:row_comment_query_change_v3)  |
|list> cashBalance |string |t(:row_comment_query_cashBalance_v3)  |
|list> feeRate |string |t(:row_comment_query_feeRate_v3)  |
|list> tradeId |string |t(:row_comment_query_tradeId_v3)  |
|list> orderId |string |t(:row_comment_query_orderId_v3)  |
|list> orderLinkId |string |t(:row_comment_query_orderLinkId_v3)  |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |



### t(:dv_transfer)
t(:wallet_para_transfers_v3)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/asset/v1/private/transfer' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fromAccountType": "SPOT",
    "toAccountType": "OPTION",
    "amount": "15",
    "coin": "USDT",
    "transferId": "1aaacac2-fd1a-4a50-8b1a-f99343669f9f",
    "sign": "9fdd3488b2c8e5bb27feefd31c90ae8ccc2054ebb219eb08f5943101316fa0fa",
    "timestamp": "1659603566249",
    "api_key": "T0d98KyVamQ62YBzN8",
    "recv_window": "5000"
}'

``` 
```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {
        "transfer_id": "1aaacac2-fd1a-4a50-8b1a-f99343669f9f"
    },
    "ext_info": null,
    "time_now": 1659603553203,
    "rate_limit_status": 16,
    "rate_limit_reset_ms": 1659603553203,
    "rate_limit": 4
}
```



<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpTransfer>/asset/v1/private/transfer</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpTransfer"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transfer_id |<b>true</b> |string |t(:row_comment_transfer_id_v3)    |
|amount |<b>true</b> |string |t(:row_comment_amount_v3)    |
|coin |<b>true</b> |string |t(:row_comment_coin_v3)   |
|<a href="#account-type-from_account_type-to_account_type">from_account_type</a> |<b>true</b> |string |t(:row_comment_accounttype)   |
|<a href="#account-type-from_account_type-to_account_type">to_account_type</a> |<b>true</b> |string |t(:row_comment_accounttype)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transfer_id |string |t(:row_comment_query_transfer_id_v3)    |


### t(:dv_queryExchangeRecords)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v2/private/exchange/exchange-order-all' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 7d52a4dd60ba912747f5401fa1c9a1dc8de76d5354f380b5973a86d9744a9c38' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657873597617' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw ''
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "totalCount" 2,
    "list": [
    {
      "exchangeTxId": "7ad50cb1-9ad0-4f74-804b-d82a516e1029",
      "exchangeRate": "40.57202774",
      "fromCoin": "BTC",
      "fromAmount": "0.1",
      "toCoin": "ETH",
      "toAmount": "4.05720277",
      "createdAt": "2020-06-15 03:32:52"
    },
    {
      "exchangeTxId": "8be60cb1-9ad0-4f74-804b-d82a516e1029",
      "exchangeRate": "39.92359901",
      "fromCoin": "BTC",
      "toCoin": "ETH",
      "toAmount": "39.923599",
      "fromAmount": "1",
      "createdAt": "2020-06-12 08:27:51"
     }
    ]
}

```

t(:wallet_para_assetexchangerecords_v3)


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpExchangeOrder>/asset/v2/private/exchange/exchange-order-all</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpExchangeOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|fromCoin |false |string |t(:row_comment_fromCoin_v3) |
|toCoin |false |string |t(:row_comment_toCoin_v3) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|totalCount |number |t(:row_comment_query_totalCount_v3) |
|list > fromCoin |string |t(:row_comment_query_fromCoin_v3)  |
|list > fromAmount |string |t(:row_comment_query_fromAmount_v3)  |
|list > toCoin |string |t(:row_comment_query_toCoin_v3)  |
|list > toAmount |string |t(:row_comment_query_toAmount_v3)  |
|list > exchangeRate |string |t(:row_comment_query_exchangeRate_v3)  |
|list > createdAt |string |t(:row_comment_query_createdAt_v3)  |
|list > exchangeTxId |string |t(:row_comment_query_exchangeTxId_v3)  |

### t(:dv_interestBillStatement)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/unified/v3/private/account/borrow-history' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 7d52a4dd60ba912747f5401fa1c9a1dc8de76d5354f380b5973a86d9744a9c38' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657873597617' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw ''
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "nextPageCursor": "3347422%3A2%2C3347422%3A2",
        "currency": null,
        "list": [
            {
                "createTime": 1673255100075,
                "costExemption": "0.0003064720575562080220552",
                "InterestBearingBorrowSize": "0",
                "currency": "USDT",
                "hourlyBorrowRate": "0.0000055138",
                "borrowCost": "0"
            }
        ]
    },
    "retExtInfo": {},
    "time": 1673266124062
}
```

t(:wallet_para_interestBillStatement_v3)


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpBorHis>/unified/v3/private/account/borrow-history</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpBorHis"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|currency |false |string |t(:row_comment_query_currency_v3)   |
|startTime |false |number |t(:row_comment_startTime_v3)   |
|endTime |false |number |t(:row_comment_endTime_v3)   |
|direction |false |string |t(:row_comment_direction_v3)   |
|limit |false |number |t(:row_comment_limit_v3)   |
|cursor |false |string |t(:row_comment_cursor_v3)   |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> currency |string |t(:row_comment_query_currency_v3)   |
|list> createdTime |number |t(:row_comment_query_createdTime_v3)  |
|list> borrowCost |string |t(:row_comment_query_borrowCost_v3)  |
|list> hourlyBorrowRate |string |t(:row_comment_query_hourlyBorrowRate_v3)  |
|list> InterestBearingBorrowSize |string |t(:row_comment_query_InterestBearingBorrowSize_v3)  |
|list> costExemption |string |t(:row_comment_query_costExemption_v3)  |

### t(:dv_queryLoanInterest)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/unified/v3/private/account/borrow-rate' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 7d52a4dd60ba912747f5401fa1c9a1dc8de76d5354f380b5973a86d9744a9c38' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1657873597617' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw ''
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "freeBorrowingAmount": "15000",
                "currency": "USDC",
                "maxBorrowingAmount": "1500000",
                "hourlyBorrowRate": "0.00000342460000000000"
            },
            {
                "freeBorrowingAmount": "30000",
                "currency": "USDT",
                "maxBorrowingAmount": "2500000",
                "hourlyBorrowRate": "0.00000551380000000000"
            }
        ]
    },
    "retExtInfo": {},
    "time": 1673264677870
}
```


t(:wallet_para_queryLoanInterest_v3)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpBorRate>/unified/v3/private/account/borrow-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpBorRate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|currency |false |string |t(:row_comment_currency_v3)   |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> currency |string |t(:row_comment_currency_v3)   |
|list> hourlyBorrowRate |string |t(:row_comment_query_hourlyBorrowRate_v3)  |
|list> maxBorrowingAmount |string |t(:row_comment_query_maxBorrowingAmount_v3)  |
|list> freeBorrowingAmount |string |t(:row_comment_query_freeBorrowingAmount_v3)  |


### t(:dv_setMarginMode)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/unified/v3/private/account/setMarginMode' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: a1487d336f003c389651fc89aa88cc9b19be6e2b12eb75b70180b61b0a03fd96' \
--header 'X-BAPI-API-KEY: CYZHHQAUQVHCGTHJPX' \
--header 'X-BAPI-TIMESTAMP: 1670481748474' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "setMarginMode":"PORTFOLIO_MARGIN"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "Request accepted",
    "result": {
        "reasons": []
    }
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=setMarginMode>/unified/v3/private/account/setMarginMode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#setMarginMode"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|setMarginMode |<b>true</b> |string |t(:row_comment_set_margin_mode)   |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:dv_queryAccountInfo)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/unified/v3/private/account/info' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 2640e6dc39a87bda2440ed6cbf55b2c852053ae24d956f663be3aca98bbffa37' \
--header 'X-BAPI-API-KEY: CYZHHQAUQVHCGTHJPX' \
--header 'X-BAPI-TIMESTAMP: 1670482882077' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw ''
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "Success",
    "marginMode": "PORTFOLIO_MARGIN",
    "updateTime": "1670481749000"
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=getAccountInfo>/unified/v3/private/account/info</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#getAccountInfo"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|marginMode |string |t(:row_comment_set_margin_mode)   |
|updateTime |string |t(:row_resp_comment_updateTime)   |
