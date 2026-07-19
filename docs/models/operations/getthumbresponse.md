# GetThumbResponse


## Fields

| Field                                                   | Type                                                    | Required                                                | Description                                             | Example                                                 |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| `ContentType`                                           | `string`                                                | :heavy_check_mark:                                      | HTTP response content type for this operation           |                                                         |
| `StatusCode`                                            | `int`                                                   | :heavy_check_mark:                                      | HTTP response status code for this operation            |                                                         |
| `RawResponse`                                           | [*http.Response](https://pkg.go.dev/net/http#Response)  | :heavy_check_mark:                                      | Raw HTTP response; suitable for custom response parsing |                                                         |
| `BinaryResponse`                                        | `io.ReadCloser`                                         | :heavy_minus_sign:                                      | The thumbnail for the device                            | <binary data>                                           |
| `Res`                                                   | `*string`                                               | :heavy_minus_sign:                                      | The thumb URL on the device                             |                                                         |