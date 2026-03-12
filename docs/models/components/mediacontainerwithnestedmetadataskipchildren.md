# MediaContainerWithNestedMetadataSkipChildren

When found on a show item, indicates that the children (seasons) should be skipped in favor of the grandchildren (episodes). Useful for mini-series, etc.


## Supported Types

### 

```go
mediaContainerWithNestedMetadataSkipChildren := components.CreateMediaContainerWithNestedMetadataSkipChildrenBoolean(bool{/* values here */})
```

### MediaContainerWithNestedMetadataSkipChildren2

```go
mediaContainerWithNestedMetadataSkipChildren := components.CreateMediaContainerWithNestedMetadataSkipChildrenMediaContainerWithNestedMetadataSkipChildren2(components.MediaContainerWithNestedMetadataSkipChildren2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch mediaContainerWithNestedMetadataSkipChildren.Type {
	case components.MediaContainerWithNestedMetadataSkipChildrenTypeBoolean:
		// mediaContainerWithNestedMetadataSkipChildren.Boolean is populated
	case components.MediaContainerWithNestedMetadataSkipChildrenTypeMediaContainerWithNestedMetadataSkipChildren2:
		// mediaContainerWithNestedMetadataSkipChildren.MediaContainerWithNestedMetadataSkipChildren2 is populated
}
```
