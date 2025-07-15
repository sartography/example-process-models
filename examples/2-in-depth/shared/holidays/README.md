Returns a list of all US Federal holidays names and dates within a specified date range.  The start of the date range is specified by the variable `start_date' and the end of the date range is specified by the variable `end_date`,  The *Get Holidays* Script Tasks determines all US Federal holidays based on the following lists of holidays and criteria: 

**Fixed Holidays**
| Holiday | Criteria |
| --------- | -------- |
| New Year's Day | January 1st |
| Juneteenth National Independence Day | June 19th |
| Independence Day | July 4th |
| Veterans Day | November 11th |
| Christmas Day | December 25th |
    
**Floating Holidays**
| Holiday | Criteria |
| --------- | -------- |
| Martin Luther King Jr. Day | 3rd Monday in January |
| Washington's Birthday | 3rd Monday in February |
| Memorial Day | Last Monday in May |
| Labor Day | 1st Monday in September |
| Columbus Day | 2nd Monday in October |
| Thanksgiving Day | 4th Thursday in November |

The script returns a list that includes the holiday name and date.  A list of dates only can be obtained using this Python list comprehension:

`holiday_dates = [holiday[0] for holiday in holidays]`

The process could easily be updated to include other countries' holidays. 