# txn3

Transaction Builder for Web3

## Installation

```console
$ npm install txn3
```

## Usage

```typescript
import Txn3 from "txn3";

const txn3 = new Txn3({ ethereum: { sepolia: "https://rpc.sepolia.org" } });
```

## Documentation

### Methods

#### Send

Sends the native currency.

##### Signature

```typescript
send(params: SendParams) => Transaction
```

##### Parameters

```typescript
interface SendParams {
  amount: string;
  from: string;
  to: string;
}
```

##### Example

```typescript
txn3.ethereum("sepolia").send({
  amount: "0.123",
  from: "0x...",
  to: "0x...",
});
```

#### Send an NFT

##### Signature

```typescript
sendNft(params: SendNftParams) => Transaction
```

##### Parameters

```typescript
interface SendNftParams {
  amount: string;
  contractAddress: string;
  from: string;
  to: string;
  tokenId: string;
}
```

##### Example

```typescript
txn3.ethereum("sepolia").sendNft({
  amount: "0.123",
  contractAddress: "0x...",
  from: "0x...",
  to: "0x...",
  tokenId: "123",
});
```

#### Send a Token

##### Signature

```typescript
sendToken(params: SendTokenParams) => Transaction
```

##### Parameters

```typescript
interface SendTokenParams {
  amount: string;
  contractAddress: string;
  from: string;
  to: string;
}
```

##### Example

```typescript
txn3.ethereum("sepolia").sendToken({
  amount: "0.123",
  contractAddress: "0x...",
  from: "0x...",
  to: "0x...",
});
```

#### Swap

##### Signature

```typescript
swap(params: SwapParams) => Transaction
```

#### Bridge

##### Signature

```typescript
bridge(params: BridgeParams) => Transaction
```

#### Stake

##### Signature

```typescript
stake(params: StakeParams) => Transaction
```

#### Supply

##### Signature

```typescript
supply(params: SupplyParams) => Transaction
```

#### Borrow

##### Signature

```typescript
borrow(params: BorrowParams) => Transaction
```

### Types

#### Transaction

```typescript
interface Transaction {
  from(serialized: string): Transaction;
  serialize(): string;
}
```

#### SendParams

```typescript
interface SendParams {
  amount: string;
  from: string;
  to: string;
}
```

#### SendNftParams

```typescript
interface SendNftParams {
  amount: string;
  contractAddress: string;
  from: string;
  to: string;
}

interface EthereumSendNftParams extends SendNftParams {
  tokenId: string;
}
```

#### SendTokenParams

```typescript
interface SendTokenParams {
  amount: string;
  contractAddress: string;
  from: string;
  to: string;
}
```
