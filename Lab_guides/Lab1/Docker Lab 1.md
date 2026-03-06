Name: Adham Mamdouh El-Sherbini
# Question 1:

## Github Account:

![/Screenshots/Lab1/7.png]
## Running Nginx container:

![[Screenshots/Lab1/1.png]]
<div style="page-break-after: always;"></div>
## Running Apache container:
- Before we can pull this container image, we have to first create an account on [Docker Hub](https://hub.docker.com/explore) and then login to this registry: **dhi.io**
- Also unlike other container images which have a default tag (Latest) this one has a specific tag: **2-debian13-dev**

![[Screenshots/Lab1/8.png]]

![[Screenshots/Lab1/2.png]]

<div style="page-break-after: always;"></div>
## Checking cgroups and resource limits:

![[3_mod.png]]

![[Screenshots/Lab1/4.png]]
### **Notes:**

1. The `cpu.max` is calculated as follows:
   $$ cpu.max = \# \ of \ Cores\ \times \ quota $$
   $$ cpu.max = 1 \times 100000 = 100000 $$
   where: `quota` is how much CPU time a process group (i.e container) will use, this number is usually about 100000 microseconds.

2. The `memory.max` is **73400320 bytes** which is equivalent to 70 MB ($70 \times 1024 \times 1024 = 73400320$).

<div style="page-break-after: always;"></div>
# Question 2:

![[Screenshots/Lab1/6.png]]

![[Screenshots/Lab1/9.png]]
