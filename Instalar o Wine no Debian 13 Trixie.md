# Instalar o Wine no Debian 13

### 1. Verifique as arquiteturas instaladas
Verifique a arquitetura de 64 bits. O comando a seguir deve responder com "amd64".
```
dpkg --print-architecture
```
Veja se a arquitetura de 32 bits já está instalada. O comando a seguir deve responder com "i386"
```
dpkg --print-foreign-architectures
```
Se não exibir "i386", execute o seguinte.
```
sudo dpkg --add-architecture i386
```
Verifique novamente com
```
dpkg --print-foreign-architectures
```
### 2. Baixe e adicione a chave do repositório WineHQ
```
sudo mkdir -pm755 /etc/apt/keyrings
wget -O - https://dl.winehq.org/wine-builds/winehq.key | sudo gpg --dearmor -o /etc/apt/keyrings/winehq-archive.key -
```
### 3. Adicione o repositório WineHQ
```
sudo wget -NP /etc/apt/sources.list.d/ https://dl.winehq.org/wine-builds/debian/dists/trixie/winehq-trixie.sources
```
