---
title: Executar fluxos de IU a partir de outros fluxos | Microsoft Docs
description: Executar fluxos de IU a partir de outros fluxos em modo assistido ou automático.
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
ms.date: 03/03/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0852e8b52f7b158d8fc97316b0f719f8e557a15f
ms.sourcegitcommit: 14ea422c0b306f738757036cc0e240584dd810f5
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79188119"
---
# <a name="run-attended-and-unattended-ui-flows"></a>Executar os fluxos de UI com e sem assistência

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

    - **Gateway**: Selecione o gateway que criou anteriormente ou utilize **Novo gateway** para criar um novo gateway.   
    - **Domínio e Nome de utilizador**: apresenta a conta escolar ou profissional do dispositivo.
    - **Palavra-passe**: forneça a palavra-passe da sua conta escolar ou profissional.

      ![Definições de ligação](../media/run-ui-flow/uiflow-connection-card.png "Definições de ligação")

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

## <a name="run-ui-flows-unattended-or-attended"></a>Executar fluxos de IU automáticos ou assistidos

Ao criar fluxos de IU, execute-os em modo **assistido** ou **automático**. O modo automático é melhor para aplicações que não necessitam de supervisão humana.

Ao executar de forma automática, os fluxos de IU iniciam sessão automaticamente nos dispositivos de destino com o Windows 10, Windows Server 2016 ou Windows Server 2019. Quando a automatização for concluída, os fluxos de IU terminarão sessão no dispositivo e comunicarão a sua atividade no Power Automate.

Ao serem executados de forma assistida, os fluxos de IU utilizarão uma sessão de utilizador do Windows existente.

Os fluxos de IU utilizarão os modos assistidos ou automáticos consoante o estado da máquina, conforme descrito abaixo neste artigo.

### <a name="unattended-mode"></a>Modo automático

Para executar fluxos de IU automáticos, a máquina de destino tem de estar disponível, com todas as sessões de utilizadores terminadas. As sessões de utilizador do Windows bloqueadas impedem a execução dos fluxos de IU.

Os fluxos de IU realizam o seguinte:
1. Os fluxos de IU criam, gerem e depois disponibilizam a sessão de utilizador do Windows em dispositivos de destino.

1. Os fluxos de IU automáticos serão executados em dispositivos com o ecrã bloqueado.

1. Os dispositivos com o Windows 10 não podem ser executados de forma automática se existirem sessões de utilizador do Windows ativas no dispositivo (mesmo que estejam bloqueadas). Verá este erro: *Não é possível executar o fluxo de IU. Existe uma sessão de utilizador do Windows bloqueada ou inativa no dispositivo de destino*.

1. No Windows Server, se tiver uma sessão de utilizador bloqueada do Windows aberta com o mesmo utilizador que o fluxo de IU é suposto executar, verá o mesmo erro: *Não é possível executar o fluxo de IU. Existe uma sessão de utilizador do Windows bloqueada ou inativa no dispositivo de destino*.

### <a name="attended-mode"></a>Modo assistido
Para executar um fluxo de IU assistido, é necessário ter uma sessão de utilizador do Windows ativa que corresponda ao nome do utilizador configurado para a sua ligação. A sessão não deve estar bloqueada.

Quando um fluxo de IU assistido começar a ser executado na máquina de destino, recomendamos que evite interações com o seu dispositivo (por exemplo: movimentos com o rato) até que a execução esteja concluída.


## <a name="schedule-multiple-ui-flows-on-the-same-device"></a>Agendar múltiplos fluxos de IU no mesmo dispositivo

Pode agendar a execução de múltiplos fluxos de IU num ou mais dispositivos. Se for acionada a execução de mais de um fluxo de IU no mesmo dispositivo, o back-end dos fluxos de IU orquestrará as execuções ao seguir estas regras:

1.  Envia o primeiro fluxo de IU para o dispositivo de destino.

