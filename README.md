Automating OpenVPN Connection with a Bash Script

This guide explains how to automate an OpenVPN connection using a simple bash script and schedule it to run on boot using cron.
Steps to Set Up:

1. Create a New Bash Script:

        touch file_name.sh

2. Download and fill the txt your options.
3. Open the file in the nano text editor.:

        nano file_name.sh
   Paste the filled script using Ctrl + Shift + V.
   Save and exit (Ctrl + X, Y, Enter).

    

4. Make the Script Executable:

        chmod +x file_name.sh



5. Schedule the Script with Cron:
   Open the crontab editor:

        crontab -e

   Add the following line to schedule the script at reboot:


        @reboot /path/to/your/file_name.sh

    

    Save and exit (Ctrl + X, Y, Enter).
   
    @reboot to start at boot 

    Note: You can use Crontab Generator [ https://crontab-generator.org/ ] to generate more complex scheduling options.

Reboot Your System:

    sudo reboot


Post-Reboot Checks:

  1. Verify VPN Connection: After rebooting, check if the VPN is connected:

         ifconfig

   Look for the VPN interface in the output (e.g., tun0).

  2. Verify Cron Status: Check if the cron service executed the script successfully:
     
    systemctl status cron

Troubleshooting:

  If you encounter this error: pam_unix(sudo:auth): conversation failed,
  edit the PAM (Pluggable Authentication Module) configuration for sudo:


    sudo nano /etc/pam.d/sudo

Add the following line to the file:

        auth       sufficient   pam_permit.so

  Save and exit (Ctrl + X, Y, Enter).

  Reboot Again: After making changes to PAM, reboot your system:

      sudo reboot


