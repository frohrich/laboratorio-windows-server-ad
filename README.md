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

```text
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