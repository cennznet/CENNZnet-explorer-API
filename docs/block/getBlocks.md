# Get Blocks

Get blocks

**Method** : `GET`

**URL** : `/api/scan/blocks?row={row}&page={page}`


## Request Query Parameters

| Parameter | IsOptional | Type | Description |
|:----------|:---|:-----|:------------|
|row|No|number|Specify the number of records to return in one request, specified as an integer from 1 to 100.|
|page|No|number|Specify the page of results to return.<br> For example, `{ ..., page: 2 }` returns the second page of posts results.<br> By retrieving `{ ..., page: 1 }`, then `{ ..., page: 2 }, and so on|


**Example** 

`/api/scan/blocks?row=1&page=0`

## Success Response

**Code** : `201 CREATED`

**Body**

```json
{
    "code": 0,
    "message": "Success",
    "ttl": 1,
    "data": {
        "blocks": [
            {
                "hash": "0x64c7c08d3fdc6d9f72d6b9d943ac6860c2a0b2b1f26ae4ff5891821a38b9d7fe",
                "block_num": 3997696,
                "block_timestamp": 1606767155,
                "event_count": 1,
                "extrinsics_count": 1,
                "validator": "5DoZ3fwdTjvo8EZAVkZLPMkWAEwMpvDX7TUvYrohFUTbQpWN",
                "finalized": true
            }
        ],
        "count": 3988906
    }
}
```

## Error Responses

**Condition** : If `row` or `page` is invalid.

**Code** : `400 Bad Request`
