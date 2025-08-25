Desativar o KVM para o Virtual Box

1. Para verificar o nome do KVM
```
# lsmod |grep kvm
```
2. Desativar o módulo KVM
```
# modprobe -r <kvm name>
```
