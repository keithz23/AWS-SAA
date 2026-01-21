###Amazon Web Services - EC2
-EC2 is one of most popular services in AWS.
-EC2 = Elastic Compute Cloud = Infrastructure as a Service (IaaS).
It mainly consists in the capability of:
-Renting virtual machine (EC2).
-Storing data on virtual hard drives (EBS).
-Distributing traffic with Load Balancers (ELB).
-Scaling the number of virtual machines according to the demand (Auto Scaling Groups).
-Knowing EC2 is fundamental to understand how Cloud works.
#1. EC2 Sizing and Configuration options.
-Operating System (OS): Linux, Windows or MacOS.
-How much compute power & cores (CPU).
-How much random access memory (Ram).
-How much storage space:
--Networking optimized (EBS-optimized).
--Hardware (EC2 Instance Store).
-Network Card: speed of the card, Public IP address.
-Firewall: Security Groups.
-Bootstrap Script (configure at first launch): EC2 User Data.
#2. EC2 User Data
-It is possible to bootstrap an EC2 instance at launch with a script.
-The script is called EC2 User Data.
-bootstrapping = configuring the instance at first launch.
-That script is only executed at the first launch of the instance.
EC2 User Data can be used to:
-Update the OS.
-Install software packages.
-Downloading common file from the internet.
-Anything you can think of.
The EC2 User Data Script run with the root user.
