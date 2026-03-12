# MediaContainerWithDecisionSkipParent

When present on an episode or track item, indicates parent should be skipped in favor of grandparent (show).


## Supported Types

### 

```go
mediaContainerWithDecisionSkipParent := components.CreateMediaContainerWithDecisionSkipParentBoolean(bool{/* values here */})
```

### MediaContainerWithDecisionSkipParent2

```go
mediaContainerWithDecisionSkipParent := components.CreateMediaContainerWithDecisionSkipParentMediaContainerWithDecisionSkipParent2(components.MediaContainerWithDecisionSkipParent2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch mediaContainerWithDecisionSkipParent.Type {
	case components.MediaContainerWithDecisionSkipParentTypeBoolean:
		// mediaContainerWithDecisionSkipParent.Boolean is populated
	case components.MediaContainerWithDecisionSkipParentTypeMediaContainerWithDecisionSkipParent2:
		// mediaContainerWithDecisionSkipParent.MediaContainerWithDecisionSkipParent2 is populated
}
```
