# Instalando o Microsoft Edge no Debian, Ubuntu e Linux Mint

Supondo que o seu sistema esteja devidamente atualizado, abra novamente o terminal e execute o comando abaixo para importar a chave de assinatura GPG da Microsoft:
```
cd /tmp && curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg && sudo install -o root -g root -m 644 microsoft.gpg /usr/share/keyrings/ && cd $HOME
```
 Na sequência, adicione o repositório oficial do Microsoft Edge no seu sistema com:
``` 
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/microsoft.gpg] https://packages.microsoft.com/repos/edge stable main" | sudo tee /etc/apt/sources.list.d/microsoft-edge.list
```
 Atualize o cache dos repositórios:
```
sudo apt update
```
 E, por último, instale a versão desejada do navegador Microsoft Edge executando um dos comandos abaixo:
```
### Para instalar o Microsoft Edge (estável):
sudo apt install microsoft-edge-stable

### Para instalar o Microsoft Edge Beta:
sudo apt install microsoft-edge-beta

### Para instalar o Microsoft Edge Dev:
sudo apt install microsoft-edge-dev
```

# Instalando o Microsoft Edge via Flatpak

Flatpak é um dos sistemas de empacotamento de softwares mais conhecidos do Linux e que funciona de forma independente do gerenciador de pacotes das distribuições. No principal repositório de flatpaks, o Flathub, está disponível para instalação as Stable e Dev do Microsoft Edge.

Caso queira instalar o Microsoft Edge via Flatpak no seu Debian, Ubuntu ou Linux Mint, basta executar um dos comandos abaixo:
```
### Para instalar o Microsoft Edge (estável):
flatpak install flathub com.microsoft.Edge

### Para instalar o Microsoft Edge Dev:
flatpak install flathub com.microsoft.EdgeDev
```
# Informação!
Para instalar flatpaks é necessário que tenha o repositório Flathub adicionado no seu sistema. Para isso, basta executar o comando:
```
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```
# Instalando complementos no Microsoft Edge

Além dos vários recursos já integrados nativamente no navegador Microsoft Edge, também é possível adicionar uma série de novas funcionalidades no seu navegador com as mais variadas extensões disponíveis na loja de Complementos do Microsoft Edge (ou mesmo na Chrome Web Store), permitindo que você crie documentos, ouça músicas, edite fotos e muito mais! Acesse o link abaixo e confira:

Microsoft favicon  Visite a loja de Complementos do Microsoft Edge   

# Como desinstalar o Microsoft Edge?

Se você não deseja mais utilizar o Microsoft Edge e deseja removê-lo do seu Debian, Linux Mint ou Ubuntu? Então basta executar os comandos abaixo (de acordo com a versão do Edge e método de instalação usado):

Se instalou o Microsoft Edge através do repositório oficial, execute:
```
### Para desinstalar o Microsoft Edge (estável):
sudo apt remove microsoft-edge-stable

### Para desinstalar o Microsoft Edge Beta:
sudo apt remove microsoft-edge-beta

### Para desinstalar o Microsoft Edge Dev:
sudo apt remove microsoft-edge-dev
```
Caso também queira remover o repositório do Microsoft Edge do seu sistema, basta executar o comando:
```
sudo rm /etc/apt/sources.list.d/microsoft-edge*.list
```
Se instalou o Microsoft Edge via Flatpak, execute:
```
### Para remover o Microsoft Edge (estável):
flatpak remove com.microsoft.Edge

### Para remover o Microsoft Edge Dev:
flatpak remove com.microsoft.EdgeDev
```
