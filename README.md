# Ansible-Playbook

Este repositório contém uma coleção de *scripts*, usando *Ansible*, para o provisionamento de um *home server*. Além disso, também provisionam uma forma de acesso remoto à rede local do usuário, utilizando um serviço de VPN instalado em um servidor na nuvem, como um *VPS - Virtual Private Server*. São provisionados os seguintes serviços:

## Traefik

<img align="left" width="150" src="https://cdn.jsdelivr.net/gh/walkxhub/dashboard-icons/png/traefik.png">

*Proxy* reverso. Age como ponto de entrada dos pacotes HTTP/HTTPS dos serviços (portas 80 e 443), adicionando funcionalidades à esses serviços, como:

- Suporte à HTTPS para serviços que não o suportam nativamente
- Suporte à autenticação/*SSO* (*Single Sign-On*)
- Redirecionamento automático de HTTP para HTTPS
- Gerenciamento e Auto-renovação de certificados digitais, assinados por *Let's Encrypt*

<br clear="left"/>

## Pi-Hole

<img align="left" width="150" src="https://cdn.jsdelivr.net/gh/walkxhub/dashboard-icons/png/pihole.png">

Servidor *DNS*(*Domain Name System*). Age como um bloqueador de anúncios em toda a rede local, sob o princípio de *DNS sinkhole*, ou seja, envia endereços não-roteáveis para um conjunto específico de domínios, neste caso, provedores de anúncios como, por exemplo, o *Google Ads*.

  Também é utilizado nesta aplicação como um servidor de *DNS* local, sendo capaz de resolver endereços internos da rede local, permitindo o acesso aos serviços utilizando um nome de domínio/subdomínio como `home.lan`, ao invés de um endereço IP como `192.168.10.35`.

<br clear="left"/>

## Nextcloud

<img align="left" width="150" src="https://cdn.jsdelivr.net/gh/walkxhub/dashboard-icons/png/nextcloud.png">

Serviço que opera como uma nuvem privada, sendo um substituto auto-hospedado à serviços como *Google Drive*, *Dropbox* e *iCloud*. Algumas das funções presentes são:

- *Backup* automático de diretórios utilizando clientes do *Nextcloud*, disponíveis para Android, iOS, Windows, Linux e macOS. Com foco no *backup* automático de fotos nos clientes *mobile* (*Android* e *iOS*), funcionalidade parecida com a apresentada por *Google Photos*;

- Função de gerência e sincronização de calendários, contatos e histórico de ligações, através dos protocolos CardDAV, CalDAV e Webcal.

- Presença de uma *interface web* e aplicativos de clientes com uma experiência que remete à de serviços baseados em nuvem como *Google Drive*.

<br clear="left"/>

## Home Assistant

<img align="left" width="150" src="https://cdn.jsdelivr.net/gh/walkxhub/dashboard-icons/png/home-assistant.png">

**Work in Progress...**

<br clear="left"/>

## Homarr

<img align="left" width="150" src="https://cdn.jsdelivr.net/gh/walkxhub/dashboard-icons/png/homarr.png">

Este serviço apresenta uma *dashboard* em sua *interface web* com *links* para todos os outros serviços hospedados na rede. Desta forma, serve como um ponto de entrada para estas aplicações, além de funcionar como um "*hub*" do *home server*.
<br clear="left"/>

## Media Server

Um conjunto de serviços integrados com a função de **requisição**, **obtenção**, **indexação** e **reprodução** de diversos tipos de mídia. Os serviços utilizados, bem como suas respectivas funções na cadeia de gerenciamento de mídia são:

### Jellyseerr

<img align="left" width="150" src="https://cdn.jsdelivr.net/gh/walkxhub/dashboard-icons/png/jellyseerr.png">

Serviço responsável pela **requisição** dos arquivos de mídia. Através de sua interface, os usuários podem requerir por programas de TV ou filmes à serem obtidos por outros serviços da cadeia.

<br clear="left"/>

### Radarr, Sonarr, Lidarr

<img align="left" width="150" src="https://cdn.jsdelivr.net/gh/walkxhub/dashboard-icons/png/radarr.png">
<img align="left" width="150" src="https://cdn.jsdelivr.net/gh/walkxhub/dashboard-icons/png/sonarr.png">
<img align="left" width="150" src="https://cdn.jsdelivr.net/gh/walkxhub/dashboard-icons/png/lidarr.png">

Os três serviços têm a função de **requisição** e **indexação** dos arquivos de mídia. Isso se baseia na busca em indexadores pelos arquivos requisitados (tanto através da *interface web* da aplicação, quanto de outros serviços, como o **jellyseerr**), de acordo com metados relevantes a aquele tipo de mídia. Cada um dos três aplicativos é focado em um tipo de mídia, sendo estes:

- **Radarr:** Voltado para obtenção de filmes;
- **Lidarr:** Voltado para músicas;
- **Sonarr:** Voltado para séries, seriados, programas de TV e *anime*.

<br clear="left"/>

### Prowlarr

<img align="left" width="150" src="https://cdn.jsdelivr.net/gh/walkxhub/dashboard-icons/png/prowlarr.png">

Este é o serviço responsável por gerenciar os indexadores utilizados na busca de arquivos nos aplicativos Radarr, Sonarr e Lidarr; proporcionando uma forma centralizada para gerência destes indexadores através de sua **interface web**.

<br clear="left"/>

### Transmission

<img align="left" width="150" src="https://cdn.jsdelivr.net/gh/walkxhub/dashboard-icons/png/transmission.png">

Cliente *BitTorrent*. Na cadeia de gerenciamento de mídia, é o responsável pela **obtenção** dos arquivos encontrados através dos serviços Radarr, Sonarr e  Lidarr.

<br clear="left"/>

### Jellyfin

<img align="left" width="150" src="https://cdn.jsdelivr.net/gh/walkxhub/dashboard-icons/png/jellyfin.png">

Serviço reponsável pela **reprodução** dos títulos já obtidos nas etapas anteriores da cadeia de gerência de mídia. Através de sua *interface web*, os usuários podem pesquisar e reproduzir os títulos de suas bibiliotecas.

<br clear="left"/>
