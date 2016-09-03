# Key-value store

This is a proof of concept key-value store that uses `nimona/journal` and 
`nimona/registry`. It uses the journal as a WAL (Write Ahead Log) to store
all events (`SET`, `DELETE`) and the registry to replay these events and
recreate the state of the key-value store.

It exposes a very simple HTTP interface in the form of `GET /:key` and 
`POST /:key`. 

The end goal is to have a fully distributed key-value store with raft leader 
election and journal replication over some form of RPC.
