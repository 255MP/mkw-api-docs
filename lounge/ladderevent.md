# Event
Endpoint: `/api/ladderevent.php`

## GET (single event)
Returns the specified event.

Intent: `ladderevent:retrieve`

### Request

| parameter | required | description |
| --------- | -------- | ----------- |
| event_id  | Y        | Event ID    |

### Response

| parameter | value |
| --------- | ----- |
| event_id  | 500   |

```json
{
  "status": "success",
  "results": [
    {
      "event_id": 500,
      "ladder_id": 1,
      "event_type": "FFA",
      "tier": "Tier 5",
      "event_date": "2021-08-12 02:18:22",
      "event_detail_id": 7486,
      "team": 1,
      "ranking": 1,
      "player_id": 871,
      "multiplier": "1",
      "races": 12,
      "score": 93,
      "subbed_out": 0,
      "subbed_in": 0,
      "current_mmr": 8161,
      "change_mmr": 259,
      "updated_mmr": 8420,
      "peak_mmr": 8503,
      "current_lr": 4594,
      "change_lr": 275,
      "updated_lr": 4869,
      "peak_lr": 4869,
      "player_name": "Edison",
      "player_country_flag": null,
      "discord_user_id": "82947273561997312",
      "update_date": "2021-08-07 01:12:41",
      "promotion": "-",
      "current_division": "Gold",
      "updated_division": "Gold",
      "current_class": "Class S",
      "updated_class": "Class S",
      "current_emblem": "https://i.imgur.com/kjAfn9H.png",
      "updated_emblem": "https://i.imgur.com/kjAfn9H.png"
    },
    ...
    {
      "event_id": 500,
      "ladder_id": 1,
      "event_type": "FFA",
      "tier": "Tier 5",
      "event_date": "2021-08-12 02:18:22",
      "event_detail_id": 7498,
      "team": 12,
      "ranking": 11,
      "player_id": 2847,
      "multiplier": "1",
      "races": 12,
      "score": 59,
      "subbed_out": 0,
      "subbed_in": 0,
      "current_mmr": 6793,
      "change_mmr": -297,
      "updated_mmr": 6496,
      "peak_mmr": 7002,
      "current_lr": 4208,
      "change_lr": -104,
      "updated_lr": 4104,
      "peak_lr": 4225,
      "player_name": "scythe",
      "player_country_flag": null,
      "discord_user_id": "482973487611510784",
      "update_date": "2021-08-07 01:12:41",
      "promotion": "-",
      "current_division": "Gold",
      "updated_division": "Gold",
      "current_class": "Class A",
      "updated_class": "Class A",
      "current_emblem": "https://i.imgur.com/kjAfn9H.png",
      "updated_emblem": "https://i.imgur.com/kjAfn9H.png"
    }
  ]
}
```

## GET (event list)
Returns a list of the most recent events based on the specified ladder.

Intent: `ladderevent:retrieve`

### Request

| parameter | required | description                                       |
| --------- | -------- | ------------------------------------------------- |
| all       | Y        | Specifies a list of all events should be returned |
| ladder_id | Y        | Ladder ID                                         |
| limit     | N        | Limit the number of events returned               |

### Response

| parameter | value |
| --------- | ----- |
| all       | 1     |
| ladder_id | 1     |
| limit     | 5    |

```json
{
  "status": "success",
  "results": [
    {
      "event_id": 3062,
      "subs": "0",
      "players": 12,
      "races": 12,
      "ladder_id": 1,
      "event_type": "2v2",
      "tier": "Tier 5",
      "is_delete": 0,
      "event_date": "2021-09-17 22:43:07"
    },
    ...
    {
      "event_id": 3056,
      "subs": "0",
      "players": 12,
      "races": 12,
      "ladder_id": 1,
      "event_type": "FFA",
      "tier": "Tier 1",
      "is_delete": 0,
      "event_date": "2021-09-17 21:32:04"
    }
  ]
}
```

## DELETE
Remove a specific event.

Intent: `ladderevent:delete`

### Request

| parameters    | required | description        |
| ------------- | -------- | ------------------ |
| code          | Y        | API key            |
| event_id     | Y        | Event ID          |

### Response

| parameter     | value     |
| ------------- | --------- |
| code          | `API key` |
| event_id     | 500         |

```json
{
  "status": "success",
  "results": [
    {
      "event_id": 500,
      "ladder_id": 1,
      "event_type": "FFA",
      "tier": "Tier 5",
      "event_date": "2021-08-12 02:18:22",
      "event_detail_id": 7486,
      "team": 1,
      "ranking": 1,
      "player_id": 871,
      "multiplier": "1",
      "races": 12,
      "score": 93,
      "subbed_out": 0,
      "subbed_in": 0,
      "current_mmr": 8161,
      "change_mmr": 259,
      "updated_mmr": 8420,
      "peak_mmr": 8503,
      "current_lr": 4594,
      "change_lr": 275,
      "updated_lr": 4869,
      "peak_lr": 4869,
      "player_name": "Edison",
      "player_country_flag": null,
      "discord_user_id": "82947273561997312",
      "update_date": "2021-08-07 01:12:41",
      "promotion": "-",
      "current_division": "Gold",
      "updated_division": "Gold",
      "current_class": "Class S",
      "updated_class": "Class S",
      "current_emblem": "https://i.imgur.com/kjAfn9H.png",
      "updated_emblem": "https://i.imgur.com/kjAfn9H.png"
    },
    ...
    {
      "event_id": 500,
      "ladder_id": 1,
      "event_type": "FFA",
      "tier": "Tier 5",
      "event_date": "2021-08-12 02:18:22",
      "event_detail_id": 7498,
      "team": 12,
      "ranking": 11,
      "player_id": 2847,
      "multiplier": "1",
      "races": 12,
      "score": 59,
      "subbed_out": 0,
      "subbed_in": 0,
      "current_mmr": 6793,
      "change_mmr": -297,
      "updated_mmr": 6496,
      "peak_mmr": 7002,
      "current_lr": 4208,
      "change_lr": -104,
      "updated_lr": 4104,
      "peak_lr": 4225,
      "player_name": "scythe",
      "player_country_flag": null,
      "discord_user_id": "482973487611510784",
      "update_date": "2021-08-07 01:12:41",
      "promotion": "-",
      "current_division": "Gold",
      "updated_division": "Gold",
      "current_class": "Class A",
      "updated_class": "Class A",
      "current_emblem": "https://i.imgur.com/kjAfn9H.png",
      "updated_emblem": "https://i.imgur.com/kjAfn9H.png"
    }
  ]
}
```
