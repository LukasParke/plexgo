# LibrarySectionAllowSync


## Supported Types

### 

```go
librarySectionAllowSync := components.CreateLibrarySectionAllowSyncBoolean(bool{/* values here */})
```

### AllowSync2

```go
librarySectionAllowSync := components.CreateLibrarySectionAllowSyncAllowSync2(components.AllowSync2{/* values here */})
```

## Union Discrimination

Use the `Type` field to determine which variant is active, then access the corresponding field:

```go
switch librarySectionAllowSync.Type {
	case components.LibrarySectionAllowSyncTypeBoolean:
		// librarySectionAllowSync.Boolean is populated
	case components.LibrarySectionAllowSyncTypeAllowSync2:
		// librarySectionAllowSync.AllowSync2 is populated
}
```
