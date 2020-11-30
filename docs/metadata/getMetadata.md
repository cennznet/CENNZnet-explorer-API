# Get Metadata

Get Basic Chain Information

**Method** : `POST`

**URL** : `/api/scan/metadata`


## Request Body

Do not need to supply a request body with this method.

## Success Response

**Code** : `201 CREATED`

**Body**

```ts
{
  code: number;
  message: string;
  ttl: number;
  data: {
    addressType: number;
    blockTime: number;
    balanceAccuracy: number;
    commissionAccuracy: number;
    blockNum: number;
    count_event: number;
    count_extrinsic: number;
    count_signed_extrinsic: number;
    finalized_blockNum: number;
    implName: string;
    specVersion: number;
    networkNode: string;
    eraLength: number;
    eraProgress: number;
    current_validator_count: number;
    count_transfer: number;
  }
}

```


**Example**

```json
{
    "code": 0,
    "message": "Success",
    "ttl": 1,
    "data": {
        "balanceAccuracy": 9,
        "commissionAccuracy": 9,
        "networkNode": "azalea",
        "blockNum": 3779985,
        "count_event": 7431576,
        "count_extrinsic": 7101805,
        "count_signed_extrinsic": 1022649,
        "finalized_blockNum": 3744236,
        "implName": "cennznet-node",
        "specVersion": 36,
        "blockTime": 5000,
        "eraLength": 720,
        "eraProgress": 160,
        "current_validator_count": 12,
        "count_transfer": 199654
    }
}
```
