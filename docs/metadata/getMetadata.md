# Get Metadata

Get Basic Chain Information

**Method** : `GET`

**URL** : `/api/scan/metadata`

## Success Response

**Code** : `201 CREATED`

**Body**

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
