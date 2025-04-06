---
layout: post
title: PG-Practice ClamAV Walkthrough
date: 2025-04-06
categories: Box
---
## Introduction
In this walkthrough we will be solving Proving Grounds Easy Linux Machine ClamAV. Let’s start ..

## Enumeration
First I run quick nmap scan to see which ports are open on the target host:
`nmap --open $IP`
<figure>
  <img src="image.png" alt="alt text">
  <figcaption>Nmap scan for identifying open ports</figcaption>
</figure>
Then I run UDP scan in case any valuable UDP ports are open:

`nmap -sU -F $IP`
<figure>
  <img src="image-4.png" alt="alt text">
  <figcaption>Nmap scan for identifying open ports</figcaption>
</figure>

We can run detailed Nmap scan in background while interacting with open services.
`nmap -sVC -vvv 192.168.245.42 --script vuln -p22,25,80,139,199,445`