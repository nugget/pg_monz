#
# Makefile to simplify installtion of pg_monz
#

PREFIX			?= /usr/local
AGENTDCONFDIR	?= $(PREFIX)/etc/zabbix22/zabbix_agentd.conf.d
SCRIPTDIR		?= $(PREFIX)/bin

SCRIPT_UID		?= root
SCRIPT_GID		?= wheel

CONF_UID		?= root
CONF_GID		?= zabbix

SCRIPTS			?= find_dbname.sh find_dbname_table.sh

all:

install: install-agentd install-scripts

install-scripts:
	@echo installing discovery scripts
	install -m 0755 -o $(SCRIPT_UID) -g $(SCRIPT_GID) $(SCRIPTS) $(SCRIPTDIR)

install-agentd:
	@echo Installing UserParameter config for zabbix_agentd
	install -m 0644 -o $(CONF_UID) -g $(CONF_GID) userparameter_pgsql.conf $(AGENTDCONFDIR)


