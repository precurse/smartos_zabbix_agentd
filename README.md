# smartos_zabbix_agentd
Files required to setup zabbix_agentd on SmartOS

This has been confirmed working on both the read-only hypervisor as well as zoned instances.

Steps to install:
- Create a 'zabbix' user (Linux defaults with the 110 userid and 115 for groupid).
- Download the latest pre-compiled zabbix agent from http://www.zabbix.com/download.php for Solaris 10 amd64.
- Extract to /opt/zabbix directory (Folder structure should be /opt/zabbix/sbin, /opt/zabbix/conf, etc.).
- Edit the conf/zabbix_agentd.conf file to your requirements.
- Copy the zabbix_agentd.xml file to the /opt/custom/smf/ directory.
- Run 'svccfg import /opt/custom/smf/zabbix_agentd.xml'.
- Run 'svcadm enable network/zabbix_agentd'.

Additional step required for the read-only hypervisor:
- Follow this guide to create 'zabbix' user https://wiki.smartos.org/display/DOC/Allowing+user+CRUD+in+the+global+zone.


