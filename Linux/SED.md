## TOPIC:SED(STREAM EDITOR)

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

we can use sed command to print(retrive),delete and replace data,insert data with out opening file.

SED (Print the records):



Use1:sed -n '3p' demo.txt    (It will display only the thrid line)

Use2:sed -n '$p' demo.txt    (It will display the last line) ,$ means last line.

Use3:sed -n '2,4p' demo.txt  (It will display from 2nd to 4th lines).

Use4:sed -n '5!p' demo.txt  (It will display all lines except 5th line).

Use5:sed -n '2,4p'demo.txt  (It will display all lines from 2nd to 4th).

Use6:sed -n '2,4!p'demo.txt  (It will display all lines except 2 to 4).

Use7:sed -n  '7p;6p;15p' demo.txt (It will display 7,6,15 lines).

Use8:sed -n '/unix/p' demo.txt (It will display all lines which contains unix).



sed -n -e '/tej/p' -e '/pavan/p' -e '/ntr/p' chiru (search multiple pattern by using sed command)





SED (delete the records):



Use9:sed '3d' demo.txt (Here d means delete) (I t will delete 3rd record.But this line wont't be deleted in the file).

Use10:sed '$d' demo.txt (It will delete last record.But this line won't be deleted in the file).

Use11:sed '1d' demo.txt (It will delete first record.But this line won't be deleted in the file).

Use12:sed -i '5d' demo.txt ( i means for deleteing record permanently in the file) (It delete 5th record in the file).

Use13:sed -i '1,$d' demo.txt (It will delete 1st record to last record permanently).

Use14:sed -i'1d (After 1d we are using enter key)then we see like this :-> $d' demo.txt (then it will delete frist and last records)

use\*   :sed -i '/rajesh/d' NTR  (It delete all lines which consist of word Rajesh permanently)





SED (Replace the string):



Use15:sed 's/sai/unix/g' demo.txt (It will repalce all occurrences of sai with unix while displaying content.It wont modify file content).

g Means :-> global means every occurrences.

Use16:sed 's/sai/unix/' demo.txt (It will repalce only the first occurrences of sai with unix while displaying content.It wont modify file content).

Use17:sed 's/sai/unix/gi' demo.txt (i means :-> ignore the case sensitive for replacement)

Use18:sed -i 's/sai/unix/gi' demo.txt (-i means:->To replace the string permanently in the file)

Use19:sed -i 's/^$/unix/g' demo.txt ( It replace the every blank line with unix)

Use20:sed -i 's/\\<kumar\\>//g' demo.txt (It deletes only kumar word in the file). 

Use21:sed '10,50 s/kumar/linux/g' demo.txt (It replace the particular word in the range 10 to 50 lines).



use22: sed 's/tej/boss/2i' chiru  (IT will replace 2nd occurance of each line ,tej word  with boss word)



sed 's/ /,/g' chiru  (converted normal file into comma separated file i.e CSV file)



sed -e   '6 s/tej/boss/gi' -e '13 s/tej/boss/gi' chiru (replace in 2 specific lines)







How to print odd and even line:

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*



sed -n '1\~2 p' chiru (to print odd lines)

sed -n '0\~2 p' chiru   (to print even lines in a file)



How to remove empty line in a file:

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

sed -i '/^$/d' chiru





How to insert new record by using sed command:

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*



i  ---> insert before given line



a -----> insert after given line



c  -----> replace given line







sed '3i bruslee' chiru  (insert bruslee before 3rd line)



sed '11a lavakusha' chiru (insert new line after 11th line)



sed '2c apple' chiru  (replace entire 2nd line with some other record)







sed '/ntr/a nannaku prematho' chiru  (insert new record after  searching pattern)







sed '/ntr/i nannaku prematho' chiru  (insert new record before  searching pattern)

































