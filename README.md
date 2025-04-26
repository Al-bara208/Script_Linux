#!/bin/bash

echo "Username"
echo
whoami

echo

echo "System Name"
echo
lsb_release -a

echo

echo "Today's Date"
echo
date

echo

echo "Files"
echo
ls

echo

echo "Healer"
echo
lscpu

echo

echo "Ram"
echo
free -m

echo

echo "Disk"
echo
fdisk -l

echo

echo "Peripherals"
echo
lspci

echo

echo "USB connected devices"

lsusb

echo

echo "Scanning networked devices"
echo
echo "Enter IP address"
read target

nmap "$target"

echo

echo "Check the connection"
echo
ping -c 4 127.0.0.1

echo

echo "Devices connected to your network"
echo
echo "Enter IP address"
read target

nmap -sn "$target"

echo

echo "The open ports"
echo
echo "Enter IP address"
read target

nmap -Pn "$target"

echo

echo "Firewall lnspection"
echo
read target

nmap -pn -p- "$target"

echo

echo "ssh case"
echo
read target

nmap -p 22 -sV "$target"

echo

echo "User list"
echo
w

echo

echo "Package analysis"
echo
ss

echo

echo "User history"
echo
ps aux

echo

echo "System update"
echo
sudo apt update && sudo apt upgrade -y
