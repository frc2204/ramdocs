# Networking
Networking refers to the communication between two or more computers and devices.
This document will cover the basics of networking, how it works, and it's applications in the world and FIRST.

## IP Addresses
An IP address is a unique set of numbers and dots that identifies each device connected to a network. It's like a home
address, but for computers, smartphones, or robots. For example, if I wanted to send a letter to my friend, I would need
to know their address. If I wanted to send a message to a computer, I would need to know its IP address.

### IPv4
IPv4 refers to the 4th version of the Internet Protocol. It is the most common version of IP addresses, and is the
version that is supported by FIRST. 

IP addresses are comprised of 4 sections (known as octets), with each section being a number from 0-255.

??? question "Why is the number range 0-255?"
    The number range is 0-255 because each section is 8 bits (or one byte), and 8 bits can represent 256 numbers (0-255).

If you do the calculations, you'll find that there are $2^{32}$ or $4,294,967,296$ possible IPv4 addresses.

Unfortunately, this is a problem because there are more than 4 billion devices connected to the internet. This means that there are
not enough IPv4 addresses for every device to have a unique address. How can we solve this problem? Well, we can use 
IPv6, or turn to the use of private IP addresses.

## Public vs. Private IP Addresses


### Network Classes

