# SkipChildren

When found on a show item, indicates that the children (seasons) should be skipped in favor of the grandchildren (episodes). Useful for mini-series, etc.


## Supported Types

### 

```go
skipChildren := operations.CreateSkipChildrenBoolean(bool{/* values here */})
```

### SkipChildren2

```go
skipChildren := operations.CreateSkipChildrenSkipChildren2(operations.SkipChildren2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch skipChildren.Type {
	case operations.SkipChildrenTypeBoolean:
		// skipChildren.Boolean is populated
	case operations.SkipChildrenTypeSkipChildren2:
		// skipChildren.SkipChildren2 is populated
}
```
