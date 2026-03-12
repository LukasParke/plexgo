# HasVoiceActivity

Voice activity detection availability flag returned by PMS.
PMS may return this as a boolean or as string values (`"0"` or `"1"`).



## Supported Types

### 

```go
hasVoiceActivity := components.CreateHasVoiceActivityBoolean(bool{/* values here */})
```

### Two

```go
hasVoiceActivity := components.CreateHasVoiceActivityTwo(components.Two{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch hasVoiceActivity.Type {
	case components.HasVoiceActivityTypeBoolean:
		// hasVoiceActivity.Boolean is populated
	case components.HasVoiceActivityTypeTwo:
		// hasVoiceActivity.Two is populated
}
```
