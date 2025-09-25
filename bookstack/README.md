# 📚 BookStack Docker Deployment

BookStack is a free and open-source platform for organizing and managing documentation. This setup uses Docker Compose with a Traefik reverse proxy for production deployments.

---


##  Step-by-Step Setup

---

### ⚙️ 1. Prerequisites

Ensure these are installed on your machine (or server):

- Docker
- Docker Compose

---

### 🧾 2. Create and configure your `.env`

Copy the example file:

```bash
cp .env.example .env
````

Then **edit `.env`** to include real values:

---

### 🔐 3. Generate the `APP_KEY`

BookStack needs an app key. Generate it once using:

```bash
docker run -it --rm --entrypoint /bin/bash lscr.io/linuxserver/bookstack:latest appkey
```

Copy the output (`base64:...`) and paste into `.env` as `APP_KEY`.

---

### 📦 4. Setup Docker Volumes (skip if doing this for the first time)

Ensure the following folders exist:

```bash
mkdir -p config db
```

These persist your BookStack and database data.

---


### 🚀 6. Start BookStack

```bash
docker compose up -d
```

BookStack will be available at:

```
localhost:6875
```

---

### 🔐 7. First Login Credentials

Unless otherwise configured, default login is:

* **Email:** `admin@admin.com`
* **Password:** `password`
