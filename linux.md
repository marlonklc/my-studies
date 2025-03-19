## commom commands
##### show service status: `systemctl status <servicename>`
##### find any file wich contains a text: `find ./* -type f -exec grep -l <textToFind> {} \;`

#### fix problem with 'unexpeted end of file' or '$'\r': command not found' (problem edit linux files using windows via terminal) 
`sed -i 's/\r$//' filename`



### tools for monitoring memory/cpu usage
based on: https://signoz.io/guides/graphing-a-process-memory-usage/

`ps aux | grep <process-name>` very commom tool to list all process running, detailing ID, memory and cpu usage. It simple, but help !

`top` or `htop` essential tools for real-time monitoring, 


`sar` (system activity reporter) powerful tool used to collect and report, but not familiry for beginners.


## firewall

ufw (Uncomplicated Firewall) its a default tool linux's firewall, but there are many others alternatives like iptables, firewalld.

`sudo ufw status`

allow just specific ip and port
`sudo ufw allow from <ip> to any port 5432`
`sudo ufw deny 5432`

block all connections
`
sudo ufw default deny incoming
sudo ufw default allow outgoing
`


## java alternatives (manage java versions)
to manage the java versions need install java alternatives
`sudo apt install -y java-common`
to list all java installed
`update-java-alternatives --list`
install java
``
set current java version
`sudo update-java-alternatives --set <name>`

## sdkman (manage java versions)
to manage the java versions need install sdkman
`apt install zip` (if not installed)
`curl -s "https://get.sdkman.io" | bash`
`source "$HOME/.sdkman/bin/sdkman-init.sh"`

list all java versions available
`sdk list java`
install java version
`sdk install <name>`
switch by versions
`sdk use java 17.0.7-jbr`
after all, check current java version
`java -version`


### swap
show swap space availables
`sudo swapon --show`

free utility that show memory usage and cache memory, also swap usage
`free -h`

check free disk space
`df -h

define size of swap
`sudo fallocate -l 4G /swapfile`

show created swap file
`ls -lh /swapfile`

enable permission to swap file
`sudo chmod 600 /swapfile`

mark the file as swap space
`sudo mkswap /swapfile`

finally, enable swap space
`sudo swapon /swapfile`

Our recent changes have enabled the swap file for the current session. However, if we reboot, the server will not retain the swap settings automatically. We can change this by adding the swap file to our /etc/fstab file.

Back up the /etc/fstab file in case anything goes wrong
`sudo cp /etc/fstab /etc/fstab.bak`

Add the swap file information to the end of your /etc/fstab file by typing:
`echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab`

#### tunning swapiness
change priority of swap usage, from 0 being more priority, to 100 to less priority
`sudo sysctl vm.swappiness=<1-100>`