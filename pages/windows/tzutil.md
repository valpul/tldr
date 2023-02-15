# tzutil

> A tool for displaying or configuring the system time zone.
> More information: <https://ss64.com/nt/timezones.html>.

- Get the current time zone:

`tzutil /g`

- List all the available time zones:

`tzutil /l`

-- In this format

`display name = (UTC-06:00) Central Time (US & Canada)`
`time zone ID = Central Standard Time`

- Set the system time zone to the specific value:

`tzutil /s {{timezone_id}}`
