---
title: Gerir fluxos a partir do telemóvel | Microsoft Docs
description: Veja uma lista dos fluxos, ative ou desative-a e veja os eventos, ações e histórico de execução de cada fluxo
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
ms.openlocfilehash: ce9a943f50ef5c8cc69e5dbf8fde796a75e4cdf9
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195819"
---
# <a name="manage-flows-in-power-automate-from-your-phone"></a>Gerir fluxos no Power Automate a partir do telemóvel

Veja uma lista de todos os fluxos que criou e, para cada fluxo, veja os eventos e ações, ative ou desative e explore o histórico de execução dele.

**Pré-requisitos**

* Instale a aplicação móvel do Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows) num [dispositivo suportado](getting-started.md#use-the-mobile-app). Neste tópico, os gráficos refletem a versão da aplicação do iPhone, mas os gráficos do Android e Windows Phone são semelhantes.
* Se ainda não tiver um fluxo, crie um no [site do Power Automate](https://flow.microsoft.com/). Para um teste mais fácil, utilize um fluxo que possa acionar em vez de aguardar por um evento externo.

O fluxo neste tutorial é executado quando receber correio de um endereço específico:

![Fluxo de acionador na receção de correio de endereço específico](./media/mobile-manage-flows/create-trigger.png)

Poderá configurar esse fluxo com o seu endereço de e-mail pessoal para fins de teste e um endereço diferente (por exemplo, do seu gestor) quando o fluxo estiver pronto para utilização real.

Quando o fluxo é executado, envia uma notificação push personalizada para o telemóvel, com a sintaxe:

![Enviar mensagem para Slack](./media/mobile-manage-flows/create-event.png)

**Nota**: também pode [monitorizar a atividade do fluxo](mobile-monitor-activity.md) a partir da aplicação móvel.

## <a name="manage-a-flow"></a>Gerir um fluxo
1. Abra a aplicação móvel e, em seguida, toque em **Meus fluxos** na parte inferior do ecrã para listar todos os fluxos.
   
    Cada entrada mostra o nome do fluxo, ícones para os eventos e ações dele, a hora de última execução e um ícone que indica se a última execução foi concluída com êxito.
   
    ![Lista de fluxos](./media/mobile-manage-flows/flow-list.png)
2. Toque num fluxo para visualizar as opções de gestão.
   
    ![Opções de gestão de um fluxo](./media/mobile-manage-flows/flow-details.png)
3. Toque no seletor **Ativar fluxo** para ativar ou desativar o fluxo.
4. Toque em **Ver fluxo** para visualizar os eventos e ações para esse fluxo, toque em cada evento ou numa ação para expandi-lo e, em seguida, toque em **Anterior**.
   
    ![Eventos e ações para um fluxo](./media/mobile-manage-flows/flow-event-action.png)
5. Toque em **Executar histórico** para visualizar os êxitos, as falhas do fluxo, ou ambos.
   
    ![Lista de execuções](./media/mobile-manage-flows/history-mixed.png)
6. Toque numa execução para visualizar se cada evento e ação foi concluída com êxito e, se assim for, quanto tempo (em segundos) demorou.
   
    ![Detalhes da execução](./media/mobile-manage-flows/flow-run.png)

