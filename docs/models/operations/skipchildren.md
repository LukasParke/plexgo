# SkipChildren

When found on a show item, indicates that the children (seasons) should be skipped in favor of the grandchildren (episodes). Useful for mini-series, etc.


## Supported Types

### 

```go
skipChildren := operations.CreateSkipChildrenBoolean(bool{/* values here */})
```

### Two

```go
skipChildren := operations.CreateSkipChildrenTwo(operations.Two{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch skipChildren.Type {
	case operations.SkipChildrenTypeBoolean:
		// skipChildren.Boolean is populated
	case operations.SkipChildrenTypeTwo:
		// skipChildren.Two is populated
}
```
