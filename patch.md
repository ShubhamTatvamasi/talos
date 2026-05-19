# Patch

List machine config:
```bash
talosctl get machineconfig
```
> `-o yaml` for details

Patch machine:
```bash
talosctl patch machineconfig --patch @patch.yaml -n 10.10.159.85
```

Reboot node:
```bash
talosctl reboot -n 10.10.159.85
```

