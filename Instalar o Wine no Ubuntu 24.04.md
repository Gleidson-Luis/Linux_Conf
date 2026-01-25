# Instalar o Wine no Ubuntu 24.04

### 1. Atualizar o sistema e instalar pré-requisitos
```
sudo apt update && sudo apt upgrade -y
sudo apt install -y wget gnupg2 ca-certificates software-properties-common apt-transport-https
```

### 2. Habilitar arquitetura de 32 bits (necessário para muitos programas Windows)
```
sudo dpkg --add-architecture i386
```

### 3. Adicionar a chave de segurança do WineHQ
```
sudo mkdir -p /etc/apt/keyrings
wget -O- https://dl.winehq.org/wine-builds/winehq.key | sudo gpg --dearmor | sudo tee /etc/apt/keyrings/winehq-archive.key
```
### 4. Adicionar o repositório WineHQ para o Ubuntu 24.04 (Noble)

### Verifique o codename exato do seu Ubuntu (pode ser noble)
```
sudo wget -O /etc/apt/sources.list.d/winehq-noble.sources https://dl.winehq.org/wine-builds/ubuntu/dists/noble/winehq-noble.sources
```
### 5. Atualizar o apt e instalar o Wine (versão estável)
```
sudo apt update
sudo apt install --install-recommends winehq-stable
```

# Método 2: Repositório Padrão do Ubuntu (Mais simples, versão mais antiga)
bash

### 1. Habilitar arquitetura de 32 bits
```
sudo dpkg --add-architecture i386
```

### 2. Instalar o Wine
```
sudo apt update
sudo apt install wine64 wine32 # Ou apenas 'sudo apt install wine'
```

### Como usar após a instalação
1. Clique com o botão direito em um arquivo .exe ou .msi do Windows.
2. Selecione "Abrir com outro aplicativo" e escolha "Wine Windows Program Loader" ou apenas "Wine".
3. Na primeira execução, o Wine pode pedir para instalar componentes adicionais (como o wine-mono), clique em "Instalar". 
