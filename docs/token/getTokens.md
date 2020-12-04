# Get Tokens

Get token list

**Method** : `GET`

**URL** : `/api/scan/tokens`

## Success Response

**Code** : `201 CREATED`

**Body**

```json
{
    "code": 0,
    "message": "Success",
    "ttl": 1,
    "data": {
        "detail": {
            "CENNZ": {
                "symbol": "CENNZ",
                "accuracy": 4,
                "id": 1,
                "total_issuance": "50000000000000000000",
                "available_balance": "26000000000000000000",
                "locked_balance": "10000000000000000000"
            },
            "CPAY": {
                "symbol": "CPAY",
                "accuracy": 4,
                "id": 2,
                "total_issuance": "210715383551538102034124770858930254020",
                "available_balance": "202747397621542581282156564637953782295",
                "locked_balance": "0"
            }
        },
        "token": [
            "CENNZ",
            "CPAY"
        ]
    }
}
```
