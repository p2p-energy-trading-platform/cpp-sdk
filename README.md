# GridX C++ SDK

Generated C++ protobuf SDK for the GridX - P2P Energy Trading Platform.

This SDK contains C++ protobuf message types generated from the [`protobuf`](https://github.com/p2p-energy-trading-platform/protobuf) repository.

## Purpose

The C++ SDK is mainly used by the Matching Engine to encode and decode Kafka message payloads.

It does not include C++ gRPC service stubs.

## Generated Files

Do not manually edit files inside:

```text
gen/
```

These files are generated automatically from the protobuf contract repo.

## Usage

Add this SDK as a dependency in the C++ service, then link against:

```bash
gridx_cpp_sdk
```

Example:

```cpp
#include "gridx/test/v1/test.pb.h"

gridx::test::v1::TestMoney money;
money.set_currency_code("LKR");
```

## Versioning

This SDK follows the same version as the protobuf contract release.

```text
protobuf v0.2.0
cpp-sdk  v0.2.0
```