# ☸ k3s-cluster Installation (Server + Agents)

This guide sets up a lightweight Kubernetes cluster with **one k3s server (control plane)** and multiple **agent (worker) nodes**.

---

## 🔧 Requirements
- Linux hosts (Ubuntu Server is used in my homelab
- Basic networking between nodes
- `curl` installed
- At least:
  - Server: 2 vCPU, 4–6 GB RAM, SSD recommended (my k3s-master VM has 4GB RAM, 40GB SSD, and 2 vCPU)
    <img width="671" height="228" alt="image" src="https://github.com/user-attachments/assets/3dc6cd2b-685a-4144-bf49-47c93252c597" />

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
## 🔑 Create token

```bash
sudo k3s token create
```
---
## ☸️ k3s agent nodes 
[k3s-worker1](https://github.com/raoulmoise/homelab/blob/main/k3s-cluster/k3s-workers/worker1/README.md)

---
## 🚧 Status
<img width="1308" height="63" alt="image" src="https://github.com/user-attachments/assets/f861a86e-8b19-4d83-96a9-9069f5754913" />


🟢 Actively maintained as part of my [`homelab`](https://github.com/raoulmoise/homelab) project.

---
