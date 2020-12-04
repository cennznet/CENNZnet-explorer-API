# Check hash

Check whether a hash is an extrinsic hash or a block hash

**Method** : `GET`

**URL** : `/api/scan/check_hash?hash={hash}`


## Request Query Parameters

| Parameter | IsOptional | Type | Description |
|:----------|:---|:-----|:------------|
|hash|No|string|A block hash or an extrinsic hash|

**Example** 

`/api/scan/check_hash?hash=0x1ab5bcc30bb2f3b2fb6cdd2a737c506184bd29f131dd050b5073990880d0a1ff`


## Success Response

**Condition** : The hash is a valid block hash or extrinsic hash

**Code** : `201 CREATED`

**Body**

```json
{
    "code": 0,
    "message": "Success",
    "ttl": 1,
    "data": {
        "hash_type": "block"
    }
}
```


## Error Responses

**Condition** : The hash is not a valid block hash or extrinsic hash

**Code** : `404 Not Found`

**Content example**

```json
{
    "statusCode": 404,
    "message": "Not Found"
}
```