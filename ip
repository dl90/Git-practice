#!/bin/bash

ipconfig getpacket en0

echo "--------------------------------------------------------------------"
echo "Enter siaddr ip."
read ip

echo "--------------------------------------------------------------------"
echo "performing full port scan on $ip"
nmap -p- $ip

echo "--------------------------------------------------------------------"
echo "performing service scan on $ip"
nmap -sV --version-intensity 5 $ip