# Types

#### Overview <a href="#overview" id="overview"></a>

The **Types** module implements core object types, such as:

* **Address**
* **Hash**
* **Header**
* lots of helper functions

#### RLP Encoding / Decoding <a href="#rlp-encoding-decoding" id="rlp-encoding-decoding"></a>

Unlike clients such as GETH, the TingChain doesn't use reflection for the encoding. The preference was to not use reflection because it introduces new problems, such as performance degradation, and harder scaling.

The **Types** module provides an easy-to-use interface for RLP marshaling and unmarshalling, using the FastRLP package.

Marshaling is done through the _MarshalRLPWith_ and _MarshalRLPTo_ methods. The analogous methods exist for unmarshalling.

By manually defining these methods, the TingChain doesn't need to use reflection. In _rlp\_marshal.go_, you can find methods for marshaling:

* **Bodies**
* **Blocks**
* **Headers**
* **Receipts**
* **Logs**
* **Transactions**
