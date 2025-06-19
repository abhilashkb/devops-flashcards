# 📚 Ansible Flashcards Cheat Sheet

Quick flashcard-style guide to refresh your Ansible knowledge — perfect for interviews and day-to-day automation tasks.

---

## 1. ❓ What is Ansible, and how does it work?

<details>
<summary>Show Answer</summary>

Ansible is an open-source automation tool used for configuration management, application deployment, and task automation.  
It works by connecting to remote machines over SSH (or WinRM for Windows) and executing tasks described in YAML files (Playbooks) without requiring any agent on the target machines.

</details>

---

## 2. ❓ Explain the difference between Playbooks, Roles, and Tasks.

<details>
<summary>Show Answer</summary>

- **Playbooks:** The main files where automation tasks are defined in YAML.
- **Tasks:** Individual action steps (like installing packages, copying files) within Playbooks.
- **Roles:** A reusable, structured way to organize Playbooks, containing tasks, handlers, variables, templates, and files.

</details>

---

## 3. ❓ What is an Ansible Inventory, and how do you manage dynamic inventories?

<details>
<summary>Show Answer</summary>

Ansible Inventory defines the list of hosts or groups of hosts on which tasks run.

- **Static Inventory:** Defined in an INI or YAML file.
- **Dynamic Inventory:** Generated from external sources (like AWS, GCP, etc.) using inventory plugins or scripts.

Example:
