# Governable
[Git Source](https://github.com/isle-labs/isle-contract/blob/main/contracts/abstracts/Governable.sol)

**Inherits:**
[IGovernable](/docs/contracts/interfaces/IGovernable.md)

See the documentation in {IGovernable}.


## State Variables

### governor

The address of the governor account or contract.


```solidity
address public override governor;
```


### pendingGovernor
The address of the pending governor account or contract.


```solidity
address public override pendingGovernor;
```


### ______gap

```solidity
uint256[50] private ______gap;
```


## Functions

### onlyGovernor

Reverts if called by any account other than the governor.


```solidity
modifier onlyGovernor() virtual;
```

### nominateGovernor

Configure the pendingGovernor to newGovnernor parameter.


```solidity
function nominateGovernor(address newGovernor_) external virtual override onlyGovernor;
```
**Parameters**

| Name           | Type      | Description       |
| -------------- | ----------| ----------------- |
| `newGovernor_` | `address` | The new governor. |


### acceptGovernor

The pending governor should accept and become the governor.

_Only the pendingGovernor can trigger this function._


```solidity
function acceptGovernor() external virtual override;
```

### cancelPendingGovenor

Cancel the nominated pending governor.

_Only the governor can trigger this function_

```solidity
function cancelPendingGovenor() external virtual override onlyGovernor;
```

