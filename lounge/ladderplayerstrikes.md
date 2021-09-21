# Strikes
Endpoint: `/api/ladderplayerstrikes.php`

## GET
Returns a list of players whom hit the max strike limit. If you are trying to retrieve the current strike amount for a particular player, you must use the **Ladder Player** API endpoint.

Intent: `ladderplayerstrikes:retrieve`

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
      "player_id": 7,
      "player_name": "255MP",
      "strikes": 6,
      "max_strikes": 5
    }
  ]
}
```

## POST / PUT
Adds award/penalty to players in a specified ladder.

Intent: `ladderplayerstrikes:update`

### Request

| parameter    | required | description                                                                 |
| ------------ | -------- | --------------------------------------------------------------------------- |
| code         | Y        | API key                                                                     |
| ladder_id    | Y        | Ladder ID                                                                   |
| player_ids   | Y        | Comma separated list of player IDs                                          |
| player_names | Y        | Comma separated list of player names (required if `player_ids` is not used) |
| strikes      | Y        | Strike amount (positive to add, negative to remove)                          |

### Response

| parameter    | value     |
| ------------ | --------- |
| code         | `API key` |
| ladder_id    | 1         |
| player_names | 255MP     |
| strikes      | 3         |

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
      "strikes": 9,
      "current_mmr": 625,
      "current_lr": 1120,
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
      "penalties": 495,
      "max_strikes": 5,
      "ranking": "Unranked",
      "percentile": 0,
      "previous_ranking": "Unranked",
      "previous_percentile": 0,
      "last_event_date": "2021-08-27 03:14:40",
      "total_events_since_date": 0,
      "since_date": null,
      "update_date": "2021-08-27 03:14:40",
      "current_division": "Iron",
      "current_class": "Class F",
      "url": "https://www.mkwlounge.gg/ladder/player.php?player_id=7&ladder_id=1",
      "current_emblem": "https://i.imgur.com/ktQ5lTG.png"
    }
  ]
}
```
