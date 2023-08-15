# t(:websocket)


## t(:websocketauthentication)
> t(:websocket_codequote_auth_usdc)

```python
import hmac
import websocket
import threading
import time
import json

def on_message(ws, message):
    print(json.loads(message))

def on_error(ws, error):
    print('we got error')
    print(error)

def on_close(ws):
    print("### about to close please don't close ###")

def send_auth(ws):
    api_key = 'XXXXXXXXXXXXXXXXXXXX'
    secret = 'XXXXXXXXXXXXXXXXXXXX'
    expires = int((time.time() + 10) * 1000)
    _val = f'GET/realtime{expires}'
    print(_val)
    signature = str(hmac.new(
        bytes(secret, 'utf-8'),
        bytes(_val, 'utf-8'), digestmod='sha256'
    ).hexdigest())
    
    ws.send(
      json.dumps({
        "op": "auth",
        "args": [api_key, expires, signature]
      })
    )

def on_open(ws):
    print('opened')
    send_auth(ws)
    def pingPer(ws):
        while True:
            ws.send(
              json.dumps({
              "op": "ping",
              "args": ["946656000000"]
              })
            )
            time.sleep(25)
    t1 = threading.Thread(target=pingPer, args=(ws,))
    t1.start()
    ws.send(
      json.dumps({
        "op": "subscribe", "id": "{100003}", 
        "args": ["user.option.order", "user.option.position", 
                 "user.option.tradeHistory", "user.option.orderHistory"]
      })
    )

def connWS():
    ws = websocket.WebSocketApp("wss://stream-testnet.bybit.com/trade/option/usdc/private/v1",
                                on_message=on_message,
                                on_error=on_error,
                                on_close=on_close,
                                on_open=on_open
                                )
    ws.run_forever()

if __name__ == "__main__":
    connWS()
```


t(:usdc_websocket_para_endpoint)

<aside class="warning">
t(:websocket_best_practices)
</aside>


## t(:heartbeat)
> t(:websocket_codequote_heartbeat)

```javascript
ws.send('{"op":"ping","args":["1535975085152"]}');
```

> t(:codequote_responseExample)

```javascript
{"op":"pong","args":["1535975085152"]}
```


<aside class="warning">
t(:websocket_aside_heartbeat)
</aside>

t(:websocket_aside_heartbeat_option)

<!-- 连接数限制
## t(:websocketlimit)
t(:websocket_para_limit)
-->

## t(:usdc_disconnect_protection)
<aside class="notice">
t(:usdc_disconnect_protection_para)
</aside>

t(:websocket_aside_dcp_usdc)

## t(:subscribe)
### t(:websocketfilters)

<aside class="warning">
t(:option_wss_lengthLimit_warning)
</aside>

> t(:websocket_codequote_filters1)

t(:usdc_websocket_subscribe_desc)

```javascript
// Subscribing to the trade data for BTCUSDT
```

### t(:websocketunfilters)

t(:usdc_websocket_unsubscribe_desc)

## t(:websocketresponse)
> t(:websocket_codequote_response)

```javascript

```

t(:spot_websocket_para_response)

## Public Topics
### orderBook

> t(:codequote_subscribe)

```javascript
  ws.send('{"op":"subscribe","id":"requestId","args":["orderbook25.BTC-12NOV21-40000-P"]}');
```

> t(:codequote_snapshot)

```javascript

{
  "id":"orderbook100.BTC-12NOV21-40000-P-117936-1636454548726",
  "topic":"orderbook100.BTC-12NOV21-40000-P",
  "creationTime":1636454548726,
  "data":{
    "orderBook":[
    {
      "price":"1764.5",
      "size":"997.99",
      "side":"Sell"
    },
    {
      "price":"40000.5",
      "size":"0.01",
      "side":"Sell"
    }
  ]
}
}



```

t(:usdc_websocket_para_orderbook)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_price) |string |t(:row_comment_resp_price) |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |string |t(:row_comment_position_size)  |



### orderBook(delta)

> t(:codequote_subscribe)

```javascript
  ws.send('{"op":"subscribe","id":"requestId","args":["delta.orderbook100.BTC-4MAR22-25000-P"]}');
```

> t(:codequote_snapshot)

