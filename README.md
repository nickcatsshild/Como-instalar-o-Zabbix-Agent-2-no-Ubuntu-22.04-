# Como-instalar-o-Zabbix-Agent-2-no-Ubuntu-22.04-


instalar o Zabbix Agent no Ubuntu 22.04

Configure o Repositório Zabbix

A equipe zabbix fornece repositórios aptos para a instalação de pacotes Zabbix. Em seguida, adicione o repositório ao seu sistema, que são pacotes necessários para o agente Zabbix. Execute os seguintes comandos para ativar os repositórios do Zabbix.

wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_6.0+ubuntu22.04_all.deb

dpkg -i zabbix-release_latest_6.0+ubuntu22.04_all.deb

Instale o Zabbix Agent no Ubuntu

Como você adicionou com sucesso o repositório do Zabbix em seu sistema, vamos usar o seguinte comando para instalar o agente Zabbix usando o seguinte comando.

sudo apt update

apt install zabbix-agent2 zabbix-agent2-plugin-*

O Agente Zabbix está instalado no seu sistema.

Em seguida, você precisa configurar o agente Zabbix para permitir a conexão do seu servidor Zabbix. Por exemplo, seu servidor Zabbix está sendo executado com endereço IP 192.168.100.20. Para atualizá-lo, edite o arquivo de configuração do agente Zabbix /etc/zabbix/zabbix_agentd.conf:

sudo nano /etc/zabbix/zabbix_agentd.conf

Gerenciar o serviço Zabbix

Agora, reinicie o serviço Zabbix para aplicar as alterações. Também habilite o serviço para iniciar automaticamente na inicialização do sistema. Execute os seguintes comandos para reiniciar e habilitar o serviço de agente Zabbix.

sudo systemctl restart zabbix-agent2

sudo systemctl enable zabbix-agent2

