# Ubuntu

## Install software 
```
$ sudo apt-get install <name>
```

## Remove/Uninstall software 
```
$ sudo apt-get remove <name>
```

## Restart computer 
```
$ sudo reboot
```

## Display Disk Space Information in Human Readable Format
```
$ df -h
```

## See network information
```
$ ifconfig
```

## See system usage data
```
$ top
```

## Check CPU core count
```
$ cat /proc/cpuinfo | grep processor | wc -l
```

## Check which ports are in Use
```
$ netstat -nap | grep <port>
```

## Kill process on specific port
```
$ fuser -k -n tcp <port>
```

## Delete multiple files
```
$ rm <filename1> <filename2> <filename3>
```

## Delete a file and prompt before every removal
```
$ rm -i <filename1>
```
_Pass the -v option as follows to get verbose output_
```
$ rm -v <filename1>
```

## Delete all files in folder or directory
```
$ rm -rf /path/to/dir/
```

## Copy a file to directory
```
$ cp <filename1> /path/to/dir/
```

## Copy multiple files to directory
```
$ cp <filename1> <filename2> /path/to/dir/
```
_Pass the -v option as follows to get verbose output_
```
$ cp -v <filename1> <filename2> /path/to/dir/
```

## Rename a file
```
$ mv <filename> <new_filename>
```

## Move a file to a new location
```
$ mv <filename> /path/to/dir/
```


## How To Configure IP Address In Ubuntu 18.04
```
$ cd /etc/netplan/
$ sudo vi 01-netcfg.yaml
```

_Set DHCP to dhcp4: no._

_Specify the static IP address 192.168.121.199/24. Under addresses: you can add one or more IPv4 or IPv6 IP addresses that will be assigned to the network interface._

_Specify the gateway gateway4: 192.168.121.1_

_Under nameservers, set the IP addresses of the nameservers addresses: [8.8.8.8, 1.1.1.1]_


```
network:
  version: 2
  renderer: networkd
  ethernets:
    ens3:
      dhcp4: no
      addresses:
        - 192.168.121.199/24
      gateway4: 192.168.121.1
      nameservers:
          addresses: [8.8.8.8, 1.1.1.1]
```

When editing Yaml files, make sure you follow the YAML code indent standards. If there are syntax errors in the configuration, the changes will not ne applied.

Once done save and close the file and apply the changes with:
```
$ sudo netplan apply
```

Verify the changes by typing:
```
$ ip addr show dev ens3
```

That’s it! You have assigned a static IP to your Ubuntu server.

## How to Install Node
```
$ curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash 
$ sudo apt-get install -y nodejs
```


## How to Install Yarn
```
$ curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
$ echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
$ sudo apt update
$ sudo apt install yarn
```