1.  Coloca outros fluxos de IU em fila e apresenta-os como **em espera** na página de detalhes dos fluxos de IU ou gateway.

1.  Envia o seguinte fluxo de IU quando cada execução é concluída.

>[!NOTE]
>Estas regras de orquestração aplicam-se tanto aos fluxos de IU que são agendados pelo mesmo utilizador como por diferentes utilizadores no mesmo dispositivo.

>[!IMPORTANT]
>Se existirem demasiados fluxos de IU em fila de execução, o tempo pode ser excedido. O fluxo de IU falhará se não for executado 30 minutos após ser acionado.

## <a name="rerun-failed-ui-flows"></a>Voltar a executar fluxos de IU com falhas

Se a execução de um fluxo de IU falhar, pode tentar executá-lo depois de corrigir a causa dessa falha ou, em determinados casos, resolver a execução com falhas.

1. Aceda à página de detalhes dos fluxos de IU e identifique a execução com falhas que pretende executar novamente.

1. Selecione o fluxo principal da execução no qual tem interesse.

   Isto irá levá-lo à execução de fluxo principal na qual o fluxo de IU falhou.

1. Selecione o botão Voltar a submeter no menu Ação.

## <a name="troubleshoot-failures"></a>Resolver falhas

### <a name="failed-ui-flows"></a>Fluxos de IU com falhas

1. Se o seu fluxo de IU falhar com a mensagem de erro **Não é possível criar uma nova sessão**, siga estes passos para resolver o problema:

    1.  No Windows 10, confirme se não tem uma sessão de utilizador ativa bloqueada ou desbloqueada no seu dispositivo de destino.
    1.  No Windows Server 2016 ou no Windows Server 2019, confirme se não atingiu o número máximo de sessões de utilizadores ativas configuradas para a sua máquina. Caso contrário, os fluxos de IU não poderão criar novas sessões para executar novos fluxos de IU.

### <a name="ui-flows-app-status"></a>Estado da aplicação de fluxos de IU

A aplicação de fluxos de IU é o software que instala na sua máquina local que gere e executa os Fluxos de IU. Permite que os nossos serviços cloud de Fluxo de IU comuniquem e orquestrem Fluxos de IU na sua máquina.

Na lista de gateways e nas páginas de detalhes do gateway, pode ver o estado da aplicação de fluxos de IU atual para cada dispositivo.

![Uma captura de ecrã a mostrar a lista de gateways](../media/run-ui-flow/gateway-list.png)

A sua aplicação de fluxos de IU pode estar num dos seguintes estados:

1. **Disponível**: a aplicação de fluxos de IU está online e pronta para executar fluxos de IU.

1. **Em execução**: um ou mais fluxos de IU estão em execução na máquina. Todos os outros fluxos de IU que o back-end enviar para o dispositivo de destino serão colocados em fila para aguardar a sua execução.

1. **Corrigir ligação para o gateway**: o serviço cloud de fluxo de IU não pode alcançar o dispositivo de destino, provavelmente porque existe um problema com a ligação do gateway. Para resolver este problema, aceda à ligação e confirme se as credenciais que utiliza estão corretas.

1. **Desconhecido**: isto significa que o back-end não pode alcançar a aplicação de fluxos de IU.

    1. Se o **estado do gateway** for **offline**, confirme se o dispositivo está ligado e ligado à Internet. Também pode [resolver problemas do gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot)

    1. Se o **estado do gateway** for **online**, experimente as seguintes ações:

        1. Confirmar se os serviços e a aplicação de fluxos de IU estão em execução no seu dispositivo.

        1. Reiniciar o serviço de fluxo de IU no seu dispositivo.

## <a name="learn-more"></a>Saiba mais

 - Instalar o [gateway de dados no local](https://docs.microsoft.com/data-integration/gateway/service-gateway-app).
 - Documentação para [utilizar a aplicação de gateway de dados no local](https://docs.microsoft.com/flow/gateway-manage).
 - [Resolução de problemas](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot) do gateway de dados no local.
