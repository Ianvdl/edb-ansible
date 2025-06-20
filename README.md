[![Tests status](https://github.com/Ianvdl/edb-ansible/workflows/edb-ansible%20testing/badge.svg)](https://github.com/Ianvdl/edb-ansible/actions?query=workflow%3Aedb-ansible-testing)

# Ansible playbooks for deploying and managing PostgreSQL and EDB Advanced Server

This Ansible Galaxy Collection brings reference architecture deployment
capabilites for PostgreSQL or EnterpriseDB Postgres Advanced Server.

![Header image](https://github.com/Ianvdl/edb-ansible/blob/main/imgs/edb-ansible.png)

# Maintenance notice

> [!IMPORTANT]
> EDB has abandoned the original repo. This fork attempts to maintain the
> collection independently. Pull requests are welcome.

## To-do list

- :white_check_mark: Fix test infrastructure
- :white_check_mark: Update supported OSes to RHEL 9 and Ubuntu 24.04 #9
- 🔜 Publish this collection to Ansible Galaxy #11
- Remove unsupported OS and PostgreSQL versions #10

---

**Not all Distribution or versions are supported on all the operating systems
available.**

**The ansible playbook must be executed under an account that has full
privileges.**

`edb-ansible` is a repository used for hosting an Ansible Collection that
currently supports the following ansible roles:

| Role name                                                                                | Description                                                                                                                                                                                        |
|------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [tuning](roles/tuning/README.md)                                                         | The tuning role configures the system and Postgres instances for optimal performances. Most of the configuration values are calculated automatically from available resources found on the system. |
| [init_dbserver](roles/init_dbserver/README.md)                                           | Initialize the EPAS/PostgreSQL cluster (data) directory.                                                                                                                                           |
| [install_dbserver](roles/install_dbserver/README.md)                                     | Install EPAS/PostgreSQL database server packages.                                                                                                                                                  |
| [install_from_source](roles/install_from_source/README.md)                               | Dowload and install software from source.                                                                                                                                                          |
| [manage_cnpg](roles/manage_cnpg/README.md)                                    	          | Manage CloudNativePG/EDB Postgres for Kubernetes clusters and covers common tasks.                                                                                                                 |
| [manage_dbserver](roles/manage_dbserver/README.md)                                       | Manage EPAS/PostgreSQL clusters and covers common tasks.                                                                                                                                           |
| [manage_pgbouncer](roles/manage_pgbouncer/README.md)                                     | Manage PgBouncer pools list and users.                                                                                                                                                             |
| [manage_pgpool2](roles/manage_pgpool2/README.md)                                         | Manage Pgpool-II settings and users.                                                                                                                                                               |
| [manage_touchstone_tools](roles/manage_touchstone_tools/README.md)                       | Manage touchstone tools functions to enable collection and processing of system and database statistics.                                                                                           |
| [manage_operating_system](roles/manage_operating_system/README.md)                       | Manage operating system settings.                                                                                                                                                                  |
| [remove_cloudnativepg_sandbox](roles/remove_cloudnativepg_sandbox/README.md)             | Remove CloudNativePG Sandbox from Kubernetes cluster.                                                                                                                                              |
| [remove_cloudnativepostgres_sandbox](roles/remove_cloudnativepostgres_sandbox/README.md) | Remove CloudNative Postgres Sandbox from Kubernetes cluster.                                                                                                                                       |
| [setup_cloudnativepg_sandbox](roles/setup_cloudnativepg_sandbox/README.md)               | Setup CloudNativePG Sandbox from Kubernetes cluster.                                                                                                                                               |
| [setup_cloudnativepostgres_sandbox](roles/setup_cloudnativepostgres_sandbox/README.md)   | Setup CloudNative Postgres Sandbox from Kubernetes cluster.                                                                                                                                        |
| [setup_barman](roles/setup_barman/README.md)                                             | Set up EPAS/PostgreSQL backups with Barman.                                                                                                                                                        |
| [setup_barmanserver](roles/setup_barmanserver/README.md)                                 | Set up Barman (Postgres backup) server.                                                                                                                                                            |
| [setup_dbt2](roles/setup_dbt2/README.md)                                                 | Set up a database server for DBT-2.                                                                                                                                                                |
| [setup_dbt2_client](roles/setup_dbt2_client/README.md)                                   | Set up a client (a.k.a. transaction manager) for the client DBT-2.                                                                                                                                 |
| [setup_dbt2_driver](roles/setup_dbt2_driver/README.md)                                   | Set up emulated terminals (a.k.a. driver) for DBT-2.                                                                                                                                               |
| [setup_dbt3](roles/setup_dbt3/README.md)                                                 | Install the DBT-3 benchmark kit.                                                                                                                                                                   |
| [setup_dbt7](roles/setup_dbt7/README.md)                                                 | Install the DBT-7 benchmark kit.                                                                                                                                                                   |
| [setup_efm](roles/setup_efm/README.md)                                                   | Set up EDB Failover Manager (EFM) for PostgreSQL/EPAS HA cluster.                                                                                                                                  |
| [setup_hammerdb](roles/setup_hammerdb/README.md)                                         | Install HammerDB.                                                                                                                                                                                  |
| [setup_pemagent](roles/setup_pemagent/README.md)                                         | Set up Postgres Enterprise Manager (PEM) agent on the Postgres servers.                                                                                                                            |
| [setup_pemserver](roles/setup_pemserver/README.md)                                       | Set up Postgres Enterprise Manager (PEM) server.                                                                                                                                                   |
| [setup_pgbackrest](roles/setup_pgbackrest/README.md)                                     | Set up EPAS/PostgreSQL backups with pgBackRest.                                                                                                                                                    |
| [setup_pgbackrestserver](roles/setup_pgbackrestserver/README.md)                         | Set up pgBackRest server for Postgres backups and recovery.                                                                                                                                        |
| [setup_pgbouncer](roles/setup_pgbouncer/README.md)                                       | Set up PgBouncer connection pooler.                                                                                                                                                                |
| [setup_haproxy](roles/setup_haproxy/README.md)                                           | Set up HaProxy load balancer for Patroni cluster .                                                                                                                                                 |
| [setup_etcd](roles/setup_etcd/README.md)                                                 | Set up etcd for Patroni cluster.                                                                                                                                                                   |
| [setup_patroni](roles/setup_patroni/README.md)                                           | Set up for Patroni managed cluster.                                                                                                                                                                |
| [setup_pgd](roles/setup_pgd/README.md)                                                   | Set up PGD HA cluster.                                                                                                                                                                             |
| [setup_pgpool2](roles/setup_pgpool2/README.md)                                           | Set up Pgpool-II connection pooler/load balancer.                                                                                                                                                  |
| [setup_replication](roles/setup_replication/README.md)                                   | Set up the data replication (synchronous/asynchronous).                                                                                                                                            |
| [setup_repmgr](roles/setup_repmgr/README.md)                                             | Set up Repmgr for PostgreSQL HA cluster.                                                                                                                                                           |
| [setup_repo](roles/setup_repo/README.md)                                                 | Set up the EDB, PostgreSQL Community and EPEL repositories.                                                                                                                                        |
| [setup_touchstone_tools](roles/setup_touchstone_tools/README.md)                         | Set up additional packages and software for characterizing system performance.                                                                                                                     |
| [manage_dbpatches](roles/manage_dbpatches/README.md)                                     | Manage applying patches on dbservers part of EFM cluster.                                                                                                                                          |
| [tuning](roles/tuning/README.md)                                                         | Configure system and Postgres instances for optimal performance.                                                                                                                                   |

## Installation

* To install Ansible: **[Installing Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)**

The `edb_ansible` collection can be installed using three different approaches:

### Installing the `edb_postgres` Ansible Collection from Ansible Galaxy

> [!CAUTION]
> EDB has abandoned the original repo - the version currently in Ansible Galaxy
> is outdated and broken.

Installing the `edb_postgres` Ansible Collection is done by following the steps
below:

  * Open the command line
  * Type:
    ```bash
    $ ansible-galaxy collection install edb_devops.edb_postgres --force
    ```
  * Press *Enter*

This approach automatically makes the `edb_postgres` collection available to
your playbooks.

A message indicating where the collection is installed will be displayed by
ansible-galaxy. The collection code should be automatically made readily
available for you.

By default the location of your installed collection is:
`~/.ansible/collections/ansible_collections`

### Downloading the `edb-ansible` repository source code from the repository in GitHub

This method requires to have the `ansible-galaxy` tool installed.

Downloading the code from the repository can be accomplished by following the
steps below:

  * Navigate to the repository address: `https://github.com/Ianvdl/edb-ansible`
  * Click on the green *Code* Button located next to the *About* section
  * Click on the *Download Zip* Link menu option

After the code has been downloaded, the code will be available as a zip file
which requires being unzipped to your desired target destination.

After the code has been unzipped, you must go to root folder
`edb-ansible-main`, and install the collection by entering the command below:

```bash
$ make install
```

This approach automatically makes the `edb_postgres` collection available to
your playbooks.

A message indicating where the collection is installed will be displayed by
ansible-galaxy. The collection code should be automatically made readily
available for you.

By default the location of your installed collection is:
`~/.ansible/collections/ansible_collections`

### Cloning the `edb-ansible` repository source code from the repository GitHub

This method requires to have the `ansible-galaxy` tool installed.

Downloading the code from the repository can be accomplished by following the
steps below:

```bash
$ git clone git@github.com:Ianvdl/edb-ansible.git
```

After the code has been downloaded, the code will be available in your current
directory within a directory named: `edb-ansible`.

You can access the root folder of the repository by entering the command below:

```bash
$ cd edb-ansible
```

You can install the collection by entering the command below:

```bash
$ make install
```

This approach automatically makes the `edb_postgres` collection available to
your playbooks.

A message indicating where the collection is installed will be displayed by
ansible-galaxy. The collection code should be automatically made readily
available for you.

By default the location of your installed collection is:
`~/.ansible/collections/ansible_collections`

## Example of inventory file

Content of the `inventory.yml` file:

```yaml
---
all:
  children:
    pemserver:
      hosts:
        pemserver1:
          ansible_host: 110.0.0.4
          private_ip: 10.0.0.4
    primary:
      hosts:
        primary1:
          ansible_host: 110.0.0.1
          private_ip: 10.0.0.1
          pem_agent: true
          pem_server_private_ip: 10.0.0.4
    standby:
      hosts:
        standby1:
          ansible_host: 110.0.0.2
          private_ip: 10.0.0.2
          upstream_node_private_ip: 10.0.0.1
          replication_type: synchronous
          pem_agent: true
          pem_server_private_ip: 10.0.0.4
        standby2:
          ansible_host: 110.0.0.3
          private_ip: 10.0.0.3
          upstream_node_private_ip: 10.0.0.1
          replication_type: asynchronous
          pem_agent: true
          pem_server_private_ip: 10.0.0.4
```

Replace the IP addresses above with your own.

## How to include the roles in your Playbook

Below is an example of how to include all the roles for a deployment in a
playbook:

```yaml
---
- hosts: all
  name: Postgres deployment playbook
  become: yes
  gather_facts: yes

  collections:
    - edb_devops.edb_postgres

  pre_tasks:
    - name: Initialize the user defined variables
      set_fact:
        pg_version: 16
        pg_type: "EPAS"
        repo_username: "<edb-package-repository-username>"
        repo_password: "<edb-package-repository-password>"
        repo_token: "<edb-package-repository-token>"
        disable_logging: false

  roles:
    - role: setup_repo
      when: "'setup_repo' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: install_dbserver
      when: "'install_dbserver' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: init_dbserver
      when: "'init_dbserver' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: setup_replication
      when: "'setup_replication' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: setup_efm
      when: "'setup_efm' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: setup_pgpool2
      when: "'setup_pgpool2' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: manage_pgpool2
      when: "'manage_pgpool2' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: manage_dbserver
      when: "'manage_dbserver' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: setup_pemserver
      when: "'setup_pemserver' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: setup_pemagent
      when: "'setup_pemagent' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: setup_pgbackrest
      when: "'setup_pgbackrest' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: setup_pgbackrestserver
      when: "'setup_pgbackrestserver' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: setup_pgbouncer
      when: "'setup_pgbouncer' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: manage_pgbouncer
      when: "'manage_pgbouncer' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: setup_barmanserver
      when: "'setup_barmanserver' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: setup_barman
      when: "'setup_barman' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: tuning
      when: "'tuning' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
```

You can customize the above example to install PostgreSQL, EPAS, EFM or PEM or
limit what roles you would like to execute.

If you are planning to try Patroni based cluster below is an example of hot to include roles for patroni cluster
playbook:
```yaml
---
- hosts: all
  name: Postgres deployment playbook
  become: yes
  gather_facts: yes

  collections:
    - edb_devops.edb_postgres

  pre_tasks:
    - name: Initialize the user defined variables
      set_fact:
        pg_version: 16
        pg_type: "EPAS"
        repo_username: "<edb-package-repository-username>"
        repo_password: "<edb-package-repository-password>"
        repo_token: "<edb-package-repository-token>"
        use_patroni: true
        disable_logging: false

  roles:
    - role: setup_repo
      when: "'setup_repo' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: install_dbserver
      when: "'install_dbserver' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: setup_etcd
      when: "'setup_etcd' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
    - role: setup_patroni
      when: "'setup_patroni' in lookup('edb_devops.edb_postgres.supported_roles', wantlist=True)"
```

### Access to EDB's package repository

By default, the `setup_repo` role requires to define credentials (variables
`repo_username` and `repo_password` or `repo_token`) that will be used to configure the access
to EDB's package repository. Having access to EDB package repository is
necessary to deploy EDB software like EPAS, EFM or PEM.

When deploying software coming only from the community repository (PGDG) like
PostgreSQL, barman or pgbouncer, it's not needed to configure access to EDB's
repository. To disable it, the variable `enable_edb_repo` must be set to
`false`.

## Default user and passwords

If passwords are not provided for the following accounts, they will be
generated automatically:

  * `pg_superuser`
  * `pg_replication_user`
  * `pg_efm_user`
  * `pg_pem_agent_user`
  * `pg_pem_admin_user`

**Note:**

  * A password of 20 characters for each user will automatically be created
    under: `~/.edb` folder.
  * The naming convention for the password file is: `<username>_pass`

## Playbook examples

Playbook examples are located within the `playbook-examples` directory.

## SSH port configuration

When using non standard SSH port (different from 22), the port value must be
set in two places:

- in the inventory file, for each host, with the host var. `ansible_port`
- in the playbook or variable file with the variable `ssh_port`

## Playbook execution examples

```bash
# To deploy PostgreSQL version 16
$ ansible-playbook playbook.yml \
  -i inventory.yml \
  -u <ssh-user> \
  --private-key <ssh-private-key> \
  --extra-vars="pg_version=16 pg_type=PG enable_edb_repo=false"
```
```bash
# To deploy EPAS version 16 with the user ec2-user
$ ansible-playbook playbook.yml \
  -i inventory.yml \
  -u <ssh-user> \
  --private-key <ssh-private-key> \
  --extra-vars="pg_version=16 pg_type=EPAS repo_username=<edb-repo-username> repo_password=<edb-repo-password>"
# OR
$ ansible-playbook playbook.yml \
  -i inventory.yml \
  -u <ssh-user> \
  --private-key <ssh-private-key> \
  --extra-vars="pg_version=16 pg_type=EPAS repo_token=<edb-repo-token>"

```

## Database engines supported

### PostgreSQL

| Distribution                      |               13 |               14 |               15 |
| --------------------------------- |:----------------:|:----------------:|:----------------:|
| RockyLinux 8                      |:white_check_mark:|:white_check_mark:|:white_check_mark:|
| AlmaLinux 8                       |:white_check_mark:|:white_check_mark:|:white_check_mark:|
| Red Hat Linux 8                   |:white_check_mark:|:white_check_mark:|:white_check_mark:|
| Ubuntu 20.04 LTS (Focal) - x86_64 |:white_check_mark:|:white_check_mark:|:white_check_mark:|
| Debian 9 (Stretch) - x86_64       |:white_check_mark:|:white_check_mark:|:white_check_mark:|
| Debian 10 (Buster) - x86_64       |:white_check_mark:|:white_check_mark:|:white_check_mark:|

### EnterpriseDB Postgres Advanced Server

| Distribution                      |               13 |               14 |               15 |
| --------------------------------- |:----------------:|:----------------:|:----------------:|
| RockyLinux 8                      |:white_check_mark:|:white_check_mark:|:white_check_mark:|
| AlmaLinux 8                       |:white_check_mark:|:white_check_mark:|:white_check_mark:|
| Red Hat Linux 8                   |:white_check_mark:|:white_check_mark:|:white_check_mark:|
| Ubuntu 20.04 LTS (Focal) - x86_64 |:white_check_mark:|:white_check_mark:|:white_check_mark:|
| Debian 9 (Stretch) - x86_64       |:white_check_mark:|:white_check_mark:|:white_check_mark:|
| Debian 10 (Buster) - x86_64       |:white_check_mark:|:white_check_mark:|:white_check_mark:|

- :white_check_mark: - Tested and supported
- :x: - Not tested and not supported

## License

BSD

## Contributors
<a href="https://github.com/Ianvdl/edb-ansible/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=Ianvdl/edb-ansible" />
</a>

Made with [contrib.rocks](https://contrib.rocks).

## Author information

These are the original authors of the EDB version.

Authors:
  * Doug Ortiz
  * Vibhor Kumar
  * Julien Tachoires
  * Mark Wong
  * Vincent Phan
  * Hannah Stoik
  * Bryan Barajas

