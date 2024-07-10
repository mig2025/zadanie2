Задание Обновление ядра Centos8

Рабочее место Debian 12

при добалении репозитория https://www.elrepo.org/elrepo-release-8.el8.elrepo.noarch.rpm возникла ошибка=> Error: Failed to download metadata for repo 'appstream'

Решение:

1. cd /etc/yum.repos.d/
2. sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
3. sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
4. yum update -y

Итог:

Ядро до обновления: 4.18.0-516.el8.x86_64

Ядро после обновления: 6.9.8-1.el8.elrepo.x86_64