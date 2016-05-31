# Date format

Dates can be tailor formatted with the keywords below. As an example, the format `%Y-%m-%d %H:%M:%S` might output something similar to `2010-10-18 18:55:00`.


## Formatting keywords

### Day

Keyword | Outputs | Description
--- | --- | ----
`%a` | Mon through Sun | An abbreviated textual representation of the day
`%A` | Monday through Sunday | A full textual representation of the day
`%d` | 01-31 | Two-digit day of the month (with leading zeros)
`%e` | 1-31 | Day of the month, with a space preceding single digits.


### Week

Keyword | Outputs | Description
--- | --- | ---
`%V` | 01 to 53 | Week number


### Month

Keyword | Outputs | Description
--- | --- | ---
`%b` | Jan through Dec | Abbreviated month name
`%B` | January through December | Full month name
`%m` | 01 to 12 | Two digit representation of the month


### Year

Keyword | Outputs | Description
--- | --- | ---
`%Y` | Example: 2015 | Four digit representation of the year


### Time

Keyword | Outputs | Description
--- | --- | ---
`%H` | 00 to 23 | Two digit representation of the hour in 24-hour format
`%I` | 01 to 12 | Two digit representation of the hour in 12-hour format
`%l` (lower-case L) | 1 to 12 | Hour in 12-hour format, with a space preceeding single digits
`%p` | Example: AM | UPPER-CASE 'AM' or 'PM' based on the given time
`%P` | Example: am | lower-case 'am' or 'pm' based on the given time
`%M` | 00 to 59 | Two digit representation of the minute
`%S` | 00 to 59 | Two digit representation of the second