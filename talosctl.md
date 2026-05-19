# talosctl

Check running services:
```bash
talosctl service
```

Check processes:
```bash
talosctl ps
```

list files:
```bash
talosctl ls /var/openebs/local
```

read file:
```bash
talosctl read /etc/os-release
```

Check talos dashboard:
```bash
talosctl dashboard
```

List machine config:
```bash
talosctl get machineconfig -o yaml
```

Patch machine:
```bash
talosctl patch machineconfig --patch @patch.yaml -n 10.10.159.85
```

Reboot node:
```bash
talosctl reboot -n 10.10.159.85
```

