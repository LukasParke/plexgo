# MediaContainerWithNestedMetadataSkipParent

When present on an episode or track item, indicates parent should be skipped in favor of grandparent (show).


## Supported Types

### 

```go
mediaContainerWithNestedMetadataSkipParent := components.CreateMediaContainerWithNestedMetadataSkipParentBoolean(bool{/* values here */})
```

### MediaContainerWithNestedMetadataSkipParent2

```go
mediaContainerWithNestedMetadataSkipParent := components.CreateMediaContainerWithNestedMetadataSkipParentMediaContainerWithNestedMetadataSkipParent2(components.MediaContainerWithNestedMetadataSkipParent2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch mediaContainerWithNestedMetadataSkipParent.Type {
	case components.MediaContainerWithNestedMetadataSkipParentTypeBoolean:
		// mediaContainerWithNestedMetadataSkipParent.Boolean is populated
	case components.MediaContainerWithNestedMetadataSkipParentTypeMediaContainerWithNestedMetadataSkipParent2:
		// mediaContainerWithNestedMetadataSkipParent.MediaContainerWithNestedMetadataSkipParent2 is populated
}
```
