# Class
Endpoint: `/api/laddertier.php`

## GET
Returns a list of tiers for a specified ladder.

Intent: `laddertier:retrieve`

### Request

| parameter   | required | description                                       |
| ----------- | -------- | ------------------------------------------------- |
| ladder_type | Y        | `rt` or `ct`                                      |
| ladder_id   | N        | Ladder ID (required if `ladder_type` is not used) |

### Response

| parameter   | value |
| ----------- | ----- |
| ladder_type | rt    |

```json
{
  "status": "success",
  "results": [
    {
      "ladder_id": 5,
      "tier": "Master"
    },
    ...
    {
      "ladder_id": 5,
      "tier": "Tier 8"
    }
  ]
}
```

## POST / PUT
Adds a new tier if the `tier_name` does not exists, otherwise updates the existing entry if the `tier_name` exists for the specified ladder. `tier_name` matching is case-insensitive and ignores whitespaces.

Intent: `laddertier:update`

### Request

| parameter   | required | description                                       |
| ----------- | -------- | ------------------------------------------------- |
| code        | Y        | API key                                           |
| ladder_type | Y        | `rt` or `ct`                                      |
| ladder_id   | N        | Ladder ID (required if `ladder_type` is not used) |
| tier_name   | Y        | Tier name                                         |

### Response

| parameter   | value     |
| ----------- | --------- |
| code        | `API key` |
| ladder_type | rt        |
| tier_name   | Tier 1    |

```json
{
  "status": "success",
  "results": [
    {
      "ladder_id": 5,
      "tier": "Master"
    },
    ...
    {
      "ladder_id": 5,
      "tier": "Tier 1"
    },
    {
      "ladder_id": 5,
      "tier": "Tier 8"
    }
  ]
}
```

## DELETE
Remove the specified tier for a specified ladder.

Intent: `laddertier:delete`

### Request

| parameter   | required | description                                       |
| ----------- | -------- | ------------------------------------------------- |
| code        | Y        | API key                                           |
| ladder_type | Y        | `rt` or `ct`                                      |
| ladder_id   | N        | Ladder ID (required if `ladder_type` is not used) |
| tier_name   | Y        | Tier name                                         |

### Response

| parameter   | value     |
| ----------- | --------- |
| code        | `API key` |
| ladder_type | rt        |
| tier_name   | Tier 1    |

```json
{
  "status": "success",
  "results": [
    {
      "ladder_id": 5,
      "tier": "Master"
    },
    ...
    {
      "ladder_id": 5,
      "tier": "Tier 8"
    }
  ]
}
```
