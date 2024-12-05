# ReentrancyGuardUpgradeable
[Git Source](https://github.com/isle-labs/isle-contract/blob/main/contracts/libraries/ReentrancyGuard.sol)

**Inherits:**
[VersionedInitializable](/docs/contracts/libraries/upgradability/VersionedInitializable.md)


## State Variables
### NOT_ENTERED

```solidity
uint256 private constant NOT_ENTERED = 1;
```


### ENTERED

```solidity
uint256 private constant ENTERED = 2;
```


### ReentrancyGuardStorageLocation

```solidity
bytes32 private constant ReentrancyGuardStorageLocation =
    0x9b779b17422d0df92223018b32b4d1fa46e071723d6817e2486d003becc55f00;
```


## Functions
### _getReentrancyGuardStorage


```solidity
function _getReentrancyGuardStorage() private pure returns (ReentrancyGuardStorage storage $);
```

### __ReentrancyGuard_init


```solidity
function __ReentrancyGuard_init() internal onlyInitializing;
```

### nonReentrant


```solidity
modifier nonReentrant();
```

## Structs
### ReentrancyGuardStorage

```solidity
struct ReentrancyGuardStorage {
    uint256 _status;
}
```

