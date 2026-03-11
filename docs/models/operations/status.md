# Status

## Example Usage

```go
import (
	"github.com/LukeHagar/plexgo/models/operations"
)

value := operations.StatusOnline

// Open enum: custom values can be created with a direct type cast
custom := operations.Status("custom_value")
```


## Values

| Name            | Value           |
| --------------- | --------------- |
| `StatusOnline`  | online          |
| `StatusOffline` | offline         |