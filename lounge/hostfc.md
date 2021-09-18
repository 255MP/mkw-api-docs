# Host Friend Code
Endpoint: `/api/hostfc.php`

## GET
Returns a list of friend codes for the specified users in a specified guild.

Intent: `hostfc:retrieve`

### Request

| parameter        | required | description                       |
| ---------------- | -------- | --------------------------------- |
| discord_guild_id | Y        | Discord Guild ID                  |
| discord_user_id  | Y        | Discord User ID (comma separated) |

### Response

| parameter        | value                                  |
| ---------------- | -------------------------------------- |
| discord_guild_id | 387347467332485122                     |
| discord_user_id  | 373695448399216642, 207213178298302465 |

```json
{
  "status": "success",
  "results": [
    {
      "discord_guild_id": "387347467332485122",
      "discord_user_id": "373695448399216642",
      "fc": "4172-1200-2150"
    },
    {
      "discord_guild_id": "387347467332485122",
      "discord_user_id": "207213178298302465",
      "fc": "3010-2050-8492"
    }
  ]
}
```

## POST / PUT
Add/update the friend code for a specified user in a specified guild.

Intent: `hostfc:update`

### Request

| parameter        | required | description      |
| ---------------- | -------- | ---------------- |
| code             | Y        | API key          |
| discord_guild_id | Y        | Discord Guild ID |
| discord_user_id  | Y        | Discord User ID  |

### Response

| parameter        | value              |
| ---------------- | ------------------ |
| code             | `API key`          |
| discord_guild_id | 387347467332485122 |
| discord_user_id  | 373695448399216642 |

```json
{
  "status": "success",
  "results": []
}
```

## DELETE
Remove the friend code for a specified user in a specified guild.

Intent: `hostfc:delete`

### Request

| parameter        | required | description      |
| ---------------- | -------- | ---------------- |
| code             | Y        | API key          |
| discord_guild_id | Y        | Discord Guild ID |
| discord_user_id  | Y        | Discord User ID  |

### Response

| parameter        | value              |
| ---------------- | ------------------ |
| code             | `API key`          |
| discord_guild_id | 387347467332485122 |
| discord_user_id  | 373695448399216642 |

```json
{
  "status": "success",
  "results": []
}
```
