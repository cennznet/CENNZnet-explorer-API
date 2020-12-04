# Get Extrinsics

Get Extrinsics

**Method** : `GET`

**URL** : 

`/api/scan/extrinsics?signed={signed}&row={row}&page={page}`

`/api/scan/extrinsics?signed={signed}&address={address}&row={row}&page={page}`


## Request Query Parameters

| Parameter | IsOptional | Type | Description |
|:----------|:---|:-----|:------------|
|signed|No|enum ('signed', 'all')|Get only signed extrinsics|
|address|Yes|string|Get extrinsics of a specific address|
|row|No|number|Specify the number of records to return in one request, specified as an integer from 1 to 100.|
|page|No|number|Specify the page of results to return.<br> For example, `{ ..., page: 2 }` returns the second page of posts results.<br> By retrieving `{ ..., page: 1 }`, then `{ ..., page: 2 }, and so on|


**Example** 

`/api/scan/extrinsics?signed=signed&row=1&page=0`

`/api/scan/extrinsics?signed=signed&address=5FLXuBZYiz7q2ZV8xV8bmkC6BVuGoiwBqT7jXL93eWz3jMRW&row=1&page=0`

## Success Response

**Code** : `201 CREATED`

**Body**

```json
{
    "code": 0,
    "message": "Success",
    "ttl": 1,
    "data": {
        "extrinsics": [
            {
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
                "signature": "0x41876536e3a63a906b1c49bd448dd8d97f73d2f181e4b96524b293fcccd81c04828cca95a87820d7d4f4962b5584ead08df1682ae1fae21da95cb0ee306f4904"
            }
          ]
      }
}
```

## Error Responses

**Condition** : If `row` or `page` is invalid.

**Code** : `400 Bad Request`


### Or

**Condition** : If `signed` is not a valid enum value

**Code** : `400 BAD REQUEST`

**Content example**

```json
{
    "statusCode": 400,
    "message": [
        "signed must be a valid enum value"
    ],
    "error": "Bad Request"
}
```