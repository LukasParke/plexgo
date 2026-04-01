# AllowSync


## Supported Types

### 

```go
allowSync := operations.CreateAllowSyncBoolean(bool{/* values here */})
```

### Two

```go
allowSync := operations.CreateAllowSyncTwo(operations.Two{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch allowSync.Type {
	case operations.AllowSyncTypeBoolean:
		// allowSync.Boolean is populated
	case operations.AllowSyncTypeTwo:
		// allowSync.Two is populated
}
```
