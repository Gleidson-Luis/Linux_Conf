# Compartilhar pasta
Para partilhar uma pasta na rede em um computador com Ubuntu 24, você deve instalar o Samba (o protocolo SMB/CIFS para partilha com outros sistemas, incluindo Windows) via terminal, definir um utilizador e palavra-passe para aceder à pasta, e configurar a partilha no ficheiro smb.conf. Depois, reinicie o serviço Samba e aceda à pasta a partir de outro computador na rede, usando o IP do computador Ubuntu no formato `\\<IP_do_Ubuntu>\`. 
1. Instale o Samba no Ubuntu

    Abra o terminal (Ctrl + Alt + T). 

Execute os seguintes comandos para instalar o pacote e atualizar a lista de pacotes: 

Código
```
    sudo apt update
    sudo apt install samba smbclient
```
Insira a sua palavra-passe quando solicitado e confirme a instalação, digitando "S" (para português) ou "Y" (para inglês). 

2. Crie um utilizador para partilha (se necessário) 

    Para aceder à pasta partilhada, é recomendado criar um utilizador e definir uma palavra-passe: 

Código
```
    sudo smbpasswd -a [seu_nome_de_usuario]
```
Insira e confirme a palavra-passe do utilizador. 

3. Configure a pasta no ficheiro smb.conf 

    Abra o ficheiro de configuração do Samba com um editor de texto: 

Código
```
    sudo nano /etc/samba/smb.conf
```
Vá para o final do ficheiro e adicione o seguinte bloco: 

Código
```
    [NomeDaPasta]
       comment = Pasta de Exemplo
       path = /caminho/para/a/pasta/que/quer/partilhar
       browseable = yes
       read only = no
       guest ok = no
       valid users = [seu_nome_de_usuario]
```
NomeDaPasta: O nome que a pasta terá na rede. 

path: O caminho completo para a pasta que deseja partilhar. 
[seu_nome_de_usuario]: O nome de utilizador que criou no passo 2. 

Guarde o ficheiro e saia do editor (Ctrl + X, Y, Enter). 

4. Reinicie o serviço Samba 

Para que as alterações tenham efeito, reinicie o serviço Samba: 

Código

    sudo systemctl restart smbd.service

5. Aceda à pasta a partir de outro computador 

    Encontre o endereço IP do seu computador Ubuntu (pode usar ip addr show).
    Em outro computador (Windows ou outro Linux), abra o explorador de ficheiros e digite na barra de endereços: \\<IP_do_Ubuntu>\NomeDaPasta.
    Insira as credenciais (utilizador e palavra-passe) que definiu para aceder à pasta.
