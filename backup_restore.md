Install and configure infrastructure with Ansible:

    ansible-playbook infra.yaml

Restore MySql data from backup

    
    sudo -u backup duplicity --no-encryption restore rsync://alekseibahmatov@backup.torchify.io/mysql /home/backup/restore/mysql
    
    mysql agama < /home/backup/mysql/agama.sql

Restore influxdb data from backup

    sudo -u backup duplicity --no-encryption restore rsync://alekseibahmatov@backup.torchify.io/influxdb /home/backup/restore/influxdb

    service telegraf stop

    influx -execute 'DROP DATABASE telegraf'

    influxd restore -portable -database telegraf /home/backup/restore/influxdb