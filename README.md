# DApp JS

Javascript API for DApp.

<!-- TOC -->

- [Common](#common)
    - [1. DApp.getAppInfo](#1-dappgetappinfo)
    - [2. DApp.share](#2-dappshare)
    - [3. DApp.scanQRCode](#3-dappscanqrcode)
    - [4. DApp.getCurrentWallet](#4-dappgetcurrentwallet)
    - [5. DApp.getWallets](#5-dappgetwallets)
- [EOS](#eos)
    - [1. DApp.eos.transaction()](#1-dappeostransaction)
- [ETH](#eth)
    - [1. DApp.web3.eth.sendTransaction()](#1-dappweb3ethsendtransaction)

<!-- /TOC -->

### Common

#### 1. DApp.getAppInfo

```javascript
DApp.getAppInfo()
```

##### Returns

`Object`:
- `result`: `Boolean`
- `data`: `Object`
    - `name`: `String`
    - `system`: `String`
    - `version`: `String`
    - `sys_version`: `String`
- `msg`: `String`


#### 2. DApp.share

```javascript
DApp.share(params)
```

##### Parameters

`params`- `Object`:
- `title`: `String`
- `desc`: `String`
- `url`: `String`
- `previewImage`: `String`


#### 3. DApp.scanQRCode
```javascript
DApp.scanQRCode()
```

##### Returns

`Object`:
- `result`: `Boolean`
- `data`: `String`
- `msg`: `String`


#### 4. DApp.getCurrentWallet

获取用户当前钱包

```javascript
DApp.getCurrentWallet()
```

##### Returns

`Object`:
- `result`: `Boolean`
- `data`: `Object`
    - `name`: `String`
    - `address`: `String`
    - `blockchain`: `String`
- `msg`: `String`


#### 5. DApp.getWallets

获取用户钱包列表


```javascript
DApp.getWallets()
```
##### Parameters

`params`- `Object`:
- `blockchain`: `String` - 可选
- `chainId`: `String`- 可选
- `permission`: `String` - 可选 'owner | active'  *待讨论

##### Returns

`Object`:
- `result`: `Boolean`
- `data`: `Array`
    - `address`: `String`
    - `name`: `String`
    - `blockchain`: `String`
- `msg`: `String`



### EOS

window下注入DApp.eos 实例， 实现eos.js的所有get请求

至少实现标准的 transaction 请求 

#### 1. DApp.eos.transaction()

##### Parameters

`params`- `Object`:
- `actions`: `Array`- Standard EOS actions
- `address`: `String` - 可选 public key 作为身份区分 * 待讨论

##### Returns

`Object`:
- `result`: `Boolean`
- `data`: `Object`
    - `transactionId` : `Stirng`
- `msg`: `String`


### ETH

window下注入DApp.web3 实例, 实现web3.js的所有get请求

至少实现通用 sendTransaction 请求

#### 1. DApp.web3.eth.sendTransaction()

##### Parameters

`params`- `Object`:
- `from`: `String`
- `to`: `String` 可选
- `value`: `Number|String|BigNumber` 可选
- `gas`: `Number|String|BigNumber` 可选
- `gasPrice`: `Number|String|BigNumber` 可选
- `data`: `String` 可选
- `nonce`: `Number` 可选

##### Returns

`Object`:
- `result`: `Boolean`
- `data`: `Object`
    - `transactionId` : `Stirng`
- `msg`: `String`








