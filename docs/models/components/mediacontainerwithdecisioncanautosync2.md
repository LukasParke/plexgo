# MediaContainerWithDecisionCanAutoSync2


## Supported Types

### Two1

```go
mediaContainerWithDecisionCanAutoSync2 := components.CreateMediaContainerWithDecisionCanAutoSync2Two1(components.Two1{/* values here */})
```

### 

```go
mediaContainerWithDecisionCanAutoSync2 := components.CreateMediaContainerWithDecisionCanAutoSync2Boolean(bool{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch mediaContainerWithDecisionCanAutoSync2.Type {
	case components.MediaContainerWithDecisionCanAutoSync2TypeTwo1:
		// mediaContainerWithDecisionCanAutoSync2.Two1 is populated
	case components.MediaContainerWithDecisionCanAutoSync2TypeBoolean:
		// mediaContainerWithDecisionCanAutoSync2.Boolean is populated
}
```
