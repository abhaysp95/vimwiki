# Some Networking tips and tools

* `ifconfig` shows your ethernet, wifi, localhost's informations, like ipv4, ipv6 addr, tx & rx packets etc.
* `tcpdump` for troubleshooting networks(maybe). Shows time, your ip, reciever's addr, packets(in `ascii`, `hex` etc. formats). Give port number, wifi name etc. to view anything specific like `ssh`
* `netstat` shows network statistics, ip-table, active network connections, state, local and foreign addr, ssh etc.

### /etc/hosts file

| ip to route to  | domain to route to | alias for it |
|-----------------|--------------------|--------------|
| aaa.bbb.ccc.ddd | example.com        | exp          |

So, basically it first goes to the ip mentioned in `/etc/hosts` and if it nothing is found there then it goes to router or external network.

### hostname

In order to change hostname, enter
```sh
sudo hostnamectl set-hostname name_of_host
```
Then edit `/etc/hosts` file and replace previous hostname with new one. Then type:
```sh
sudo service hostname restart
```
> This should work in every distro

* `traceroute` prints the route packets trace to network host. Trace the route to server whose domain you entered.
```sh
traceroute domain_name
```

* `nmap` Network exploration tool and security/port scanner
