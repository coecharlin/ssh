
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
```bash
```
