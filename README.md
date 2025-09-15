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
* [ ] PR opened

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

Checklist:

* [ ] New branch created
* [ ] File committed
* [ ] PR opened

---

## Task 02 — Linux Basics (pwd, ls, cd)

**Goal:** Practice basic Linux navigation.

Commands to run:

```bash
pwd
ls -l
mkdir practice && cd practice
touch file1 file2
ls -l
```

Commit your notes:

```bash
echo "Practiced pwd, ls, cd, mkdir, touch" > linux-notes.txt
git add linux-notes.txt
git commit -m "add linux basics notes"
git push -u origin task-02-linux-basics
```

Checklist:

* [ ] Practiced pwd, ls, mkdir, touch
* [ ] Notes committed
* [ ] PR opened

---

## Task 03 — File Maintenance & Permissions

**Goal:** Learn file creation, renaming, and permissions.

Commands to run:

```bash
mv file1 file1-renamed
cp file2 file2-copy
rm file2-copy
chmod 600 file1-renamed
ls -l
```

Commit your learnings:

```bash
echo "Practiced mv, cp, rm, chmod" >> linux-notes.txt
git add linux-notes.txt
git commit -m "update notes with file maintenance"
git push
```

Checklist:

* [ ] Practiced mv, cp, rm, chmod
* [ ] Notes updated

---

## Task 04 — Pipes & Redirection

**Goal:** Use >, >>, | and some useful commands.

Commands to run:

```bash
echo "hello world" > output.txt
echo "another line" >> output.txt
cat output.txt | grep hello
ls /etc | wc -l
```

Commit your learnings:

```bash
echo "Practiced redirection and pipes" >> linux-notes.txt
git add linux-notes.txt
git commit -m "add redirection and pipes notes"
git push
```

Checklist:

* [ ] Practiced >, >>, |, wc, grep

---

## Task 05 — Nginx Web Server

**Goal:** Install nginx and serve custom page.

Commands to run:

```bash
sudo apt update && sudo apt install -y nginx
sudo systemctl start nginx
curl http://localhost
```

Replace default index page:

```bash
echo "<h1>Hello from DevOps!</h1>" | sudo tee /var/www/html/index.html
sudo systemctl reload nginx
```

Commit a screenshot or note:

```bash
echo "Deployed custom nginx page" >> web-notes.txt
git add web-notes.txt
git commit -m "add nginx notes"
git push -u origin task-05-nginx
```

Checklist:

* [ ] Nginx installed
* [ ] Custom page displayed
* [ ] Notes committed

---

## Task 06 — SQLite Database

**Goal:** Create small database and query it.

Commands to run:

```bash
sudo apt install -y sqlite3
sqlite3 test.db "create table users(id int, name text);"
sqlite3 test.db "insert into users values(1,'Alice');"
sqlite3 test.db "select * from users;"
```

Commit your learnings:

```bash
echo "Practiced sqlite3 basic commands" >> db-notes.txt
git add db-notes.txt
git commit -m "add sqlite notes"
git push -u origin task-06-sqlite
```

Checklist:

* [ ] Table created
* [ ] Data inserted and selected
* [ ] Notes committed

---

## Task 07 — Bash Script & Cronjob

**Goal:** Create a script and schedule it.

Commands to run:

```bash
echo -e "#!/bin/bash\necho 'Hello, today is $(date)'" > hello.sh
chmod +x hello.sh
./hello.sh
crontab -e
# Add: * * * * * /path/to/hello.sh >> /tmp/hello.log 2>&1
```

Commit your learnings:

```bash
echo "Created hello.sh and scheduled cron" >> script-notes.txt
git add script-notes.txt
git commit -m "add bash script and cron notes"
git push -u origin task-07-bash-cron
```

Checklist:

* [ ] Script created and runs
* [ ] Cronjob tested
* [ ] Notes committed
