# Kali-Linux-virtual-machine-
This was my first Kali Linux VM and my first time setting up a network by hand. I wanted a safe place to practise on without touching my main computer, and I wanted to actually understand how the networking works instead of leaving everything on automatic.
# My First Kali Linux Virtual Machine

This was my first Kali Linux VM and my first time setting up a network by hand. I wanted a safe place to practise on without touching my main computer, and I wanted to actually understand how the networking works instead of leaving everything on automatic.

## Skills I practised

Basic network configuration, troubleshooting, virtual networking in VirtualBox, and confirming connectivity.

## What I did

I downloaded Kali Linux and imported it into VirtualBox. Then I changed the network adapter from NAT to NAT Network. After that I set up the connection manually inside Kali. I typed in my own IP address, subnet mask and gateway in the network connection settings.

## How I tested it

I opened a terminal and ran two commands:

    ping -c 3 8.8.8.8
    ping -c 3 google.com

The first one checks that the VM can reach the internet using a plain IP address. The second checks that DNS works as well, because the VM has to turn the name google.com into an IP address before it can get a reply. Running both is useful when something goes wrong. If the IP address works but the name doesn't, the problem is probably DNS and not the connection itself.

Once the pings worked I opened Firefox in the VM and searched Google myself, and that worked too.

## What I got out of it

The best part was the hands on practice. Because I typed in the IP address, subnet mask and gateway myself, I had to learn what each one does and why a wrong value breaks the connection. I also learned the difference between NAT and NAT Network. NAT Network is the better choice if I want several VMs to talk to each other later. I also got a bit more confident with basic troubleshooting, using ping to work out if a problem is the connection or the name lookup.

## What this lab didn't cover

I only used one VM, so I couldn't test how machines on the same network talk to each other. I proved the VM could get to the internet, but not that it could reach another device on its own network.

## What I want to try next

I want to add a second VM to the same NAT Network and point it at the same default gateway. One VM would keep a manual IP address and the other would get its address from DHCP. Then I'd test if they can still reach each other even though they were set up differently.

I'd also need to pick my manual IP address outside the range the DHCP server hands out. If both machines ended up with the same address I'd get an IP conflict, and figuring out why would be a good troubleshooting exercise on its own.

## Recommendations for anyone trying this

Write down your IP address, subnet mask and gateway before you change anything, so you can go back if the connection breaks. Test with the IP address first and the domain name second, so you know straight away if the problem is DNS. Restart the network connection after you save your changes, because sometimes the old settings stick around until you do.
