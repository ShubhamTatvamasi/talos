# talos

Install talosctl:
```bash
brew install siderolabs/tap/talosctl
```

```
mkdir -p ~/.talos
cd ~/.talos
```

```bash
talosctl gen config portainer-cluster https://10.0.171.76:6443
```

Update talos config file:
```bash
cp ~/.talos/talosconfig ~/.talos/config
```

```bash
talosctl config endpoint 10.0.171.76
```

