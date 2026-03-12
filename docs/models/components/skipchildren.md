# SkipChildren

When found on a show item, indicates that the children (seasons) should be skipped in favor of the grandchildren (episodes). Useful for mini-series, etc.


## Supported Types

### 

```go
skipChildren := components.CreateSkipChildrenBoolean(bool{/* values here */})
```

### SkipChildren2

```go
skipChildren := components.CreateSkipChildrenSkipChildren2(components.SkipChildren2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch skipChildren.Type {
	case components.SkipChildrenTypeBoolean:
		// skipChildren.Boolean is populated
	case components.SkipChildrenTypeSkipChildren2:
		// skipChildren.SkipChildren2 is populated
}
```
