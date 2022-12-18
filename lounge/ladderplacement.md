# Placement
Endpoint: `/api/ladderplacement.php`

## GET
Returns a list of placement that players can be assigned to after playing an event.

Intent: `ladderplacement:retrieve`

### Request

| parameter | required | description |
| --------- | -------- | ----------- |
| ladder_id | Y        | Ladder ID   |

### Response

| parameter | value |
| --------- | ----- |
| ladder_id | 1     |

```json
 {
  "status": "success",
  "results": [
    {
      "ladder_id": 1,
      "ladder_placement_name": "Iron",
      "base_mmr": 625,
      "base_lr": 625
    },
    ...
    {
      "ladder_id": 1,
      "ladder_placement_name": "Platinum",
      "base_mmr": 5750,
      "base_lr": 5750
    }
  ]
}
```

## POST / PUT
Adds a new placement if the `placement_name` does not exists, otherwise updates the existing entry if the `placement_name` exists for the specified ladder. `placement_name` matching is case-insensitive and ignores whitespaces.

Intent: `ladderplacement:update`

### Request

| parameter      | required | description    |
| -------------- | -------- | -------------- |
| code           | Y        | API key        |
| ladder_id      | Y        | Ladder ID      |
| placement_name | Y        | Placement name |
| base_mmr       | Y        | Base MMR       |
| base_lr        | Y        | Base LR        |

### Response

| parameter      | value     |
| -------------- | --------- |
| code           | API key |
| ladder_id      | 1         |
| placement_name | Wood      |
| base_mmr       | 250       |
| base_lr        | 251       |

```json
 {
  "status": "success",
  "results": [
    {
      "ladder_id": 1,
      "ladder_placement_name": "Wood",
      "base_mmr": 250,
      "base_lr": 251
    },
    {
      "ladder_id": 1,
      "ladder_placement_name": "Iron",
      "base_mmr": 625,
      "base_lr": 625
    },
    ...
    {
      "ladder_id": 1,
      "ladder_placement_name": "Platinum",
      "base_mmr": 5750,
      "base_lr": 5750
    }
  ]
}
```

## DELETE
Remove a specified placement for a specified ladder.

Intent: `ladderplacement:delete`

### Request

| parameter      | required | description    |
| -------------- | -------- | -------------- |
| code           | Y        | API key        |
| ladder_id      | Y        | Ladder ID      |
| placement_name | Y        | Placement name |

### Response

| parameter      | value     |
| -------------- | --------- |
| code           | `API key` |
| ladder_id      | 1         |
| placement_name | Wood      |

```json
 {
  "status": "success",
  "results": [
    {
      "ladder_id": 1,
      "ladder_placement_name": "Iron",
      "base_mmr": 625,
      "base_lr": 625
    },
    ...
    {
      "ladder_id": 1,
      "ladder_placement_name": "Platinum",
      "base_mmr": 5750,
      "base_lr": 5750
    }
  ]
}
```
