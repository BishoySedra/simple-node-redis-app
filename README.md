# 🧠 Simple Node.js + Redis App

This is a simple Node.js application using Express and Redis to demonstrate basic key-value storage. The app is containerized using Docker and Docker Compose for easy setup and deployment.

---

## 🚀 Features

- ✅ Built with [Node.js](https://nodejs.org/) and [Express](https://expressjs.com/)
- ✅ Connects to [Redis](https://redis.io/) for in-memory data storage
- ✅ Simple REST API to set and get values from Redis
- ✅ Lightweight Docker setup using `node:alpine`
- ✅ Ready to run in development or test environments

---

## 📁 Project Structure

```
.
├── Dockerfile
├── docker-compose.yml
├── main.js
├── package.json
└── .dockerignore
```

---

## ⚙️ Prerequisites

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

---

## 🧑‍💻 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/BishoySedra/simple-node-redis-app.git
cd simple-node-redis-app
```

### 2. Build and run the app using Docker Compose

```bash
docker-compose up --build
```

This will:
- Build the Node.js app image
- Pull the latest Redis image
- Start both containers in a shared network

### 3. Access the app

Visit: [http://localhost:3000](http://localhost:3000)

---

## 📡 API Endpoints

### `GET /`
Returns a simple greeting message.

### `GET /set/:key/:value`
Stores a key-value pair in Redis.

**Example:**
```bash
curl http://localhost:3000/set/name/John
```

### `GET /get/:key`
Retrieves the value of a given key from Redis.

**Example:**
```bash
curl http://localhost:3000/get/name
```

---

## 🐳 Docker Details

### Dockerfile Highlights
- Based on `node:alpine` for a minimal image
- Sets working directory to `/app`
- Installs dependencies via `npm install`
- Starts app using `npm start`

### docker-compose.yml Highlights
- `app`: Node.js container built from local `Dockerfile`
- `redis`: Uses the official `redis:latest` image
- `restart: always`: Ensures app container restarts automatically if it crashes
- App accessible at port `3000` on `localhost`

---

## 📂 .dockerignore

Excludes unnecessary files from the Docker image:

```text
node_modules
npm-debug.log
Dockerfile
docker-compose.yml
.dockerignore
.git
.gitignore
.env
*.md
```

---

## 🛑 Stopping the App

```bash
docker-compose down
```

This stops and removes the containers, but retains the images.

---

## 🧪 Troubleshooting

- Make sure port `3000` is not being used by another process.
- If Redis isn't reachable, ensure the service name is correct (`redis`) and check `docker-compose logs`.

---

## ✨ Author

Developed by [Bishoy Sedra](https://github.com/BishoySedra)
