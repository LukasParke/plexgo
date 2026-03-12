# MediaContainerWithDecisionSkipChildren

When found on a show item, indicates that the children (seasons) should be skipped in favor of the grandchildren (episodes). Useful for mini-series, etc.


## Supported Types

### 

```go
mediaContainerWithDecisionSkipChildren := components.CreateMediaContainerWithDecisionSkipChildrenBoolean(bool{/* values here */})
```

### MediaContainerWithDecisionSkipChildren2

```go
mediaContainerWithDecisionSkipChildren := components.CreateMediaContainerWithDecisionSkipChildrenMediaContainerWithDecisionSkipChildren2(components.MediaContainerWithDecisionSkipChildren2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch mediaContainerWithDecisionSkipChildren.Type {
	case components.MediaContainerWithDecisionSkipChildrenTypeBoolean:
		// mediaContainerWithDecisionSkipChildren.Boolean is populated
	case components.MediaContainerWithDecisionSkipChildrenTypeMediaContainerWithDecisionSkipChildren2:
		// mediaContainerWithDecisionSkipChildren.MediaContainerWithDecisionSkipChildren2 is populated
}
```
