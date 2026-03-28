# ⚙️ Ansible – kabbilkarthi

Private Ansible repository for automating system configuration
and Linux OS tuning.

---

## 📁 Repository Structure

Ansible/
├── .ansible.cfg       # Ansible configuration (inventory path, defaults)
├── hosts              # Inventory file (target hosts)
├── .limits.yaml       # Playbook: OS limits & sysctl tuning
├── setup.yml          # Playbook: Initial system setup
└── README.md

---

## 📋 Playbooks

| File | Description |
|---|---|
| `.limits.yaml` | Set/remove nproc, nofile limits and sysctl kernel parameters |
| `setup.yml` | Initial system setup and baseline configuration |

---

## 🚀 Usage

### Run limits playbook
ansible-playbook .limits.yaml -e "user=kabbil"

### Run with a specific tag
ansible-playbook .limits.yaml -e "user=kabbil" --tags add_nproc

### Run setup playbook
ansible-playbook setup.yml

---

## 🏷️ Tags – .limits.yaml

| Tag | Action |
|---|---|
| `existing` | View current limits & sysctl values |
| `add_nproc` | Set nproc hard/soft limits |
| `add_nofile` | Set nofile hard/soft limits |
| `add_pid_max` | Set kernel.pid_max |
| `add_threads_max` | Set kernel.threads-max |
| `add_vm_max_map_count` | Set vm.max_map_count |
| `add_file_max` | Set fs.file-max |
| `remove_nproc` | Remove nproc limits |
| `remove_nofile` | Remove nofile limits |
| `remove_pid_max` | Remove kernel.pid_max |
| `remove_threads_max` | Remove kernel.threads-max |
| `remove_vm_max_map_count` | Remove vm.max_map_count |
| `remove_file_max` | Remove fs.file-max |
| `updated` | View updated values after changes |
| `cleanup` | Remove Ansible temp files |

---

## ⚠️ Required Variables

| Variable | Description | How to Pass |
|---|---|---|
| `user` | Linux user to apply limits | `-e "user=<username>"` |

> ❗ Playbook fails immediately if `user` is not provided.

---

## 📫 Contact

- 📧 g.i.kabbil@gmail.com

---

> *"Automate everything. Stay curious. Keep learning."* 🚀
