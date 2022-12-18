# Boundary (Division/Ranking)
Endpoint: `/api/ladderboundary.php`

## GET
Returns a list of divisions/ranking for a specified ladder.

Intent: `ladderboundary:retrieve`

### Request

| parameter   | required | description                                       |
| ----------- | -------- | ------------------------------------------------- |
| ladder_type | Y        | `rt` or `ct`                                      |
| ladder_id   | N        | Ladder ID (required if `ladder_type` is not used) |

#### Example

| parameter   | value |
| ----------- | ----- |
| ladder_type | rt    |

### Response

```json
{
  "status": "success",
  "results": [
    {
      "ladder_order": 1,
      "ladder_boundary_name": "Iron",
      "minimum_lr": null,
      "maximum_lr": 1249,
      "color": "#887f7d",
      "emblem": "https://i.imgur.com/ktQ5lTG.png"
    },
    ...
    {
      "ladder_order": 10,
      "ladder_boundary_name": "Grandmaster",
      "minimum_lr": 12000,
      "maximum_lr": null,
      "color": "#851dd6",
      "emblem": "https://i.imgur.com/lojv77Q.png"
    }
  ]
}
```

## POST / PUT
Adds a new division/ranking if the `boundary_name` does not exists, otherwise updates the existing entry if the `boundary_name` exists for the specified ladder. `boundary_name` matching is case-insensitive and ignores whitespaces.

Intent: `ladderboundary:update`

### Request

| parameter     | required | description         |
| ------------- | -------- | ------------------- |
| code          | Y        | API key             |
| ladder_id     | Y        | Ladder ID           |
| boundary_name | Y        | Division/rank name  |
| minimum_lr    | N        | Minimum LR          |
| color         | Y        | Hexidecimal color   |
| emblem        | Y        | URL to emblem image |

### Response

| parameter     | value                           |
| ------------- | ------------------------------- |
| code          | `API key`                       |
| ladder_id     | 1                               |
| boundary_name | Wood                            |
| minimum_lr    | 250                             |
| color         | #663300                         |
| emblem        | https://i.imgur.com/ETxn48m.png |

```json
{
  "status": "success",
  "results": [
    {
      "ladder_order": 1,
      "ladder_boundary_name": "Iron",
      "minimum_lr": null,
      "maximum_lr": 249,
      "color": "#887f7d",
      "emblem": "https://i.imgur.com/ktQ5lTG.png"
    },
    {
      "ladder_order": 2,
      "ladder_boundary_name": "Wood",
      "minimum_lr": 250,
      "maximum_lr": 1249,
      "color": "#663300",
      "emblem": "https://i.imgur.com/ETxn48m.png"
    },
    ...
    {
      "ladder_order": 11,
      "ladder_boundary_name": "Grandmaster",
      "minimum_lr": 12000,
      "maximum_lr": null,
      "color": "#851dd6",
      "emblem": "https://i.imgur.com/lojv77Q.png"
    }
  ]
}
```

## DELETE
Remove a specified division/ranking for a specified ladder.

Intent: `ladderboundary:delete`

### Request

| parameter     | required | description                            |
| ------------- | -------- | -------------------------------------- |
| code          | Y        | API key                                |
| ladder_type   | Y        | `rt` or `ct`                           |
| ladder_id     | N        | Ladder ID (alternative to ladder_type) |
| boundary_name | Y        | Division/rank name                     |

### Response

| parameter     | value   |
| ------------- | ------- |
| code          | API key |
| ladder_id     | 1       |
| boundary_name | Wood    |

```json
{
  "status": "success",
  "results": [
    {
      "ladder_order": 1,
      "ladder_boundary_name": "Iron",
      "minimum_lr": null,
      "maximum_lr": 249,
      "color": "#887f7d",
      "emblem": "https://i.imgur.com/ktQ5lTG.png"
    },
    ...
    {
      "ladder_order": 10,
      "ladder_boundary_name": "Grandmaster",
      "minimum_lr": 12000,
      "maximum_lr": null,
      "color": "#851dd6",
      "emblem": "https://i.imgur.com/lojv77Q.png"
    }
  ]
}
```
