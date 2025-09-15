# devops-hands-on — Hands‑On Guide

---

## How to work on tasks

1. For each task: create a branch named `task-XX-shortname` (e.g. `task-01-git`).
2. Do the work, commit, push.
3. Open a PR with short notes (copy the checklist for that task).
4. Tag me for review.

---

## Task 00 — Setup

**Goal:** Get repo cloned and open first PR.

```bash
git clone <repo-url> devops-hands-on
cd devops-hands-on
git checkout -b task-00-setup
echo "My name is <your name> and I am starting DevOps hands-on" > intro.txt
git add intro.txt
git commit -m "add intro file"
git push -u origin task-00-setup
```

Checklist:

* [ ] Repo cloned
* [ ] Intro file added

---

## Task 01 — Git Basics

**Goal:** Learn branching and merging.

```bash
git checkout -b task-01-git
echo "Learning git branches" > git-notes.txt
git add git-notes.txt
git commit -m "add git notes"
git push -u origin task-01-git
```

Open PR → Mentor will merge after review.

---

## Task 02 — Add Simple Code & Test

**Goal:** Create a small Python script and run it.

```bash
echo "print('hello world')" > app.py
python3 app.py
```

Commit and push app.py to a new branch.

Checklist:

* [ ] Script runs locally and prints hello world

---

## Task 03 — GitHub Actions CI

**Goal:** Run the script in CI.

```bash
mkdir -p .github/workflows
cat > .github/workflows/ci.yml <<'YAML'
name: CI
on: [push, pull_request]
jobs:
  run:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Run app
        run: python3 app.py
YAML

git add .github/workflows/ci.yml
git commit -m "add CI workflow"
git push -u origin task-03-ci
```

Checklist:

* [ ] Workflow runs and shows output in Actions tab

---

## Task 04 — Docker Basics

**Goal:** Run the app in a container.

```bash
cat > Dockerfile <<'DOCK'
FROM python:3.11-slim
COPY app.py .
CMD ["python", "app.py"]
DOCK

docker build -t devops-app:0.1 .
docker run --rm devops-app:0.1
```

Checklist:

* [ ] Image builds successfully
* [ ] Container prints hello world

---

## Task 05 — Monitoring (Quick)

**Goal:** Run Prometheus + Grafana quickly.

```bash
mkdir monitoring
cd monitoring
cat > docker-compose.yml <<'YAML'
version: '3'
services:
  prometheus:
    image: prom/prometheus
    ports:
      - "9090:9090"
  grafana:
    image: grafana/grafana
    ports:
      - "3000:3000"
YAML

docker compose up -d
```

Visit Grafana at [http://localhost:3000](http://localhost:3000).

---

## Task 06 — Deploy to Cloud or VM (Optional)

If you have access, run the Docker image on a small EC2 instance or any VM.

---

# Mentor Quick Cheatsheet

**Git:** `git status`, `git checkout -b branch`, `git add .`, `git commit -m "msg"`, `git push`

**Docker:** `docker build -t name .`, `docker run --rm name`

**CI:** Check Actions tab → rerun jobs if needed.

**Monitoring:** `docker compose up -d`, visit Grafana at :3000.

Keep review light — just check that tasks run and output looks good.
