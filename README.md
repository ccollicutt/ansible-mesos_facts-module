##mesos_facts

Note, beta, still lots to do... :)

The example below assumes mesos is listening on the eth0 ip and is being run against several mesos masters. The debug messages will then print which one is the master.

Note that this module transforms some of the mesos variables returned in the stats.json from "master/elected" to "master_elected", ie. all slashes are replaced with underscores.

ip and port are not required and will default to ```127.0.0.1``` and ```5050``` respectively.

```bash
- mesos_facts: ip={{ ansible_eth0.ipv4.address }}
- debug: msg="{{ inventory_hostname }} with ip {{ ansible_eth0.ipv4.address }} is mesos master and has {{ mesos.activated_slaves }} active slaves"
  when: mesos.elected == True
```
