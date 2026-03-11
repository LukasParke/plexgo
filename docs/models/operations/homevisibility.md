# HomeVisibility

Whether this hub is visible on the home screen
  - all: Visible to all users
  - none: Visible to no users
  - admin: Visible to only admin users
  - shared: Visible to shared users


## Example Usage

```go
import (
	"github.com/LukeHagar/plexgo/models/operations"
)

value := operations.HomeVisibilityAll
```


## Values

| Name                   | Value                  |
| ---------------------- | ---------------------- |
| `HomeVisibilityAll`    | all                    |
| `HomeVisibilityNone`   | none                   |
| `HomeVisibilityAdmin`  | admin                  |
| `HomeVisibilityShared` | shared                 |