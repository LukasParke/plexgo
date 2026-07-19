# Authentication

## Overview

Plex Authentication operations

### Available Operations

* [RegisterDeviceJWK](#registerdevicejwk) - Register Device JWK
* [GetAuthKeys](#getauthkeys) - Get Auth Keys
* [GetAuthNonce](#getauthnonce) - Get Auth Nonce
* [ExchangeJWTToken](#exchangejwttoken) - Exchange JWT Token
* [GetClaimToken](#getclaimtoken) - Get Claim Token
* [GetFeatures](#getfeatures) - Get Features
* [Ping](#ping) - Ping the server
* [CreateOAuthPin](#createoauthpin) - Create OAuth PIN
* [CreateLegacyPin](#createlegacypin) - Create Legacy PIN
* [LinkOAuthPin](#linkoauthpin) - Link OAuth PIN
* [GetServerAccessTokens](#getserveraccesstokens) - Get Server Access Tokens
* [GetTokenDetails](#gettokendetails) - Get Token Details
* [ChangePassword](#changepassword) - Change Password
* [PostUsersSignInData](#postuserssignindata) - Get User Sign In Data
* [SignOut](#signout) - Sign Out
* [SwitchHomeUser](#switchhomeuser) - Switch Home User
* [GetOAuthPin](#getoauthpin) - Get OAuth PIN Status

## RegisterDeviceJWK

Register a device public key (JWK) for JWT-based authentication.

### Example Usage

<!-- UsageSnippet language="go" operationID="registerDeviceJWK" method="post" path="/auth/jwk" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo/models/components"
	"github.com/LukeHagar/plexgo"
	"github.com/LukeHagar/plexgo/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New(
        plexgo.WithAccepts(components.AcceptsApplicationXML),
        plexgo.WithClientIdentifier("abc123"),
        plexgo.WithProduct("Plex for Roku"),
        plexgo.WithVersion("2.4.1"),
        plexgo.WithPlatform("Roku"),
        plexgo.WithPlatformVersion("4.3 build 1057"),
        plexgo.WithDevice("Roku 3"),
        plexgo.WithModel("4200X"),
        plexgo.WithDeviceVendor("Roku"),
        plexgo.WithDeviceName("Living Room TV"),
        plexgo.WithMarketplace("googlePlay"),
        plexgo.WithSecurity("<YOUR_API_KEY_HERE>"),
    )

    res, err := s.Authentication.RegisterDeviceJWK(ctx, operations.RegisterDeviceJWKRequest{
        JWKRegistrationRequest: &components.JWKRegistrationRequest{
            Jwk: &components.Jwk{
                Crv: plexgo.Pointer("string value"),
                Kid: plexgo.Pointer("string value"),
                Kty: plexgo.Pointer("string value"),
                X: plexgo.Pointer("string value"),
            },
        },
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.AuthTokenResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                  | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `ctx`                                                                                      | [context.Context](https://pkg.go.dev/context#Context)                                      | :heavy_check_mark:                                                                         | The context to use for the request.                                                        |
| `request`                                                                                  | [operations.RegisterDeviceJWKRequest](../../models/operations/registerdevicejwkrequest.md) | :heavy_check_mark:                                                                         | The request object to use for the request.                                                 |
| `opts`                                                                                     | [][operations.Option](../../models/operations/option.md)                                   | :heavy_minus_sign:                                                                         | The options for this request.                                                              |

### Response

**[*operations.RegisterDeviceJWKResponse](../../models/operations/registerdevicejwkresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetAuthKeys

Get Plex public JWKs for signature verification.

### Example Usage

<!-- UsageSnippet language="go" operationID="getAuthKeys" method="get" path="/auth/keys" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo/models/components"
	"github.com/LukeHagar/plexgo"
	"github.com/LukeHagar/plexgo/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New(
        plexgo.WithAccepts(components.AcceptsApplicationXML),
        plexgo.WithClientIdentifier("abc123"),
        plexgo.WithProduct("Plex for Roku"),
        plexgo.WithVersion("2.4.1"),
        plexgo.WithPlatform("Roku"),
        plexgo.WithPlatformVersion("4.3 build 1057"),
        plexgo.WithDevice("Roku 3"),
        plexgo.WithModel("4200X"),
        plexgo.WithDeviceVendor("Roku"),
        plexgo.WithDeviceName("Living Room TV"),
        plexgo.WithMarketplace("googlePlay"),
        plexgo.WithSecurity("<YOUR_API_KEY_HERE>"),
    )

    res, err := s.Authentication.GetAuthKeys(ctx, operations.GetAuthKeysRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.AuthKeysResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                      | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `ctx`                                                                          | [context.Context](https://pkg.go.dev/context#Context)                          | :heavy_check_mark:                                                             | The context to use for the request.                                            |
| `request`                                                                      | [operations.GetAuthKeysRequest](../../models/operations/getauthkeysrequest.md) | :heavy_check_mark:                                                             | The request object to use for the request.                                     |
| `opts`                                                                         | [][operations.Option](../../models/operations/option.md)                       | :heavy_minus_sign:                                                             | The options for this request.                                                  |

### Response

**[*operations.GetAuthKeysResponse](../../models/operations/getauthkeysresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetAuthNonce

Get a nonce to sign in client JWT authentication flow.

### Example Usage

<!-- UsageSnippet language="go" operationID="getAuthNonce" method="get" path="/auth/nonce" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo/models/components"
	"github.com/LukeHagar/plexgo"
	"github.com/LukeHagar/plexgo/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New(
        plexgo.WithAccepts(components.AcceptsApplicationXML),
        plexgo.WithClientIdentifier("abc123"),
        plexgo.WithProduct("Plex for Roku"),
        plexgo.WithVersion("2.4.1"),
        plexgo.WithPlatform("Roku"),
        plexgo.WithPlatformVersion("4.3 build 1057"),
        plexgo.WithDevice("Roku 3"),
        plexgo.WithModel("4200X"),
        plexgo.WithDeviceVendor("Roku"),
        plexgo.WithDeviceName("Living Room TV"),
        plexgo.WithMarketplace("googlePlay"),
        plexgo.WithSecurity("<YOUR_API_KEY_HERE>"),
    )

    res, err := s.Authentication.GetAuthNonce(ctx, operations.GetAuthNonceRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.AuthNonceResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                        | Type                                                                             | Required                                                                         | Description                                                                      |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `ctx`                                                                            | [context.Context](https://pkg.go.dev/context#Context)                            | :heavy_check_mark:                                                               | The context to use for the request.                                              |
| `request`                                                                        | [operations.GetAuthNonceRequest](../../models/operations/getauthnoncerequest.md) | :heavy_check_mark:                                                               | The request object to use for the request.                                       |
| `opts`                                                                           | [][operations.Option](../../models/operations/option.md)                         | :heavy_minus_sign:                                                               | The options for this request.                                                    |

### Response

**[*operations.GetAuthNonceResponse](../../models/operations/getauthnonceresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## ExchangeJWTToken

Exchange a signed client JWT for a Plex JWT token.

### Example Usage

<!-- UsageSnippet language="go" operationID="exchangeJWTToken" method="post" path="/auth/token" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo/models/components"
	"github.com/LukeHagar/plexgo"
	"github.com/LukeHagar/plexgo/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New(
        plexgo.WithAccepts(components.AcceptsApplicationXML),
        plexgo.WithClientIdentifier("abc123"),
        plexgo.WithProduct("Plex for Roku"),
        plexgo.WithVersion("2.4.1"),
        plexgo.WithPlatform("Roku"),
        plexgo.WithPlatformVersion("4.3 build 1057"),
        plexgo.WithDevice("Roku 3"),
        plexgo.WithModel("4200X"),
        plexgo.WithDeviceVendor("Roku"),
        plexgo.WithDeviceName("Living Room TV"),
        plexgo.WithMarketplace("googlePlay"),
        plexgo.WithSecurity("<YOUR_API_KEY_HERE>"),
    )

    res, err := s.Authentication.ExchangeJWTToken(ctx, operations.ExchangeJWTTokenRequest{
        TokenExchangeRequest: &components.TokenExchangeRequest{
            ClientIdentifier: plexgo.Pointer("string value"),
            Jwt: plexgo.Pointer("string value"),
            Scope: plexgo.Pointer("string value"),
        },
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.AuthTokenResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                | Type                                                                                     | Required                                                                                 | Description                                                                              |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `ctx`                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                    | :heavy_check_mark:                                                                       | The context to use for the request.                                                      |
| `request`                                                                                | [operations.ExchangeJWTTokenRequest](../../models/operations/exchangejwttokenrequest.md) | :heavy_check_mark:                                                                       | The request object to use for the request.                                               |
| `opts`                                                                                   | [][operations.Option](../../models/operations/option.md)                                 | :heavy_minus_sign:                                                                       | The options for this request.                                                            |

### Response

**[*operations.ExchangeJWTTokenResponse](../../models/operations/exchangejwttokenresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetClaimToken

Get a claim token for new server setup.

### Example Usage

<!-- UsageSnippet language="go" operationID="getClaimToken" method="get" path="/claim/token.json" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo/models/components"
	"github.com/LukeHagar/plexgo"
	"github.com/LukeHagar/plexgo/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New(
        plexgo.WithAccepts(components.AcceptsApplicationXML),
        plexgo.WithClientIdentifier("abc123"),
        plexgo.WithProduct("Plex for Roku"),
        plexgo.WithVersion("2.4.1"),
        plexgo.WithPlatform("Roku"),
        plexgo.WithPlatformVersion("4.3 build 1057"),
        plexgo.WithDevice("Roku 3"),
        plexgo.WithModel("4200X"),
        plexgo.WithDeviceVendor("Roku"),
        plexgo.WithDeviceName("Living Room TV"),
        plexgo.WithMarketplace("googlePlay"),
        plexgo.WithSecurity("<YOUR_API_KEY_HERE>"),
    )

    res, err := s.Authentication.GetClaimToken(ctx, operations.GetClaimTokenRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.ClaimTokenResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                          | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `ctx`                                                                              | [context.Context](https://pkg.go.dev/context#Context)                              | :heavy_check_mark:                                                                 | The context to use for the request.                                                |
| `request`                                                                          | [operations.GetClaimTokenRequest](../../models/operations/getclaimtokenrequest.md) | :heavy_check_mark:                                                                 | The request object to use for the request.                                         |
| `opts`                                                                             | [][operations.Option](../../models/operations/option.md)                           | :heavy_minus_sign:                                                                 | The options for this request.                                                      |

### Response

**[*operations.GetClaimTokenResponse](../../models/operations/getclaimtokenresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetFeatures

Get Plex Pass feature flags for the logged-in user.

### Example Usage

<!-- UsageSnippet language="go" operationID="getFeatures" method="get" path="/features" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New(
        plexgo.WithSecurity("<YOUR_API_KEY_HERE>"),
    )

    res, err := s.Authentication.GetFeatures(ctx)
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.GetFeaturesResponse](../../models/operations/getfeaturesresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## Ping

Health / latency check. No authentication required.

### Example Usage

<!-- UsageSnippet language="go" operationID="ping" method="get" path="/ping" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New()

    res, err := s.Authentication.Ping(ctx)
    if err != nil {
        log.Fatal(err)
    }
    if res.SuccessResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.PingResponse](../../models/operations/pingresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## CreateOAuthPin

Create a 4-character PIN for device linking via OAuth. The user must visit https://plex.tv/link and enter the PIN to authorize the device.

### Example Usage

<!-- UsageSnippet language="go" operationID="createOAuthPin" method="post" path="/pins" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo/models/components"
	"github.com/LukeHagar/plexgo"
	"github.com/LukeHagar/plexgo/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New(
        plexgo.WithAccepts(components.AcceptsApplicationXML),
        plexgo.WithClientIdentifier("abc123"),
        plexgo.WithProduct("Plex for Roku"),
        plexgo.WithVersion("2.4.1"),
        plexgo.WithPlatform("Roku"),
        plexgo.WithPlatformVersion("4.3 build 1057"),
        plexgo.WithDevice("Roku 3"),
        plexgo.WithModel("4200X"),
        plexgo.WithDeviceVendor("Roku"),
        plexgo.WithDeviceName("Living Room TV"),
        plexgo.WithMarketplace("googlePlay"),
    )

    res, err := s.Authentication.CreateOAuthPin(ctx, operations.CreateOAuthPinRequest{}, operations.CreateOAuthPinSecurity{
        ClientIdentifier: "<YOUR_API_KEY_HERE>",
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                              | Type                                                                                   | Required                                                                               | Description                                                                            |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| `ctx`                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                  | :heavy_check_mark:                                                                     | The context to use for the request.                                                    |
| `request`                                                                              | [operations.CreateOAuthPinRequest](../../models/operations/createoauthpinrequest.md)   | :heavy_check_mark:                                                                     | The request object to use for the request.                                             |
| `security`                                                                             | [operations.CreateOAuthPinSecurity](../../models/operations/createoauthpinsecurity.md) | :heavy_check_mark:                                                                     | The security requirements to use for the request.                                      |
| `opts`                                                                                 | [][operations.Option](../../models/operations/option.md)                               | :heavy_minus_sign:                                                                     | The options for this request.                                                          |

### Response

**[*operations.CreateOAuthPinResponse](../../models/operations/createoauthpinresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## CreateLegacyPin

Legacy PIN creation (XML).

### Example Usage

<!-- UsageSnippet language="go" operationID="createLegacyPin" method="post" path="/pins.xml" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New(
        plexgo.WithSecurity("<YOUR_API_KEY_HERE>"),
    )

    res, err := s.Authentication.CreateLegacyPin(ctx)
    if err != nil {
        log.Fatal(err)
    }
    if res.Body != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.CreateLegacyPinResponse](../../models/operations/createlegacypinresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## LinkOAuthPin

Link a PIN to an account (OAuth completion).

### Example Usage

<!-- UsageSnippet language="go" operationID="linkOAuthPin" method="put" path="/pins/link" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo"
	"github.com/LukeHagar/plexgo/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New(
        plexgo.WithSecurity("<YOUR_API_KEY_HERE>"),
    )

    res, err := s.Authentication.LinkOAuthPin(ctx, &operations.LinkOAuthPinAuthenticationRequestBody{
        AuthToken: plexgo.Pointer("example"),
        Pin: plexgo.Pointer("example"),
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.SuccessResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                            | Type                                                                                                                 | Required                                                                                                             | Description                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                                | :heavy_check_mark:                                                                                                   | The context to use for the request.                                                                                  |
| `request`                                                                                                            | [operations.LinkOAuthPinAuthenticationRequestBody](../../models/operations/linkoauthpinauthenticationrequestbody.md) | :heavy_check_mark:                                                                                                   | The request object to use for the request.                                                                           |
| `opts`                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                             | :heavy_minus_sign:                                                                                                   | The options for this request.                                                                                        |

### Response

**[*operations.LinkOAuthPinResponse](../../models/operations/linkoauthpinresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetServerAccessTokens

List access tokens for the server.

### Example Usage

<!-- UsageSnippet language="go" operationID="getServerAccessTokens" method="get" path="/server/access_tokens" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo/models/components"
	"github.com/LukeHagar/plexgo"
	"github.com/LukeHagar/plexgo/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New(
        plexgo.WithAccepts(components.AcceptsApplicationXML),
        plexgo.WithClientIdentifier("abc123"),
        plexgo.WithProduct("Plex for Roku"),
        plexgo.WithVersion("2.4.1"),
        plexgo.WithPlatform("Roku"),
        plexgo.WithPlatformVersion("4.3 build 1057"),
        plexgo.WithDevice("Roku 3"),
        plexgo.WithModel("4200X"),
        plexgo.WithDeviceVendor("Roku"),
        plexgo.WithDeviceName("Living Room TV"),
        plexgo.WithMarketplace("googlePlay"),
        plexgo.WithSecurity("<YOUR_API_KEY_HERE>"),
    )

    res, err := s.Authentication.GetServerAccessTokens(ctx, operations.GetServerAccessTokensRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.ServerAccessTokensResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                          | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                              | [context.Context](https://pkg.go.dev/context#Context)                                              | :heavy_check_mark:                                                                                 | The context to use for the request.                                                                |
| `request`                                                                                          | [operations.GetServerAccessTokensRequest](../../models/operations/getserveraccesstokensrequest.md) | :heavy_check_mark:                                                                                 | The request object to use for the request.                                                         |
| `opts`                                                                                             | [][operations.Option](../../models/operations/option.md)                                           | :heavy_minus_sign:                                                                                 | The options for this request.                                                                      |

### Response

**[*operations.GetServerAccessTokensResponse](../../models/operations/getserveraccesstokensresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetTokenDetails

Get the User data from the provided X-Plex-Token

### Example Usage

<!-- UsageSnippet language="go" operationID="getTokenDetails" method="get" path="/user" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo/models/components"
	"github.com/LukeHagar/plexgo"
	"github.com/LukeHagar/plexgo/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New(
        plexgo.WithAccepts(components.AcceptsApplicationXML),
        plexgo.WithClientIdentifier("abc123"),
        plexgo.WithProduct("Plex for Roku"),
        plexgo.WithVersion("2.4.1"),
        plexgo.WithPlatform("Roku"),
        plexgo.WithPlatformVersion("4.3 build 1057"),
        plexgo.WithDevice("Roku 3"),
        plexgo.WithModel("4200X"),
        plexgo.WithDeviceVendor("Roku"),
        plexgo.WithDeviceName("Living Room TV"),
        plexgo.WithMarketplace("googlePlay"),
        plexgo.WithSecurity("<YOUR_API_KEY_HERE>"),
    )

    res, err := s.Authentication.GetTokenDetails(ctx, operations.GetTokenDetailsRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.UserPlexAccount != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                              | Type                                                                                   | Required                                                                               | Description                                                                            |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| `ctx`                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                  | :heavy_check_mark:                                                                     | The context to use for the request.                                                    |
| `request`                                                                              | [operations.GetTokenDetailsRequest](../../models/operations/gettokendetailsrequest.md) | :heavy_check_mark:                                                                     | The request object to use for the request.                                             |
| `opts`                                                                                 | [][operations.Option](../../models/operations/option.md)                               | :heavy_minus_sign:                                                                     | The options for this request.                                                          |

### Response

**[*operations.GetTokenDetailsResponse](../../models/operations/gettokendetailsresponse.md), error**

### Errors

| Error Type             | Status Code            | Content Type           |
| ---------------------- | ---------------------- | ---------------------- |
| sdkerrors.BadRequest   | 400                    | application/json       |
| sdkerrors.Unauthorized | 401                    | application/json       |
| sdkerrors.SDKError     | 4XX, 5XX               | \*/\*                  |

## ChangePassword

Change or reset the logged-in user's password.

### Example Usage

<!-- UsageSnippet language="go" operationID="changePassword" method="post" path="/users/password" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo/models/components"
	"github.com/LukeHagar/plexgo"
	"github.com/LukeHagar/plexgo/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New(
        plexgo.WithAccepts(components.AcceptsApplicationXML),
        plexgo.WithClientIdentifier("abc123"),
        plexgo.WithProduct("Plex for Roku"),
        plexgo.WithVersion("2.4.1"),
        plexgo.WithPlatform("Roku"),
        plexgo.WithPlatformVersion("4.3 build 1057"),
        plexgo.WithDevice("Roku 3"),
        plexgo.WithModel("4200X"),
        plexgo.WithDeviceVendor("Roku"),
        plexgo.WithDeviceName("Living Room TV"),
        plexgo.WithMarketplace("googlePlay"),
        plexgo.WithSecurity("<YOUR_API_KEY_HERE>"),
    )

    res, err := s.Authentication.ChangePassword(ctx, operations.ChangePasswordRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.SuccessResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                            | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `ctx`                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                | :heavy_check_mark:                                                                   | The context to use for the request.                                                  |
| `request`                                                                            | [operations.ChangePasswordRequest](../../models/operations/changepasswordrequest.md) | :heavy_check_mark:                                                                   | The request object to use for the request.                                           |
| `opts`                                                                               | [][operations.Option](../../models/operations/option.md)                             | :heavy_minus_sign:                                                                   | The options for this request.                                                        |

### Response

**[*operations.ChangePasswordResponse](../../models/operations/changepasswordresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## PostUsersSignInData

Sign in user with username and password and return user data with Plex authentication token

### Example Usage

<!-- UsageSnippet language="go" operationID="postUsersSignInData" method="post" path="/users/signin" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo/models/components"
	"github.com/LukeHagar/plexgo"
	"github.com/LukeHagar/plexgo/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New(
        plexgo.WithAccepts(components.AcceptsApplicationXML),
        plexgo.WithClientIdentifier("abc123"),
        plexgo.WithProduct("Plex for Roku"),
        plexgo.WithVersion("2.4.1"),
        plexgo.WithPlatform("Roku"),
        plexgo.WithPlatformVersion("4.3 build 1057"),
        plexgo.WithDevice("Roku 3"),
        plexgo.WithModel("4200X"),
        plexgo.WithDeviceVendor("Roku"),
        plexgo.WithDeviceName("Living Room TV"),
        plexgo.WithMarketplace("googlePlay"),
    )

    res, err := s.Authentication.PostUsersSignInData(ctx, operations.PostUsersSignInDataRequest{
        RequestBody: &operations.PostUsersSignInDataRequestBody{
            Login: "username@email.com",
            Password: "password123",
            RememberMe: plexgo.Pointer(true),
            VerificationCode: plexgo.Pointer("123456"),
        },
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.UserPlexAccount != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                      | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `ctx`                                                                                          | [context.Context](https://pkg.go.dev/context#Context)                                          | :heavy_check_mark:                                                                             | The context to use for the request.                                                            |
| `request`                                                                                      | [operations.PostUsersSignInDataRequest](../../models/operations/postuserssignindatarequest.md) | :heavy_check_mark:                                                                             | The request object to use for the request.                                                     |
| `opts`                                                                                         | [][operations.Option](../../models/operations/option.md)                                       | :heavy_minus_sign:                                                                             | The options for this request.                                                                  |

### Response

**[*operations.PostUsersSignInDataResponse](../../models/operations/postuserssignindataresponse.md), error**

### Errors

| Error Type             | Status Code            | Content Type           |
| ---------------------- | ---------------------- | ---------------------- |
| sdkerrors.BadRequest   | 400                    | application/json       |
| sdkerrors.Unauthorized | 401                    | application/json       |
| sdkerrors.SDKError     | 4XX, 5XX               | \*/\*                  |

## SignOut

Invalidate the current authentication token.

### Example Usage

<!-- UsageSnippet language="go" operationID="signOut" method="delete" path="/users/signout" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo/models/components"
	"github.com/LukeHagar/plexgo"
	"github.com/LukeHagar/plexgo/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New(
        plexgo.WithAccepts(components.AcceptsApplicationXML),
        plexgo.WithClientIdentifier("abc123"),
        plexgo.WithProduct("Plex for Roku"),
        plexgo.WithVersion("2.4.1"),
        plexgo.WithPlatform("Roku"),
        plexgo.WithPlatformVersion("4.3 build 1057"),
        plexgo.WithDevice("Roku 3"),
        plexgo.WithModel("4200X"),
        plexgo.WithDeviceVendor("Roku"),
        plexgo.WithDeviceName("Living Room TV"),
        plexgo.WithMarketplace("googlePlay"),
        plexgo.WithSecurity("<YOUR_API_KEY_HERE>"),
    )

    res, err := s.Authentication.SignOut(ctx, operations.SignOutRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.SuccessResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                              | Type                                                                   | Required                                                               | Description                                                            |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `ctx`                                                                  | [context.Context](https://pkg.go.dev/context#Context)                  | :heavy_check_mark:                                                     | The context to use for the request.                                    |
| `request`                                                              | [operations.SignOutRequest](../../models/operations/signoutrequest.md) | :heavy_check_mark:                                                     | The request object to use for the request.                             |
| `opts`                                                                 | [][operations.Option](../../models/operations/option.md)               | :heavy_minus_sign:                                                     | The options for this request.                                          |

### Response

**[*operations.SignOutResponse](../../models/operations/signoutresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## SwitchHomeUser

Switch to a Plex Home user and return a new auth token.

### Example Usage

<!-- UsageSnippet language="go" operationID="switchHomeUser" method="post" path="/home/users/{id}/switch" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo/models/components"
	"github.com/LukeHagar/plexgo"
	"github.com/LukeHagar/plexgo/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New(
        plexgo.WithAccepts(components.AcceptsApplicationXML),
        plexgo.WithClientIdentifier("abc123"),
        plexgo.WithProduct("Plex for Roku"),
        plexgo.WithVersion("2.4.1"),
        plexgo.WithPlatform("Roku"),
        plexgo.WithPlatformVersion("4.3 build 1057"),
        plexgo.WithDevice("Roku 3"),
        plexgo.WithModel("4200X"),
        plexgo.WithDeviceVendor("Roku"),
        plexgo.WithDeviceName("Living Room TV"),
        plexgo.WithMarketplace("googlePlay"),
        plexgo.WithSecurity("<YOUR_API_KEY_HERE>"),
    )

    res, err := s.Authentication.SwitchHomeUser(ctx, operations.SwitchHomeUserRequest{
        ID: 135337,
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.SuccessResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                            | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `ctx`                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                | :heavy_check_mark:                                                                   | The context to use for the request.                                                  |
| `request`                                                                            | [operations.SwitchHomeUserRequest](../../models/operations/switchhomeuserrequest.md) | :heavy_check_mark:                                                                   | The request object to use for the request.                                           |
| `opts`                                                                               | [][operations.Option](../../models/operations/option.md)                             | :heavy_minus_sign:                                                                   | The options for this request.                                                        |

### Response

**[*operations.SwitchHomeUserResponse](../../models/operations/switchhomeuserresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetOAuthPin

Poll the PIN status. Returns authToken when the user has linked the device.

### Example Usage

<!-- UsageSnippet language="go" operationID="getOAuthPin" method="get" path="/pins/{pinId}" -->
```go
package main

import(
	"context"
	"github.com/LukeHagar/plexgo/models/components"
	"github.com/LukeHagar/plexgo"
	"github.com/LukeHagar/plexgo/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := plexgo.New(
        plexgo.WithAccepts(components.AcceptsApplicationXML),
        plexgo.WithClientIdentifier("abc123"),
        plexgo.WithProduct("Plex for Roku"),
        plexgo.WithVersion("2.4.1"),
        plexgo.WithPlatform("Roku"),
        plexgo.WithPlatformVersion("4.3 build 1057"),
        plexgo.WithDevice("Roku 3"),
        plexgo.WithModel("4200X"),
        plexgo.WithDeviceVendor("Roku"),
        plexgo.WithDeviceName("Living Room TV"),
        plexgo.WithMarketplace("googlePlay"),
    )

    res, err := s.Authentication.GetOAuthPin(ctx, operations.GetOAuthPinRequest{
        PinID: 876892,
    }, operations.GetOAuthPinSecurity{
        ClientIdentifier: "<YOUR_API_KEY_HERE>",
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                        | Type                                                                             | Required                                                                         | Description                                                                      |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `ctx`                                                                            | [context.Context](https://pkg.go.dev/context#Context)                            | :heavy_check_mark:                                                               | The context to use for the request.                                              |
| `request`                                                                        | [operations.GetOAuthPinRequest](../../models/operations/getoauthpinrequest.md)   | :heavy_check_mark:                                                               | The request object to use for the request.                                       |
| `security`                                                                       | [operations.GetOAuthPinSecurity](../../models/operations/getoauthpinsecurity.md) | :heavy_check_mark:                                                               | The security requirements to use for the request.                                |
| `opts`                                                                           | [][operations.Option](../../models/operations/option.md)                         | :heavy_minus_sign:                                                               | The options for this request.                                                    |

### Response

**[*operations.GetOAuthPinResponse](../../models/operations/getoauthpinresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |