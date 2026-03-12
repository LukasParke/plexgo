# SkipParent

When present on an episode or track item, indicates parent should be skipped in favor of grandparent (show).


## Supported Types

### 

```go
skipParent := components.CreateSkipParentBoolean(bool{/* values here */})
```

### SkipParent2

```go
skipParent := components.CreateSkipParentSkipParent2(components.SkipParent2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch skipParent.Type {
	case components.SkipParentTypeBoolean:
		// skipParent.Boolean is populated
	case components.SkipParentTypeSkipParent2:
		// skipParent.SkipParent2 is populated
}
```
