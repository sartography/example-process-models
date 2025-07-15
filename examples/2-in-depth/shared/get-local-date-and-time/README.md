### Overview
The *Get Local Date and Time* process consists of one Script Task named "Get Local Date and Time" which executes a Python script as described here:  
### Purpose
This process provides a flexible way to obtain the current date and time in a desired format and timezone, which can be useful for various applications requiring localized time information.
### Script Task Functionality
**Time Zone Handling**
The script checks for a variable `ldt_tz` (timezone). If not provided, it defaults to "US/Eastern", using the `pytz` library to localize the current time to the specified timezone.  
**Date Formatting**
The script checks for a variable `ldt_date_format`. If not provided, it defaults to "MDY" (Month-Day-Year). and then formats the date according to the variable.  
**Time Formatting**
The script checks for a variable `ldt_time_format`. If not provided it defaults to "12" hour time and then formats the time accordingly.  
**Return Values**
The script checks for a variable `ldt_return`. if not provided it defaults to "all". If `ldt_return` is "all," it generates and returns the following variables:
- A localized Python datetime object: `ldt_obj`
- A localized date string: `local_date_str`
- A localized time string: `ldt_local_time_str`
- A localized date and time string: `ldt_local_datetime_str`