# Users

## Overview

Plex Users operations

### Available Operations

* [GetLegacyResources](#getlegacyresources) - Get Legacy Resources
* [GetLegacyUsers](#getlegacyusers) - Get Legacy Users
* [GetFriends](#getfriends) - Get Friends
* [GetHome](#gethome) - Get home hubs
* [GetHomeUsers](#gethomeusers) - Get home hubs Users
* [CreateHomeUser](#createhomeuser) - Create Home User
* [GetMyPlexAccount](#getmyplexaccount) - Get MyPlex Account
* [GetUserServer](#getuserserver) - Get User Server Association
* [GetServerUserFeatures](#getserveruserfeatures) - Get Server User Features
* [ShareServer](#shareserver) - Share Server
* [UpdateViewStateSync](#updateviewstatesync) - Update View State Sync
* [GetUsers](#getusers) - Get list of all connected users
* [GetAccountXML](#getaccountxml) - Get Account (XML)
* [GetAccountJSON](#getaccountjson) - Get Account (JSON)
* [DeleteHomeUser](#deletehomeuser) - Delete Home User
* [UpdateHomeUser](#updatehomeuser) - Update Home User
* [UpdateRestrictedUser](#updaterestricteduser) - Update Restricted User
* [GetServerDetails](#getserverdetails) - Get Server Details
* [ShareServerLegacy](#shareserverlegacy) - Share Server (Legacy v1)
* [RemoveShare](#removeshare) - Remove Share
* [UpdateShare](#updateshare) - Update Share
* [GetUserOptOuts](#getuseroptouts) - Get User Opt-Outs

## GetLegacyResources

Get legacy published server connections (XML).

### Example Usage

<!-- UsageSnippet language="go" operationID="getLegacyResources" method="get" path="/api/resources" -->
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

    res, err := s.Users.GetLegacyResources(ctx)
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

**[*operations.GetLegacyResourcesResponse](../../models/operations/getlegacyresourcesresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetLegacyUsers

Get legacy friends list (XML).

### Example Usage

<!-- UsageSnippet language="go" operationID="getLegacyUsers" method="get" path="/api/users/" -->
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

    res, err := s.Users.GetLegacyUsers(ctx)
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

**[*operations.GetLegacyUsersResponse](../../models/operations/getlegacyusersresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetFriends

Get the list of friends and shared users.

### Example Usage

<!-- UsageSnippet language="go" operationID="getFriends" method="get" path="/friends" -->
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

    res, err := s.Users.GetFriends(ctx, operations.GetFriendsRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                    | Type                                                                         | Required                                                                     | Description                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `ctx`                                                                        | [context.Context](https://pkg.go.dev/context#Context)                        | :heavy_check_mark:                                                           | The context to use for the request.                                          |
| `request`                                                                    | [operations.GetFriendsRequest](../../models/operations/getfriendsrequest.md) | :heavy_check_mark:                                                           | The request object to use for the request.                                   |
| `opts`                                                                       | [][operations.Option](../../models/operations/option.md)                     | :heavy_minus_sign:                                                           | The options for this request.                                                |

### Response

**[*operations.GetFriendsResponse](../../models/operations/getfriendsresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetHome

Get Plex Home user list.

### Example Usage

<!-- UsageSnippet language="go" operationID="getHome" method="get" path="/home" -->
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

    res, err := s.Users.GetHome(ctx)
    if err != nil {
        log.Fatal(err)
    }
    if res.MediaContainerWithHubs != nil {
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

**[*operations.GetHomeResponse](../../models/operations/gethomeresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetHomeUsers

Get the list of Plex Home users.

### Example Usage

<!-- UsageSnippet language="go" operationID="getHomeUsers" method="get" path="/home/users" -->
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

    res, err := s.Users.GetHomeUsers(ctx, operations.GetHomeUsersRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.MediaContainerWithDirectory != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                        | Type                                                                             | Required                                                                         | Description                                                                      |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `ctx`                                                                            | [context.Context](https://pkg.go.dev/context#Context)                            | :heavy_check_mark:                                                               | The context to use for the request.                                              |
| `request`                                                                        | [operations.GetHomeUsersRequest](../../models/operations/gethomeusersrequest.md) | :heavy_check_mark:                                                               | The request object to use for the request.                                       |
| `opts`                                                                           | [][operations.Option](../../models/operations/option.md)                         | :heavy_minus_sign:                                                               | The options for this request.                                                    |

### Response

**[*operations.GetHomeUsersResponse](../../models/operations/gethomeusersresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## CreateHomeUser

Create a new Plex Home user.

### Example Usage

<!-- UsageSnippet language="go" operationID="createHomeUser" method="post" path="/home/users" -->
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

    res, err := s.Users.CreateHomeUser(ctx, operations.CreateHomeUserRequest{})
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
| `request`                                                                            | [operations.CreateHomeUserRequest](../../models/operations/createhomeuserrequest.md) | :heavy_check_mark:                                                                   | The request object to use for the request.                                           |
| `opts`                                                                               | [][operations.Option](../../models/operations/option.md)                             | :heavy_minus_sign:                                                                   | The options for this request.                                                        |

### Response

**[*operations.CreateHomeUserResponse](../../models/operations/createhomeuserresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetMyPlexAccount

Get linked MyPlex account info on PMS.

### Example Usage

<!-- UsageSnippet language="go" operationID="getMyPlexAccount" method="get" path="/myplex/account" -->
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

    res, err := s.Users.GetMyPlexAccount(ctx)
    if err != nil {
        log.Fatal(err)
    }
    if res.UserPlexAccount != nil {
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

**[*operations.GetMyPlexAccountResponse](../../models/operations/getmyplexaccountresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetUserServer

Get server association information for the logged-in user.

### Example Usage

<!-- UsageSnippet language="go" operationID="getUserServer" method="get" path="/server" -->
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

    res, err := s.Users.GetUserServer(ctx, operations.GetUserServerRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.ConnectionInfo != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                          | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `ctx`                                                                              | [context.Context](https://pkg.go.dev/context#Context)                              | :heavy_check_mark:                                                                 | The context to use for the request.                                                |
| `request`                                                                          | [operations.GetUserServerRequest](../../models/operations/getuserserverrequest.md) | :heavy_check_mark:                                                                 | The request object to use for the request.                                         |
| `opts`                                                                             | [][operations.Option](../../models/operations/option.md)                           | :heavy_minus_sign:                                                                 | The options for this request.                                                      |

### Response

**[*operations.GetUserServerResponse](../../models/operations/getuserserverresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetServerUserFeatures

Get features enabled per shared user for the server.

### Example Usage

<!-- UsageSnippet language="go" operationID="getServerUserFeatures" method="get" path="/server/users/features" -->
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

    res, err := s.Users.GetServerUserFeatures(ctx, operations.GetServerUserFeaturesRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.ServerUserFeaturesResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                          | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                              | [context.Context](https://pkg.go.dev/context#Context)                                              | :heavy_check_mark:                                                                                 | The context to use for the request.                                                                |
| `request`                                                                                          | [operations.GetServerUserFeaturesRequest](../../models/operations/getserveruserfeaturesrequest.md) | :heavy_check_mark:                                                                                 | The request object to use for the request.                                                         |
| `opts`                                                                                             | [][operations.Option](../../models/operations/option.md)                                           | :heavy_minus_sign:                                                                                 | The options for this request.                                                                      |

### Response

**[*operations.GetServerUserFeaturesResponse](../../models/operations/getserveruserfeaturesresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## ShareServer

Share a server with a friend or managed user.

### Example Usage

<!-- UsageSnippet language="go" operationID="shareServer" method="post" path="/shared_servers" -->
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

    res, err := s.Users.ShareServer(ctx, operations.ShareServerRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.SuccessResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                      | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `ctx`                                                                          | [context.Context](https://pkg.go.dev/context#Context)                          | :heavy_check_mark:                                                             | The context to use for the request.                                            |
| `request`                                                                      | [operations.ShareServerRequest](../../models/operations/shareserverrequest.md) | :heavy_check_mark:                                                             | The request object to use for the request.                                     |
| `opts`                                                                         | [][operations.Option](../../models/operations/option.md)                       | :heavy_minus_sign:                                                             | The options for this request.                                                  |

### Response

**[*operations.ShareServerResponse](../../models/operations/shareserverresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## UpdateViewStateSync

Enable or disable watch-state sync consent for the logged-in user.

### Example Usage

<!-- UsageSnippet language="go" operationID="updateViewStateSync" method="put" path="/user/view_state_sync" -->
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

    res, err := s.Users.UpdateViewStateSync(ctx, operations.UpdateViewStateSyncRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.SuccessResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                      | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `ctx`                                                                                          | [context.Context](https://pkg.go.dev/context#Context)                                          | :heavy_check_mark:                                                                             | The context to use for the request.                                                            |
| `request`                                                                                      | [operations.UpdateViewStateSyncRequest](../../models/operations/updateviewstatesyncrequest.md) | :heavy_check_mark:                                                                             | The request object to use for the request.                                                     |
| `opts`                                                                                         | [][operations.Option](../../models/operations/option.md)                                       | :heavy_minus_sign:                                                                             | The options for this request.                                                                  |

### Response

**[*operations.UpdateViewStateSyncResponse](../../models/operations/updateviewstatesyncresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetUsers

Get list of all users that are friends and have library access with the provided Plex authentication token

### Example Usage

<!-- UsageSnippet language="go" operationID="getUsers" method="get" path="/users" -->
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

    res, err := s.Users.GetUsers(ctx, operations.GetUsersRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `ctx`                                                                    | [context.Context](https://pkg.go.dev/context#Context)                    | :heavy_check_mark:                                                       | The context to use for the request.                                      |
| `request`                                                                | [operations.GetUsersRequest](../../models/operations/getusersrequest.md) | :heavy_check_mark:                                                       | The request object to use for the request.                               |
| `opts`                                                                   | [][operations.Option](../../models/operations/option.md)                 | :heavy_minus_sign:                                                       | The options for this request.                                            |

### Response

**[*operations.GetUsersResponse](../../models/operations/getusersresponse.md), error**

### Errors

| Error Type             | Status Code            | Content Type           |
| ---------------------- | ---------------------- | ---------------------- |
| sdkerrors.BadRequest   | 400                    | application/json       |
| sdkerrors.Unauthorized | 401                    | application/json       |
| sdkerrors.SDKError     | 4XX, 5XX               | \*/\*                  |

## GetAccountXML

Get the logged-in user's account details in XML format (legacy v1 endpoint).

### Example Usage

<!-- UsageSnippet language="go" operationID="getAccountXML" method="get" path="/users/account" -->
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

    res, err := s.Users.GetAccountXML(ctx, operations.GetAccountXMLRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.Body != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                          | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `ctx`                                                                              | [context.Context](https://pkg.go.dev/context#Context)                              | :heavy_check_mark:                                                                 | The context to use for the request.                                                |
| `request`                                                                          | [operations.GetAccountXMLRequest](../../models/operations/getaccountxmlrequest.md) | :heavy_check_mark:                                                                 | The request object to use for the request.                                         |
| `opts`                                                                             | [][operations.Option](../../models/operations/option.md)                           | :heavy_minus_sign:                                                                 | The options for this request.                                                      |

### Response

**[*operations.GetAccountXMLResponse](../../models/operations/getaccountxmlresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetAccountJSON

Get the logged-in user's account details in JSON format (legacy v1 endpoint).

### Example Usage

<!-- UsageSnippet language="go" operationID="getAccountJSON" method="get" path="/users/account.json" -->
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

    res, err := s.Users.GetAccountJSON(ctx, operations.GetAccountJSONRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.UserPlexAccount != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                            | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `ctx`                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                | :heavy_check_mark:                                                                   | The context to use for the request.                                                  |
| `request`                                                                            | [operations.GetAccountJSONRequest](../../models/operations/getaccountjsonrequest.md) | :heavy_check_mark:                                                                   | The request object to use for the request.                                           |
| `opts`                                                                               | [][operations.Option](../../models/operations/option.md)                             | :heavy_minus_sign:                                                                   | The options for this request.                                                        |

### Response

**[*operations.GetAccountJSONResponse](../../models/operations/getaccountjsonresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## DeleteHomeUser

Remove a Plex Home user.

### Example Usage

<!-- UsageSnippet language="go" operationID="deleteHomeUser" method="delete" path="/home/users/{userId}" -->
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

    res, err := s.Users.DeleteHomeUser(ctx, operations.DeleteHomeUserRequest{
        UserID: 768153,
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
| `request`                                                                            | [operations.DeleteHomeUserRequest](../../models/operations/deletehomeuserrequest.md) | :heavy_check_mark:                                                                   | The request object to use for the request.                                           |
| `opts`                                                                               | [][operations.Option](../../models/operations/option.md)                             | :heavy_minus_sign:                                                                   | The options for this request.                                                        |

### Response

**[*operations.DeleteHomeUserResponse](../../models/operations/deletehomeuserresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## UpdateHomeUser

Update a Plex Home user.

### Example Usage

<!-- UsageSnippet language="go" operationID="updateHomeUser" method="put" path="/home/users/{userId}" -->
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

    res, err := s.Users.UpdateHomeUser(ctx, operations.UpdateHomeUserRequest{
        UserID: 187897,
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
| `request`                                                                            | [operations.UpdateHomeUserRequest](../../models/operations/updatehomeuserrequest.md) | :heavy_check_mark:                                                                   | The request object to use for the request.                                           |
| `opts`                                                                               | [][operations.Option](../../models/operations/option.md)                             | :heavy_minus_sign:                                                                   | The options for this request.                                                        |

### Response

**[*operations.UpdateHomeUserResponse](../../models/operations/updatehomeuserresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## UpdateRestrictedUser

Update restricted (managed) home user settings.

### Example Usage

<!-- UsageSnippet language="go" operationID="updateRestrictedUser" method="put" path="/home/users/restricted/{userId}" -->
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

    res, err := s.Users.UpdateRestrictedUser(ctx, operations.UpdateRestrictedUserRequest{
        UserID: 130660,
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

| Parameter                                                                                        | Type                                                                                             | Required                                                                                         | Description                                                                                      |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                            | [context.Context](https://pkg.go.dev/context#Context)                                            | :heavy_check_mark:                                                                               | The context to use for the request.                                                              |
| `request`                                                                                        | [operations.UpdateRestrictedUserRequest](../../models/operations/updaterestricteduserrequest.md) | :heavy_check_mark:                                                                               | The request object to use for the request.                                                       |
| `opts`                                                                                           | [][operations.Option](../../models/operations/option.md)                                         | :heavy_minus_sign:                                                                               | The options for this request.                                                                    |

### Response

**[*operations.UpdateRestrictedUserResponse](../../models/operations/updaterestricteduserresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetServerDetails

Get server details for sharing.

### Example Usage

<!-- UsageSnippet language="go" operationID="getServerDetails" method="get" path="/servers/{machineId}" -->
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

    res, err := s.Users.GetServerDetails(ctx, operations.GetServerDetailsRequest{
        MachineID: "<id>",
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.ServerConfiguration != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                | Type                                                                                     | Required                                                                                 | Description                                                                              |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `ctx`                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                    | :heavy_check_mark:                                                                       | The context to use for the request.                                                      |
| `request`                                                                                | [operations.GetServerDetailsRequest](../../models/operations/getserverdetailsrequest.md) | :heavy_check_mark:                                                                       | The request object to use for the request.                                               |
| `opts`                                                                                   | [][operations.Option](../../models/operations/option.md)                                 | :heavy_minus_sign:                                                                       | The options for this request.                                                            |

### Response

**[*operations.GetServerDetailsResponse](../../models/operations/getserverdetailsresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## ShareServerLegacy

Share a library with a friend (legacy v1 XML endpoint).

### Example Usage

<!-- UsageSnippet language="go" operationID="shareServerLegacy" method="post" path="/servers/{machineId}/shared_servers" -->
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

    res, err := s.Users.ShareServerLegacy(ctx, operations.ShareServerLegacyRequest{
        MachineID: "<id>",
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

| Parameter                                                                                  | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `ctx`                                                                                      | [context.Context](https://pkg.go.dev/context#Context)                                      | :heavy_check_mark:                                                                         | The context to use for the request.                                                        |
| `request`                                                                                  | [operations.ShareServerLegacyRequest](../../models/operations/shareserverlegacyrequest.md) | :heavy_check_mark:                                                                         | The request object to use for the request.                                                 |
| `opts`                                                                                     | [][operations.Option](../../models/operations/option.md)                                   | :heavy_minus_sign:                                                                         | The options for this request.                                                              |

### Response

**[*operations.ShareServerLegacyResponse](../../models/operations/shareserverlegacyresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## RemoveShare

Remove a share / friend.

### Example Usage

<!-- UsageSnippet language="go" operationID="removeShare" method="delete" path="/sharings/{userId}" -->
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

    res, err := s.Users.RemoveShare(ctx, operations.RemoveShareRequest{
        UserID: 858924,
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

| Parameter                                                                      | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `ctx`                                                                          | [context.Context](https://pkg.go.dev/context#Context)                          | :heavy_check_mark:                                                             | The context to use for the request.                                            |
| `request`                                                                      | [operations.RemoveShareRequest](../../models/operations/removesharerequest.md) | :heavy_check_mark:                                                             | The request object to use for the request.                                     |
| `opts`                                                                         | [][operations.Option](../../models/operations/option.md)                       | :heavy_minus_sign:                                                             | The options for this request.                                                  |

### Response

**[*operations.RemoveShareResponse](../../models/operations/removeshareresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## UpdateShare

Update friend filters (allowSync, filterMovies, etc.).

### Example Usage

<!-- UsageSnippet language="go" operationID="updateShare" method="put" path="/sharings/{userId}" -->
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

    res, err := s.Users.UpdateShare(ctx, operations.UpdateShareRequest{
        UserID: 139113,
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

| Parameter                                                                      | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `ctx`                                                                          | [context.Context](https://pkg.go.dev/context#Context)                          | :heavy_check_mark:                                                             | The context to use for the request.                                            |
| `request`                                                                      | [operations.UpdateShareRequest](../../models/operations/updatesharerequest.md) | :heavy_check_mark:                                                             | The request object to use for the request.                                     |
| `opts`                                                                         | [][operations.Option](../../models/operations/option.md)                       | :heavy_minus_sign:                                                             | The options for this request.                                                  |

### Response

**[*operations.UpdateShareResponse](../../models/operations/updateshareresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |

## GetUserOptOuts

Get online media source opt-out settings for a user.

### Example Usage

<!-- UsageSnippet language="go" operationID="getUserOptOuts" method="get" path="/user/{uuid}/settings/opt_outs" -->
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

    res, err := s.Users.GetUserOptOuts(ctx, operations.GetUserOptOutsRequest{
        UUID: "17dd8bb4-eb45-4878-97c7-017f7d9a2384",
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.UserOptOutsResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                            | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `ctx`                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                | :heavy_check_mark:                                                                   | The context to use for the request.                                                  |
| `request`                                                                            | [operations.GetUserOptOutsRequest](../../models/operations/getuseroptoutsrequest.md) | :heavy_check_mark:                                                                   | The request object to use for the request.                                           |
| `opts`                                                                               | [][operations.Option](../../models/operations/option.md)                             | :heavy_minus_sign:                                                                   | The options for this request.                                                        |

### Response

**[*operations.GetUserOptOutsResponse](../../models/operations/getuseroptoutsresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| sdkerrors.Error    | 401                | application/json   |
| sdkerrors.SDKError | 4XX, 5XX           | \*/\*              |