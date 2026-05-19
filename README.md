# talos

Install talosctl:
```bash
brew install siderolabs/tap/talosctl
```

Setup talso directory:
```
mkdir -p ~/.talos
cd ~/.talos
```

Get talos config
```bash
talosctl gen config portainer-cluster https://10.0.171.76:6443
```

Update talos config file:
```bash
cp ~/.talos/talosconfig ~/.talos/config
```

Update endpoint and node in talso config:
```bash
talosctl config endpoint 10.0.171.76
talosctl config node 10.0.171.76
```

