# Local Time API

The Local Time API allows other mods to get the time and date format that the player has set in this mod's settings. It also factors in daylight savings time if the user enables it.

## Settings

The following settings can be configured by the user:

- `local_time_api.time_format`: The time format, which can be "24_hour" (default) or "12_hour".
- `local_time_api.date_order`: The order of the day, month, and year in the date. It can be "day_month_year" (default), "month_day_year", "year_month_day", or "year_day_month".
- `local_time_api.date_separator`: The character that separates the day, month, and year in the date. It can be "slash" (default), "dash", "period", or "comma".
- `local_time_api.timezone`: The timezone, which defaults to "UTC_00_00". It can be any of the UTC offsets from "UTC_minus_12" to "UTC_plus_14".
- `local_time_api.daylight_saving_time`: A boolean value that determines whether daylight saving time is factored in. It is disabled by default.

These settings can be found under settings -> content: mods -> Local Time Api.

## Usage

To use the Local Time API in your mod, you need to add this mod as a dependency. You can then access the `local_time` and `local_date` global variables to get the current time and date according to the user's settings.

Here's an example of how to use these variables in your mod:

```lua
minetest.register_on_joinplayer(function(player)
    minetest.chat_send_all(local_date.." "..local_time)
end)

This code will print out the date and time to the chat when a player joins the world, with a space separating them.

