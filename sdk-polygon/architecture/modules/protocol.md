# Protocol

## Overview <a href="#overview" id="overview"></a>

The **Protocol** module contains the logic for the synchronization protocol.

The TingChain uses **libp2p** as the networking layer, and on top of that runs **gRPC**.

## **GRPC for Other Nodes**

#### &#x20;<a href="#copy" id="copy"></a>

```
service V1 {
    // Returns status information regarding the specific point in time
    rpc GetCurrent(google.protobuf.Empty) returns (V1Status);
    
    // Returns any type of object (Header, Body, Receipts...)
    rpc GetObjectsByHash(HashRequest) returns (Response);
    
    // Returns a range of headers
    rpc GetHeaders(GetHeadersRequest) returns (Response);
    
    // Watches what new blocks get included
    rpc Watch(google.protobuf.Empty) returns (stream V1Status);
}
```

## **Status Object**



```
message V1Status {
    string difficulty = 1;
    string hash = 2;
    int64 number = 3;
}
```
