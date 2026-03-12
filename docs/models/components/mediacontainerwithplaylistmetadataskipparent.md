# MediaContainerWithPlaylistMetadataSkipParent

When present on an episode or track item, indicates parent should be skipped in favor of grandparent (show).


## Supported Types

### 

```go
mediaContainerWithPlaylistMetadataSkipParent := components.CreateMediaContainerWithPlaylistMetadataSkipParentBoolean(bool{/* values here */})
```

### MediaContainerWithPlaylistMetadataSkipParent2

```go
mediaContainerWithPlaylistMetadataSkipParent := components.CreateMediaContainerWithPlaylistMetadataSkipParentMediaContainerWithPlaylistMetadataSkipParent2(components.MediaContainerWithPlaylistMetadataSkipParent2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch mediaContainerWithPlaylistMetadataSkipParent.Type {
	case components.MediaContainerWithPlaylistMetadataSkipParentTypeBoolean:
		// mediaContainerWithPlaylistMetadataSkipParent.Boolean is populated
	case components.MediaContainerWithPlaylistMetadataSkipParentTypeMediaContainerWithPlaylistMetadataSkipParent2:
		// mediaContainerWithPlaylistMetadataSkipParent.MediaContainerWithPlaylistMetadataSkipParent2 is populated
}
```
