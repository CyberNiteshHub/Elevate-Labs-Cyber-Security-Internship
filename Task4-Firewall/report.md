# Task 4: Firewall Configuration using UFW

## Objective
To configure and test firewall rules to allow or block network traffic.

## Tool Used
UFW (Uncomplicated Firewall) on Kali Linux

## Steps Performed

1. Installed UFW firewall
2. Enabled firewall service
3. Checked current firewall rules
4. Blocked port 23 (Telnet)
5. Tested blocked port using telnet command
6. Allowed SSH (port 22)
7. Removed test rule

## Commands Used

sudo apt install ufw -y
sudo ufw enable
sudo ufw status
sudo ufw deny 23
telnet localhost 23
sudo ufw allow 22
sudo ufw delete deny 23

## Results

- Port 23 successfully blocked
- Telnet connection failed (rule working)
- SSH port 22 allowed successfully

## Conclusion

Firewall rules were successfully configured using UFW to control network traffic and improve system security.
