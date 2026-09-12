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
### 4. Atualizar o banco de dados de pacotes
```
sudo apt update
```
### 5. Instale o Wine
```
sudo apt install --install-recommends winehq-stable
```
### 6. Verifique a instalação
```
wine --version
```
### 7. Configurar o Wine
Para abrir o painel de configuração do Wine, abra uma janela do Terminal e execute winecfg.

Se/Quando a instalação do mono for oferecida, aceite a oferta, a menos que tenha certeza de que nunca precisará dela. Consulte este Apêndice para obter informações sobre Wine Mono.

Quando solicitado, defina sua versão preferida do Windows e quaisquer outras configurações apropriadas.
```
wine winecfg
```
Se você estiver criando prefixos Wine personalizados, essa configuração deverá ser repetida para cada prefixo.
### 7. Um teste simples
Exibir um relógio
```
wine clock
```
