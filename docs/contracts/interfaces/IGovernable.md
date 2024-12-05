# IGovernable

[Git Source](https://github.com/isle-labs/isle-contract/blob/main/contracts/interfaces/IGovernable.sol)

Contract module that provides a basic access control mechanism, with a governor that can be granted exclusive access to specific functions. The inheriting contract must set the initial governor in the constructor.

## Functions

### governor

The address of the governor account or contract.

```solidity
function governor() external view returns (address governor_);
```

### pendingGovernor

The address of the pending governor account or contract.

```solidity
function pendingGovernor() external view returns (address pendingGovernor_);
```

### nominateGovernor

Configure the pendingGovernor to newGovnernor parameter.

_Does not revert if the pendingGovernor is the same, or there is already a pendingGovernor address._

```solidity
function nominateGovernor(address newGovernor) external;
```

**Parameters**

| Name          | Type      | Description                                                 |
| ------------- | --------- | ----------------------------------------------------------- |
| `newGovernor` | `address` | The nominated governor, it will become the pendingGovernor. |

### acceptGovernor

The pending governor should accept and become the governor.

_Only the pendingGovernor can trigger this function._

```solidity
function acceptGovernor() external;
```

### cancelPendingGovenor

Cancel the nominated pending governor.

_Only the governor can trigger this function_

```solidity
function cancelPendingGovenor() external;
```

## Events

### AcceptGovernor

Emitted when the pendingGovernor is accepted.

```solidity
event AcceptGovernor(address indexed oldGovernor, address indexed newGovernor);
```

**Parameters**

| Name          | Type      | Description                      |
| ------------- | --------- | -------------------------------- |
| `oldGovernor` | `address` | The address of the old governor. |
| `newGovernor` | `address` | The address of the new governor. |

### NominateGovernor

Emitted when the pendingGovernor is nominated.

_Configure the pending governor value, not revert if the pending governor is not zero address_

```solidity
event NominateGovernor(address indexed governor, address indexed pendingGovernor);
```

**Parameters**

| Name              | Type      | Description                            |
| ----------------- | --------- | -------------------------------------- |
| `governor`        | `address` | The address of original governor       |
| `pendingGovernor` | `address` | The address of the new pendingGovernor |

### CancelPendingGovernor

Emitted when the pendingGovernor is reset to zero address

_Reset the pending governor to zero address_

```solidity
event CancelPendingGovernor(address indexed oldPendingGovernor);
```

**Parameters**

| Name                 | Type      | Description                              |
| -------------------- | --------- | ---------------------------------------- |
| `oldPendingGovernor` | `address` | The original configured pending governor |