```javascript

{
  "id":"delta.orderbook100.BTC-4MAR22-25000-P-65815768-1646214405074",
  "topic":"delta.orderbook100.BTC-4MAR22-25000-P",
  "creationTime":1646214405074,
  "data":{
  "version":"55",
    "dataType":"NEW",
    "orderBook":[
    {
      "price":"10",
      "size":"1.67",
      "side":"Buy"
    },
    {
      "price":"5",
      "size":"0.01",
      "side":"Buy"
    }
  ]
}
}
```


> t(:codequote_delta)

```javascript
{
  "id":"delta.orderbook100.BTC-4MAR22-25000-P-65815769-1646214587050",
    "topic":"delta.orderbook100.BTC-4MAR22-25000-P",
    "creationTime":1646214587050,
    "data":{
    "version":"56",
      "dataType":"CHANGE",
      "delete":[

    ],
      "update":[

    ],
      "insert":[
      {
        "price":"15",
        "size":"1",
        "side":"Buy"
      }
    ]
  }
}
```


t(:usdc_websocket_para_orderbook_100)
t(:usdcCommonDesc)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_price) |string |t(:row_comment_resp_price) |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |string |t(:row_comment_position_size)  |




### t(:bybitTradeHistory)
> t(:codequote_subscribe)

```javascript
  ws.send('{"op":"subscribe","id":"{1001}","args":["recenttrades.BTC"]}');
```


> t(:usdc_trade_codequote_snapshot)

```javascript
{
    "id":"recenttrades.BTC-118388-1636510323155",
    "topic":"recenttrades.BTC",
    "creationTime":1636510323155,
    "data":{
        "coin":"BTC",
        "trades":[
            {
                "symbol":"BTC-31DEC21-36000-P",
                "tradeId":"787bf079-b6a5-5bc0-a76d-59dad9036e7b",
                "price":"371",
                "size":"0.01",
                "tradeTime":"1636510323144",
                "side":"Buy",
                "isBlockTrade": false,
                "iv": "0.6544782237284431",
                "markIv": "0.6447",
                "underlyingPrice": "20098.8800",
                "markPrice": "759.5557",
                "indexPrice": "20103.2800",
                "crossSeq":"118388"
            }
        ]
    }
}
```


t(:usdc_current_24_total)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| tradeTime |string |t(:tradeTime) |
| t(:row_parameter_symbol) |string |t(:usdcSymbol) |
| t(:row_parameter_side) |string |t(:websocketTradeSide) |
| size |string |t(:row_comment_position_size) |
| t(:row_parameter_price) |string |t(:row_comment_exec_price) |
| tradeId |string | t(:tradeId) |
| underlyingPrice |string|t(:usdcUnderlyingPrice)|
| markPrice |string|t(:usdcMarkPrice)|
| indexPrice |string|t(:usdcIndexPrice)|
| markIv |string|t(:usdcMarkPriceIv)|
| iv|string|t(:usdcIv)|
| isBlockTrade |bool | t(:usdc_isBlockTrade) |
| crossSeq |string | t(:usdcCrossSeq) |




### t(:latestSymbolInfo)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","id":"{1001}","args":["instrument_info.BTC-19NOV21-58000-P"]}');
```

> t(:codequote_snapshot)

```javascript

{
    "id":"instrument_info.BTC-19NOV21-58000-P-98790-1636511446299",
    "topic":"instrument_info.BTC-19NOV21-58000-P",
    "creationTime":1636511446299,
    "data":{
        "symbol":"BTC-19NOV21-58000-P",
        "bidPrice":"421",
        "askPrice":"465",
        "bidIv":"0.7785",
        "askIv":"0.8012",
        "bidSize":"17",
        "askSize":"18",
        "markPrice":"442.51157238",
        "markPriceIv":"0.7897",
        "indexPrice":"67102.13",
        "underlyingPrice":"67407.49",
        "lastPrice":"0",
        "delta":"-0.10385629",
        "gamma":"0.00002132",
        "theta":"-82.72572574",
        "vega":"19.33584131",
        "change24h":"0",
        "volume24h":"0",
        "turnover24h":"0",
        "high24h":"0",
        "low24h":"0",
        "totalVolume":"0",
        "totalTurnover":"0",
        "openInterest":"0",
        "predictedDeliveryPrice":"62330.90608575"
    }
}

