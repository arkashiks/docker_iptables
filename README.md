# docker_iptables
static iptables example for docker (with {"iptables": false} option)

Example of iptables rules, which will allow docker images to work without docker daemon messing around with iptables. May be suitable for those who needs to reload iptables rules while docker daemon is active. Reloading rules will flush docker added lines and will require docker daemon restart. To address that, static iptables config with docker rules created.

To use this, you need to add following option in /etc/docker/daemon.json:

```
{"iptables": false}
```

Option above will tell docker not to manipulate iptables anyhow.

Rules set contains NAT options, so docker containers can access internet.
