# GetPlaylistGeneratorItemsSkipChildren

When found on a show item, indicates that the children (seasons) should be skipped in favor of the grandchildren (episodes). Useful for mini-series, etc.


## Supported Types

### 

```go
getPlaylistGeneratorItemsSkipChildren := operations.CreateGetPlaylistGeneratorItemsSkipChildrenBoolean(bool{/* values here */})
```

### GetPlaylistGeneratorItemsSkipChildren2

```go
getPlaylistGeneratorItemsSkipChildren := operations.CreateGetPlaylistGeneratorItemsSkipChildrenGetPlaylistGeneratorItemsSkipChildren2(operations.GetPlaylistGeneratorItemsSkipChildren2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch getPlaylistGeneratorItemsSkipChildren.Type {
	case operations.GetPlaylistGeneratorItemsSkipChildrenTypeBoolean:
		// getPlaylistGeneratorItemsSkipChildren.Boolean is populated
	case operations.GetPlaylistGeneratorItemsSkipChildrenTypeGetPlaylistGeneratorItemsSkipChildren2:
		// getPlaylistGeneratorItemsSkipChildren.GetPlaylistGeneratorItemsSkipChildren2 is populated
}
```
