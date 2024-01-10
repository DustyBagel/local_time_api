## Local Time API Documentation
The Local Time API allows other mods to get the time and date format that the player has set in this mod’s settings. It also factors in daylight savings time if the user enables it.

## Settings
The following settings can be configured by the user:

local_time_api.time_format: The time format, which can be “24_hour” (default) or “12_hour”.
local_time_api.date_order: The order of the day, month, and year in the date. It can be “day_month_year” (default), “month_day_year”, “year_month_day”, or “year_day_month”.
local_time_api.date_separator: The character that separates the day, month, and year in the date. It can be “slash” (default), “dash”, “period”, or “comma”.
local_time_api.timezone: The timezone, which defaults to “UTC_00_00”. It can be any of the UTC offsets from “UTC_minus_12” to “UTC_plus_14”.
local_time_api.daylight_saving_time: A boolean value that determines whether daylight saving time is factored in. It is disabled by default.
These settings can be found under settings -> content: mods -> Local Time Api.

## Usage
Here’s an example of how to use these variables in your mod:

```Lua
minetest.register_on_joinplayer(function()
    local local_time = get_local_time()
    local local_date = get_local_date()
    minetest.chat_send_all("The time is "..local_time)
    minetest.chat_send_all("The date is "..local_date)
end)
```

This example code will print out the date and time to the chat when a player joins the world.

To get the local time or date, you need to call the function that gets the local time or date. Then, store it in a variable to use in your code. When we call one of these functions, they get the time or date at that moment. Keep this in mind when using this because if you call one of the functions and store it in a variable and you want to get the time or date again, you need to call the function again or the time or date will return as what they were when we called the respective function last.

## Other Information
If this documentation is unclear, please make an issue about it at: https://github.com/DustyBagel/local_time_api/issues . I will get back to you as soon as possible.
