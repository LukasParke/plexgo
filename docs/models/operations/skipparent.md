# SkipParent

When present on an episode or track item, indicates parent should be skipped in favor of grandparent (show).


## Supported Types

### 

```go
skipParent := operations.CreateSkipParentBoolean(bool{/* values here */})
```

### SkipParent2

```go
skipParent := operations.CreateSkipParentSkipParent2(operations.SkipParent2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch skipParent.Type {
	case operations.SkipParentTypeBoolean:
		// skipParent.Boolean is populated
	case operations.SkipParentTypeSkipParent2:
		// skipParent.SkipParent2 is populated
}
```
