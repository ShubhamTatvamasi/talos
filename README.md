# talos

Install talosctl:
```bash
brew install siderolabs/tap/talosctl
```

---

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

---

Check disk:
```bash
talosctl -n 10.10.171.76 get disks --insecure
```

```bash
talosctl apply-config \
  --insecure \
  --nodes 10.10.171.76 \
  --file ~/.talos/controlplane.yaml \
  --talosconfig ~/.talos/talosconfig
```

```bash
talosctl bootstrap \
  --nodes 10.10.171.76 \
  --endpoints 10.10.171.76 \
  --talosconfig ~/.talos/talosconfig
```

```
talosctl \
  --nodes 10.10.171.76 \
  --endpoints 10.10.171.76 \
  --talosconfig ~/.talos/talosconfig \
  kubeconfig ~/.talos/kubeconfig
```


```bash
export KUBECONFIG=~/.talos/kubeconfig
```


