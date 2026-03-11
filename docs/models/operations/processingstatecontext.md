# ProcessingStateContext

The error which could have occurred (or `good`)

## Example Usage

```go
import (
	"github.com/LukeHagar/plexgo/models/operations"
)

value := operations.ProcessingStateContextGood
```


## Values

| Name                                            | Value                                           |
| ----------------------------------------------- | ----------------------------------------------- |
| `ProcessingStateContextGood`                    | good                                            |
| `ProcessingStateContextSourceFileUnavailable`   | sourceFileUnavailable                           |
| `ProcessingStateContextSourceFileMetadataError` | sourceFileMetadataError                         |
| `ProcessingStateContextClientProfileError`      | clientProfileError                              |
| `ProcessingStateContextIoError`                 | ioError                                         |
| `ProcessingStateContextTranscoderError`         | transcoderError                                 |
| `ProcessingStateContextUnknownError`            | unknownError                                    |
| `ProcessingStateContextMediaAnalysisError`      | mediaAnalysisError                              |
| `ProcessingStateContextDownloadFailed`          | downloadFailed                                  |
| `ProcessingStateContextAccessDenied`            | accessDenied                                    |
| `ProcessingStateContextCannotTranscode`         | cannotTranscode                                 |
| `ProcessingStateContextCodecInstallError`       | codecInstallError                               |