```

t(:usdcLastestSymbolInfo)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) |string |t(:usdcSymbol) |
| bidPrice |string |t(:bidPrice) |
| askPrice |string |t(:askPrice) |
| bidIv |string |t(:bidIv) |
| askIv |string |t(:askIv) |
| bidSize |string |t(:bidSize) |
| askSize |string |t(:askSize) |
| markPrice |string |t(:usdcMarkPrice) |
| markPriceIv |string |t(:markPriceIv) |
| indexPrice |string |t(:usdcIndexPrice) |
| underlyingPrice |string |t(:underlying) |
| lastPrice |string |t(:usdcLastPrice) |
| delta |string |t(:delta) |
| gamma |string |t(:gamma) |
| theta |string |t(:theta) |
| vega |string |t(:vega) |
| change24h |string |t(:price24Pcnt) |
| volume24h |string |t(:volume24h) |
| turnover24h |string |t(:turnover24h) |
| high24h |string |t(:highPrice24h) |
| low24h |string |t(:lowPrice24h) |
| totalVolume |string |t(:totalVolume) |
| totalTurnOver |string |t(:totalTurnOver) |
| openInterest |string |t(:openInterest) |
| predictedDeliveryPrice |string |t(:usdcPredictedDeliveryPrice) |


### t(:websocketIntrumentInfoBaseCoin)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","id":"{1001}","args":["instrument_info.all.ETH"]}');
```

> t(:codequote_snapshot)

```javascript
{
    "id": "ai92u",
    "topic": "instrument_info.all.ETH",
    "creationTime": 1667893322171,
    "data": {
        "instrumentInfos": [
            {
                "symbol": "ETH-30DEC22-15000-P",
                "lastPrice": "13718",
                "openInterest": "0",
                "indexPrice": "1490.62",
                "markPrice": "13510.54129157",
                "markPriceIv": "1.4895",
                "change24h": "0",
                "volume24h": "0",
                "turnover24h": "0",
                "totalVolume": "16",
                "totalTurnover": "20285",
                "underlyingPrice": "1489.54",
                "delta": "-0.99993509",
                "gamma": "0.00000032",
                "vega": "0.00148202",
                "theta": "-0.00212192"
            },
    "type": "MergedSnapshot"
}
```

t(:usdcLatestSymbolInfoBaseCoin)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) |string |t(:usdcSymbol) |
| lastPrice |string |t(:usdcLastPrice) |
| openInterest |string |t(:openInterest) |
| indexPrice |string |t(:usdcIndexPrice) |
| markPrice |string |t(:usdcMarkPrice) |
| markPriceIv |string |t(:markPriceIv) |
| change24h |string |t(:price24Pcnt) |
| volume24h |string |t(:volume24h) |
| turnover24h |string |t(:turnover24h) |
| totalVolume |string |t(:totalVolume) |
| totalTurnOver |string |t(:totalTurnOver) |
| underlyingPrice |string |t(:underlying) |
| delta |string |t(:delta) |
| gamma |string |t(:gamma) |
| vega |string |t(:vega) |
| theta |string |t(:theta) |


### t(:websocketEstimatedDeliveryPrice)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","id":"Customized id","args":["estimated_delivery_price.BTC_USD.19OCT22"]}');
```
> t(:codequote_responseExampleFormatAll)

```json
{
  "id": "xpGadboW8t-239",
  "topic": "estimated_delivery_price.BTC_USD.19OCT22",
  "creationTime": 1666164911010,
  "data": {
    "baseCoin": "BTC",
    "quoteCoin": "USD",
    "expireTime": "1666166400",
    "estimatedDeliveryPrice": "19209.32403847",
    "timestamp": "1666164911",
    "reqId": "xpGadboW8t-239"
  }
}
```

t(:websocketEstimatedDeliveryPrice_para)

<aside class="notice">
t(:websocketEstimatedDeliveryPrice_note)
</aside>

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| baseCoin |string |t(:usdcBaseCoin) |
| quoteCoin |string |t(:usdcQuoteCoin) |
| expireTime |string |t(:usdc_expireTime) |
| estimatedDeliveryPrice |string |t(:usdc_estimatedDeliveryPrice) |
| timestamp |string |t(:usdc_timestamp) |
| reqId |string |t(:usdc_reqId) |


### t(:websocketunderlyingPrice)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","id":"Customized id","args":["underlying.ETH_USD.19OCT22"]}');
```
> t(:codequote_responseExampleFormatAll)

