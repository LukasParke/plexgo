# ProcessingState

The state of processing if this generator is part of an optimizer playlist

## Example Usage

```go
import (
	"github.com/LukeHagar/plexgo/models/operations"
)

value := operations.ProcessingStateProcessed
```


## Values

| Name                        | Value                       |
| --------------------------- | --------------------------- |
| `ProcessingStateProcessed`  | processed                   |
| `ProcessingStateCompleted`  | completed                   |
| `ProcessingStateTombstoned` | tombstoned                  |
| `ProcessingStateDisabled`   | disabled                    |
| `ProcessingStateError`      | error                       |
| `ProcessingStatePending`    | pending                     |