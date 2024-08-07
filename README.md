# EngageMinds S2S Event API

## ChangeLog

| Version | Change |
|---------|--------|
| 1       |        |

* HTTP POST TO `https://a.engageminds.ai/s2s/es`
* Request header `Content-Type: application/json` is required
* The API accepts request body compression, in either `gzip` or `deflate` format, specified by the request
  header `Content-Encoding`, which is mandatory in this case.

## RequestBody

| Name | Type                                   | Explain            | Example | Required |
|------|----------------------------------------|--------------------|---------|----------|
| ...  | Array of [EventRequest](#EventRequest) | EventRequest Array |         | ✔︎       |

### EventRequest

| Name   | Type                     | Explain                              | Example | Required |
|--------|--------------------------|--------------------------------------|---------|----------|
| ...    |                          | [BasicFields](COMMON.md#basicfields) |         | ✔︎       |
| events | Array of [Event](#event) | Event Array                          |         | ✔︎       |

### Event

| Name  | Type                           | Explain                                 | Example                                                                                            | Required |
|-------|--------------------------------|-----------------------------------------|----------------------------------------------------------------------------------------------------|----------|
| ts    | int64                          | event trigger timestamp in milliseconds | 1567479919643                                                                                      | ✔︎       |
| cdid  | string                         | account ID                              | 1029                                                                                               | ✖︎       |
| eid   | string                         | EventName                               | app_start                                                                                          | ✔︎       |
| props | map&lt;string,any&gt;          | Event Properties                        | {"duration":30}                                                                                    | ✔︎       |
| err   | Array of [EventErr](#eventErr) | response errors from                    | [{"prop": "EventTest305", "type": "PropInconsistent", "value": "{\"age\":18,\"name\":\"story\"}"}] | ✖︎       |

### EventErr

| Name  | Type   | Explain        | Example         | Required |
|-------|--------|----------------|-----------------|----------|
| type  | string | error type     | UserPropInvalid | ✔︎       |
| prop  | string | property name  | email           | ✖︎       |
| value | any    | property value | a@b.com         | ✔︎       |

## RequestBody JSON Example

```json
[
  {
    "ts": 1683602299467,
    "appk": "xXXxxXxXxxXxxXxxXxxX",
    "ssid": "xXXxxXxXxxXxxXxxXxxX",
    "fit": 1683551893,
    "flt": 1683551896,
    "zo": 480,
    "tz": "Asia\/Shanghai",
    "session": "32fc6332-58f3-4659-8eee-93ddd63fcffd",
    "uid": "889232a0-b5bc-4978-b6b9-2828910537c2",
    "gaid": "f5bb825f-a1b8-44f8-a24d-10ca1ad1abe1",
    "lang": "zh",
    "bundle": "com.example.test",
    "make": "Xiaomi",
    "brand": "Xiaomi",
    "model": "MI 9 SE",
    "os": 1,
    "osv": "12",
    "appv": "2.5.0",
    "sdk": 1,
    "sdkv": "1.0.0",
    "width": 1080,
    "height": 2129,
    "contype": 2,
    "carrier": "中国联通",
    "mccmnc": "4601",
    "gcy": "cn",
    "rid": "4da49ac3-055f-47b9-9be8-2db7aeda0af0",
    "sco": 1,
    "dtype": 1,
    "adtk": 1,
    "ntf": 1,
    "gp": 1,
    "bps": {
      "aaa": 1,
      "bbb": "ccc"
    },
    "events": [
      {
        "ts": 1683602299467,
        "cdid": "xXXxxXxXxxXxx",
        "eid": "app_start",
        "props": {
          "start_reason": "intent://aaa"
        }
      },
      {
        "ts": 1683602299467,
        "cdid": "xXXxxXxXxxXxx",
        "eid": "app_page_view",
        "props": {
          "title": "EmDemo",
          "name": "aaa",
          "url": "a.b.MainFragment",
          "referrer": "a.b.MainPagerActivity"
        }
      }
    ]
  }
]
```

## ResponseBody

| Name   | Type                     | Explain      | Example | Required |
|--------|--------------------------|--------------|---------|----------|
| events | Array of [Event](#event) | error events | ..      | ✖︎       |

## ResponseBody Example

```json
{
  "events": [
    {
      "prop": "EPstoryEventTest305",
      "type": "PropInconsistent",
      "value": "{\"age\":18,\"name\":\"story\"}"
    }
  ]
}
```

SeeAlso [SDK-GO](https://github.com/engageminds/em-sdk-go)  [SDK-JAVA](https://github.com/engageminds/em-sdk-java)