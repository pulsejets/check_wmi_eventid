Check_wmi_eventid is a script to check windows event log , for a certian eventid..
Simple example : check application log , for eventtype error(-t) and eventid 9003(-e) with in the last 60 mins(-m60), 
set warning (-w) if greater than 1 ,and set error(-c) if greater than 3 

check_wmi_eventid -H 172.10.10.10 -u domain/user -p password -l application -e 9003 -w 1 -c 3 -t1 -m60 

example : same as above , but with arguments -O -W -C, these are custom plugin output for OK,Warning and Critical 
Marco $MARCOLIST , can be used!! 


check_wmi_eventid -H 172.10.10.10 -u domain/user -p password -l application -e 9003 -w 1 -c 3 -t1 -m60 -O "Every thing is OK" 
-W "Warning : something is not right" -C "It is totaly bad , found ITEMCOUNT events" 

Version 1.1 

Added an ekstra argument - s, that gives you the option to match for a string in the given eventid 

Version 1.2 

Bug fix - when using -C custom critical text 


Version 1.3 

added to the -t, -e, -s, -S and -l argument , so that you can select multipel arguments. 


Version 1.4 

Bug fix .. error in script when -c or -w wasn't set 


Version 1.5 by rojobull

Bug fix - getops line Was missing a colon after the S optin which would ignor the source name provided.

Bug fix - adjust WQL_Constructor function so that spaces are not used as a delimiter.

Improvement. Changed the date option to convert time into UTC instead of specifying an offset

Added option to use a credentials file instead of passing
