Desativar o KVM para o Virtual Box

1. Para verificar o nome do KVM
```
# lsmod |grep kvm
```
2. Desativar o módulo KVM
```
# modprobe -r <kvm name>
```
Para desabilitar o KVM num sistema Debian, pode desinstalar os pacotes qemu-kvm e libvirt-daemon-system com o comando sudo apt remove --purge qemu-kvm libvirt-daemon-system, ou, se preferir apenas parar o serviço, use sudo systemctl stop libvirtd e sudo systemctl disable libvirtd, e então reinicie a máquina. 

Opção 1: Remover os pacotes (Recomendado se já não precisar do KVM) Esta opção remove completamente o KVM e as suas dependências do sistema.

    Abra o terminal e digite o seguinte comando para remover os pacotes:
    bash

    sudo apt remove --purge qemu-kvm libvirt-daemon-system

O apt remove --purge remove os pacotes e as suas configurações.

Em seguida, execute o comando sudo apt autoremove --purge para remover quaisquer pacotes órfãos que não sejam mais necessários.
Finalmente, reinicie o sistema com sudo reboot para que as alterações tenham efeito. 

Opção 2: Desativar o serviço KVM (Se quiser desativar temporariamente)
Se apenas não quiser que o KVM inicie com o sistema, pode desativar o serviço libvirtd.

Pare o serviço atual:

    sudo systemctl stop libvirtd

Desative o serviço para que ele não inicie no próximo boot:

    sudo systemctl disable libvirtd

Para desativar a carga dos módulos de KVM no momento do boot, pode adicionar as seguintes linhas a um ficheiro em /etc/modprobe.d/:
bash

    echo "install kvm_intel /bin/true" | sudo tee -a /etc/modprobe.d/kvm-blacklist.conf
    echo "install kvm /bin/true" | sudo tee -a /etc/modprobe.d/kvm-blacklist.conf

Isto impedirá que os módulos KVM sejam carregados no arranque do kernel. 

Para desativar o KVM no BIOS/UEFI (Se o sistema não iniciar corretamente)
Se o erro for referente ao KVM estar desabilitado pelo próprio BIOS (como visto em Ask Ubuntu), pode ser que precise de verificar a configuração da virtualização na BIOS/UEFI do seu sistema. 
Reinicie o computador e, durante o arranque, pressione a tecla indicada para aceder ao BIOS/UEFI (geralmente F2, F10, F12 ou Del).
Procure por opções relacionadas com "Virtualization Technology", "Intel Virtual Technology", ou "AMD-V" e certifique-se de que estão ativadas.
Guarde as alterações e saia do BIOS/UEFI. 
