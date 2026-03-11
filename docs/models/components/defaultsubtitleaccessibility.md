# DefaultSubtitleAccessibility

The subtitles for the deaf or hard-of-hearing (SDH) searches mode (0 = Prefer non-SDH subtitles, 1 = Prefer SDH subtitles, 2 = Only show SDH subtitles, 3 = Only show non-SDH subtitles)

## Example Usage

```go
import (
	"github.com/LukeHagar/plexgo/models/components"
)

value := components.DefaultSubtitleAccessibilityPreferNonSdh
```


## Values

| Name                                       | Value                                      |
| ------------------------------------------ | ------------------------------------------ |
| `DefaultSubtitleAccessibilityPreferNonSdh` | 0                                          |
| `DefaultSubtitleAccessibilityPreferSdh`    | 1                                          |
| `DefaultSubtitleAccessibilityOnlySdh`      | 2                                          |
| `DefaultSubtitleAccessibilityOnlyNonSdh`   | 3                                          |