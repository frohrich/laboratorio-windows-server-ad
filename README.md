# Laboratório de Rede Corporativa com Windows Server e Active Directory

## Sobre o projeto

Este projeto simula uma pequena rede corporativa utilizando máquinas virtuais no Oracle VirtualBox.

O objetivo foi criar um ambiente com Windows Server e Windows 10 cliente, configurando rede interna, domínio, Active Directory, usuários e login em domínio.

Este laboratório foi desenvolvido como prática do curso **Curso Prático de Redes de Computadores e Internet**, da plataforma Curso em Vídeo.

---

## Tecnologias e ferramentas utilizadas

- Oracle VirtualBox
- Windows Server 2025
- Windows 10 Pro
- Active Directory Domain Services
- DNS
- Roteamento e NAT
- Configuração de IP fixo
- Rede interna no VirtualBox
- Prompt de Comando do Windows

---

## Estrutura do laboratório

O ambiente foi montado com duas máquinas virtuais:

- Windows Server
- Windows 10 Cliente

O Windows Server possui duas placas de rede:

    Placa 1 - Internet
    Modo: Bridge
    IP: 192.168.15.254
    Máscara: 255.255.255.0
    Gateway: 192.168.15.1

    Placa 2 - Rede Local
    Modo: Rede Interna
    IP: 172.16.0.254
    Máscara: 255.255.0.0
    Gateway: vazio

O Windows 10 cliente foi configurado na rede interna:

    IP: 172.16.0.1
    Máscara: 255.255.0.0
    Gateway: 172.16.0.254
    DNS: 172.16.0.254

---

## Diagrama da rede

    Internet / Roteador
    192.168.15.1
            ↓
    Windows Server
    192.168.15.254 / 172.16.0.254
            ↓
    Windows 10 Cliente
    172.16.0.1

---

## Configurações realizadas

Durante o laboratório foram realizadas as seguintes configurações:

- Criação de máquinas virtuais no Oracle VirtualBox.
- Instalação do Windows Server 2025.
- Instalação do Windows 10 Pro.
- Configuração de duas placas de rede no servidor.
- Configuração de rede interna entre servidor e cliente.
- Configuração de IP fixo no servidor e no cliente.
- Configuração de gateway e DNS no cliente apontando para o servidor.
- Instalação e configuração do Active Directory Domain Services.
- Criação do domínio `hrbr.local`.
- Criação de usuários no Active Directory.
- Organização dos usuários em uma Unidade Organizacional chamada `vendas`.
- Ingresso do Windows 10 no domínio.
- Login no Windows 10 utilizando usuário do domínio.

---

## Active Directory

Foi criado o domínio:

    hrbr.local

Dentro do Active Directory, foi criada uma Unidade Organizacional chamada:

    vendas

Nessa unidade foram adicionados usuários representando funcionários da empresa.

---

## Validação do domínio

Após ingressar o Windows 10 no domínio, foi realizado login com usuário do Active Directory.

A validação foi feita pelo Prompt de Comando utilizando:

    echo %USERDOMAIN%

Resultado:

    HRBR

Também foi utilizado:

    whoami

Resultado:

    hrbr\gabrielvitor

Isso confirmou que o login foi realizado com usuário do domínio.

---

## Problemas encontrados e soluções

Durante o laboratório, alguns problemas foram encontrados:

### Firewall bloqueando ping

Mesmo com os IPs corretos, o Windows 10 não conseguia pingar o Windows Server.

A causa foi o firewall do Windows Server bloqueando solicitações ICMP.

Solução aplicada:

    File and Printer Sharing (Echo Request - ICMPv4-In)

A regra foi habilitada no firewall do Windows Server.

---

### Windows 10 Home não ingressa em domínio

Durante os testes, foi identificado que o Windows 10 Home não permite ingresso em domínio Active Directory.

Solução aplicada:

    Instalação do Windows 10 Pro

---

### DNS para ingresso no domínio

Para o Windows 10 localizar corretamente o domínio `hrbr.local`, o DNS do cliente precisou apontar para o servidor:

    DNS: 172.16.0.254

---

## Prints do laboratório

### Máquinas virtuais no VirtualBox

![VirtualBox com Windows Server e Windows 10](01-virtualbox-vms.png)

### IP da placa de Internet do Windows Server

![IP servidor internet](02-ip-servidor-internet.png)

### IP da placa de rede local do Windows Server

![IP servidor rede local](03-ip-servidor-rede-local.png)

### IP do cliente Windows 10

![IP cliente Windows 10](04-ip-cliente-windows10.png)

### Active Directory com usuários

![Active Directory usuários](05-active-directory-usuarios.png)

### Windows 10 conectado ao domínio

![Cliente no domínio](06-cliente-no-dominio.png)

### Login no domínio pelo CMD

![Login domínio CMD](07-login-dominio-cmd.png)

---

## Aprendizados

Com este laboratório, foi possível praticar conceitos importantes de redes e infraestrutura, como:

- Modelo cliente-servidor.
- Configuração de IP fixo.
- Gateway e DNS.
- Rede interna em ambiente virtual.
- Windows Server.
- Active Directory.
- Criação e organização de usuários.
- Ingresso de cliente no domínio.
- Testes de conectividade.
- Resolução de problemas com firewall e DNS.

---

## Conclusão

Este projeto permitiu simular uma rede corporativa básica utilizando Windows Server e Windows 10.

O laboratório representa uma estrutura comum em empresas, onde o servidor centraliza o controle de usuários, permissões, domínio e serviços de rede.

Esse conhecimento é importante para áreas como suporte técnico, help desk, infraestrutura de TI e administração de redes.
