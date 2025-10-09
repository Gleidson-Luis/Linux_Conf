# Instalar o Flatpak no Debian

1. Instalar Flatpak
Um pacote flatpak está disponível no Debian 10 (Buster) e versões mais recentes. Para instalá-lo, execute o seguinte como root:
```
sudo apt install flatpak
```
2. Instalar o plugin Software Flatpak
Se você estiver usando o GNOME, também é uma boa ideia instalar o plugin Flatpak para o software GNOME. Para fazer isso, execute:
```
sudo apt install gnome-software-plugin-flatpak
```
Se você estiver executando o KDE, deverá instalar o backend Plasma Discover Flatpak:
```
sudo apt install plasma-discover-backend-flatpak
```
3. Adicione o repositório Flathub

O Flathub é o melhor lugar para obter aplicativos Flatpak. Para habilitá-lo, baixe e instale o arquivo de repositório do Flathub ou execute o seguinte em um terminal:
```
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```
4. Reiniciar
Para concluir a configuração, reinicie o sistema. Agora, tudo o que você precisa fazer é instalar os aplicativos !
