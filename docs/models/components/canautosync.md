# CanAutoSync

Indicates if the stream can auto-sync.


## Supported Types

### 

```go
canAutoSync := components.CreateCanAutoSyncBoolean(bool{/* values here */})
```

### CanAutoSync2

```go
canAutoSync := components.CreateCanAutoSyncCanAutoSync2(components.CanAutoSync2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch canAutoSync.Type {
	case components.CanAutoSyncTypeBoolean:
		// canAutoSync.Boolean is populated
	case components.CanAutoSyncTypeCanAutoSync2:
		// canAutoSync.CanAutoSync2 is populated
}
```
