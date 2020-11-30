# Get Extrinsic

Get Extrinsic Detail by extrinsic hash or by extrinsic index

**Method** : `POST`

**URL** : `/api/scan/extrinsic`


## Request Body

```ts
{
  extrinsic_index: string;
}
```
or
```ts
{
  hash: string;
}
```
There should be at least one of `extrinsic_index` and `hash` in the request body.

| Parameter | IsOptional | Type | Description |
|:----------|:---|:-----|:------------|
|extrinsic_index|Must exist if `hash` is not exist|string|extrinsic_index is the combination of the block number and the extrinsic index in that block.<br>For example, for the 2nd extrinsic in block 280000, `extrinsic_index` is `280000-2`|
|hash|Must exist if `extrinsic_index` is not exist|string|Extrinsic hash|


**Example** 
```json
{
	"hash": "0xbe3781892d397395afdde9086cc0028426612468bd37841241284e92facf34ea"
}
```
```json
{
  "extrinsic_index": "3779709-1"
}
```

## Success Response

**Condition** : At least one of `extrinsic_index` and `hash` is in request body and is valid

**Code** : `201 CREATED`

**Body**

```json
{
    "code": 0,
    "message": "Success",
    "ttl": 1,
    "data": {
        "account_id": "5FLXuBZYiz7q2ZV8xV8bmkC6BVuGoiwBqT7jXL93eWz3jMRW",
        "block_num": 3779709,
        "block_timestamp": 1605669700,
        "extrinsic_index": "3779709-1",
        "extrinsic_hash": "0xbe3781892d397395afdde9086cc0028426612468bd37841241284e92facf34ea",
        "call_module": "syloGroups",
        "call_module_function": "updateMember",
        "params": "[{\"name\":\"group_id\",\"type\":\"Hash\",\"value\":\"0x106851423c9fb772de97ab014bba76006e48c0d845acaddb377854bc57c51452\"},{\"name\":\"meta\",\"type\":\"Meta\",\"value\":[[\"chat:message:HEAD\",\"\\\"QmNxXEgMcfCVgdVD1pZBGPRQxLxjZ28m2js21mpRmSrq7i\\\"\"]]}]",
        "fee": "1000000000000",
        "tip": null,
        "finalized": true,
        "success": true,
        "signature": "0x41876536e3a63a906b1c49bd448dd8d97f73d2f181e4b96524b293fcccd81c04828cca95a87820d7d4f4962b5584ead08df1682ae1fae21da95cb0ee306f4904",
        "event": [
            {
                "event_index": "3779709-1",
                "block_num": 3779709,
                "module_id": "system",
                "event_id": "ExtrinsicSuccess",
                "params": "[{\"type\":\"DispatchInfo\",\"value\":{\"weight\":100000,\"class\":\"Normal\",\"paysFee\":true}}]",
                "event_idx": 1,
                "finalized": true,
                "extrinsic_hash": "0xbe3781892d397395afdde9086cc0028426612468bd37841241284e92facf34ea",
                "extrinsic_idx": 1
            }
        ]
    }
}
```

## Error Responses

**Condition** : `extrinsic_index` and `hash` are both not exist in request body

**Code** : `400 Bad Request`


**Content example**

```json
{
    "statusCode": 400,
    "message": [
        "extrinsic_index must be a string",
        "hash must be a string"
    ],
    "error": "Bad Request"
}
```

### Or

**Condition** : The extrinsic is not exist

**Code** : `404 Not Found`

**Content example**

```json
{
    "statusCode": 404,
    "message": "Not Found"
}
```