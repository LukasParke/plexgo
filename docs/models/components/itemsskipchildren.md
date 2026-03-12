# ItemsSkipChildren

When found on a show item, indicates that the children (seasons) should be skipped in favor of the grandchildren (episodes). Useful for mini-series, etc.


## Supported Types

### 

```go
itemsSkipChildren := components.CreateItemsSkipChildrenBoolean(bool{/* values here */})
```

### ItemsSkipChildren2

```go
itemsSkipChildren := components.CreateItemsSkipChildrenItemsSkipChildren2(components.ItemsSkipChildren2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch itemsSkipChildren.Type {
	case components.ItemsSkipChildrenTypeBoolean:
		// itemsSkipChildren.Boolean is populated
	case components.ItemsSkipChildrenTypeItemsSkipChildren2:
		// itemsSkipChildren.ItemsSkipChildren2 is populated
}
```
