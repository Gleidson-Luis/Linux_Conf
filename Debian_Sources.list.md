🧾 1️⃣ Formato clássico (/etc/apt/sources.list)

Crie ou edite o arquivo /etc/apt/sources.list com o conteúdo abaixo:
```
# Debian 13.1 "Trixie" - Repositórios oficiais (Brasil)

# Principal
deb http://debian.c3sl.ufpr.br/debian/ trixie main contrib non-free non-free-firmware
deb-src http://debian.c3sl.ufpr.br/debian/ trixie main contrib non-free non-free-firmware

# Atualizações de segurança
deb http://security.debian.org/debian-security trixie-security main contrib non-free non-free-firmware
deb-src http://security.debian.org/debian-security trixie-security main contrib non-free non-free-firmware

# Atualizações estáveis (point releases)
deb http://debian.c3sl.ufpr.br/debian/ trixie-updates main contrib non-free non-free-firmware
deb-src http://debian.c3sl.ufpr.br/debian/ trixie-updates main contrib non-free non-free-firmware

# Backports (opcional)
# deb http://debian.c3sl.ufpr.br/debian/ trixie-backports main contrib non-free non-free-firmware
# deb-src http://debian.c3sl.ufpr.br/debian/ trixie-backports main contrib non-free non-free-firmware

# Proposed updates (opcional)
# deb http://debian.c3sl.ufpr.br/debian/ trixie-proposed-updates main contrib non-free non-free-firmware
# deb-src http://debian.c3sl.ufpr.br/debian/ trixie-proposed-updates main contrib non-free non-free-firmware
```
🧱 2️⃣ Formato moderno (/etc/apt/sources.list.d/debian.sources)

O Debian 13 suporta o formato deb822, que organiza melhor os repositórios.
Crie o arquivo /etc/apt/sources.list.d/debian.sources com:
```
# Debian 13.1 "Trixie" - Repositórios oficiais (Brasil)
# Formato moderno (deb822)
# Mirror: C3SL - UFPR

# Repositório principal e atualizações
Types: deb deb-src
URIs: http://debian.c3sl.ufpr.br/debian/
Suites: trixie trixie-updates
Components: main contrib non-free non-free-firmware
Signed-By: /usr/share/keyrings/debian-archive-keyring.gpg

# Repositório de segurança
Types: deb deb-src
URIs: http://security.debian.org/debian-security
Suites: trixie-security
Components: main contrib non-free non-free-firmware
Signed-By: /usr/share/keyrings/debian-archive-keyring.gpg

# Backports (ativado)
Types: deb deb-src
URIs: http://debian.c3sl.ufpr.br/debian/
Suites: trixie-backports
Components: main contrib non-free non-free-firmware
Signed-By: /usr/share/keyrings/debian-archive-keyring.gpg

# Proposed updates (ativado)
Types: deb deb-src
URIs: http://debian.c3sl.ufpr.br/debian/
Suites: trixie-proposed-updates
Components: main contrib non-free non-free-firmware
Signed-By: /usr/share/keyrings/debian-archive-keyring.gpg
```
✅ Teste e verificação

Depois de criar o arquivo no formato que quiser:
```
sudo apt update
```
Se tudo estiver certo, você verá as listas de pacotes sendo baixadas de:

debian.c3sl.ufpr.br

security.debian.org
