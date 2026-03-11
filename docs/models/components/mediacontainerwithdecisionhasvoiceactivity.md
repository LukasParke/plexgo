# MediaContainerWithDecisionHasVoiceActivity

Voice activity detection availability flag returned by PMS.
PMS returns this as string values (`"0"` or `"1"`) instead of a JSON boolean.


## Example Usage

```go
import (
	"github.com/LukeHagar/plexgo/models/components"
)

value := components.MediaContainerWithDecisionHasVoiceActivityFalse
```


## Values

| Name                                              | Value                                             |
| ------------------------------------------------- | ------------------------------------------------- |
| `MediaContainerWithDecisionHasVoiceActivityFalse` | 0                                                 |
| `MediaContainerWithDecisionHasVoiceActivityTrue`  | 1                                                 |