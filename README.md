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
talosctl gen config portainer-cluster https://10.10.171.76:6443
```

Update talos config file:
```bash
cp ~/.talos/talosconfig ~/.talos/config
```

```bash
yq -i '.cluster.allowSchedulingOnControlPlanes = true' ~/.talos/controlplane.yaml
```


Update endpoint in talso config:
```bash
talosctl config endpoint 10.10.171.76
```

node
```
talosctl config node 10.10.171.76
```

