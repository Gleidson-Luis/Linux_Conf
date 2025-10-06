1. Se você instalou o VirtualBox por meio do script do instalador, poderá encontrar o diretório onde ele está instalado executando
```
cat /etc/vbox/vbox.cfg
```
2. Você pode então executar o script de desinstalação localizado no diretório de instalação. Supondo que ele esteja instalado em /opt/VirtualBox, execute
```
sudo /opt/VirtualBox/uninstall.sh
sudo rm -rf /opt/VirtualBox/
```
