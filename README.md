# HabitTracker
The program allows the user to record his habits in order to change them. For example, he can decide to do more sports on a regular basis. He can specify whether he wants to record daily or weekly habits. When he fulfills his task, he simply puts a check in a checkbox. The program is designed to be easy and logical to use.

The program is created in Phyton 3 and standard functions and standard modules were used. For example, the GUI was programmed using the Tkinter module and the data was stored in SQLite. 

On an information page, the longest and shortest series of the user's confirmations is displayed. The calculation of these series is done directly on the database. For this purpose, a virtual table is created in which the row number and the difference between the done-at date and the start date (Julian number of days) are entered. If you then subtract the line number from this result, it will always remain the same until there is a gap. Then the result "jumps" to a higher value. 

Example:

1 | Day 1 | 1-1=0 

2 | Day 2 | 2-2=0

3 | Day 3 | 3-3=0

4 | Day 4 | 4-4=0

5 | Day 6 | 6-5=1

6 | Day 7 | 7-6=1

For day 5, the task was not completed, this day is missing. The difference number of days - line number, then results in a jump.

The result row is grouped and sorted with SQL, and the MAX and MIN date of the respective group is determined. The number of group entries gives the number of days, with the MIN and MAX dates, you can show the user from when to when he had the best (or worst) results. The SQL code for the calculation, fits in a single line. Since the calculation is done in-memory, it can be assumed that it is very fast.

For the week-by-week evaluation, we proceed in the same way, but take the integer value from the calculation of days / 7. This then results in week numbers, with which we proceed in the same way.

The SQL statement is contained in the function series-check-values.

The user can change created habits and also delete them completely. Date entries are checked and the user is informed if they are wrong.

Translated with www.DeepL.com/Translator (free version)
