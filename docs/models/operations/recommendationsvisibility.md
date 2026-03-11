# RecommendationsVisibility

The visibility of this hub in recommendations:
  - all: Visible to all users
  - none: Visible to no users
  - admin: Visible to only admin users
  - shared: Visible to shared users


## Example Usage

```go
import (
	"github.com/LukeHagar/plexgo/models/operations"
)

value := operations.RecommendationsVisibilityAll
```


## Values

| Name                              | Value                             |
| --------------------------------- | --------------------------------- |
| `RecommendationsVisibilityAll`    | all                               |
| `RecommendationsVisibilityNone`   | none                              |
| `RecommendationsVisibilityAdmin`  | admin                             |
| `RecommendationsVisibilityShared` | shared                            |