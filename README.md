
If you have an ansible group called `zookeeper_hosts`, you can simply use:

```
hosts: zookeeper_hosts
  sudo: yes
  roles:
    - role: sujaymansingh2.zookeeper
      zookeeper_servers: '{{ groups["zookeeper_hosts"] }}'
```

Make sure that each host has a `zookeeper_myid` attribute. I usually do this
by adding an attribute in the hosts file.

```
[zookeeper_hosts]
zookeeper-1.example.com zookeeper_myid=1
zookeeper-2.example.com zookeeper_myid=2
zookeeper-3.example.com zookeeper_myid=3
```
