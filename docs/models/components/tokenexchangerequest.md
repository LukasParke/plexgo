# TokenExchangeRequest


## Fields

| Field                                       | Type                                        | Required                                    | Description                                 |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| `ClientIdentifier`                          | `*string`                                   | :heavy_minus_sign:                          | Unique client identifier                    |
| `Jwt`                                       | `*string`                                   | :heavy_minus_sign:                          | JWT token to exchange for a Plex auth token |
| `Scope`                                     | `*string`                                   | :heavy_minus_sign:                          | Requested scope for the token               |