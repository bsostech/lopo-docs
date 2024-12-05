# VersionedInitializable

[Git Source](https://github.com/isle-labs/isle-contract/blob/main/contracts/libraries/upgradability/VersionedInitializable.sol)

**Author:** Aave, inspired by the OpenZeppelin Initializable contract

Helper contract to implement initializer functions. To use it, replace the constructor with a function that has the
`initializer` modifier.

_WARNING: Unlike constructors, initializer functions must be manually invoked. This applies both to deploying an
Initializable contract, as well as extending an Initializable contract via inheritance. WARNING: When used with
inheritance, manual care must be taken to not invoke a parent initializer twice, or ensure that all initializers are
idempotent, because this is not dealt with automatically as with constructors._

## State Variables

### INITIALIZABLE_STORAGE

```solidity
bytes32 private constant INITIALIZABLE_STORAGE = 0xf0c57e16840df040f15088dc2f81fe391c3923bec73e23a9662efc9c229c6a00;
```

### **\_\_**gap

```solidity
uint256[50] private ______gap;
```

## Functions

### initializer

_Modifier to use in the initializer function of a contract._

```solidity
modifier initializer();
```

### onlyInitializing

_Modifier to use when a function is restricted to the initialization phase._

```solidity
modifier onlyInitializing();
```

### getRevision

Returns the revision number of the contract

_Needs to be defined in the inherited class as a constant._

```solidity
function getRevision() public pure virtual returns (uint256);
```

**Returns**

| Name     | Type      | Description         |
| -------- | --------- | ------------------- |
| `<none>` | `uint256` | The revision number |

### isConstructor

Returns true if and only if the function is running in the constructor

```solidity
function isConstructor() private view returns (bool);
```

**Returns**

| Name     | Type   | Description                                        |
| -------- | ------ | -------------------------------------------------- |
| `<none>` | `bool` | True if the function is running in the constructor |

### \_getInitializableStorage

```solidity
function _getInitializableStorage() private pure returns (VersionedInitializableStorage storage $);
```

### \_getLastInitializedRevision

```solidity
function _getLastInitializedRevision() internal view returns (uint256);
```

### \_getInitializing

```solidity
function _getInitializing() internal view returns (bool);
```

## Structs

### VersionedInitializableStorage

_Indicates that the contract has been initialized._

```solidity
struct VersionedInitializableStorage {
    uint256 lastInitializedRevision;
    bool initializing;
}
```
