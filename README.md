## Установка WordPress и настройка MySQL с помощью Ansible

# 1. Настройка инвентарного файла (`inventory`)

Откройте файл `inventory`, пропишите хост, поменяйте пользователя и укажите путь до приватного ssh ключа.

```ini
[study-ansible]
158.160.62.49 ansible_user=user ansible_ssh_private_key_file=~/.ssh/devops_practicum
```
# 2. Настройка файла (`playbook.yml`)

Замените юзера под котором Ansible будет выполнять установку

```ini
  remote_user: user
```

# 3. Установка зависимостей (`requirements.yaml`)

Установите зависимости с помощью команды, если они отсутствуют:

```bash
ansible-galaxy collection install -r requirements.yaml
```

# 4. Установка WordPress

Выполните установку с помощью команды:

```bash
ansible-playbook -i inventory playbook.yml
```