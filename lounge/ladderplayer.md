# Award/Penalty
Endpoint: `/api/ladderplayer.php`

## GET
Returns the player profile containing award/penalty data for a specified profile in a specified ladder.

Intent: `ladderplayer:retrieve`

### Request

| parameter   | required | description                                            |
| ----------- | -------- | ------------------------------------------------------ |
| ladder_type | Y        | `rt` or `ct`                                           |
| ladder_id   | N        | Ladder ID (required if `ladder_type` is not used)      |
| player_id   | Y        | Player ID                                              |
| player_name | N        | Player name (required if `player_id` is not specified) |

### Response

| parameter   | value |
| ----------- | ----- |
| ladder_type | rt    |
| player_id   | 7     |

or

| parameter   | value |
| ----------- | ----- |
| ladder_type | rt    |
| player_name | 255MP |

```json
 {
  "status": "success",
  "results": [
    {
      "player_id": 7,
      "player_name": "255MP",
      "player_country_flag": "un",
      "player_names": "super255mp",
      "name_count": 1,
      "ladder_id": 1,
      "base_mmr": 625,
      "base_lr": 625,
      "strikes": 0,
      "current_mmr": 625,
      "current_lr": 625,
      "peak_mmr": -1,
      "peak_lr": -1,
      "lowest_mmr": -1,
      "lowest_lr": -1,
      "wins": 0,
      "loss": 0,
      "max_gain_mmr": 0,
      "max_gain_lr": 0,
      "max_loss_mmr": 0,
      "max_loss_lr": 0,
      "win_percentage": 0,
      "gainloss10_mmr": 0,
      "gainloss10_lr": 0,
      "wins10": 0,
      "loss10": 0,
      "win10_percentage": 0,
      "win_streak": 0,
      "top_score": 0,
      "average_score": 0,
      "average10_score": 0,
      "std_score": 0,
      "std10_score": 0,
      "total_events": 0,
      "penalties": 0,
      "max_strikes": 5,
      "ranking": "Unranked",
      "percentile": 0,
      "previous_ranking": "Unranked",
      "previous_percentile": 0,
      "last_event_date": "2021-09-10 22:59:36",
      "total_events_since_date": 0,
      "since_date": null,
      "update_date": "2021-09-10 22:59:36",
      "current_division": "Iron",
      "current_class": "Class F",
      "url": "https://www.mkwlounge.gg/ladder/player.php?player_id=7&ladder_id=1",
      "current_emblem": "https://i.imgur.com/ktQ5lTG.png"
    }
  ]
}
```

## POST / PUT
Adds a player to the specified ladder leaderboard.

Intent: `ladderplayer:update`

### Request

| parameter      | required | description                                       |
| -------------- | -------- | ------------------------------------------------- |
| code           | Y        | API key                                           |
| ladder_type    | Y        | `rt` or `ct`                                      |
| ladder_id      | N        | Ladder ID (required if `ladder_type` is not used) |
| placement_name | Y        | Placement name                                    |
| base_mmr       | Y        | Base MMR                                          |
| base_lr        | Y        | Base LR                                           |

### Response

| parameter      | value     |
| -------------- | --------- |
| code           | `API key` |
| ladder_type    | rt        |
| placement_name | Wood      |
| base_mmr       | 250       |
| base_lr        | 251       |

```json
 {
  "status": "success",
  "results": [
    {
      "player_id": 7,
      "player_name": "255MP",
      "player_country_flag": "un",
      "player_names": "super255mp",
      "name_count": 1,
      "ladder_id": 1,
      "base_mmr": 625,
      "base_lr": 625,
      "strikes": 0,
      "current_mmr": 625,
      "current_lr": 625,
      "peak_mmr": -1,
      "peak_lr": -1,
      "lowest_mmr": -1,
      "lowest_lr": -1,
      "wins": 0,
      "loss": 0,
      "max_gain_mmr": 0,
      "max_gain_lr": 0,
      "max_loss_mmr": 0,
      "max_loss_lr": 0,
      "win_percentage": 0,
      "gainloss10_mmr": 0,
      "gainloss10_lr": 0,
      "wins10": 0,
      "loss10": 0,
      "win10_percentage": 0,
      "win_streak": 0,
      "top_score": 0,
      "average_score": 0,
      "average10_score": 0,
      "std_score": 0,
      "std10_score": 0,
      "total_events": 0,
      "penalties": 0,
      "max_strikes": 5,
      "ranking": "Unranked",
      "percentile": 0,
      "previous_ranking": "Unranked",
      "previous_percentile": 0,
      "last_event_date": "2021-09-10 22:59:36",
      "total_events_since_date": 0,
      "since_date": null,
      "update_date": "2021-09-10 22:59:36",
      "current_division": "Iron",
      "current_class": "Class F",
      "url": "https://www.mkwlounge.gg/ladder/player.php?player_id=7&ladder_id=1",
      "current_emblem": "https://i.imgur.com/ktQ5lTG.png"
    }
  ]
}
```

## DELETE
Remove a specified player for a specified ladder.

Intent: `ladderplayer:delete`

### Request

| parameter   | required | description                                       |
| ----------- | -------- | ------------------------------------------------- |
| code        | Y        | API key                                           |
| ladder_type | Y        | `rt` or `ct`                                      |
| ladder_id   | N        | Ladder ID (required if `ladder_type` is not used) |

### Response

| parameter   | value     |
| ----------- | --------- |
| code        | `API key` |
| ladder_type | rt        |

```json
 {
  "status": "success",
  "results": []
}
```
