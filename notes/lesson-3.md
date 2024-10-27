# Настройка SSH-сервера

Заметки по видеоурок с настройком ssh-сервера на машине.

## Установка пакета OpenSSH server

```bash
sudo apt install openssh-server -y
```

## Проверка статуса и включение [демона](https://man7.org/linux/man-pages/man7/daemon.7.html) SSH

```bash
sudo systemctl start ssh
sudo systemctl enable ssh
```

## Проверка IP-адреса на локальной машине

```bash
hostname -I
```

***Примечание:** можно также использовать* ```ip a```

## От себя 😊

### Проверка того, что пакет установлен

```bash
sudo apt list --installed | grep "openssh-server" # проверяет пакет openssh-server
```

### Добавление пользователя с правами на sudo

```bash
apt install sudo
adduser <username>
usermod -aG sudo <username>

# проверка
sudo echo "превед медвед"
```

### Добавление ключа в authorized_keys

```bash
echo "<ключ из pub-файла>" >> ~/.ssh/authorized_keys
```

### Сортировка зеркал Debian по быстроте ответа

```bash
sudo apt install netselect-apt
sudo netselect-apt 
```
