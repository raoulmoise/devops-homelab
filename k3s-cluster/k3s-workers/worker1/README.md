# ☸️ k3s Worker Node – worker1

This node is part of the k3s cluster.  
It was joined to the master node using the **node token** from the server.

---
## Join Command Used

```bash
curl -sfL https://get.k3s.io | K3S_URL=https://myserver:6443 K3S_TOKEN=mynodetoken sh -
```
K3S_TOKEN = created on the master node, using the following command

K3S_URL = https://192.168.1.102:6443 - used in my homelab

```bash
sudo k3s token create
```
---

## 🚧 Status

🟢 Actively maintained as part of my [`homelab`](https://github.com/raoulmoise/homelab) project.
