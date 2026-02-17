Part 1: sed Operations
    
    $ echo “Task1” > results.txt
1. Display all lines from /etc/passwd that contain the word "bash"
        sed -n '/bash/p' /etc/passwd >> results.txt


    $ echo “Task2” >> results.txt
2. Display the entire /etc/passwd file except the 5th line.
        sed '5d' /etc/passwd >> results.txt

    
    $ echo “Task3” >> results.txt
3. In /etc/passwd, replace every word "bash" with "bourne-again" Do NOT modify the original file. Display the result to the terminal only.
        sed 's/bash/bourne-again/g' /etc/passwd >> results.txt


Part 2: awk Operations


    $ echo “Task4” >> results.txt
4. Print only the full name/comment field (usually field 5) of all users in the system from /etc/passwd.
        awk -F: '{print $5}' /etc/passwd >> results.txt


    $ echo “Task5” >> results.txt
5. Print the login (field 1), UID (field 3), and full name (field 5) of all users whose GID (field 4) is greater than 100.
        awk -F: '$4 > 100 {print $1, $3, $5}' /etc/passwd >> results.txt



    $ echo “Task6” >> results.txt
6. Print lines 10 through 20 from /etc/passwd Display line numbers alongside each line.
        awk 'NR>=10 && NR<=20 {print NR, $0}' /etc/passwd >> results.txt



    $ echo “Task7” >> results.txt
7. Calculate and display the sum of all GIDs (field 4) from the entire /etc/passwd file
        awk -F: '{sum += $4} END {print sum}' /etc/passwd >> results.txt


