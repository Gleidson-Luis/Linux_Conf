Para instalar o Plymouth e temas no Debian, use sudo apt install plymouth plymouth-themes no terminal. Para definir um tema, use sudo plymouth-set-default-theme <nome-do-tema>, liste os temas com plymouth-set-default-theme -l e ajuste o GRUB para que splash apareça na linha GRUB_CMDLINE_LINUX_DEFAULT no arquivo de configuração do GRUB. 
1. Instale os pacotes necessários 
Abra o terminal e execute o seguinte comando para instalar o Plymouth e seus temas: 
```
sudo apt install plymouth plymouth-themes
```

2. Configure o tema no GRUB
Edite o arquivo de configuração do GRUB para adicionar a opção splash. 
```
sudo nano /etc/default/grub
```

Na linha GRUB_CMDLINE_LINUX_DEFAULT, adicione splash dentro das aspas. Por exemplo:
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash". 
3. Atualize o GRUB 
Após a alteração, atualize o GRUB para aplicar as mudanças: 
```
sudo update-grub2
```

4. Altere o tema padrão
Para definir um tema, use o comando plymouth-set-default-theme. Para listar os temas disponíveis, execute: 
```
plymouth-set-default-theme -l
```

Para definir um tema, por exemplo, o tema "glow", você faria: 
```
sudo plymouth-set-default-theme glow
```

5. Reinicie o sistema
Reinicie o computador para ver as alterações.
```
sudo reboot
```
6. Configurações Completas no site:
https://linuxdicasesuporte.blogspot.com/2020/12/boot-animado-com-plymouth-no-debian-gnu.html