```json
{
  "id": "amrA4Fgksl-239",
    "topic": "underlying.ETH_USD.19OCT22",
    "creationTime": 1666147645004,
    "data": {
      "baseCoin": "ETH",
      "quoteCoin": "USD",
      "expireTime": "1666166400",
      "underlyingPrice": "1302.88340000",
      "timestamp": "1666147645",
      "underlyingOriginPrice": "1302.88340000",
      "reqId": "amrA4Fgksl-239"
  }
}
```

t(:usdc_wss_underlyingPrice_para)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| baseCoin |string |t(:usdcBaseCoin) |
| quoteCoin |string |t(:usdcQuoteCoin) |
| expireTime |string |t(:usdc_expireTime) |
| underlyingPrice |string |t(:usdc_underlyingPrice) |
| timestamp |string |t(:usdc_timestamp) |
| underlyingOriginPrice |string |t(:usdc_underlyingOriginPrice) |
| reqId |string |t(:usdc_reqId) |


### t(:websocketunderlyingPriceByBasecoin)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","id":"Customized id","args":["underlying.ETH"]}');
```
> t(:codequote_responseExampleFormatAll)

```json
{
    "id": "o9CaP",
    "topic": "underlying_price.ETH",
    "creationTime": 1667890949185,
    "data": {
        "baseCoin": "ETH",
        "priceList": [
            {
                "deliveryDate": "30DEC22",
                "isEstimated": false,
                "price": "1482.93",
                "seconds": 4496251
            },
            {
                "deliveryDate": "27JAN23",
                "isEstimated": false,
                "price": "1482.33",
                "seconds": 6915451
            }
        ]
    },
    "type": "MergedSnapshot"
}
```

t(:usdc_wss_underlyingPrice_baseCoin_para)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| baseCoin |string |t(:usdcBaseCoin) |
| priceList |array |Object |
| > deliveryDate |string |t(:usdc_deliveryDate) |
| > isEstimated |boolean |t(:usdc_isEstimated) |
| > price |string |t(:usdc_price) |
| > seconds |long |t(:usdc_seconds) |


### t(:websocketinsurance)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","args":["platform.insurance.USDC"]}')

```
> t(:codequote_responseExampleFormatAll)

```javascript
{
	'id': 'd5249692-c34b-48f0-9db5-d693a30bce09', 
	'topic': 'platform.insurance.USDC', 
	'creationTime': 1649750400693, 
	'data': 
		{
			'insuranceBalance': '1180144.86587280', 
			'settleCoin': 'USDC', 
			'timestamp': '1649750400693'
		}
}
```
t(:usdc_platform_insurance)

<aside class="notice">
t(:websocket_usdc_platform_insurance)
</aside>

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| insuranceBalance |string |t(:usdcInsuranceBalance) |
| settleCoin |string |t(:usdcSettleCoin) |
| timestamp |string |t(:timestamp) |


### t(:websocketSymbolNotify)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","args":["instrument.state.notification.BTC"]}')

```
> t(:codequote_responseExampleFormatAll)

```javascript

```
t(:websocketSymbolNotify_para)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol |string |t(:usdcSymbol) |
| <a href="#symbol-status-status">status</a> |string |t(:usdcStatus) |
| baseCoin |string |t(:usdcBaseCoin) |
| quoteCoin |string |t(:usdcQuoteCoin) |
| onlineTime |string |t(:usdcOnlineTime) |
| deliverTime |string |t(:deliveryTime) |


## Private Topics
### t(:userPositionsInfo)
> t(:codequote_subscribe)

```javascript

ws.send('{"op":"subscribe","id":"{100002}","args":["user.openapi.option.position"]}');

```

> t(:codequote_snapshot)

```javascript
{
    "id":"b9f465ed-0552-45c2-a2d5-362af0bbf939",
    "topic":"user.openapi.option.position",
    "creationTime":1654746065268,
    "data":{
        "result":[
            {
                "symbol":"BTC-9JUN22-30500-C",
                "positionStatus":"",
                "side":"Sell",
                "size":"-0.0100",
                "entryPrice":"20.00000000",
                "sessionAvgPrice":"20.00000000",
                "markPrice":"62.2119183",
                "positionIM":"",
                "positionMM":"",
                "sessionUPL":"",
                "sessionRPL":"",
                "createdAt":1654745293038,
                "updatedAt":1654745293038
            }
        ],
        "version":2,
        "baseLine":15,
        "dataType":"NEW"
    }
}
```

> t(:codequote_delta)

```javascript

