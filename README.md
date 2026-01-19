# lab3
Below is a **clean, exact, step-by-step guide to run Program-3**
❌ No optional steps
❌ No extra theory
✅ Exactly as per your lab manual images

---

# ✅ Program-3

## Code a Dockerized Python Flask Application

---

## 🔹 Step 0: Prerequisite

Make sure Docker is installed and running.

Check:

```bash
docker --version
```

---

## 📁 Step 1: Create Project Directory

```bash
mkdir Program-3
cd Program-3
```

---

## 📄 Step 2: Create `Dockerfile`

```bash
nano Dockerfile
```

**Paste EXACT content:**

```dockerfile
# Use official Python image
FROM python:latest

# Set working directory
WORKDIR /app

# Copy requirement file and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY . .

# Expose port 5000
EXPOSE 5000

# Run the app
CMD ["python", "app.py"]
```

Save → **CTRL + X → Y → Enter**

---

## 🐍 Step 3: Create `app.py`

```bash
nano app.py
```

**Paste:**

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Hello from Simple Flask Docker!"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```

Save and exit.

---

## 📦 Step 4: Create `requirements.txt`

```bash
nano requirements.txt
```

**Paste:**

```
Flask==2.3.3
```

Save and exit.

---

## 🏗️ Step 5: Build Docker Image

```bash
docker build -t program-3 .
```

Verify:

```bash
docker images
```

---

## ▶️ Step 6: Run Docker Container

```bash
docker run -p 5000:5000 program-3
```

---

## 🌐 Step 7: Test in Browser

Open browser and visit:

```
http://localhost:5000
```

✅ Output:

```
Hello from Simple Flask Docker!
```

---

## 📁 Final Project Structure

```
Program-3/
│
├── Dockerfile
├── app.py
└── requirements.txt
```

---

