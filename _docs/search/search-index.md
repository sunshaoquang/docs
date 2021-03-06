---
book: 城市搜索
permalink: /docs/search/
title: 城市查询API接口说明
version: 1.0
service: search-index
data: search
description: 功能强大的城市搜索服务，支持中英文模糊搜索，支持IP、经纬度坐标和中国行政区域编码（AD Code）查询城市的详细信息，可指定搜索范围，设置返回结果数量，查询全球热门城市列表等。
---

功能强大的城市搜索服务，支持中英文模糊搜索，支持IP、经纬度坐标和中国行政区域编码（AD Code）查询城市的详细信息，可指定搜索范围，设置返回结果数量，查询全球热门城市列表等。

> 搜索服务完全免费，并且不计入数据访问量

### 在线版本
[https://where.heweather.com](https://where.heweather.com)

### 开发文档
- [城市搜索](/docs/search/find)
- [热门城市](/docs/search/top)

### 主要功能：
* 模糊搜索：支持中英文模糊搜索，可设置搜索范围和返回结果的数量
* 城市范围可控：可设置搜索全球或单独某一个国家
* 返回结果数量：可自定义返回模糊搜索的结果数量
* 支持IP、经纬度坐标和中国AD Code查询
* 热门城市列表：可查询中国或全球热门城市列表
* 多语言：支持多远返回数据

### 应用场景
1. 天气APP中搜索城市，不再需要自己做搜索，直接调用搜索接口进行模糊查询，用户选择正确的结果，并通过这个结果返回天气数据
2. 用户搜索天气时，可在页面中直接展示热门城市，用户直接选择即可，减少搜索步骤提高用户体验
3. 对于上百万的全球城市，不再需要导入城市列表进行检索，直接调用搜索服务即可
4. 不需要维护城市列表，城市信息更新实时获取

