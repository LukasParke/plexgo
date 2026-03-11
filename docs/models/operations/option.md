# Options

## Global Options

Global options are passed when initializing the SDK client and apply to all operations.

### WithServerURL

WithServerURL allows providing an alternative server URL.

```go
plexgo.WithServerURL("https://api.example.com")
```

### WithTemplatedServerURL

WithTemplatedServerURL allows providing an alternative server URL with templated parameters.

```go
plexgo.WithTemplatedServerURL("https://{host}:{port}", map[string]string{
    "host": "api.example.com",
    "port": "8080",
})
```

### WithServerIndex

WithServerIndex allows the overriding of the default server by index.

```go
plexgo.WithServerIndex(1)
```

### WithIdentifier

WithIdentifier allows setting the identifier variable for url substitution.

```go
plexgo.WithIdentifier(/* ... */)
```

### WithIPDescription

WithIPDescription allows setting the IP-description variable for url substitution.

```go
plexgo.WithIPDescription(/* ... */)
```

### WithPort

WithPort allows setting the port variable for url substitution.

```go
plexgo.WithPort(/* ... */)
```

### WithProtocol

WithProtocol allows setting the protocol variable for url substitution.

```go
plexgo.WithProtocol(/* ... */)
```

### WithHost

WithHost allows setting the host variable for url substitution.

```go
plexgo.WithHost(/* ... */)
```

### WithFullServerURL

WithFullServerURL allows setting the full_server_url variable for url substitution.

```go
plexgo.WithFullServerURL(/* ... */)
```

### WithClient

WithClient allows the overriding of the default HTTP client used by the SDK.

```go
plexgo.WithClient(httpClient)
```

### WithSecurity

WithSecurity configures the SDK to use the provided security details.

```go
plexgo.WithSecurity(/* ... */)
```

### WithSecuritySource

WithSecuritySource configures the SDK to invoke the provided function on each method call to determine authentication.

```go
plexgo.WithSecuritySource(/* ... */)
```

### WithAccepts

WithAccepts allows setting the Accepts parameter for all supported operations.

```go
plexgo.WithAccepts(/* ... */)
```

### WithClientIdentifier

WithClientIdentifier allows setting the ClientIdentifier parameter for all supported operations.

```go
plexgo.WithClientIdentifier(/* ... */)
```

### WithProduct

WithProduct allows setting the Product parameter for all supported operations.

```go
plexgo.WithProduct(/* ... */)
```

### WithVersion

WithVersion allows setting the Version parameter for all supported operations.

```go
plexgo.WithVersion(/* ... */)
```

### WithPlatform

WithPlatform allows setting the Platform parameter for all supported operations.

```go
plexgo.WithPlatform(/* ... */)
```

### WithPlatformVersion

WithPlatformVersion allows setting the PlatformVersion parameter for all supported operations.

```go
plexgo.WithPlatformVersion(/* ... */)
```

### WithDevice

WithDevice allows setting the Device parameter for all supported operations.

```go
plexgo.WithDevice(/* ... */)
```

### WithModel

WithModel allows setting the Model parameter for all supported operations.

```go
plexgo.WithModel(/* ... */)
```

### WithDeviceVendor

WithDeviceVendor allows setting the DeviceVendor parameter for all supported operations.

```go
plexgo.WithDeviceVendor(/* ... */)
```

### WithDeviceName

WithDeviceName allows setting the DeviceName parameter for all supported operations.

```go
plexgo.WithDeviceName(/* ... */)
```

### WithMarketplace

WithMarketplace allows setting the Marketplace parameter for all supported operations.

```go
plexgo.WithMarketplace(/* ... */)
```

### WithRetryConfig

WithRetryConfig allows setting the default retry configuration used by the SDK for all supported operations.

```go
plexgo.WithRetryConfig(retry.Config{
    Strategy: "backoff",
    Backoff: retry.BackoffStrategy{
        InitialInterval: 500 * time.Millisecond,
        MaxInterval: 60 * time.Second,
        Exponent: 1.5,
        MaxElapsedTime: 5 * time.Minute,
    },
    RetryConnectionErrors: true,
})
```

### WithTimeout

WithTimeout sets the default request timeout for all operations.

```go
plexgo.WithTimeout(30 * time.Second)
```

## Per-Method Options

Per-method options are passed as the last argument to individual methods and override any global settings for that request.

### WithServerURL

WithServerURL allows providing an alternative server URL for a single request.

```go
operations.WithServerURL("http://api.example.com")
```

### WithTemplatedServerURL

WithTemplatedServerURL allows providing an alternative server URL with templated parameters for a single request.

```go
operations.WithTemplatedServerURL("http://{host}:{port}", map[string]string{
    "host": "api.example.com",
    "port": "8080",
})
```

### WithRetries

WithRetries allows customizing the default retry configuration for a single request.

```go
operations.WithRetries(retry.Config{
    Strategy: "backoff",
    Backoff: retry.BackoffStrategy{
        InitialInterval: 500 * time.Millisecond,
        MaxInterval: 60 * time.Second,
        Exponent: 1.5,
        MaxElapsedTime: 5 * time.Minute,
    },
    RetryConnectionErrors: true,
})
```

### WithOperationTimeout

WithOperationTimeout allows setting the request timeout for a single request.

```go
operations.WithOperationTimeout(30 * time.Second)
```

### WithSetHeaders

WithSetHeaders allows setting custom headers on a per-request basis. If the request already contains headers matching the provided keys, they will be overwritten.

```go
operations.WithSetHeaders(map[string]string{
    "X-Cache-TTL": "60",
})
```

### WithURLOverride

WithURLOverride allows overriding the default URL for an operation.

```go
operations.WithURLOverride("/custom/path")
```

### WithAcceptHeaderOverride

WithAcceptHeaderOverride allows overriding the `Accept` header for operations that support multiple response content types.

```go
operations.WithAcceptHeaderOverride(operations.AcceptHeaderEnumApplicationJson)
```