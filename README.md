# 🐧 Ubuntu Auto Install

Este projeto automatiza a instalação do **Ubuntu Desktop** utilizando o recurso oficial de **Autoinstall (Cloud-Init)**.

A automação permite instalar o sistema operacional já configurado com:

- usuário criado automaticamente

- idioma e teclado definidos

- fuso horário configurado

- pacotes essenciais instalados

- aplicações via Snap

- codecs e drivers automáticos

- atualização do sistema durante a instalação

Isso é útil para:

- laboratórios de informática

- ambientes corporativos

- provisionamento rápido de máquinas

- padronização de sistemas

- Dev environments


# 🏗 Arquitetura do Projeto

A arquitetura do projeto é baseada em **Infraestrutura como Código (IaC)** usando o mecanismo nativo do Ubuntu.

Fluxo da instalação:

```
`Boot da ISO do Ubuntu`

`        │`

`        ▼`

`Cloud-Init inicia`

`        │`

`        ▼`

`Arquivo autoinstall.yaml é carregado`

`        │`

`        ▼`

`Configuração automática do sistema`

`        │`

`        ▼`

`Instalação de pacotes e snaps`

`        │`

`        ▼`

`Configuração final do usuário`

`        │`

`        ▼`

`Reboot automático`
```


# 📂 Estrutura do Projeto

```
`ubuntu-auto-install`

`│`

`├── autoinstall.yaml`

`└── README.md`
```


# 📄 Arquivo Principal

## autoinstall.yaml

Este arquivo contém todas as configurações da instalação automatizada.

Ele utiliza o padrão:

```
`cloud-init`
```

e a estrutura oficial:

```
`autoinstall`
```


# ⚙️ Estrutura do Arquivo de Configuração

## 1 — Versão do Autoinstall

Define a versão do sistema de automação.

```
`autoinstall:`

`  version: 1`
```


## 2 — Identidade do Sistema

Configura usuário principal, hostname e senha.

```
`identity:`

`  realname: Sandro Nogueira`

`  hostname: ubuntu-desktop`

`  username: sandro`

`  password: (hash criptografado)`
```

### Explicação

- realname → nome do usuário

- hostname → nome da máquina

- username → usuário principal do sistema

- password → senha criptografada

A senha é gerada com:

```
`mkpasswd`
```


## 3 — Localização do Sistema

Define idioma, teclado e timezone.

```
`locale: pt\_BR.utf8`

`keyboard:`

`  layout: br`

`timezone: America/Sao\_Paulo`
```


# 📦 Instalação Automática de Pacotes

Durante a instalação do sistema, os seguintes pacotes são instalados automaticamente:

```
`libreoffice`

`gimp`

`git`

`wget`

`vim`

`htop`

`flameshot`

`openjdk-17-jdk`
```

### Finalidade dos pacotes

| **Pacote** | **Função** |
| :-: | :-: |
| LibreOffice | Suite de escritório |
| GIMP | Editor de imagens |
| Git | Controle de versão |
| Wget | Download via terminal |
| Vim | Editor de texto |
| Htop | Monitor de processos |
| Flameshot | Captura de tela |
| OpenJDK 17 | Ambiente Java |


# 📦 Instalação de Aplicações Snap

O projeto também instala aplicações via Snap automaticamente.

```
`snaps:`
```

Aplicações incluídas:

- Spotify

- Visual Studio Code

- Eclipse IDE

Configuração:

```
`spotify`

`canal: stable`

`vscode`

`canal: stable`

`eclipse`

`canal: latest/stable`

`modo classic`
```


# 🎧 Instalação de Codecs

Ativa suporte multimídia automaticamente.

```
`codecs:`

`  install: true`
```

Isso instala:

- codecs de vídeo

- codecs de áudio

- suporte multimídia completo


# 🖥 Instalação de Drivers

O sistema instala automaticamente drivers recomendados.

```
`drivers:`

`  install: true`
```

Inclui:

- drivers de GPU

- drivers proprietários quando disponíveis

- firmware necessário


# 🔄 Atualizações do Sistema

O sistema é atualizado durante a instalação.

```
`updates: all`
```

Isso garante que o sistema já saia atualizado após a instalação.


# 🔁 Reinício Automático

Após finalizar a instalação:

```
`shutdown: reboot`
```

A máquina reinicia automaticamente.


# 🧠 Fluxo Completo da Automação

```
`Inicialização do instalador Ubuntu`

`        │`

`        ▼`

`Cloud-init carrega autoinstall.yaml`

`        │`

`        ▼`

`Configuração do sistema`

`        │`

`        ▼`

`Criação de usuário`

`        │`

`        ▼`

`Configuração regional`

`        │`

`        ▼`

`Instalação de pacotes`

`        │`

`        ▼`

`Instalação de snaps`

`        │`

`        ▼`

`Instalação de drivers`

`        │`

`        ▼`

`Atualização do sistema`

`        │`

`        ▼`

`Reboot automático`
```


# 🚀 Como Usar Este Projeto

## 1 — Baixar a ISO do Ubuntu

Baixe a versão:

Ubuntu 22.04 ou superior.


## 2 — Inserir o autoinstall na ISO ou no servidor

Você pode usar:

- Ventoy

- PXE Boot

- Cloud-init server

- HTTP seed

Exemplo usando seed:

```
`ds=nocloud;s=http://server/autoinstall/`
```


## 3 — Boot na máquina

Inicie o instalador com a opção de autoinstall.


# 🏢 Casos de Uso

Este projeto é ideal para:

- Laboratórios de faculdade

- Ambientes corporativos

- Dev workstations

- Infraestrutura de TI

- Provisionamento rápido de PCs

- Padronização de ambientes Linux


# 🔐 Segurança

Boas práticas recomendadas:

- Alterar senha após instalação

- Usar chave SSH

- Remover usuário padrão em ambientes críticos

- Utilizar criptografia de disco


# 📈 Melhorias Futuras

Possíveis evoluções do projeto:

- Adicionar configuração de disco automática

- Particionamento avançado

- Instalação de Docker

- Instalação de Kubernetes

- Configuração de rede estática

- Integração com Ansible

- Provisionamento completo de DevOps


# 🧩 Arquitetura do Provisionamento

```
`Infraestrutura como Código`

`        │`

`        ▼`

`Cloud-init`

`        │`

`        ▼`

`Autoinstall YAML`

`        │`

`        ▼`

`Provisionamento Automatizado`

`        │`

`        ▼`

`Sistema Ubuntu configurado`
```


Se quiser, posso fazer algo **muito interessante para esse projeto**:

- transformar isso em um **projeto profissional de automação Linux**

- adicionar instalação automática de:

  - Docker

  - Node

  - Java

  - Kubernetes

  - ferramentas de segurança

- criar um **auto install para laboratório completo de TI**.