{
    "id":"70bd3a99-0e80-4713-8cd1-6b8e8befffd9",
    "topic":"user.openapi.option.position",
    "creationTime":1654745293064,
    "data":{
        "result":[
            {
                "symbol":"BTC-9JUN22-30500-C",
                "positionStatus":"",
                "side":"Sell",
                "size":"-0.01",
                "entryPrice":"20.00000000",
                "sessionAvgPrice":"20.00000000",
                "markPrice":"65.2197913",
                "positionIM":"",
                "positionMM":"",
                "sessionUPL":"",
                "sessionRPL":"",
                "createdAt":1654745293038,
                "updatedAt":1654745293038
            }
        ],
        "version":2,
        "baseLine":15,
        "dataType":"CHANGE"
    }
}

```



t(:usdcPositionDesc)

t(:usdcCommonDesc)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) |string |t(:usdcSymbol) |
| positionStatus |string |t(:usdcPositionStatus) |
| t(:row_parameter_side) |string |t(:side) |
| size |string |t(:usdcSize) |
| entryPrice |string |t(:entryPrice) |
| sessionAvgPrice |string |t(:sessionAvgPrice) |
| markPrice |string |t(:usdcMarkPrice) |
| positionIM |string |t(:im) |
| positionMM |string |t(:usdcMm) |
| sessionUPL |string |t(:sessionUpl) |
| sessionRPL |string |t(:sessionRpl) |
| createdAt |number |t(:createdAt) |
| updatedAt |number |t(:updatedAt) |

### t(:userFilledHistory)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","id":"{100002}","args":["user.openapi.option.trade"]}');
```

> t(:usdc_trade_codequote_snapshot)

```javascript
{
    "id":"5767b59e-3034-43a9-851f-61ed50fccddc",
    "topic":"user.openapi.option.trade",
    "creationTime":1646188735928,
    "data":{
        "result":[
            {
                "orderId":"a64db071-3c98-44db-bcc8-d4a71e7aaf86",
                "orderLinkId":"",
                "tradeId":"55565169-2da0-5cb3-9dc8-6669c6d777c9",
                "symbol":"BTC-4MAR22-42000-P",
                "side": "Sell",
                "execPrice":"840",
                "execQty":"0.04",
                "execFee":"0.52943604",
                "feeRate":"0.0003",
                "tradeTime":1646188735862,
                "lastLiquidityInd":"TAKER",
                "execType":"TRADE",
                "iv": "0.6544782237284431",
                "markIv": "0.6447",
                "underlyingPrice": "20098.8800",
                "markPrice": "759.5557",
                "indexPrice": "20103.2800",
            }
        ],
        "version":4,
        "baseLine":1
    }
}
```


t(:usdcFilledHistory)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| orderId |string | t(:usdcOrderId)|
| orderLinkId |string |t(:orderLinkId) |
| tradeId |string |t(:usdcTradeId) |
| t(:row_parameter_symbol) |string |t(:usdcSymbol) |
| t(:row_parameter_side) |string |t(:side) |
| execPrice |string |t(:excPrice) |
| execQty |string |t(:execQty) |
| execFee |string |t(:execFee) |
| feeRate|string |t(:feeRate) |
| tradeTime|number |t(:tradeTime) |
| lastLiquidityInd|string |t(:lastLiquidityInd) |
| execType |string |t(:execType) |
| underlyingPrice |string|t(:usdcUnderlyingPrice)|
| markPrice |string|t(:usdcMarkPrice)|
| indexPrice |string|t(:usdcIndexPrice)|
| markIv |string|t(:usdcMarkPriceIv)|
| iv|string|t(:usdcIv)|


### t(:activeOrders_new)

> t(:codequote_subscribe)

```javascript
 ws.send('{"op":"subscribe", "args":["user.order"]}');
```

> t(:codequote_snapshot)

