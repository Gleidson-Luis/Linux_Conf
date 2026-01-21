# Mudando o tamanho do arquivo de swap

1. Abrir o terminal e verificar o arquivo:
``` 
cat /proc/swaps
```
2. Apagar o arquivo de swap e criar um novo com o tamanho desejado, mas antes disso tem que desligar a swap
```
sudo swapoff -a
```
3. Apagar o arquivo swap
```
sudo rm /swapfile
```
4. Criar um novo arquivo swap
```
sudo fallocate -l 8G /swapfile
``` 
5. Esse arquivo precisa de uma permissão especial que só o Root precisa escrever nele
```
sudo chmod 600 /swapfile
```
6. Formatar esse arquivo como se fosse uma partição
```
sudo mkswap /swapfile
```
7. Ligar a swap novamente
```
sudo swapon /swapfile
```
