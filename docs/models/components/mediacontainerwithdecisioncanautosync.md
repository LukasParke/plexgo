# MediaContainerWithDecisionCanAutoSync

Indicates if the stream can auto-sync.


## Supported Types

### 

```go
mediaContainerWithDecisionCanAutoSync := components.CreateMediaContainerWithDecisionCanAutoSyncBoolean(bool{/* values here */})
```

### MediaContainerWithDecisionCanAutoSync2

```go
mediaContainerWithDecisionCanAutoSync := components.CreateMediaContainerWithDecisionCanAutoSyncMediaContainerWithDecisionCanAutoSync2(components.MediaContainerWithDecisionCanAutoSync2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch mediaContainerWithDecisionCanAutoSync.Type {
	case components.MediaContainerWithDecisionCanAutoSyncTypeBoolean:
		// mediaContainerWithDecisionCanAutoSync.Boolean is populated
	case components.MediaContainerWithDecisionCanAutoSyncTypeMediaContainerWithDecisionCanAutoSync2:
		// mediaContainerWithDecisionCanAutoSync.MediaContainerWithDecisionCanAutoSync2 is populated
}
```
