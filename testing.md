# Testing using curl

# Chain
```bash
curl http://localhost:82/chain
```

Example Response
```json
{"chain":[{"index":1,"previous_hash":"1","proof":100,"timestamp":1727182555.7357824,"transactions":[]},{"index":2,"previous_hash":"cdd8217a097ba6c2591755c79280e76aaab34712279b33765a93fc499f391953","proof":231098,"timestamp":1727182574.7121446,"transactions":[{"amount":1,"recipient":"6b8ff8ffa0c94e01ba861c638d889463","sender":"0"}]},{"index":3,"previous_hash":"a108991967af43e93bdbb869234f9528e7af091b962bb5e96f5177e648a3ef9a","proof":20158,"timestamp":1727182577.9086704,"transactions":[{"amount":1,"recipient":"6b8ff8ffa0c94e01ba861c638d889463","sender":"0"}]},{"index":4,"previous_hash":"3ba959ff2bfd7586d18d7d021094d8d69963330e93c24af65eb66bd3584b9bca","proof":61973,"timestamp":1727182580.1446762,"transactions":[{"amount":1,"recipient":"6b8ff8ffa0c94e01ba861c638d889463","sender":"0"}]},{"index":5,"previous_hash":"e03f593a0246185588a9a4e91bb9ff11a6aef27723e5cd81dadd6737d5d24ccc","proof":3239,"timestamp":1727182581.5793383,"transactions":[{"amount":1,"recipient":"6b8ff8ffa0c94e01ba861c638d889463","sender":"0"}]}],"length":5}

```

# Mine
```bash
curl http://localhost:82/chain
```

Example Response
```json
{"index":5,"message":"New Block Forged","previous_hash":"e03f593a0246185588a9a4e91bb9ff11a6aef27723e5cd81dadd6737d5d24ccc","proof":3239,"transactions":[{"amount":1,"recipient":"6b8ff8ffa0c94e01ba861c638d889463","sender":"0"}]}
```

# Nodes Resolve
```bash
curl http://localhost:82/nodes/resolve
```

Example Response
```json
{"chain":[{"index":1,"previous_hash":"1","proof":100,"timestamp":1727182555.7357824,"transactions":[]},{"index":2,"previous_hash":"cdd8217a097ba6c2591755c79280e76aaab34712279b33765a93fc499f391953","proof":231098,"timestamp":1727182574.7121446,"transactions":[{"amount":1,"recipient":"6b8ff8ffa0c94e01ba861c638d889463","sender":"0"}]},{"index":3,"previous_hash":"a108991967af43e93bdbb869234f9528e7af091b962bb5e96f5177e648a3ef9a","proof":20158,"timestamp":1727182577.9086704,"transactions":[{"amount":1,"recipient":"6b8ff8ffa0c94e01ba861c638d889463","sender":"0"}]},{"index":4,"previous_hash":"3ba959ff2bfd7586d18d7d021094d8d69963330e93c24af65eb66bd3584b9bca","proof":61973,"timestamp":1727182580.1446762,"transactions":[{"amount":1,"recipient":"6b8ff8ffa0c94e01ba861c638d889463","sender":"0"}]},{"index":5,"previous_hash":"e03f593a0246185588a9a4e91bb9ff11a6aef27723e5cd81dadd6737d5d24ccc","proof":3239,"timestamp":1727182581.5793383,"transactions":[{"amount":1,"recipient":"6b8ff8ffa0c94e01ba861c638d889463","sender":"0"}]},{"index":6,"previous_hash":"69e0eac93a11590b05eb6749837e5fc71d0e56c18eaecb4d41f2780704b35537","proof":6888,"timestamp":1727182842.9783645,"transactions":[{"amount":1,"recipient":"6b8ff8ffa0c94e01ba861c638d889463","sender":"0"}]}],"message":"Our chain is authoritative"}

```

# Transaction New
```curl
curl -X POST http://localhost:82/transactions/new \
-H "Content-Type: application/json" \
-d '{
    "sender": "address1",
    "recipient": "address2",
    "amount": 10
}'

```

Example Response
```json
{
  "message": "Transaction will be added to Block 3"
}
```

# Register Node

```curl
curl -X POST http://localhost:82/nodes/register \
-H "Content-Type: application/json" \
-d '{
    "nodes": ["New Node"]
}'
```

Example response
```json
{
  "message": "New nodes have been added", 
  "total_nodes": [
    "New Node"
  ]
}

```