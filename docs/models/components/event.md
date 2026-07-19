# Event

Event type that triggered the webhook.

## Example Usage

```go
import (
	"github.com/LukeHagar/plexgo/models/components"
)

value := components.EventMediaPlay
```


## Values

| Name                 | Value                |
| -------------------- | -------------------- |
| `EventMediaPlay`     | media.play           |
| `EventMediaPause`    | media.pause          |
| `EventMediaResume`   | media.resume         |
| `EventMediaStop`     | media.stop           |
| `EventMediaScrobble` | media.scrobble       |
| `EventMediaRate`     | media.rate           |
| `EventLibraryNew`    | library.new          |
| `EventLibraryOnDeck` | library.on.deck      |