# Самоконтроль выполненения задания

1. Где расположен файл с `some_fact` из второго пункта задания?
```shell
cat group_vars/all/examp.yml
```

```shell
# cat group_vars/all/examp.yml
---
  some_fact: all default fact
```

2. Какая команда нужна для запуска вашего `playbook` на окружении `test.yml`?

```shell
ansible-playbook -i inventory/test.yml site.yml
```

3. Какой командой можно зашифровать файл?

```shell
ansible-vault encrypt group_vars/deb/examp.yml
```

4. Какой командой можно расшифровать файл?

```shell
ansible-vault decrypt group_vars/deb/examp.yml
```

5. Можно ли посмотреть содержимое зашифрованного файла без команды расшифровки файла? Если можно, то как?

Да, можно.  
Например, команда для просмотра файла `group_vars/deb/examp.yml`

```shell
ansible-vault view group_vars/deb/examp.yml
```

```shell
# ansible-vault view group_vars/deb/examp.yml
Vault password:
---
  some_fact: "deb default fact"
root@deb11-test50:~/olekirs/08-ansible-01-base#
```

6. Как выглядит команда запуска `playbook`, если переменные зашифрованы?

```shell
ansible-playbook -i inventory/prod.yml site.yml --ask-vault-pass
```

7. Как называется модуль подключения к host на windows?

`winrm` или его вариант для PowerShell `psrp`

8. Приведите полный текст команды для поиска информации в документации ansible для модуля подключений ssh

```shell
ansible-doc --type connection ansible.builtin.ssh
```

9. Какой параметр из модуля подключения `ssh` необходим для того, чтобы определить пользователя, под которым необходимо совершать подключение?

```
- remote_user
        User name with which to login to the remote server, normally set by the remote_user keyword.
        If no user is supplied, Ansible will let the SSH client binary choose the user as it normally.
        [Default: (null)]
        set_via:
          cli:
          - name: user
            option: --user
          env:
          - name: ANSIBLE_REMOTE_USER
          ini:
          - key: remote_user
            section: defaults
          keyword:
          - name: remote_user
          vars:
          - name: ansible_user
          - name: ansible_ssh_user
```

