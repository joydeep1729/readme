Steps to set up scale test of 1000 agents

1. Bring up an **AiAgent** in a server (this will help you access the server remotely)

2. SSH into the device, clone the Golang code ``aind.go`` (aind.go contains code to bring up **n** number of dockers with opkg agents inside them)

3. Get the executable using ``make`` command (~$ ``make``)

4. Run the executable to launch the requirerd number of dockers (see example)
            e.g: command to run to launch 50 dockers:  ~$ ``./ScaleSetup -n 50``

Do the following needful if refquired

1. Incease the **PID MAX value**
After the dockers start spawning, the CPU load average might increase very high.
There might be some limitations on how much resource the docker service can use. To make
maximum use of the resource, one should set the PID_MAX value
Plase visit the following link for details: 
https://www.cyberciti.biz/tips/howto-linux-increase-pid-limits.html

2. Increase the **ARP Cache**
Plase visit the following link for details: 
https://www.cyberciti.biz/faq/centos-redhat-debian-linux-neighbor-table-overflow/

3. To reduce the high CPU usage by kswapd, you should set vm.swappiness = 0
Plase visit the following link for details: 
https://askubuntu.com/questions/259739/kswapd0-is-taking-a-lot-of-cpu
