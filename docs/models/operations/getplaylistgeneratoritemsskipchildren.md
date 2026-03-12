# GetPlaylistGeneratorItemsSkipChildren

When found on a show item, indicates that the children (seasons) should be skipped in favor of the grandchildren (episodes). Useful for mini-series, etc.


## Supported Types

### 

```go
getPlaylistGeneratorItemsSkipChildren := operations.CreateGetPlaylistGeneratorItemsSkipChildrenBoolean(bool{/* values here */})
```

### SkipChildren2

```go
getPlaylistGeneratorItemsSkipChildren := operations.CreateGetPlaylistGeneratorItemsSkipChildrenSkipChildren2(operations.SkipChildren2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch getPlaylistGeneratorItemsSkipChildren.Type {
	case operations.GetPlaylistGeneratorItemsSkipChildrenTypeBoolean:
		// getPlaylistGeneratorItemsSkipChildren.Boolean is populated
	case operations.GetPlaylistGeneratorItemsSkipChildrenTypeSkipChildren2:
		// getPlaylistGeneratorItemsSkipChildren.SkipChildren2 is populated
}
```
