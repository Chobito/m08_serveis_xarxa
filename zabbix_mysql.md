#Configurar zabbix_agentd y zabbix_server para monitorizar datos mysql



Mirar si /etc/zabbix/zabbix_agentd.d/ existeix, si no crearla

>Copiaremos userparameters para mysql en un directorio aparte de la configuracion Imprescindible del Agente Zabbix

_Copiar /usr/local/etc/userparameter_mysql.conf a /etc/zabbix/zabbix_agentd.d_

    cp /usr/local/etc/userparameter_mysql.conf /etc/zabbix/zabbix_agentd.d
    mkdir /var/lib/zabbix
    
>Crear /var/lib/zabbix si no existe
>crear dentro de /var/lib/zabbix un fichero llamado .my.cnf con :
    vim /var/lib/zabbix .my.cnf
    
    [mysql]
    user=zabbix
    password=zabbix
    [mysqladmin]
    user=zabbix
    password=zabbix

>Check that your zabbix_server config file is including the /etc/zabbix/zabbix_agentd.d/*.conf :
 
    vi /etc/zabbix/zabbix_agentd.conf
    Include=/etc/zabbix/zabbix_agent.d/

>Restart mariadb y zabbix-agentd

    systemctl restart mariadb zabbix-agentd
    
