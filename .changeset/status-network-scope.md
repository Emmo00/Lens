---\r
'lens': patch\r
---\r
\r
Fix `GET /status`: scope `indexer_state` to the requested network (`?network=`\r
/ `x-network`, defaulting to `STELLAR_NETWORK`) instead of returning whichever\r
chain wrote most recently, and report the answering network and its watched\r
pairs in the response. The SDEX and AMM ingesters now record the real Horizon\r
ledger, so `lastIndexedLedger` is no longer permanently null, and a new\r
`ingestLagSeconds` field surfaces a stalled ingester without Prometheus.\r
