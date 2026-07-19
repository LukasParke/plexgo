# CanAutoSync2


## Supported Types

### One

```go
canAutoSync2 := components.CreateCanAutoSync2One(components.One{/* values here */})
```

### 

```go
canAutoSync2 := components.CreateCanAutoSync2Boolean(bool{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch canAutoSync2.Type {
	case components.CanAutoSync2TypeOne:
		// canAutoSync2.One is populated
	case components.CanAutoSync2TypeBoolean:
		// canAutoSync2.Boolean is populated
}
```
