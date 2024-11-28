# Solidity API

## PauseManager

### PAUSE_ALL_ROLE

```solidity
bytes32 PAUSE_ALL_ROLE
```

This is used to pause all pausable functions.

### UNPAUSE_ALL_ROLE

```solidity
bytes32 UNPAUSE_ALL_ROLE
```

This is used to unpause all unpausable functions.

### pauseTypeStatuses

```solidity
mapping(bytes32 => bool) pauseTypeStatuses
```

### whenTypeAndGeneralNotPaused

```solidity
modifier whenTypeAndGeneralNotPaused(enum IPauseManager.PauseType _pauseType)
```

_Modifier to make a function callable only when the specific and general types are not paused._

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| _pauseType | enum IPauseManager.PauseType | The pause type value being checked. Requirements: - The type must not be paused. |

### whenTypeNotPaused

```solidity
modifier whenTypeNotPaused(enum IPauseManager.PauseType _pauseType)
```

_Modifier to make a function callable only when the type is not paused._

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| _pauseType | enum IPauseManager.PauseType | The pause type value being checked. Requirements: - The type must not be paused. |

### __PauseManager_init

```solidity
function __PauseManager_init(struct IPauseManager.PauseTypeRole[] _pauseTypeRoleAssignments, struct IPauseManager.PauseTypeRole[] _unpauseTypeRoleAssignments) internal
```

Initializes the pause manager with the given pause and unpause roles.

_This function is called during contract initialization to set up the pause and unpause roles._

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| _pauseTypeRoleAssignments | struct IPauseManager.PauseTypeRole[] | An array of PauseTypeRole structs defining the pause types and their associated roles. |
| _unpauseTypeRoleAssignments | struct IPauseManager.PauseTypeRole[] | An array of PauseTypeRole structs defining the unpause types and their associated roles. |

### _requireTypeAndGeneralNotPaused

```solidity
function _requireTypeAndGeneralNotPaused(enum IPauseManager.PauseType _pauseType) internal view virtual
```

_Throws if the specific or general types are paused.
Checks the specific and general pause types._

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| _pauseType | enum IPauseManager.PauseType | The pause type value being checked. |

### _requireTypeNotPaused

```solidity
function _requireTypeNotPaused(enum IPauseManager.PauseType _pauseType) internal view virtual
```

_Throws if the type is paused.
Checks the specific pause type._

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| _pauseType | enum IPauseManager.PauseType | The pause type value being checked. |

### pauseByType

```solidity
function pauseByType(enum IPauseManager.PauseType _pauseType) external
```

Pauses functionality by specific type.

_Requires the role mapped in `_pauseTypeRoles` for the pauseType._

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| _pauseType | enum IPauseManager.PauseType | The pause type value. |

### unPauseByType

```solidity
function unPauseByType(enum IPauseManager.PauseType _pauseType) external
```

Unpauses functionality by specific type.

_Requires the role mapped in `_unPauseTypeRoles` for the pauseType._

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| _pauseType | enum IPauseManager.PauseType | The pause type value. |

### isPaused

```solidity
function isPaused(enum IPauseManager.PauseType _pauseType) public view returns (bool pauseTypeIsPaused)
```

Check if a pause type is enabled.

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| _pauseType | enum IPauseManager.PauseType | The pause type value. |

#### Return Values

| Name | Type | Description |
| ---- | ---- | ----------- |
| pauseTypeIsPaused | bool | Returns true if the pause type if paused, false otherwise. |
