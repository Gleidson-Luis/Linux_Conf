# Aumentar a porcentagem para utilização de memória swap

1. Verificar a porcentagem de inicio da Swap
```
$ cat /proc/sys/vm/swappiness
```
2. Se estiver "60", isso indica que assim que chegar em 40% de uso da memória RAM, ele automaticamente inicia o uso da memória Swap. Para aumentar para 90%, digitar o comando abaixo:
```
$ echo 'vm.swappiness=10' | sudo tee /etc/sysctl.d/99-swappiness.conf
```
3. Verificar se o arquivo foi criado
```
$ cat /etc/sysctl.d/99-swappiness.conf
```
Resultado: vm.swappiness=10

4. Revalidar o arquivo
```
$ sudo sysctl --system
```
5. Verificar se houve atualização
```
$ cat /proc/sys/vm/swappiness
```
Se o valor estiver 10, a configuração foi efetuada com sucesso.
