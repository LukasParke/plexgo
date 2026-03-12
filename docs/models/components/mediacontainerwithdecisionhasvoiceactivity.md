# MediaContainerWithDecisionHasVoiceActivity

Voice activity detection availability flag returned by PMS.
PMS may return this as a boolean or as string values (`"0"` or `"1"`).



## Supported Types

### 

```go
mediaContainerWithDecisionHasVoiceActivity := components.CreateMediaContainerWithDecisionHasVoiceActivityBoolean(bool{/* values here */})
```

### HasVoiceActivity2

```go
mediaContainerWithDecisionHasVoiceActivity := components.CreateMediaContainerWithDecisionHasVoiceActivityHasVoiceActivity2(components.HasVoiceActivity2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch mediaContainerWithDecisionHasVoiceActivity.Type {
	case components.MediaContainerWithDecisionHasVoiceActivityTypeBoolean:
		// mediaContainerWithDecisionHasVoiceActivity.Boolean is populated
	case components.MediaContainerWithDecisionHasVoiceActivityTypeHasVoiceActivity2:
		// mediaContainerWithDecisionHasVoiceActivity.HasVoiceActivity2 is populated
}
```
