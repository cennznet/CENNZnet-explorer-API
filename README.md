**CENNZnet explorer APIs**
---
The CENNZnet explorer APIs are provided as a community service to access CENNZnet blockchain data.

Metadata apis
---
[Get Metadata](./docs/metadata/getMetadata.md) :

`GET /api/scan/metadata`

Token apis
---
[Get Token List](./docs/token/getTokens.md) : 

`GET /api/scan/tokens`


Extrinsic apis
---
[Get Extrinsic List](./docs/extrinsic/getExtrinsics.md) : 

`GET /api/scan/extrinsics?signed={signed}&address={address}&row={row}&page={page}`

[Get Extrinsic Detail](./docs/extrinsic/getExtrinsic.md) : 

`GET /api/scan/extrinsic?extrinsic_index={extrinsic_index}` 

`GET /api/scan/extrinsic?hash={hash}`

Block apis
---
[Get Block List](./docs/block/getBlocks.md) : 

`GET /api/scan/blocks?row={row}&page={page}`

[Get Block Detail](./docs/block/getBlock.md) : 

`GET /api/scan/block?block_num={block_number}`

`GET /api/scan/block?block_hash={block_hash}`

[Check Hash Type](./docs/block/checkHashType.md) : 

`GET /api/scan/check_hash?hash={hash}`


