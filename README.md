##mesos_facts

Note, beta, still lots to do... :)

The example below assumes mesos is listening on the eth0 ip.
```bash
    - mesos_facts: ip={{ ansible_eth0.ipv4.address }}
    - debug: msg="{{ inventory_hostname }} with ip {{ ansible_eth0.ipv4.address }} is mesos master and has {{ mesos.activated_slaves }} active slaves"
      when: mesos.elected == True
    - debug: msg="Total cpus = {{ mesos.master_cpus_total }} and memory is {{ mesos.mem_total }}"
      when: mesos.elected == True
```
