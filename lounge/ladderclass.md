# Class
Endpoint: `/api/ladderclass.php`

## GET
Returns a list of classes for a specified ladder.

Intent: `ladderclass:retrieve`

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
      "ladder_order": 1,
      "ladder_class_name": "Class F",
      "minimum_mmr": null,
      "maximum_mmr": 999
    },
    ...
    {
      "ladder_order": 8,
      "ladder_class_name": "Class X",
      "minimum_mmr": 9000,
      "maximum_mmr": null
    }
  ]
}
```

## POST / PUT
Adds a new class if the `class_name` does not exists, otherwise updates the existing entry if the `class_name` exists for the specified ladder. `class_name` matching is case-insensitive and ignores whitespaces.

Intent: `ladderclass:update`

### Request

| parameter   | required | description |
| ----------- | -------- | ----------- |
| code        | Y        | API key     |
| ladder_id   | Y        | Ladder ID   |
| class_name  | Y        | Class name  |
| minimum_mmr | N        | Minimum MMR |

### Response

| parameter   | value     |
| ----------- | --------- |
| code        | `API key` |
| ladder_id   | 1         |
| class_name  | Class Y   |
| minimum_mmr | 250       |

```json
{
  "status": "success",
  "results": [
    {
      "ladder_order": 1,
      "ladder_class_name": "Class F",
      "minimum_mmr": null,
      "maximum_mmr": 249
    },
    {
      "ladder_order": 2,
      "ladder_class_name": "Class Y",
      "minimum_mmr": 250,
      "maximum_mmr": 999
    },
    ...
    {
      "ladder_order": 9,
      "ladder_class_name": "Class X",
      "minimum_mmr": 9000,
      "maximum_mmr": null
    }
  ]
}
```

## DELETE
Remove a specified division/ranking for a specified ladder.

Intent: `ladderclass:delete`

### Request

| parameter  | required | description |
| ---------- | -------- | ----------- |
| code       | Y        | API key     |
| ladder_id  | Y        | Ladder ID   |
| class_name | Y        | Class name  |

### Response

| parameter  | value     |
| ---------- | --------- |
| code       | `API key` |
| ladder_id  | 1         |
| class_name | Class Y   |

```json
{
  "status": "success",
  "results": [
    {
      "ladder_order": 1,
      "ladder_class_name": "Class F",
      "minimum_mmr": null,
      "maximum_mmr": 999
    },
    ...
    {
      "ladder_order": 8,
      "ladder_class_name": "Class X",
      "minimum_mmr": 9000,
      "maximum_mmr": null
    }
  ]
}
```
