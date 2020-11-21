## Enabling X11 Forwarding over SSH with SSHD

1. Edit the config file, `/etc/ssh/sshd_config`, ensuring that the following options are set.
```config
X11Forwarding yes
X11DisplayOffset 10
```
2. Restart the sshd server.
```bash
sudo systemctl restart sshd
```