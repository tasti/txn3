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

#### Transfer

Transfers the native currency.

##### Signature

```typescript
transfer(params: TransferParams) => Transaction
```

##### Parameters

```typescript
interface TransferParams {
  amount: string;
  from: string;
  to: string;
}
```

##### Example

```typescript
txn3.ethereum("sepolia").transfer({
  amount: "0.123",
  from: "0x...",
  to: "0x...",
});
```

#### Transfer an NFT

##### Signature

```typescript
transferNft(params: TransferNftParams) => Transaction
```

##### Parameters

```typescript
interface TransferNftParams {
  amount: string;
  contractAddress: string;
  from: string;
  to: string;
  tokenId: string;
}
```

##### Example

```typescript
txn3.ethereum("sepolia").transferNft({
  amount: "0.123",
  contractAddress: "0x...",
  from: "0x...",
  to: "0x...",
  tokenId: "123",
});
```

#### Transfer a Token

##### Signature

```typescript
transferToken(params: TransferTokenParams) => Transaction
```

##### Parameters

```typescript
interface TransferTokenParams {
  amount: string;
  contractAddress: string;
  from: string;
  to: string;
}
```

##### Example

```typescript
txn3.ethereum("sepolia").transferToken({
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

#### TransferParams

```typescript
interface TransferParams {
  amount: string;
  from: string;
  to: string;
}
```

#### TransferNftParams

```typescript
interface TransferNftParams {
  amount: string;
  contractAddress: string;
  from: string;
  to: string;
}

interface EthereumTransferNftParams extends TransferNftParams {
  tokenId: string;
}
```

#### TransferTokenParams

```typescript
interface TransferTokenParams {
  amount: string;
  contractAddress: string;
  from: string;
  to: string;
}
```
