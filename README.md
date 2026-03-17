# 🚀 Project Setup Guide

This guide will help you quickly set up and run both the frontend and backend services.

---

## 📦 1. Clone the repository

After cloning the repository, run:

```bash
git submodule update --init --recursive
```

---

## ⚙️ 2. Configure Environment Variables

Copy the example environment file:

```bash
cp CourseLangChain/.env.example CourseLangChain/.env
```

Then edit `CourseLangChain/.env` and update the `MODEL` value if needed.

---

## 🤖 3. Start Ollama

Run the Ollama container:

```bash
docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama
```

Pull the model specified in your `.env`:

```bash
docker exec -i ollama ollama pull <MODEL>
```

> Replace `<MODEL>` with the value you set in `CourseLangChain/.env`.

---

## 🎨 4. Build Frontend

```bash
cd CourseLangChain-frontend
docker compose up --build
```

---

## 🧠 5. Build and Start Backend

Go back to the repository root:

```bash
cd ..
docker compose up -d --build
```

---

## 📜 6. View Logs

To monitor services:

```bash
docker compose logs -f
```

---

## ✅ You're Ready!

* Frontend and backend should now be running
* Ollama model is loaded and ready
* Logs are available for debugging

---

If you run into issues, double-check:

* Docker is running
* Ports are available
* `.env` configuration is correct
