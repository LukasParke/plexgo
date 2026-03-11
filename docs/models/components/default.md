# Default

The default value of this setting


## Supported Types

### 

```go
default := components.CreateDefaultStr(string{/* values here */})
```

### 

```go
default := components.CreateDefaultNumber(float64{/* values here */})
```

### 

```go
default := components.CreateDefaultBoolean(bool{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch default.Type {
	case components.DefaultTypeStr:
		// default.Str is populated
	case components.DefaultTypeNumber:
		// default.Number is populated
	case components.DefaultTypeBoolean:
		// default.Boolean is populated
}
```
