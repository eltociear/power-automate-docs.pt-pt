---
title: Monitorizar a atividade a partir do telemóvel | Microsoft Docs
description: Veja quantas vezes cada fluxo foi concluído com êxito ou falhou, quando ocorreu cada execução e quanto tempo demorou
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/11/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2c02b50289988a6462ed33df92350e9e4286b785
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74376822"
---
# <a name="monitor-activity-in-power-automate-from-your-phone"></a>Monitorizar a atividade no Power Automate a partir do telemóvel
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Veja um resumo de quantas vezes cada fluxo foi concluído com êxito ou falhou hoje, ontem e nos dias anteriores. Explore os detalhes sobre cada execução, tal como quando foi executado, quanto tempo demorou cada passo e, em caso de falha, por que motivo.

**Pré-requisitos**

<iframe width="560" height="315" src="https://www.youtube.com/embed/vZuYZ64K3tI?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

* Instale a aplicação móvel Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows) num [dispositivo suportado](getting-started.md#use-the-mobile-app). Neste tópico, os gráficos refletem a versão da aplicação do iPhone, mas os gráficos do Android e Windows Phone são semelhantes.
* Se ainda não tiver um fluxo, crie um no [site do Power Automate](https://flow.microsoft.com/). Para um teste mais fácil, utilize um fluxo que possa acionar em vez de aguardar por um evento externo.

O fluxo neste tutorial é executado quando receber correio de um endereço específico:

![Fluxo de acionador na receção de correio de endereço específico](./media/mobile-monitor-activity/create-trigger.png)

Poderá configurar esse fluxo com o seu endereço de e-mail pessoal para fins de teste e um endereço diferente (por exemplo, do seu gestor) quando o fluxo estiver pronto para utilização real.

Quando o fluxo é executado, envia uma notificação push personalizada para o telemóvel, com a sintaxe:

![Enviar notificação push](./media/mobile-monitor-activity/create-event.png)

**Nota:** também pode [gerir os seus fluxos](mobile-manage-flows.md) a partir da aplicação móvel.

## <a name="display-a-summary-of-activity"></a>Visualizar um resumo da atividade
<iframe width="560" height="315" src="https://www.youtube.com/embed/nVCGJamOw6s?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Se o fluxo não tiver sido executado antes, acione uma execução para gerar dados.
   
    A apresentação dos dados na aplicação poderá demorar algum tempo.
2. Abra a aplicação móvel, que mostra o separador **Atividade** por predefinição.
   
    Este separador organiza os dados por dia, com os dados de hoje na parte superior.
   
    ![Atividade organizada por dia](./media/mobile-monitor-activity/activity-day2.png)
   
    Cada entrada mostra o nome de um fluxo com ícones que correspondem às ações e eventos do acionador dela.
   
    ![Nome e ícones para cada fluxo](./media/mobile-monitor-activity/activity-flow-name.png)
   
    Se pelo menos uma execução de um fluxo tiver sido concluída com êxito durante um dia, uma entrada mostrará o número de êxitos e a hora da última conclusão com êxito. Se um fluxo tiver falhado, uma entrada diferente mostrará informações semelhantes.
   
    ![Resumo de êxitos ou falhas](./media/mobile-monitor-activity/activity-summary.png)
   
    Se um fluxo enviar uma notificação push, será apresentado o texto da notificação mais recente na parte inferior da entrada, no caso de execuções com êxito.
   
    ![Exemplo de notificação push](./media/mobile-monitor-activity/activity-notification.png)
3. Se forem enviadas várias notificações push durante um dia, percorra a notificação para a esquerda para ver as notificações de até três execuções anteriores. Se forem enviadas mais de quatro notificações durante um dia, percorra para a esquerda até aparecer **Ver mais** e, em seguida, toque para ver uma lista de todas as notificações.
   
    ![Exemplo de notificação push](./media/mobile-monitor-activity/activity-notification-list.png)
4. Toque em **Anterior** para voltar ao resumo da atividade.
5. Para filtrar o resumo da atividade, toque no ícone no canto superior direito.
   
    Pode visualizar todas as entradas, apenas as entradas de falha ou apenas as entradas que incluam notificações push.
   
    ![Visualizar todas as execuções, apenas falhas ou apenas notificações](./media/mobile-monitor-activity/activity-filter.png)

## <a name="show-details-of-a-run"></a>Visualizar detalhes de uma execução
1. No resumo da atividade, toque numa entrada para visualizar detalhes da execução mais recente.
   
     Cada evento e ação é apresentada com um ícone que indica se o evento ou ação foi concluída com êxito ou falhou. Se tiver sido concluída com êxito também será apresentado o tempo que demorou (em segundos).
   
    ![Detalhes de uma execução](./media/mobile-monitor-activity/activity-icons.png)
2. Na parte inferior do ecrã, toque em **Ver execuções anteriores** para listar todas as execuções do fluxo e, em seguida, toque em execução para visualizar os detalhes dela.
   
    ![Histórico de êxitos/falhas](./media/mobile-monitor-activity/history-mixed.png)

