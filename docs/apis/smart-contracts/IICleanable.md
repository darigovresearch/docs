---
title: IICleanable
---

<!-- This is an autogenerated file. Do not edit! -->

# `IICleanable` { #ct_iicleanable }

<div class="api-node-source" markdown>
[Source](https://gitlab.com/flarenetwork/flare-smart-contracts/-/tree/master/contracts/token/interface/IICleanable.sol)
</div>

<div class="api-node-internal" markdown>

Internal interface for entities that can have their block history cleaned.

</div>

<div class="api-node-type" markdown>

## Functions

<div class="api-node" markdown>

### `cleanupBlockNumber` { #fn_cleanupblocknumber_deea13e7 }

<div class="api-node-source" markdown>
Defined in `IICleanable` ([Docs](./IICleanable.md), [Source](https://gitlab.com/flarenetwork/flare-smart-contracts/-/tree/master/contracts/token/interface/IICleanable.sol)).
</div>

<div class="api-node-internal" markdown>

```solidity
function cleanupBlockNumber(
) external view returns (
    uint256);
```

Get the current cleanup block number set with [`setCleanupBlockNumber`](#fn_setcleanupblocknumber_13de97f5).

| Returns | Type | Description |
| ------- | ---- | ----------- |
| [0] | `uint256` | The currently set cleanup block number. |
</div>
</div>

<div class="api-node" markdown>

### `setCleanerContract` { #fn_setcleanercontract_f6a494af }

<div class="api-node-source" markdown>
Defined in `IICleanable` ([Docs](./IICleanable.md), [Source](https://gitlab.com/flarenetwork/flare-smart-contracts/-/tree/master/contracts/token/interface/IICleanable.sol)).
</div>

<div class="api-node-internal" markdown>

```solidity
function setCleanerContract(
    address _cleanerContract
) external;
```

Set the contract that is allowed to call history cleaning methods.

| Parameters | Type | Description |
| ---------- | ---- | ----------- |
| `_cleanerContract` | `address` | Address of the cleanup contract. Usually this will be an instance of [`CleanupBlockNumberManager`](./CleanupBlockNumberManager.md). |

</div>
</div>

<div class="api-node" markdown>

### `setCleanupBlockNumber` { #fn_setcleanupblocknumber_13de97f5 }

<div class="api-node-source" markdown>
Defined in `IICleanable` ([Docs](./IICleanable.md), [Source](https://gitlab.com/flarenetwork/flare-smart-contracts/-/tree/master/contracts/token/interface/IICleanable.sol)).
</div>

<div class="api-node-internal" markdown>

```solidity
function setCleanupBlockNumber(
    uint256 _blockNumber
) external;
```

Set the cleanup block number.
Historic data for the blocks before [`cleanupBlockNumber`](#fn_cleanupblocknumber_deea13e7) can be erased.
History before that block should never be used since it can be inconsistent.
In particular, cleanup block number must be lower than the current vote power block.

| Parameters | Type | Description |
| ---------- | ---- | ----------- |
| `_blockNumber` | `uint256` | The new cleanup block number. |

</div>
</div>

</div>

