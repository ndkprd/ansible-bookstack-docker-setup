# ansible-bookstack-docker-setup

## Description

Ansible playbook to setup docker-based Bookstack app and database. This branch is for getting ready for roles division.

## File Tree

```
├── hosts.ini
├── LICENSE
├── playbook.yaml
├── README.md
└── roles
    ├── basic-setup
    │   ├── tasks
    │   │   └── main.yaml
    │   └── vars
    │       └── main.yaml
    ├── bookstack-docker-setup
    │   ├── tasks
    │   │   └── main.yaml
    │   ├── templates
    │   │   ├── app-docker-compose.yaml.j2
    │   │   └── db-docker-compose.yaml.j2
    │   └── vars
    │       └── main.yaml
    ├── docker-setup
    │   ├── tasks
    │   │   └── main.yaml
    │   └── vars
    │       └── main.yaml
    └── group_vars
        └── all.yaml

```

## How to Use

1. Install Ansible;
2. Clone this repo;
3. Move inside the project directory:
```
cd ansible-bookstack-docker-setup
```
4. Edit `hosts.ini` file with your hosts;
5. Edit all the `roles/<role-name>/vars/main.yaml` files with your need;
6. Run the playbook:
```
ansible-playbook -i hosts.yaml playbook.yaml
```

## Resolution

Point your reverse-proxy towards <app-server>:6875 (if your reverse-proxy and bookstack-app are on different server), and you should be able to access your Bookstack instance using the URL you define in `app_url` variable in `roles/bookstack-docker-setup/vars/main.yaml` file.

