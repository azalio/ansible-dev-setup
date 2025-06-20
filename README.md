# Developer Environment Setup with Ansible

Ansible playbook для настройки окружения разработчика на выделенном сервере.

## Что устанавливается

- Node.js (версия 20) + npm
- Golang (версия 1.21.5)
- golangci-lint (версия v1.55.2)
- make
- Необходимые системные пакеты

## Использование

1. Отредактируйте файл `inventory` и укажите IP адрес или hostname вашего сервера:
```ini
[dev-servers]
192.168.1.100 ansible_user=your_username
```

2. Запустите playbook:
```bash
ansible-playbook -i inventory dev-environment.yml
```

Для локального сервера (если Ansible установлен на том же сервере):
```bash
ansible-playbook -i inventory dev-environment.yml --connection=local
```

## Настройка переменных окружения

После установки Go, переменные окружения будут добавлены в `/etc/profile`. Для применения изменений:
```bash
source /etc/profile
```

Или перелогиньтесь в систему.

## Проверка установки

Playbook автоматически проверит версии всех установленных инструментов и выведет результат в конце выполнения.# ansible-dev-setup
