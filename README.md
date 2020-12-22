# Docker-Configuration
###### Tutorial para instalação, execução e reinstalação do docker

# Tabela de Conteúdos

* [Instalando Docker](#ancora1)
  * [Instalando Docker no Windows](#ancora1.1)
  * [Instalando Docker no MacOS](#ancora1.2)
* [Reutilizando um projeto](#ancora2)
  
<a id="ancora1"></a>
# Instalando Docker

<a id="ancora1.1"></a>
## Docker Windows 10

#### Tutorial de como baixar abaixo, mas irei explicar agora
* [Docker - Windows 10](https://www.notion.so/Docker-Desktop-WSL-2-fc6af93d3cac4de9a4a185f78c4a9566#706ab91aa12e4ae482467368964f772d)

#### Abra o Powershell como admin e execute o comando. Esse comando irá ativar o recurso do Windows **Subsistema do Windows para Linux**.:
```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

#### Em seguida, rode o comando. Esse comando irá ativar o recurso do Windows Plataforma de Máquina Virtual.
```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

#### Reinicie a sua máquina para aplicar as alterações anteriores.

#### Abra o Powershell como admin e execute o comando:
```powershell
wsl --set-default-version 2
```

#### Caso apareça a mensagem ```WSL 2 requires an update to its kernel component. For information please visit https://aka.ms/wsl2kernel``` ou ```Erro: 0x1bc```. Instale: 
* [Pacote de atualização do kernel do linux](https://docs.microsoft.com/pt-br/windows/wsl/install-win10#step-4---download-the-linux-kernel-update-package).

<a id="ancora1.2"></a>
## Docker Mac

#### Necessário somente baixar o docker e instalar o executável.
* [Docker - MacOS](https://hub.docker.com/editions/community/docker-ce-desktop-mac)

<a id="ancora2"></a>
# Reutilizando um projeto

#### Partimos de uma imagem existente
```javascript
FROM node:10
```

#### Definimos a pasta e copiamos 
```javascript
WORKDIR /usr/app
COPY . ./
```

#### Instalamos as dependências
```javascript
RUN yarn
```

#### Qual porta queremos expor
```javascript
EXPOSE 3333
```

#### Executamos nossa aplicação
```javascript
CMD yar start
```
