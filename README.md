# LB Date Math Extension

LioranBoard Extension that allows you to do simple math with dates. You can add and substract minutes/hours/days/years (and more) to a specific date or the current date and time, in any format you like.


## Commands

This extension adds two commands to LB.

### Date Math

The main command. Allows you to add and substract any number of any time unit to an specific date. You can also use it to change the date format.

* __variable__: The name of the variable where will be saved the result of the operation.
* __inFormat__: The format of the date or time you input. More information about formatting below.
* __date__: The date (or time) you will operate with. Must be in the format added in inFormat. You can fill it with _today_ or _now_ to get the current date and time (both do the same).
* __operator__: Only two options: += to add or -= to substract.
* __number__: Number you want to add or substract. You can leave it blank to don't do any math and just change the format of the date.
* __unit__: Time unit of the number of the previous box. Can be minutes, hours, days, months or years.
* __outFormat__: The format of the output result. If you leave it blank the extension will keep the input format (inFormat). More information about formatting below.

#### Examples and And Different Uses

* ___Example of addition and change of format:___ Add 5 months to the date 10-04-2020 and change the format.

<img src="https://raw.githubusercontent.com/SebasF1349/LB-Date-Math-Extension/main/Examples/Example%201.1.jpeg">

<img src="https://raw.githubusercontent.com/SebasF1349/LB-Date-Math-Extension/main/Examples/Example%201.2.jpeg">

* ___Example of changing format:___ Get the day of the week of the 21th Oct 2019. number is blank and operator and unit doesn't matter, as there is no math involved.

<img src="https://raw.githubusercontent.com/SebasF1349/LB-Date-Math-Extension/main/Examples/Example%202.1.jpeg">

<img src="https://raw.githubusercontent.com/SebasF1349/LB-Date-Math-Extension/main/Examples/Example%202.2.jpeg">

* ___Example of getting today's date:___ Get the last month (today is 15th Aug)

<img src="https://raw.githubusercontent.com/SebasF1349/LB-Date-Math-Extension/main/Examples/Example%203.1.jpeg">

<img src="https://raw.githubusercontent.com/SebasF1349/LB-Date-Math-Extension/main/Examples/Example%203.2.jpeg">

### Date Diff

This command only takes the difference between two dates or times. Useful to know how much time is left until an event. It can return float numbers.

* __variable__: The name of the variable where will be saved the result of the operation.
* __inFormat__: The format of the date or time you input. More information about formatting below.
* __date1__: The first date. Must be in the inFormat format. You can fill it with _today_ or _now_ to get the current date and time (both do the same).
* __date2__: The second date. Must be in the inFormat format. You can fill it with _today_ or _now_ to get the current date and time (both do the same). The command will do date1 - date2.
* __unit__: The time unit you want for the result. Can be minutes, hours, days, months or years. 

#### Examples

* ___Simple example:___ Calculate how many days are between 2nd Feb 2020 and 3th Mar 2020.

<img src="https://raw.githubusercontent.com/SebasF1349/LB-Date-Math-Extension/main/Examples/Example%204.1.jpeg">

<img src="https://raw.githubusercontent.com/SebasF1349/LB-Date-Math-Extension/main/Examples/Example%204.2.jpeg">

* ___Example with negative and non-integer result:___ Calculate how many months are between 7th Oct 2018 and 4th May 2018. As the second date is later than the first one, the result is a negative number. Also, take notice of the not integer result.

<img src="https://raw.githubusercontent.com/SebasF1349/LB-Date-Math-Extension/main/Examples/Example%205.1.jpeg">

<img src="https://raw.githubusercontent.com/SebasF1349/LB-Date-Math-Extension/main/Examples/Example%205.2.jpeg">

## Formatting

One of the main features of the extension is the ability to do math in any date format you want, even adding text to it. To do that, the extension uses the _moment.js_ library that's incorporated in the LB Transmitter.

Here are some of the most common tokens available. You can check every possibility here: [Moment.js documentation](https://momentjs.com/docs/#/displaying/format/)

|  Category | Token |  Output |
|--|--|--|
| Day of Month | D | 1 2 ... 30 31 |
| | DD | 01 02 ... 30 31 |
| | Do | 1st 2nd ... 30th 31st |
| Day of Week | ddd | Sun Mon ... Fri Sat |
| | dddd | Sunday Monday ... Friday Saturday |
| Month | MM | 01 02 ... 11 12 |
| | MMM | Jan Feb ... Nov Dec |
| | MMMM | January February ... November December |
| Year | YY | 70 71 ... 29 30 |
| | YYYY |  1970 1971 ... 2029 2030 |
| Hour | HH | 00 01 ... 22 23 |
| | hh |  01 02 ... 11 12 |
| | kk |  01 02 ... 23 24 |
| Minute | mm | 00 01 ... 58 59 |
| Second | ss | 00 01 ... 58 59 |
| Time | LT | 8:30 PM |
| Month numeral, day of month, year  | L | 00 01 ... 58 59 |
| Month name, day of month, year | LL | September 4, 1986 |
| Month name, day of month, year, time | LLL | September 4, 1986 8:30 PM |
| Month name, day of month, day of week, year, time | LLLL | Thursday, September 4, 1986 8:30 PM |

### Adding Text

In the format you can use any character that's not a letter (like -, / or even spaces) without any problem. If you want to add words, you need to put them between [ ].

### Examples

The following examples can be used in any of the inFormat or outFormat boxes. For the examples, take into account that today is 15th Aug 2021, 6:50 PM.

| Format | Output |
|--|--|
|YYYYMMDD|20210815|
|MM/DD-YY|08/15-21|
|dddd Do [of the month] MMMM, [year] YYYY|Sunday 15th of the month August, year 2021|
|[rubbish] ddd- [LioranBoard] /HHmm|rubbish Sun- LioranBoard /0650|

## Clarifications

* When you add a date without a time, the default time will be 00:00.
* Outputs are always strings, even when it's just a number. Remember to use String to Real command if you plan to do math with those.
* Added yellow alerts in the receiver if any important field is not complete or the format is wrong.

## Installation

1. Download the last version of the Date_Math.lbe file from [releases](https://github.com/SebasF1349/LB-Date-Math-Extension/releases).
2. Open the LioranBoard Receiver and press on Install Extension.
3. Select the downloaded Date_Math.lbe file and be sure to select your current transmitter.
4. Use the Send to Extension command to select any of the extension commands: Date Math or Date Diff.
5. Create something cool.

