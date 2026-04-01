# SlashGetResponses200AllowSync


## Supported Types

### 

```go
slashGetResponses200AllowSync := components.CreateSlashGetResponses200AllowSyncBoolean(bool{/* values here */})
```

### SlashGetResponses200AllowSync2

```go
slashGetResponses200AllowSync := components.CreateSlashGetResponses200AllowSyncSlashGetResponses200AllowSync2(components.SlashGetResponses200AllowSync2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch slashGetResponses200AllowSync.Type {
	case components.SlashGetResponses200AllowSyncTypeBoolean:
		// slashGetResponses200AllowSync.Boolean is populated
	case components.SlashGetResponses200AllowSyncTypeSlashGetResponses200AllowSync2:
		// slashGetResponses200AllowSync.SlashGetResponses200AllowSync2 is populated
}
```