```javascript
{
    "id": "0feb2c52-d10c-4f25-a60c-59e0b6755bbb17195215-6820-4d50-abf8-7c98f9e00570",
    "topic": "user.order",
    "creationTime": 1658123196619,
    "data": {
        "orderId": "0feb2c52-d10c-4f25-a60c-59e0b6755bbb",
        "symbol": "BTC-30SEP22-28000-C",
        "orderStatus": "New",
        "side": "Buy",
        "orderPrice": "460",
        "orderAllSize": "1",
        "orderFilledSize": "0",
        "orderRemainingSize": "1",
        "orderType": "Limit",
        "orderTime": "1658123196611",
        "timeInForce": "GoodTillCancel",
        "createTimeStamp": "1658123196611",
        "updateTimeStamp": "1658123196617",
        "orderLinkId": "option0008",
        "execType": "newed",
        "iv": "0.0",
        "version": "286819574",
        "placeMode": "basic",
        "placeType": "price",
        "userId": "533285"
    }
}
```

t(:usdcWssOrderNew)
t(:usdcWssOrderNewDesc)

<aside class="notice">
t(:usdc_websocket_orderDelta_notice)
</aside>

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string |t(:usdcOrderId)|
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|orderStatus |string|t(:orderStatus)|
|t(:row_parameter_side) |string|t(:side)|
|<a href="#price-price">orderPrice</a> |string|t(:usdcOrderPrice)|
|orderAllSize |string|t(:usdcOrderAllSize)|
|orderFilledSize |string|t(:usdcOrderFilledSize)|
|orderRemainingSize |string|t(:row_comment_leaves_qty)|
|orderType |string|t(:row_comment_order_type)|
|orderTime |string|t(:usdcOrderTime)|
|t(:row_parameter_timeInForce)|string|t(:row_comment_timeInForce)|
|createTimeStamp|string|t(:createdAt)|
|updateTimeStamp|string|t(:updatedAt)|
|orderLinkId |string|t(:orderLinkId)|
|execType |string|t(:usdcExecType)|
|iv |string|t(:optionIv)|
|version |string|t(:usdcVersion)|
|cancelType|string|t(:usdcCancelType)|
|userId|string|t(:usdcUserId)|
|placeMode |string|t(:usdcPlayMode)|
|placeType |string|t(:usdcPlayType)|


### t(:activeOrders)

> t(:codequote_subscribe)

```javascript
 ws.send('{"op":"subscribe","id":"{100003}","args":["user.openapi.option.order"]}');
```

> t(:codequote_snapshot)

```javascript
{
    "id": "9cc72f54-a80b-4ce0-b20b-e2c485797af1",
    "topic": "user.openapi.option.order",
    "creationTime": 1664184773564,
    "data": {
        "result": [
            {
                "orderId": "4c1e6c4f-e778-460d-8155-cb19ae6ee144",
                "orderLinkId": "",
                "createdAt": 1664184773539,
                "updatedAt": 1664184773539,
                "symbol": "BTC-27SEP22-21000-P",
                "orderStatus": "New",
                "side": "Buy",
                "price": "500.00000000",
                "cashFlow": null,
                "realisedPnl": "",
                "qty": "0.5",
                "cumExecQty": "0",
                "leavesQty": "0.5",
                "orderIM": "252.8784385000000000",
                "orderType": "Limit",
                "reduceOnly": 0,
                "timeInForce": "GoodTillCancel",
                "cumExecFee": "0",
                "iv": "0.000",
                "orderPnl": "",
                "cumExecValue": "0",
                "cancelType": "UNKNOWN",
                "placeType": "price",
                "blockTradeId": "",
                "updateTimeStamp": 1664184773557
            }
        ],
        "baseLine": 6,
        "dataType": "CHANGE",
        "version": 2
    }
}
```

> t(:codequote_delta)

```javascript
{
  "id":"620aeb31-b281-4736-9318-b9193c95ec33",
  "topic":"user.openapi.option.order",
  "creationTime":1646212354560,
  "data":{
  "result":[
    {
      "orderId":"41c44ec8-c8ca-40c5-b468-6fc252bfc081",
      "orderLinkId":"1000ss0005",
      "createdAt":1646212354483,
      "updatedAt":1646212354483,
      "symbol":"BTC-24JUN22-25000-P",
      "orderStatus":"New",
      "side":"Buy",
      "price":"100",
      "cashFlow":null,
      "realisedPnl":"",
      "qty":"1",
      "cumExecQty":"0",
      "leavesQty":"1",
      "orderIM":"110",
      "orderType":"Limit",
      "reduceOnly":0,
      "timeInForce":"GoodTillCancel",
      "cumExecFee":"0",
      "iv":"0.533",
      "orderPnl":"",
      "cumExecValue":"0",
      "cancelType":"UNKNOWN"
    }
  ],
    "version":13,
    "baseLine":2,
    "dataType":"CHANGE"
}
}
```

