# AllowSync


## Supported Types

### 

```go
allowSync := components.CreateAllowSyncBoolean(bool{/* values here */})
```

### AllowSync3

```go
allowSync := components.CreateAllowSyncAllowSync3(components.AllowSync3{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch allowSync.Type {
	case components.AllowSyncTypeBoolean:
		// allowSync.Boolean is populated
	case components.AllowSyncTypeAllowSync3:
		// allowSync.AllowSync3 is populated
}
```
