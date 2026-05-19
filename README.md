# talos

Install talosctl:
```bash
brew install siderolabs/tap/talosctl
```

---

Check disk:
```bash
talosctl -n 10.10.159.85 get disks --insecure
```

Setup talso directory:
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

Update endpoint in talso config:
```bash
talosctl config endpoint 10.10.159.85
```

Update node in talso config:
```
talosctl config node 10.10.159.85
```

Apply Talso config: 
```bash
talosctl apply-config \
  --insecure \
  --nodes 10.10.159.85 \
  --file ~/.talos/controlplane.yaml
```

Bootstrap Talso cluster:
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