t(:usdcActiveOrder)
t(:usdcCommonDesc)

<aside class="warning">
t(:usdc_websocket_orders_warning)
</aside>

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string |t(:usdcOrderId)|
|orderLinkId |string|t(:orderLinkId)|
|createdAt|number|t(:createdAt)|
|updatedAt|number|t(:updatedAt_depreciate)|
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|orderStatus |string|t(:orderStatus)|
|t(:row_parameter_side) |string|t(:side)|
|t(:row_parameter_price) |string|t(:usdcOrderPrice)|
|cashFlow|string|t(:cashFlow)|
|realisedPnl|string|t(:realisedPnl)|
|qty|string|t(:usdcOrderQty)|
|cumExecQty |string|t(:cumExecQty)|
|leavesQty |string|t(:row_comment_leaves_qty)|
|orderIM |string|t(:im)|
|orderType |string|t(:row_comment_order_type)|
|reduceOnly |number|t(:reduceOnly)|
|t(:row_parameter_timeInForce)|string|t(:row_comment_timeInForce)|
|cumExecFee |string|t(:cumExecFee)|
|iv |string|t(:optionIv)|
|orderPnl |string| Order PNL|
|cumExecValue |string|t(:cumExecValue)|
|cancelType|string|t(:usdcCancelType)|
|placeType|string|t(:optionPlaceType_comment)|
|blockTradeId |string|t(:blockTradeId)|
|updateTimestamp|long|t(:updatedAt)|


### t(:websocketService)

> t(:codequote_subscribe)

```javascript
ws.send(json.dumps({"op": "subscribe", "id": "{100003}","args": ["user.service"]}))
```

> t(:codequote_snapshot)

```javascript
{
    "id": "8110961210943238",
    "topic": "user.service",
    "creationTime": 1660535756358,
    "data": {
        "pushId": "11c9c4d888502c3b",
        "serviceType": "PORTFOLIO_MARGIN",
        "operationType": "SELF",
        "serviceStep": "OPEN",
        "serviceStatus": "SUCCESS",
        "version": 18
    }
}
```

t(:usdc_margin_mode)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| pushId |string |t(:usdc_userService_pushId) |
| serviceType |string |t(:usdc_userService_serviceType) |
| operationType |string |t(:usdc_userService_operationType) |
| serviceStep |string |t(:usdc_userService_serviceStep) |
| serviceStatus |string |t(:usdc_userService_serviceStatus) |

### t(:userGreeks)

> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","id":"{100003}","args":["user.openapi.greeks"]}');

```

> t(:codequote_snapshot)

```javascript

{
    "id":"b3666f79-abf0-45a6-9c6d-ff4d41912b57",
    "topic":"user.openapi.greeks",
    "creationTime":1646274372152,
    "data":{
        "result":[
            {
                "coin":"BTC",
                "totalDelta":"0.0006714372",
                "totalGamma":"-0.0000000654",
                "totalVega":"-0.3207237154",
                "totalTheta":"0.1142353260"
            }
        ],
        "version":3984,
        "baseLine":1
    }
}

```

t(:udscGeeksDesc)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| coin |string |t(:usdcBaseCoin) |
| totalDelta |string |t(:delta) |
| totalGamma |string |t(:gamma) |
| totalVega|string |t(:vega) |
| totalTheta |string |t(:theta) |


### t(:userMmpEvent)

> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","id":"{100003}","args":["user.mmp.event"]}');

```

> t(:codequote_snapshot)

```javascript
{
    "id":"1714254779362547",
    "topic":"user.mmp.event",
    "creationTime":1654138213982,
    "data":{
        "triggerStatus":"MMP_FREEZE",
        "triggerTimestamp":"1654138213787",
        "frozenPeriodMs":"9999999999999",
        "baseCoin":"BTC"
    }
}

```

t(:usdcMmpEventDesc)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| triggerStatus |string |t(:usdcMmpTriggerStatus) |
| triggerTimestamp |string |t(:usdcMmpTriggerTimestamp) |
| frozenPeriodMs |string |t(:usdcFrozenPeriodMs) |
| baseCoin|string |t(:usdcBaseCoin) |
