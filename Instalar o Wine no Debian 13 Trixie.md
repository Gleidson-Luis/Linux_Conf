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
