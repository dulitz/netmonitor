# netmonitor

Netmonitor is (what I assume is yet another) Prometheus network connectivity monitor. 

Prometheus itself, the blackbox_exporter, and snmp_exporter are all good
network monitoring tools. But they are not good for measuring packet loss rates
because they don't issue enough requests.

Also no Prometheus monitors seem to export the length of time before a TLS
certificate expires.

* Config

```
mysp:
  probe: icmp
  rate: [[10.100.0.0/16, 0.25], [235.84.203.0/24, 0.5]]
    - 10.100.9.1
    - 10.100.9.65
    - 235.84.203.225
```

The default ICMP echo-request rate is one packet per second.

