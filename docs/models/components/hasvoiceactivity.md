# HasVoiceActivity

Voice activity detection availability flag returned by PMS.
PMS returns this as string values (`"0"` or `"1"`) instead of a JSON boolean.


## Example Usage

```go
import (
	"github.com/LukeHagar/plexgo/models/components"
)

value := components.HasVoiceActivityFalse
```


## Values

| Name                    | Value                   |
| ----------------------- | ----------------------- |
| `HasVoiceActivityFalse` | 0                       |
| `HasVoiceActivityTrue`  | 1                       |