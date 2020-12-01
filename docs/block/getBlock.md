# Get Block

Get block information

**Method** : `POST`

**URL** : `/api/scan/block`


## Request Body

```ts
{
  block_num: number;
}
```
or
```ts
{
  block_hash: string;
}
```
There should be at least one of `block_num` or `block_hash` in the request body.

| Parameter | IsOptional | Type | Description |
|:----------|:---|:-----|:------------|
|block_num|Must exist if `block_hash` is not exist|number|Block number|
|block_hash|Must exist if `block_num` is not exist|string|Block hash|


**Example** 
```json
{
	"block_num": 2800000
}
```
```json
{
	"block_hash": "0x1ab5bcc30bb2f3b2fb6cdd2a737c506184bd29f131dd050b5073990880d0a1ff"
}
```

## Success Response

**Condition** : At least one of `block_num` or `block_hash` is in request body and is valid

**Code** : `201 CREATED`

**Body**

```json
{
    "code": 0,
    "message": "Success",
    "ttl": 1,
    "data": {
        "hash": "0x1ab5bcc30bb2f3b2fb6cdd2a737c506184bd29f131dd050b5073990880d0a1ff",
        "block_num": 2800000,
        "block_timestamp": 1600065420,
        "event_count": 2,
        "extrinsics_count": 2,
        "validator": "5FpNQ5NfhhRMyE1BMCy7fwPXHtd8ht6mME64AFr58y2ehesc",
        "finalized": true,
        "extrinsics_root": "0xff973cbe567f08691a59b28e919ec26ec13d286eb5391c3cc366ded0072cf168",
        "parent_hash": "0x2c0ef3e639532fbf860f7ecc9cb0c6beab74a08feb06c7e292d013dc3199d892",
        "state_root": "0xee23109354d89e503103a859e910e096e3f974818dec32d70633b1bc2d0bf37c",
        "spec_version": 36,
        "extrinsics": [
            {
                "account_id": "5C4hrfjw9DjXZTzV3MwzrrAr9P1MJhSrvWGWqi1eSuyUpnhM",
                "block_num": 2800000,
                "block_timestamp": 1600065420,
                "extrinsic_index": "2800000-0",
                "extrinsic_hash": "0x5df0999b89a7b8ad70f5a03bb07b2bbb8ab55606278b5004e0779a7e52a883f0",
                "call_module": "timestamp",
                "call_module_function": "set",
                "params": "[{\"name\":\"now\",\"type\":\"Compact<Moment>\",\"value\":1600065420000}]",
                "fee": "0",
                "tip": null,
                "finalized": true,
                "success": true,
                "signature": null
            },
            {
                "account_id": "5C4hrfjw9DjXZTzV3MwzrrAr9P1MJhSrvWGWqi1eSuyUpnhM",
                "block_num": 2800000,
                "block_timestamp": 1600065420,
                "extrinsic_index": "2800000-1",
                "extrinsic_hash": "0x81cd5c07eb3e767c32107e0a2fee1b94f42c89dbf452435016ffd8c6cfcd412e",
                "call_module": "finalityTracker",
                "call_module_function": "finalHint",
                "params": "[{\"name\":\"hint\",\"type\":\"Compact<BlockNumber>\",\"value\":2799995}]",
                "fee": "0",
                "tip": null,
                "finalized": true,
                "success": true,
                "signature": null
            }
        ],
        "events": [
            {
                "event_index": "2800000-0",
                "block_num": 2800000,
                "module_id": "system",
                "event_id": "ExtrinsicSuccess",
                "params": "[{\"type\":\"DispatchInfo\",\"value\":{\"weight\":10000,\"class\":\"Operational\",\"paysFee\":true}}]",
                "event_idx": 0,
                "finalized": true,
                "extrinsic_hash": "0x5df0999b89a7b8ad70f5a03bb07b2bbb8ab55606278b5004e0779a7e52a883f0",
                "extrinsic_idx": 0
            },
            {
                "event_index": "2800000-1",
                "block_num": 2800000,
                "module_id": "system",
                "event_id": "ExtrinsicSuccess",
                "params": "[{\"type\":\"DispatchInfo\",\"value\":{\"weight\":10000,\"class\":\"Normal\",\"paysFee\":true}}]",
                "event_idx": 1,
                "finalized": true,
                "extrinsic_hash": "0x81cd5c07eb3e767c32107e0a2fee1b94f42c89dbf452435016ffd8c6cfcd412e",
                "extrinsic_idx": 1
            }
        ],
        "logs": [
            {
                "block_num": 2800000,
                "log_index": "2800000-0",
                "log_type": "PreRuntime",
                "origin_type": "PreRuntime",
                "data": "{\"data\":\"0x02060000001c03131300000000\",\"engine\":1161969986}"
            },
            {
                "block_num": 2800000,
                "log_index": "2800000-1",
                "log_type": "Seal",
                "origin_type": "Seal",
                "data": "{\"data\":\"0xee71d59474eb1674eb9c1ae21effef949a08fd3384992e3e6c9e495fda1a8a18de491b2e40caefdaf4918e294850bfa77c304eb02ded4718c58474e5be6aa087\",\"engine\":1161969986}"
            }
        ]
    }
}
```

## Error Responses

**Condition** : Neither `block_num` or `block_hash` was found in the request body

**Code** : `400 Bad Request`


**Content example**

```json
{
    "statusCode": 400,
    "message": [
        "block_num must be a positive number",
        "block_hash must be a string"
    ],
    "error": "Bad Request"
}
```

### Or

**Condition** : The block does not exist

**Code** : `404 Not Found`

**Content example**

```json
{
    "statusCode": 404,
    "message": "Not Found"
}
```
