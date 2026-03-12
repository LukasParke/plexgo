# ItemsSkipParent

When present on an episode or track item, indicates parent should be skipped in favor of grandparent (show).


## Supported Types

### 

```go
itemsSkipParent := components.CreateItemsSkipParentBoolean(bool{/* values here */})
```

### ItemsSkipParent2

```go
itemsSkipParent := components.CreateItemsSkipParentItemsSkipParent2(components.ItemsSkipParent2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch itemsSkipParent.Type {
	case components.ItemsSkipParentTypeBoolean:
		// itemsSkipParent.Boolean is populated
	case components.ItemsSkipParentTypeItemsSkipParent2:
		// itemsSkipParent.ItemsSkipParent2 is populated
}
```
