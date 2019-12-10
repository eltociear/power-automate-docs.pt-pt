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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e7d5e4219c46703019f995b625c6d672a767018a
ms.sourcegitcommit: 683127e3655abeec9ae6e86fcdf4ac2256101d08
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/06/2019
ms.locfileid: "74882115"
---
# <a name="set-up-ui-flows"></a>Configurar fluxos de IU

[Este tópico é uma documentação de pré-lançamento e está sujeito a alterações.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

> [!IMPORTANT]
> A funcionalidade dos fluxos de IU está atualmente a ser implementada nas regiões. Se não vir a funcionalidade no seu ambiente, não conseguirá criar fluxos de IU. Se obtiver um erro ao tentar executá-la num fluxo, tente novamente mais tarde.

Para poder utilizar o dispositivo para criar fluxos de IU, terá de assegurar que o dispositivo cumpre os requisitos aqui descritos.

> [!TIP]
> Antes de criar um fluxo de IU, verifique a [lista de conectores](https://flow.microsoft.com/connectors/) para ver se a aplicação que quer automatizar já tem um conector. Se já tiver, considere criar um fluxo em vez de um fluxo de IU. Também poderá criar [o seu próprio conetor](https://docs.microsoft.com/connectors/custom-connectors/).

## <a name="prerequisites"></a>Pré-requisitos

- Um plano [pago](https://flow.microsoft.com/pricing/) ou de [avaliação](https://flow.microsoft.com/manage/) do Power Automate.

- Uma conta escolar ou profissional para iniciar sessão no dispositivo Windows com privilégios de administrador e no Power Automate.

- Um dispositivo com o Windows 10, o Windows Server 2016 ou o Windows Server 2019.
- Um teclado dos EUA (QWERTY) ligado.

- A [próxima versão do Microsoft Edge](https://www.microsoftedgeinsider.com) ou Google Chrome.

- Um [ambiente](https://docs.microsoft.com/power-platform/admin/environments-overview) com uma [base de dados do Common Data Service](https://docs.microsoft.com/power-platform/admin/create-database).

## <a name="limitations"></a>Limitações

Os fluxos de IU (pré-visualização) estão disponíveis em inglês.

Não há suporte para o seguinte:

-   Fluxos de IU para Computador

    -   Vários monitores
    -   Máquinas virtuais
    -   Duplo clique, passagem do rato, entrada por toque/caneta
    -   Interações no Windows (Explorador de ficheiros, menu de inicialização, barra de tarefas e etc.)

-   Fluxos de IU para a Web

    -   Clicar com o botão direito do rato
    -   As informações das sessões dos utilizadores (por exemplo, cookies) não serão reutilizadas durante a reprodução. Terá de editar o script para incorporar as informações de início de sessão quando for solicitado pelos sites.

Encontra as limitações específicas da funcionalidade incluídas na documentação de cada funcionalidade.

## <a name="install-ui-flows-on-your-device"></a>Instalar fluxos de IU no dispositivo

O programa de instalação de fluxos de IU contém todos os componentes necessários para gravar, editar e testar fluxos de IU para computador. 

>[!IMPORTANT]
>O programa de instalação de fluxos de IU instala o componente WebDriver e a extensão do browser dos fluxos de IU. Ambos são necessários para gravar, testar e executar fluxos de IU para computador.

Siga estes passos para instalar a aplicação de fluxos de IU:

1. [Transfira o programa de instalação dos fluxos de IU](https://go.microsoft.com/fwlink/?linkid=2102613).
1. Abra o ficheiro **Setup.Microsoft.Flow.UIflow.exe**. Este ficheiro encontra-se provavelmente na pasta **Transferências**, depois de o ter transferido no passo anterior.
1. Siga as instruções do programa de instalação **Configuração de fluxos de IU (pré-visualização)** para concluir a instalação.

> [!TIP]
> Se quiser alterar a definição da recolha de dados, reinstale os fluxos de IU e altere a definição.

## <a name="activate-the-ui-flows-browser-extension"></a>Ativar a extensão do browser dos fluxos de IU 

Depois de o programa de instalação dos fluxos de IU ter sido concluído, o browser vai pedir-lhe para ativar a extensão.

- No Microsoft Edge (Chromium), selecione cada ícone de aviso no canto superior direito do browser e, em seguida, selecione **Ativar extensão**.
-   No Google Chrome, selecione **Ativar extensão**, quando lhe for pedido.  

> [!TIP]
> Se não viu o pedido no browser, verifique o seguinte:
> - Tem de utilizar o Microsoft Edge (Chromium) ou o Google Chrome
> - Pode ser necessário ativar a extensão manualmente. Com o Microsoft Edge (Chromium), navegue para **edge://extensions** ou, com o Google Chrome, navegue para **chrome://extensions**.
> - Se a extensão dos fluxos de IU do Power Automate não aparecer, poderá reinstalá-la com o [programa de instalação dos fluxos de IU](https://go.microsoft.com/fwlink/?linkid=2102613).

<!-- To do for Gautier: check if the below is not bugged as there was one at some point.
> - Reinstall the extension from the Chrome store
Navigate to this link https://chrome.google.com/webstore/detail/microsoft-flow-preview/jcajipieipkmjpfakbdhmjidmhidogoo and install it manually, that will fix any issues. (For Edge Chromium, use the same link and accept when prompted to install from external stores.)
-->

## <a name="optional-install-selenium-ide-to-automate-web-applications"></a>(opcional) Instalar o IDE Selenium para automatizar as aplicações Web

O IDE Selenium é uma ferramenta open source que lhe permite gravar e reproduzir interações humanas em sites.

Com os fluxos de IU, pode executar scripts do IDE Selenium no Power Automate e mantê-los armazenados de forma segura (com a governação de TI adequada) no Common Data Service.

Siga estes passos para instalar o IDE Selenium:

1. [Transfira e instale](https://go.microsoft.com/fwlink/?linkid=2107665) o IDE Selenium para a próxima versão do Microsoft Edge ou Google Chrome.

1. No Microsoft Edge (Chromium), selecione **Permitir extensões de outras lojas** e, em seguida, selecione **Adicionar ao Chrome**.

## <a name="install-the-on-premises-data-gateway"></a>Instalar o gateway de dados no local

Precisará do gateway para acionar o fluxo de IU de um [evento, agendamento ou fluxo de botão](../getting-started.md#types-of-flows).

>[!TIP]
>O gateway não é necessário, caso pretenda apenas criar, editar e testar os fluxos de IU no dispositivo.

[Instale o gateway de dados no local](https://docs.microsoft.com/data-integration/gateway/service-gateway-install), caso precise dele.

## <a name="uninstall-ui-flows"></a>Desinstalar os fluxos de IU

1. Abra o menu **iniciar** > **Definições** > **Aplicações**.
1. Procure **Fluxos de IU (pré-visualização)** e selecione.
1. Selecione **Desinstalar**.

## <a name="next-steps"></a>Passos seguintes

- Saiba como [criar fluxos de IU para computador](create-desktop.md).
- Saiba como [criar fluxos de IU para a Web](create-web.md).
- Saiba como executar [fluxos de IU](run-ui-flow.md).
- Saiba como [gerir fluxos de IU](manage.md).
- Saiba mais sobre o [gateway no local](../gateway-reference.md#use-a-gateway)

## <a name="limitations"></a>Limitações
- As versões mais recentes de cada componente são necessárias para gravar, testar ou executar fluxos de IU.
- Desinstale as versões anteriores antes de instalar a versão mais recente.


