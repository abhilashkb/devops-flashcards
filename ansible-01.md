
---
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
```

ansible-inventory --list -i inventory\_aws\_ec2.yml

```

</details>

---

## 4. ❓ How do you handle secrets in Ansible (Ansible Vault)?

<details>
<summary>Show Answer</summary>

Ansible Vault allows encrypting sensitive data such as passwords or API keys.

Encrypt a file:
```

ansible-vault encrypt secret.yml

```

Decrypt temporarily for execution:
```

ansible-playbook site.yml --ask-vault-pass

```

</details>

---

## 5. ❓ What are Ansible Modules, and name a few commonly used ones.

<details>
<summary>Show Answer</summary>

Modules are standalone scripts that perform specific tasks.

**Common modules:**
- `copy`: Copy files to remote hosts.
- `file`: Manage file properties.
- `yum` / `apt`: Install packages.
- `service`: Manage services.
- `user`: Manage user accounts.
- `command` / `shell`: Run commands on remote nodes.

</details>

---

## 6. ❓ Explain Idempotency in Ansible.

<details>
<summary>Show Answer</summary>

Idempotency ensures that running the same task multiple times produces the same result and does not cause changes unless necessary.  
Ansible tasks are idempotent by design — they check the current state before making any change.

</details>

---

## 7. ❓ How do you debug Ansible Playbooks?

<details>
<summary>Show Answer</summary>

- Use `-v`, `-vvv` flags for detailed output.
- The `debug` module to print variable values:

```

* debug:
  var: variable\_name

```

- Check logs or dry-run with `--check`.

</details>

---

## 8. ❓ What is the difference between ansible and ansible-playbook commands?

<details>
<summary>Show Answer</summary>

- **ansible:** Executes a single ad-hoc command on hosts.
```

ansible all -m ping

```

- **ansible-playbook:** Executes a full Playbook (set of tasks).
```

ansible-playbook site.yml

```

</details>

---

## 9. ❓ How do you conditionally execute tasks in Ansible? (when, register)

<details>
<summary>Show Answer</summary>

- **register:** Captures output of a task.

```

* name: Check file existence
  stat:
  path: /tmp/testfile
  register: file\_status

```

- **when:** Runs a task conditionally.

```

* name: Remove file if exists
  file:
  path: /tmp/testfile
  state: absent
  when: file\_status.stat.exists

```

</details>

---

## 10. ❓ What are Ansible Facts, and how are they useful?

<details>
<summary>Show Answer</summary>

Facts are system properties (like OS, IP, memory) collected from managed hosts.

View facts:

```

ansible all -m setup

```

Use facts in Playbooks to make decisions based on the host environment.

</details>

---

## 📝 Contribution

Feel free to fork and contribute more flashcards!

## 🧩 License

MIT License
```

---
