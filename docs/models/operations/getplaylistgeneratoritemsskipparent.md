# GetPlaylistGeneratorItemsSkipParent

When present on an episode or track item, indicates parent should be skipped in favor of grandparent (show).


## Supported Types

### 

```go
getPlaylistGeneratorItemsSkipParent := operations.CreateGetPlaylistGeneratorItemsSkipParentBoolean(bool{/* values here */})
```

### GetPlaylistGeneratorItemsSkipParent2

```go
getPlaylistGeneratorItemsSkipParent := operations.CreateGetPlaylistGeneratorItemsSkipParentGetPlaylistGeneratorItemsSkipParent2(operations.GetPlaylistGeneratorItemsSkipParent2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch getPlaylistGeneratorItemsSkipParent.Type {
	case operations.GetPlaylistGeneratorItemsSkipParentTypeBoolean:
		// getPlaylistGeneratorItemsSkipParent.Boolean is populated
	case operations.GetPlaylistGeneratorItemsSkipParentTypeGetPlaylistGeneratorItemsSkipParent2:
		// getPlaylistGeneratorItemsSkipParent.GetPlaylistGeneratorItemsSkipParent2 is populated
}
```
