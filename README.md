# talos

https://github.com/siderolabs/talos/releases

https://github.com/siderolabs/talos/releases/download/v1.13.2/metal-amd64.iso

Install talosctl:
```bash
brew install siderolabs/tap/talosctl
```

---

Check connectivity to talos cluster:
```bash
talosctl -n 10.10.159.85 get disks --insecure
```
> We only need `--insecure` flag before we `apply-config` on our cluster.

Setup talos directory:
```
mkdir -p ~/.talos
cd ~/.talos
```

Generate talos config
```bash
talosctl gen config \
  portainer-cluster \
  https://10.10.159.85:6443
```

Rename talos config file:
```bash
mv ~/.talos/talosconfig ~/.talos/config
```

Update endpoint in talos config:
```bash
talosctl config endpoint 10.10.159.85
```

Update node in talos config:
```
talosctl config node 10.10.159.85
```

Apply talos config: 
```bash
talosctl apply-config \
  --insecure \
  --nodes 10.10.159.85 \
  --file ~/.talos/controlplane.yaml
```
> This will download container images and reboot the nodes

Bootstrap talos cluster:
```bash
talosctl bootstrap
```
> Wait 2-3 minues after this.

---

Download kubeconfig:
```
talosctl \
  kubeconfig ~/.talos/kubeconfig
```

Set kubeconfig:
```bash
export KUBECONFIG=~/.talos/kubeconfig
```

Test connection:
```
kubectl get po -A
```

