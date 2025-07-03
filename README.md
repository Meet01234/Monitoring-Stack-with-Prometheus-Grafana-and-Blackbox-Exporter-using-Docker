
# 🚀 Monitoring Stack with Prometheus, Grafana, and Blackbox Exporter using Docker

![Screenshot](Monitoring.png)

This project sets up a complete monitoring stack using Docker: Prometheus for metrics, Grafana for visualization, and Blackbox Exporter for endpoint probing.

---

## 📦 Final Project Structure

```
monitor/
├── docker-compose.yml
├── prometheus.yml
├── blackbox.yml
├── blackbox_exporter-0.18.0.linux-amd64/
└── output.log
```

---

---

## ✅ Step 1: Update & Install Required Packages
```bash
apt update -y
sudo apt install net-tools -y           # For netstat
apt install docker.io -y                # Install Docker
apt install docker-compose -y           # Install Docker Compose
```

## ✅ Step 2: Clone the Monitoring Project from GitHub
```bash
git clone <YOUR_REPO>
cd <YOUR_REPO>
```

## ✅ Step 3: (Optional) Run Blackbox Exporter Manually (not needed if using Docker)
```bash
chmod +x -R blackbox_exporter-0.18.0.linux-amd64/
cd blackbox_exporter-0.18.0.linux-amd64/
./blackbox_exporter --config.file=blackbox.yml &> output.log &
```

## ✅ Step 4: Check Port Usage (optional debugging)
```bash
sudo netstat -tunlp
```

## ✅ Step 5: Edit Prometheus Configuration
```bash
cd /home/ubuntu/monitor/
nano prometheus.yml
# 🔧 Update with your EC2 instance IP
```

## ✅ Step 6: Launch Monitoring Stack via Docker Compose
```bash
docker-compose up -d
```
🔄 This will bring up Prometheus, Grafana, and Blackbox Exporter as Docker containers.

---
## ✅ Step 7: Access the Tools

| Service     | URL                        |
|-------------|----------------------------|
| Blackbox    | http://<Your_EC2_IP>:9115  |

![Output Screenshot](Black.png)

---

---

| Grafana     | http://<Your_EC2_IP>:3000  |
🛡 **Grafana Login:** `admin / admin`

![Output Screenshot](Grafana.png)

---

---

| Prometheus  | http://<Your_EC2_IP>:9090  |

![Output Screenshot](Prom.png)

---

---
# Final Output

![Output Screenshot](Final.png)

![Output Screenshot](Ou.png)

---
