# DownloadQueueItemStatus

The state of the item:
  - deciding: The item decision is pending
  - waiting: The item is waiting for transcode
  - processing: The item is being transcoded
  - available: The item is available for download
  - error: The item encountered an error in the decision or transcode
  - expired: The transcoded item has timed out and is no longer available

## Example Usage

```go
import (
	"github.com/LukeHagar/plexgo/models/components"
)

value := components.DownloadQueueItemStatusDeciding
```


## Values

| Name                                | Value                               |
| ----------------------------------- | ----------------------------------- |
| `DownloadQueueItemStatusDeciding`   | deciding                            |
| `DownloadQueueItemStatusWaiting`    | waiting                             |
| `DownloadQueueItemStatusProcessing` | processing                          |
| `DownloadQueueItemStatusAvailable`  | available                           |
| `DownloadQueueItemStatusError`      | error                               |
| `DownloadQueueItemStatusExpired`    | expired                             |