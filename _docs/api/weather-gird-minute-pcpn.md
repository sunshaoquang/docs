---
title: 分钟级降水（邻近预报）
book: API
service: api
data: weather
version: 6.1
description: 由中国气象局、清华大学以及和风天气联合研发的我国首个精确到1公里格点的全国分钟级降雨预报数据，为每一分钟的降雨进行预测。
toc: true
---

## 数据介绍

由中国气象局、清华大学以及和风天气联合研发的我国首个精确到1公里格点的全国分钟级降雨预报数据，为每一分钟的降雨进行预测。[了解更多](https://www.heweather.com/blog/live-forecast)

## 获取方式

HTTP GET

## 数据格式

JSON

## 请求URL

**商业版：**

```
https://api.heweather.net/s6/weather/grid-minute?{parameters}
```

`parameters`代表请求参数，包括必选和可选参数。所有请求参数均使用`&`进行分隔，参数值存在中文或特殊字符的情况，需要对参数进行 **url encode**。

> 请注意，在替换`{parameters}`对应值的时候，URL中不要包含大括号`{}`

### 请求URL示例

```
# 获取某一坐标分钟级降水情况：
https://api.heweather.net/s6/weather/grid-minute?location=116.4,39.9&key=xxx
```

## 请求参数

| 参数     | 描述                                                         | 选择 | 示例值               |
| -------- | ------------------------------------------------------------ | ---- | -------------------- |
| location | 需要查询的地区，仅可使用经纬度坐标查询<br>经纬度格式：经度,纬度（**经度在前纬度在后**，英文`,`分隔，十进制格式，北纬东经为正，南纬西经为负 | 必选 | location=116.40,39.9 |
| lang     | 多语言，可以不使用该参数，默认为简体中文<br>详见[多语言参数](/docs/refer/i18n) | 可选 | lang=en              |
| unit     | 单位选择，公制（m）或英制（i），默认为公制单位<br>详见[度量衡单位参数](/docs/refer/unit) | 可选 | unit=i               |
| key      | 用户认证key，请参考[如何获取你的KEY](https://www.heweather.com/support/setup-app-key)<br>支持[数字签名](/docs/refer/sercet-authorization)方式进行认证，推荐使用 | 必选 | key=xxxxxxxxxxxxxx   |

## 返回参数和数值说明

### `basic` 基础信息

| 参数        | 描述                     | 示例值     |
| ----------- | ------------------------ | ---------- |
| lat         | 地区／城市纬度           | 39.956074  |
| lon         | 地区／城市经度           | 116.310316 |
| parent_city | 该地区／城市的上级城市   | 北京       |
| admin_area  | 该地区／城市所属行政区域 | 北京       |
| cnty        | 该地区／城市所属国家名称 | 中国       |
| tz          | 该地区／城市所在时区     | +8         |

### `grid_minute_forecast` 临近预报

| 参数 | 描述                           | 示例值           |
| ---- | ------------------------------ | ---------------- |
| date | 预报日期，格式yyyy-MM-dd HH:mm | 2013-12-30 20:35 |
| txt  | 分钟降雨描述                   | 未来2小时无降雨  |

### `pcpn_5m` 未来两小时5分钟降水量

| 参数 | 描述                       | 示例值           |
| ---- | -------------------------- | ---------------- |
| time | 时间，格式yyyy-MM-dd HH:mm | 2013-12-30 20:35 |
| pcpn | 降水量                     | 10               |

### `pcpn_type`降水类型

| 参数      | 描述                     | 示例 |
| --------- | ------------------------ | ---- |
| pcpn_type | 降水类型，rain雨，snow雪 | rain |

### `update` 接口更新时间

| 参数 | 描述                                     | 示例值           |
| ---- | ---------------------------------------- | ---------------- |
| loc  | 当地时间，24小时制，格式yyyy-MM-dd HH:mm | 2017-10-25 12:34 |
| utc  | UTC时间，24小时制，格式yyyy-MM-dd HH:mm  | 2017-10-25 04:34 |

### `status` 接口状态

| 参数   | 描述                                                         | 示例 |
| ------ | ------------------------------------------------------------ | ---- |
| status | 接口状态，具体含义请参考[接口状态码及错误码](/docs/refer/status-code) | ok   |

## 数据返回示例

```json
{
    "HeWeather6": [
        {
            "basic": {
                "admin_area": "北京",
                "cnty": "中国",
                "lat": "39.90",
                "lon": "116.40",
                "parent_city": "北京",
                "tz": "+8.0"
            },
            "grid_minute_forecast": {
                "date": "2018-04-08 18:25"
            },
            "pcpn_5m": [
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 18:25"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 18:30"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 18:35"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 18:40"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 18:45"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 18:50"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 18:55"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 19:00"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 19:05"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 19:10"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 19:15"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 19:20"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 19:25"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 19:30"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 19:35"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 19:40"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 19:45"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 19:50"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 19:55"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 20:00"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 20:05"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 20:10"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 20:15"
                },
                {
                    "pcpn": "0.0",
                    "time": "2018-04-08 20:20"
                }
            ],
            "pcpn_type": {
                "pcpn_type": "rain"
            },
            "status": "ok",
            "update": {
                "loc": "2018-04-08 18:25",
                "utc": "2018-04-08 10:25"
            }
        }
    ]
}
```