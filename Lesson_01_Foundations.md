# Fedora Cybersecurity Foundation Lab

## Lesson 1: Setting Up a Professional Cybersecurity Workspace

### Instructor: SibilaDevOps

---

# Lesson Overview

This lesson introduces learners to the foundational skills required for cybersecurity and Linux administration. Students will learn how to organize a cybersecurity lab, navigate the Linux terminal, use Git for version control, and connect a local project to GitHub using secure SSH authentication.

---

# Learning Objectives

By the end of this lesson, learners should be able to:

1. Understand the purpose of a cybersecurity lab.
2. Navigate directories using Linux commands.
3. Create and organize project folders.
4. Initialize a Git repository.
5. Connect a local repository to GitHub.
6. Configure SSH authentication.
7. Push local projects to GitHub securely.
8. Document their learning journey professionally.

---

# Why We Need a Cybersecurity Lab

A cybersecurity professional must have a dedicated environment for:

* Learning Linux
* Writing scripts
* Storing reports
* Collecting evidence
* Managing projects

Instead of scattering files around the computer, we create a structured workspace called a CyberLab.

---

# Creating the CyberLab Structure

Open Terminal and create a project folder:

```bash
mkdir CyberLab
cd CyberLab
```

Verify location:

```bash
pwd
```

Expected output:

```text
/home/username/CyberLab
```

---

# Organizing the Lab

Create folders for different purposes:

```bash
mkdir Reports Scripts Logs Evidence
```

View the structure:

```bash
ls
```

Expected output:

```text
Evidence
Logs
Reports
Scripts
```

---

# Understanding Each Folder

## Reports

Stores written reports and investigations.

Examples:

* Incident Reports
* Lab Reflections
* Research Findings

## Scripts

Stores Bash and Python scripts.

Examples:

* Network Scanners
* Automation Tools
* Log Analysis Scripts

## Logs

Stores output generated from commands and investigations.

Examples:

* Scan Results
* Server Logs
* Firewall Logs

## Evidence

Stores screenshots and proof of completed work.

Examples:

* Terminal Screenshots
* Network Diagrams
* Configuration Evidence

---

# Introduction to Git

Git is a version control system.

Think of Git as a time machine for your projects.

It helps us:

* Track changes
* Restore older versions
* Collaborate with others
* Build professional portfolios

---

# Initializing a Git Repository

Inside CyberLab:

```bash
git init
```

Expected output:

```text
Initialized empty Git repository
```

This creates a hidden folder called:

```text
.git
```

which Git uses to track changes.

---

# Checking Repository Status

Run:

```bash
git status
```

This command shows:

* Modified files
* New files
* Staged files
* Commit status

---

# Understanding GitHub

GitHub is an online platform that stores Git repositories.

Benefits:

* Cloud backup
* Portfolio development
* Collaboration
* Version history

---

# The Authentication Problem

GitHub no longer allows password authentication for Git operations.

Many beginners encounter:

```text
Authentication failed
Password authentication is not supported
```

This is normal.

The modern solution is SSH authentication.

---

# Understanding SSH

SSH stands for Secure Shell.

SSH uses cryptographic keys.

Two keys are created:

## Private Key

```text
id_ed25519
```

Never share this file.

## Public Key

```text
id_ed25519.pub
```

This can be shared with GitHub.

---

# Verifying SSH Authentication

Test connection:

```bash
ssh -T git@github.com
```

Successful output:

```text
Hi username!
You've successfully authenticated.
```

This confirms GitHub trusts your computer.

---

# Connecting GitHub Repository

Check current remote:

```bash
git remote -v
```

Remove incorrect HTTPS remote:

```bash
git remote remove origin
```

Add SSH remote:

```bash
git remote add origin git@github.com:username/repository.git
```

Verify:

```bash
git remote -v
```

Expected:

```text
origin git@github.com:username/repository.git
```

---

# Saving Changes

Add files:

```bash
git add .
```

Create commit:

```bash
git commit -m "Initial Cybersecurity Lab"
```

Push to GitHub:

```bash
git push -u origin main
```

---

# Problems We Encountered

## Problem 1

Git commands failed.

Cause:

Repository not initialized.

Solution:

```bash
git init
```

---

## Problem 2

GitHub requested username and password.

Cause:

Repository was using HTTPS.

Solution:

Switch repository to SSH.

---

## Problem 3

GitHub rejected SSH key.

Cause:

Wrong key format or incorrect file copied.

Solution:

Use:

```bash
cat ~/.ssh/id_ed25519.pub
```

Copy the entire public key.

---

# Key Lessons Learned

1. Every cybersecurity project should be documented.
2. GitHub should be used from the beginning.
3. SSH is more secure than passwords.
4. Linux command line skills are essential.
5. Troubleshooting is part of learning.

---

# Portfolio Achievement

Project Completed:

Fedora Security Hardening Lab

Skills Demonstrated:

* Linux Navigation
* Directory Management
* Git Fundamentals
* GitHub Integration
* SSH Authentication
* Documentation
* Troubleshooting

---

# Next Lesson

Linux Users, Groups and Permissions

Topics:

* whoami
* id
* groups
* chmod
* chown
* sudo

Cybersecurity Concept:

Principle of Least Privilege (PoLP)

Students will learn how attackers exploit weak permissions and how system administrators secure access to files and directories.

---

# Reflection

A cybersecurity professional is not judged by how many tools they know, but by how well they can document, troubleshoot, secure, and explain their work.

Every command executed today is the foundation for more advanced skills such as penetration testing, incident response, digital forensics, cloud security, and DevSecOps.
