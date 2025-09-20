# ☸ k3s-cluster Installation (Server + Agents)

This guide sets up a lightweight Kubernetes cluster with **one k3s server (control plane)** and multiple **agent (worker) nodes**.

---

## 🔧 Requirements
- Linux hosts (Ubuntu Server is used in my homelab
- Basic networking between nodes
- `curl` installed
- At least:
  - Server: 2 vCPU, 4–6 GB RAM, SSD recommended (my k3s-master VM has 4GB RAM, 40GB SSD, and 2 vCPU)
  - Agent: 1 vCPU, 2 GB RAM

---

## ⏳ Install the k3s Server
Run on the **server node**:
```bash
curl -sfL https://get.k3s.io | sh -
```

```bash
sudo systemctl status k3s
```

<img width="640" height="68" alt="image" src="https://github.com/user-attachments/assets/4d8a9485-b538-4b3e-be59-dd8d0695a01a" />

```bash
sudo k3s kubectl get nodes
```

<img width="539" height="51" alt="image" src="https://github.com/user-attachments/assets/c463e68c-509f-463e-a20a-d70ff1fe71c0" />

---
## ☸️ k3s agent nodes *(Coming soon)*

---
## 🚧 Status

🟢 Actively maintained as part of my [`homelab`](https://github.com/raoulmoise/homelab) project.

---
