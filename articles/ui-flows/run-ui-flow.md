---
title: Executar fluxos de IU a partir de outros fluxos | Microsoft Docs
description: Executar fluxos de IU a partir de outros fluxos
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
ms.openlocfilehash: d0d5380e1ade6d1d11d557f38e7fc5db6616d1d9
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74370957"
---
# <a name="run-ui-flows"></a>Executar fluxos de IU

[Este tópico é uma documentação de pré-lançamento e está sujeito a alterações.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Depois de ter criado e testado um fluxo de IU, poderá executá-lo a partir de um evento, agendamento ou botão. Para tornar isto possível, adicione o fluxo de IU a um [Fluxo automatizado](../get-started-logic-flow.md), um [Fluxo de botão](../introduction-to-button-flows.md), um [Fluxo agendado](../run-scheduled-tasks.md) ou um [fluxo de processo de negócio](../business-process-flows-overview.md).

## <a name="prerequisites"></a>Pré-requisitos

- Precisa do [gateway de dados no local](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409) para que o dispositivo possa ter o fluxo de IU acionado pelo Power Automate.
   
   O gateway é uma ligação segura a nível empresarial entre o Power Automate e o dispositivo (onde o fluxo de IU é executado). O Power Automate utiliza o gateway para aceder ao dispositivo no local, de forma a poder acionar os fluxos de IU a partir de um evento, um agendamento ou um botão.
- Uma conta escolar ou profissional. 

   >[!IMPORTANT]
   >Terá de utilizar a mesma conta escolar ou profissional para configurar o gateway, para iniciar sessão no Power Automate e para iniciar sessão no dispositivo Windows.
   

## <a name="run-your-ui-flow-from-an-event-button-schedule-or-business-process-flow"></a>Execute o fluxo de IU a partir de um fluxo de evento, botão, agendamento ou processo de negócio

Neste exemplo, vamos utilizar um fluxo automatizado para acionar um fluxo de IU quando chega um novo e-mail.

1. Aceda ao [Power Automate](https://flow.microsoft.com/).
1. Selecione **Os meus fluxos** na barra de navegação esquerda.
1. Selecione **Novo** e, em seguida, **Automatizado – do zero**.

   >[!TIP]
   >Pode escolher qualquer outro tipo de fluxo que se adeque às suas necessidades.

1. Dê um nome ao fluxo na caixa **Nome do fluxo**.
1. Procure “novo e-mail” e, em seguida, selecione **Quando chega um novo e-mail (V3)** na lista de acionadores. 
    
   ![Selecione um acionador](../media/run-ui-flow/2d4ec17d239169a46905cef1829fa3a1.png "Selecionar um acionador")

1. Selecione **Criar** e, em seguida, **Novo passo**.

1. Procure **Fluxos de IU** e, em seguida, selecione **Executar um fluxo de IU para computador** na lista de **Ações**. 

   ![Procurar ação](../media/run-ui-flow/search-action.png "Procurar ação")

1. Forneça as informações do gateway e as credenciais do dispositivo. 

   Terá de fazer isto uma vez para cada dispositivo:

    - **Nome da ligação**: escolha um nome para o dispositivo para a Ligação do fluxo. Pode ser diferente do nome do gateway.
    - **Nome de utilizador**: indique a conta escolar ou profissional do dispositivo.
    - **Tipo de autenticação**: selecione Windows.
    - **Palavra-passe**: a palavra-passe da conta escolar ou profissional.
    - **Gateway**: selecione o gateway que criou durante a instalação.

      ![Definições de ligação](../media/run-ui-flow/connection-settings.png "Definições de ligação")

      >[!TIP]
      >Caso não veja o gateway, é possível que tenha de selecionar uma ligação diferente. Para o fazer, selecione **...** no canto superior direto do cartão **Executar um fluxo de IU para computador (pré-visualização)** e, em seguida, selecione a ligação que quer utilizar em **As minhas ligações**.

      ![Selecionar uma nova ligação](../media/run-ui-flow/select-new-connection.png "Selecionar uma nova ligação")

1. Selecione o fluxo de IU que criou anteriormente.

   ![Selecionar fluxo de IU](../media/run-ui-flow/select-ui-flow.png "Selecionar fluxo de IU")

1. Selecione **Guardar** para guardar o fluxo automatizado.

1. Teste o fluxo ao enviar um e-mail para o acionar. Verá o fluxo de IU reproduzir os passos que gravou. 

![Execução bem-sucedida que chama um fluxo de IU](../media/run-ui-flow/successful-run.png "Execução bem-sucedida que chama um fluxo de IU")

>[!TIP]
>Não interaja com o dispositivo enquanto o fluxo estiver a ser executado.

## <a name="use-inputs-and-outputs"></a>Utilizar entradas e saídas

Quando define entradas e saídas num fluxo de IU, pode transmitir informações de e para essas entradas.

1. Ao adicionar um fluxo de IU a um fluxo, poderá ver a lista de entradas que foram definidas no fluxo de IU.

   ![Entradas de fluxo de IU](../media/run-ui-flow/inputs.png "Entradas de fluxo de IU")

1. Pode povoar cada campo de texto no fluxo de IU com os valores dos passos anteriores no fluxo. Para isso, selecione o campo de texto e, em seguida, selecione uma entrada no seletor de tokens.


1. Também pode utilizar saídas do fluxo de IU como entradas para ações que surgem posteriormente no fluxo. Para isso, selecione o campo de texto e, em seguida, selecione uma entrada no seletor de tokens.

## <a name="limitations-and-known-issues"></a>Problemas e limitações conhecidos

- Não são suportados clusters de gateway.
- Uma vez que neste lançamento só são suportados os teclados dos EUA (QWERTY), a reprodução de um passo de entrada onde a sequência de teclas foi gravada num teclado que não o dos EUA (QWERTY) resultará em toques nas teclas em teclados EUA (QWERTY).

## <a name="learn-more"></a>Saiba mais

 - Instalar o [gateway de dados no local](https://docs.microsoft.com/data-integration/gateway/service-gateway-app).
 - Documentação para [utilizar a aplicação de gateway de dados no local](https://docs.microsoft.com/flow/gateway-manage).
 - [Resolução de problemas](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot) do gateway de dados no local.
