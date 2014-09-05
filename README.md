##mesos_facts

Note, beta, still lots to do... :)

The example below assumes mesos is listening on the eth0 ip and is being run against several mesos masters. The debug messages will then print which one is the master.

```bash
- mesos_facts: ip={{ ansible_eth0.ipv4.address }}
- debug: msg="{{ inventory_hostname }} with ip {{ ansible_eth0.ipv4.address }} is mesos master and has {{ mesos.activated_slaves }} active slaves"
  when: mesos.elected == True
```
