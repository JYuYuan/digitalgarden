---
{"dg-publish":true,"permalink":"/06/api/","dg-note-properties":{}}
---

# 直播推送任务API文档

## 文档地址
https://ea-dev.jncapp.cn/live-docs

## 直连网站
https://live.ddom.qzz.io/

## API接口

### 1. 推送直播任务

**接口地址：**
```
https://api-ea-{环境}.jncapp.cn/jnc-live-service/live/base/v1/live-task/push/{APPKEY}/{业务类型关系编码}/{业务编码}/{执行用户}/{业务编码}
```

#### UAT环境示例

**示例1：**
```
https://api-ea-uat.jncapp.cn/jnc-live-service/live/base/v1/live-task/push/z4AR3BKKQfKFqxDUL86EbxlRRVeS7XB8/BRbb20644581ba4c368bf36dc655ef04d8/S1MY2e1908/jyy/S1MY2e1908
```

**参数说明：**
- APPKEY: `z4AR3BKKQfKFqxDUL86EbxlRRVeS7XB8` （公司的 APPKEY）
- 业务类型关系编码: `BRbb20644581ba4c368bf36dc655ef04d8`
- 业务编码: `S1MY2e1908`
- 执行用户: `jyy`

**示例2：企业微信推送任务**
```
https://api-ea-uat.jncapp.cn/jnc-live-service/live/base/v1/live-task/push/z4AR3BKKQfKFqxDUL86EbxlRRVeS7XB8/BRf6116790a8a04100b114edb14a2421d6/lsxsh/18408226080/lsxsh
```

**参数说明：**
- APPKEY: `z4AR3BKKQfKFqxDUL86EbxlRRVeS7XB8` （公司的 APPKEY）
- 业务类型关系编码: `BRf6116790a8a04100b114edb14a2421d6` （企业微信）
- 业务编码: `lsxsh`
- 执行用户: `18408226080`

#### 生产环境示例

**示例：**
```
https://api-ea-prod.jncapp.cn/jnc-live-service/live/base/v1/live-task/push/qkH4OrqWbFMWHxegtcaEbPTM6R7xheSQ/BRf8d31807412c419784553ef2a8d5e149/test/jyy/test
```

**参数说明：**
- APPKEY: `qkH4OrqWbFMWHxegtcaEbPTM6R7xheSQ` （生产环境公司的 APPKEY）
- 业务类型关系编码: `BRf8d31807412c419784553ef2a8d5e149`
- 业务编码: `test`
- 执行用户: `jyy`

---

### 2. 推送凭证任务

**接口地址：**
```
https://api-ea-uat.jncapp.cn/jnc-live-service/live/base/v1/evidence-task/push/{APPKEY}/{业务类型关系编码}/1
```

**示例：**
```
https://api-ea-uat.jncapp.cn/jnc-live-service/live/base/v1/evidence-task/push/DTaOCbHREFIItU405Mrnxn5QbUNkQs5K/BRaeb2e47a96124b08b00670efdc7cadf4/1
```

**参数说明：**
- APPKEY: `DTaOCbHREFIItU405Mrnxn5QbUNkQs5K` （公司的 APPKEY）
- 业务类型关系编码: `BRaeb2e47a96124b08b00670efdc7cadf4`
- 任务ID: `1` （固定值，写死）

---

## 备注

- 环境：UAT测试环境 / 生产环境
- 服务：jnc-live-service
- 版本：v1
- UAT域名：`api-ea-uat.jncapp.cn`
- 生产域名：`api-ea-prod.jncapp.cn`

---

创建时间: 2026-06-25
