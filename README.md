A simple bash script to automate an ovpn connection

HOW TO ADD: 

1. touch file_name.sh [ create file ]
2. fill the script with your desired choices
3. nano file_name.sh [ edit file ]
4. ctrl + shift + v the copied FILLED script -> ctrl + x -> Y -> Enter [ copy paste and save the changes ]
5. crontab -e [ 
6. Add "<options> <path> -> ctrl + x    
[  [ @reboot to run everytime you boot or use this site https://crontab-generator.org/ ]
REBOOT
7. ifconfig [ check if the vpn is working ]
8. systemctl status cron [ check if the cron service has run successfully ]

IF there's the message "pam_unix(sudo:auth): conversation failed" DO THIS:
nano /etc/pam.d/sudo [and add to the file] "add:.auth       sufficient   pam_permit.so"
REBOOT

