# Provider

A media provider registered with the PMS.


## Fields

| Field                                  | Type                                   | Required                               | Description                            | Example                                |
| -------------------------------------- | -------------------------------------- | -------------------------------------- | -------------------------------------- | -------------------------------------- |
| `Title`                                | `*string`                              | :heavy_minus_sign:                     | Human-readable provider title.         | Plex VOD                               |
| `Identifier`                           | `*string`                              | :heavy_minus_sign:                     | Unique provider identifier.            | tv.plex.provider.vod                   |
| `Protocol`                             | `*string`                              | :heavy_minus_sign:                     | Protocol version used by the provider. | 1.0                                    |
| `Types`                                | `*string`                              | :heavy_minus_sign:                     | Content types provided.                | movie,show                             |