# MediaContainerWithPlaylistMetadataSkipChildren

When found on a show item, indicates that the children (seasons) should be skipped in favor of the grandchildren (episodes). Useful for mini-series, etc.


## Supported Types

### 

```go
mediaContainerWithPlaylistMetadataSkipChildren := components.CreateMediaContainerWithPlaylistMetadataSkipChildrenBoolean(bool{/* values here */})
```

### MediaContainerWithPlaylistMetadataSkipChildren2

```go
mediaContainerWithPlaylistMetadataSkipChildren := components.CreateMediaContainerWithPlaylistMetadataSkipChildrenMediaContainerWithPlaylistMetadataSkipChildren2(components.MediaContainerWithPlaylistMetadataSkipChildren2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch mediaContainerWithPlaylistMetadataSkipChildren.Type {
	case components.MediaContainerWithPlaylistMetadataSkipChildrenTypeBoolean:
		// mediaContainerWithPlaylistMetadataSkipChildren.Boolean is populated
	case components.MediaContainerWithPlaylistMetadataSkipChildrenTypeMediaContainerWithPlaylistMetadataSkipChildren2:
		// mediaContainerWithPlaylistMetadataSkipChildren.MediaContainerWithPlaylistMetadataSkipChildren2 is populated
}
```
