---
title: Configurar fluxos de IU no dispositivo | Microsoft Docs
description: Configurar fluxos de IU no dispositivo
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/24/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 97456d637dd272a465559d4cee8fb1d17fe3de8d
ms.sourcegitcommit: bba5bd4ae3879b6bf1521d8ed636374fe09709e7
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/01/2020
ms.locfileid: "80524676"
---
# <a name="set-up-ui-flows"></a>Configurar fluxos de IU

Para poder utilizar o dispositivo para criar fluxos de IU, terá de assegurar que o dispositivo cumpre os requisitos aqui descritos.

> [!TIP]
> Antes de criar um fluxo de IU, verifique a [lista de conectores](https://flow.microsoft.com/connectors/) para ver se a aplicação que quer automatizar já tem um conector. Se já tiver, considere criar um fluxo em vez de um fluxo de IU. Também poderá criar [o seu próprio conetor](https://docs.microsoft.com/connectors/custom-connectors/).

## <a name="prerequisites"></a>Pré-requisitos

- Um plano [pago](https://flow.microsoft.com/pricing/) ou de [avaliação](https://flow.microsoft.com/manage/) do Power Automate.

- Uma conta escolar ou profissional para iniciar sessão no dispositivo Windows com privilégios de administrador e no Power Automate.

- Um dispositivo com o Windows 10 Pro, o Windows Server 2016 ou o Windows Server 2019.

- O browser [Microsoft Edge](https://www.microsoft.com/edge/) (versão 80 ou posterior) ou Google Chrome.

- Um [ambiente](https://docs.microsoft.com/power-platform/admin/environments-overview) com uma [base de dados do Common Data Service](https://docs.microsoft.com/power-platform/admin/create-database).

- Um teclado suportado ligado.

## <a name="limitations"></a>Limitações

São necessárias as versões mais recentes de cada componente para gravar, testar ou executar fluxos de IU.

Não há suporte para o seguinte:
- As instalações do Windows 10 Home não são suportadas.

-   Fluxos de IU para Computador

    -   Vários monitores
    -   Duplo clique, passagem do rato, entrada por toque/caneta
    -   Interações no Windows (Explorador de ficheiros, menu de inicialização, barra de tarefas e etc.)

-   Fluxos de IU para a Web

    -   Clicar com o botão direito do rato.
    -   As informações das sessões dos utilizadores (por exemplo, cookies) não serão reutilizadas durante a reprodução. Terá de editar o script para incorporar as informações de início de sessão quando for solicitado pelos sites.

Encontra as limitações específicas da funcionalidade incluídas na documentação de cada funcionalidade.

## <a name="install-ui-flows-on-your-device"></a>Instalar fluxos de IU no dispositivo

O programa de instalação de fluxos de IU contém todos os componentes necessários para gravar, editar e testar fluxos de IU para computador. 

>[!IMPORTANT]
>O programa de instalação de fluxos de IU instala o componente WebDriver e a extensão do browser dos fluxos de IU. Ambos são necessários para gravar, testar e executar fluxos de IU para computador.

Siga estes passos para instalar a aplicação de fluxos de IU:

1. [Transfira o programa de instalação dos fluxos de IU](https://go.microsoft.com/fwlink/?linkid=2102613).
1. Abra o ficheiro **Setup.Microsoft.PowerAutomate.UIflow.exe**. Este ficheiro encontra-se provavelmente na pasta **Transferências**, depois de o ter transferido no passo anterior.
1. Siga as instruções do programa de instalação **Configuração de fluxos de IU** para concluir a instalação.

### <a name="set-data-collection-options"></a>Definir opções de recolha de dados

Durante a instalação, pode alterar as predefinições se não quiser enviar dados de utilização para a Microsoft. Para o fazer, desselecione a opção **Permitir que a Microsoft recolha dados de utilização para melhorar os fluxos de IU**.

![Imagem a mostrar as opções de recolha de dados](../media/ui-flows-setup/data-collection-settings.png)

## <a name="activate-the-ui-flows-browser-extension"></a>Ativar a extensão do browser dos fluxos de IU 

Depois de o programa de instalação dos fluxos de IU ter sido concluído, o browser vai pedir-lhe para ativar a extensão.

- No [Microsoft Edge](https://www.microsoft.com/edge/) (versão 80 ou posterior), selecione cada ícone de aviso no canto superior direito do browser e, em seguida, selecione **Ativar extensão**.
-   No Google Chrome, selecione **Ativar extensão**, quando lhe for pedido.  

> [!TIP]
> Se não viu o pedido no browser, verifique o seguinte:
> - Tem de utilizar o [Microsoft Edge](https://www.microsoft.com/edge/) (versão 80 ou posterior) ou o Google Chrome.
> - Pode ser necessário ativar a extensão manualmente. Com o Microsoft Edge, navegue para **edge://extensions** ou, com o Google Chrome, navegue para **chrome://extensions**.
> - Se a extensão dos fluxos de IU do Power Automate não aparecer, poderá reinstalá-la com o [programa de instalação dos fluxos de IU](https://go.microsoft.com/fwlink/?linkid=2102613).


## <a name="install-selenium-ide-to-automate-web-applications"></a>Instalar o Selenium IDE para automatizar as aplicações Web

O IDE Selenium é uma ferramenta open source que lhe permite gravar e reproduzir interações humanas em sites.

Com os fluxos de IU, pode executar scripts do IDE Selenium no Power Automate e mantê-los armazenados de forma segura (com a governação de TI adequada) no Common Data Service.

Siga estes passos para instalar o IDE Selenium:

1. [Transfira e instale](https://go.microsoft.com/fwlink/?linkid=2107665) o Selenium IDE para o [Microsoft Edge](https://www.microsoft.com/edge/) (versão 80 ou posterior) ou o Google Chrome.

1. No Microsoft Edge (versão 80 ou posterior), selecione **Permitir extensões de outras lojas** e selecione **Adicionar ao Chrome**.

## <a name="install-the-on-premises-data-gateway"></a>Instalar o gateway de dados no local

Precisará do gateway para acionar o fluxo de IU de um [evento, agendamento ou fluxo de botão](../getting-started.md#types-of-flows) num dispositivo remoto.

>[!TIP]
>O gateway não é necessário, caso pretenda apenas criar, editar e testar os fluxos de IU no dispositivo.

[Instale o gateway de dados no local](https://docs.microsoft.com/data-integration/gateway/service-gateway-install), caso precise dele.


>[!IMPORTANT]
>Quando instalar o gateway, ele assume por predefinição a região que o Power Automate utiliza.


## <a name="setup-ui-flows-connections-and-machine-credentials"></a>Configurar ligações de fluxos de IU e credenciais da máquina

1. Inicie sessão no [Power Automate](https://powerautomate.microsoft.com).
1. Expanda a opção **Dados** no lado esquerdo do ecrã.
1. Selecione **Ligações**.

   ![Uma captura de ecrã a mostrar o separador Ligações](../media/ui-flows-setup/connections-tab.png)

1. Selecione Nova ligação.

   ![Uma captura de ecrã a mostrar uma ligação](../media/ui-flows-setup/new-connection.png)

1. Procure *Fluxo de IU* e, em seguida, selecione **Fluxos de IU**.

   ![Uma captura de ecrã a mostrar a caixa de pesquisa](../media/ui-flows-setup/search-ui-flow.png)

1. Forneça as informações do gateway e as credenciais do dispositivo: 

    - **Domínio e Nome de utilizador**: forneça a sua conta do dispositivo. Pode utilizar uma conta local com o nome do utilizador (por exemplo, "NOMEDOCOMPUTADOR\\Utilizador" ou "local\\Utilizador") ou uma conta do Active Directory como "DOMÍNIO\\Utilizador".
    - **Palavra-passe**: a palavra-passe da sua conta.
    - **Escolher um gateway**: Selecione o gateway que pretende utilizar.

      ![Uma captura de ecrã a mostrar onde introduzir as credenciais para a ligação](../media/ui-flows-setup/credentials-screen.png)

1. Selecione **Criar**.

## <a name="troubleshoot-missing-gateway"></a>Resolução de problemas de um gateway em falta

Poderá não encontrar o gateway na lista durante a criação da ligação pelos motivos que se seguem:

- O gateway poderá estar instalado numa região diferente da região do Power Automate. Para resolver este problema, desinstale o gateway do dispositivo e, em seguida, reinstale-o ao selecionar [a região correta do Power Automate](../regions-overview.md#region-mappings-for-power-automate-and-gateways).
- O gateway foi eliminado pelo proprietário.

## <a name="supported-keyboard-layouts"></a>Esquemas de teclado suportados

- Teclado dos EUA – Inglês (Estados Unidos)
- Teclado dos EUA – Inglês (Austrália)
- Teclado dos EUA – Inglês (Canadá)
- Microsoft Pinyin – Chinês (Han Simplificado, China)
- Teclado alemão – Alemão (Alemanha)
- Microsoft IME – Japonês (Japão)
- Teclado do Reino Unido – Inglês (Reino Unido)
- Teclado francês – Francês (França)
- Teclado russo – Russo (Rússia)
- Teclado Português (ABNT do Brasil) – Português (Brasil)
- Teclado Português (ABNT2 do Brasil) – Português (Brasil)
- Microsoft IME – Coreia (Coreia do Sul)
- Teclado espanhol – Espanhol (Espanha)
- Teclado italiano – Italiano (Itália)
- Teclado da América Latina – Espanhol (México)
- Teclado polaco (programadores) – Polaco (Polónia)
- Teclado internacional dos Estados Unidos – Neerlandês (Países Baixos)
- Teclado Turco Q – Turco (Turquia)
- Teclado da Índia – Inglês (Índia)

## <a name="supported-languages"></a>Idiomas suportados

Eis os idiomas que o fluxo de IU suporta, para além do inglês:

|||||
----|-----|-----|--------
Basco  | Francês    | Letão   | Eslovaco
Búlgaro   |   Galego    |   Lituano  |   Esloveno
Catalão |   Alemão      |Malaio  |   Espanhol
Chinês (Simplificado)    |   Grego   |   Norueguês   |   Sueco
Chinês (Tradicional)   |   Hindi   |   Polaco  |   Tailandês
Croata    |   Húngaro   |   Português (Brasil) |   Turco
Checo   |   Indonésio  |   Português (Portugal)       |Ucraniano
Dinamarquês  |   Italiano |   Romeno    |   Vietnamita
Neerlandês       |Japonês   |   Russo 
Estónio    |Cazaque |   Sérvio (Cirílico, Sérvia)  
Finlandês     |Coreano     |Sérvio (Latim, Sérvia)

## <a name="uninstall-ui-flows"></a>Desinstalar os fluxos de IU

1. Abra o menu **iniciar** > **Definições** > **Aplicações**.
1. Procure **Fluxos de IU** e selecione essa opção.
1. Selecione **Desinstalar**.

## <a name="learn-more"></a>Saiba mais

- [Atualizar os seus fluxos de IU](upgrade.md) a partir de versões anteriores
- Saiba como [criar fluxos de IU para computador](create-desktop.md).
- Saiba como [criar fluxos de IU para a Web](create-web.md).
- Saiba como executar [fluxos de IU](run-ui-flow.md).
- Saiba como [gerir fluxos de IU](manage.md).
- Saiba mais sobre o [gateway no local](../gateway-reference.md#use-a-gateway)
