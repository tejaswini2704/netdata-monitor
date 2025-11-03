# 🧠 TASK 7: Monitor System Resources Using Netdata

## 🎯 Objective
Install and run **Netdata** to visualize real-time system and application performance metrics such as CPU, memory, disk I/O, and Docker container statistics.

---

## 🧰 Tools Used
- **Netdata (Open-Source Monitoring Tool)**
- **Docker**
- **GitHub Codespaces**

---

## 🚀 Steps to Set Up

### **1️⃣ Pull the Netdata Docker Image**
```bash
docker pull netdata/netdata
````

---

### **2️⃣ Run Netdata Container**

```bash
docker run -d \
  --name=netdata \
  -p 19999:19999 \
  --cap-add SYS_PTRACE \
  --security-opt apparmor=unconfined \
  netdata/netdata
```

> This starts Netdata in the background and exposes it on port `19999`.

---

### **3️⃣ Verify the Container**

```bash
docker ps
```
---

### **4️⃣ Forward Port in GitHub Codespaces**

1. Go to the **Ports** tab (bottom panel in Codespaces).
2. Find port `19999`.
3. Click on the **globe icon 🌐** → choose **Make Public**.
4. Open the generated URL — e.g.

   ```
   https://<your-codespace-id>-19999.app.github.dev/
   ```
5. The **Netdata Dashboard** will open in your browser 🎉.

---

### **5️⃣ Explore Metrics**

From the left panel in Netdata:

* **System Overview** → CPU, RAM, Disk usage
* **Applications** → Resource usage by processes
* **Containers** → Docker container performance
* **Network** → Bandwidth and packet stats

---

### **6️⃣ Check Logs (Optional)**

```bash
docker exec -it netdata bash
cd /var/log/netdata
ls
```

You’ll find logs like `access.log` and `error.log`.

---

### **7️⃣ Stop or Remove Container (Optional)**

```bash
docker stop netdata
docker rm netdata
```

---

## 📸 Screenshot

<img width="1912" height="861" alt="Screenshot 2025-11-03 224719" src="https://github.com/user-attachments/assets/4a0f0f6b-3e13-4f40-90c7-1f461f00e7cf" />
<img width="1909" height="812" alt="Screenshot 2025-11-03 224809" src="https://github.com/user-attachments/assets/3b5246aa-2f64-4c72-bf35-84a9e8c91cdb" />
<img width="1890" height="821" alt="Screenshot 2025-11-03 224824" src="https://github.com/user-attachments/assets/6603a9fb-6b28-4454-b5b4-756b9d4caec9" />
<img width="1411" height="544" alt="Screenshot 2025-11-03 224902" src="https://github.com/user-attachments/assets/e5de4871-add4-4476-b7ff-040b77638238" />


---

## 🎓 Outcome

By completing this task, you:

* Learned to use **Netdata** for real-time server monitoring.
* Understood how to monitor **CPU, memory, disk, and Docker containers** visually.
* Gained experience in **exposing and accessing web apps inside GitHub Codespaces**.

---

