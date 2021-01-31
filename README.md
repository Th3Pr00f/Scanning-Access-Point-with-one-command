# Scanning-Access-Point-with-one-command
Scanning-Access-Point-with-one-command (Linux)

sudo iwlist wlan0 scanning | egrep 'Cell |Encryption|Quality|Last beacon|ESSID'

It's the combination of sudo (run as root, do privileged operations), 
iwlist wlan0 scanning (produce some output on STDOUT), 
the pipe symbol "|" (connecting STDOUT of the command(s) to the left to the STDIN of the process on the right), 
and an egrep command with a "single quoted" (to prevent the shell from interpreting the "|" characters) Regular Expression to filter STDIN. 
See man bash, man sudo, man iwlist, man egrep, and man re_format for details.

if you got an error with " wlan0     Interface doesn't support scanning. ".

you can solve it with the following:

sudo ifconfig wlan0 down

sudo iwconfig wlan0 mode Managed

sudo ifconfig wlan0 up
