
# Instalação do pacote OpenSSH no Linux Ubuntu 18.04 LTS

Descricao de como instalar o OpenSSH no no Linux Ubuntu Server 18.04 LTS


## Instalação

Primeiramente atualize o sistema:

```bash
sudo apt update
sudo apt upgrade
```
Instalando o pacote openssh-server
```bash
  sudo apt install openssh-server
```
Habilitando o serviço:
```bash
sudo systemctl enable ssh
```
Iniciando o serviço:
```bash
sudo systemctl start ssh
```
Verifique se o serviço esta rodando:
```bash
sudo systemctl status ssh
```
Se não estiver executando, habilite o servidor ssh e inicie-o da seguinte forma digitando o comando systemctl:
```bash
sudo systemctl enable ssh
sudo systemctl start ssh
```
Depois voce deve configurar o firewall Ubuntu Linux chamado ufw.
```bash
sudo ufw allow ssh
sudo ufw enable
sudo ufw status
```
Agora você pode fazer login do seu computador desktop com Linux utilizando o comando:
```bash
ssh nomeUsuario@DnsOuIpServidor
```

## Como configuro a autenticação de chave pública?

Abra o Terminal e digite os seguintes comandos se o diretório .ssh não existir:

```bash
mkdir  -p  $HOME / .ssh
chmod 0700 $HOME / .ssh
```
### 1. Crie o par de chaves

No computador "Cliente", gere um par de chaves para o protocolo.
```bash
ssh-keygen  -t rsa
```

Você precisa definir o local e o nome do par de chaves. Eu recomendo que você use o local padrão se você ainda não tiver outra chave lá, por exemplo: $HOME/.ssh/id_rsa. Você será solicitado a fornecer uma senha (senha) para sua chave privada. Sugiro que você configure uma senha quando solicitado. Você deve ver dois novos arquivos no diretório $HOME/.ssh/:
- `$HOME/.ssh/id_rsa` – contém sua chave privada.
- `$HOME/.ssh/id_rsa.pub` – contém sua chave pública.

### 2. Instale a chave pública no servidor remoto

Use o comando `ssh-copy-id` para copiar seu arquivo de chave pública (por exemplo, $HOME/.ssh/id_rsa.pub) para sua conta no servidor/host remoto (por exemplo, usuario@servidor.local). Para isso, digite o seguinte comando em seu computador "Cliente":

```bash
ssh-copy-id -i  $HOME/.ssh/id_rsa.pub usuario@servidor.local
```
### 3. Teste

Use o comando `ssh-copy-id` para copiar seu arquivo de chave pública (por exemplo, $HOME/.ssh/id_rsa.pub) para sua conta no servidor/host remoto (por exemplo, usuario@servidor.local). Para isso, digite o seguinte comando em seu computador "Cliente":

```bash
ssh-copy-id -i  $HOME/.ssh/id_rsa.pub usuario@servidor.local
```
