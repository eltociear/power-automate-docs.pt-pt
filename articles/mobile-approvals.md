---
title: Aprovar pedidos num dispositivo móvel | Microsoft Docs
description: Utilize um dispositivo móvel para aprovar pedidos criados no Power Automate.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/20/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 513200d18ac2a845cd63a6d269513f3bcb45118c
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297632"
---
# <a name="approve-requests-on-your-mobile-device-by-using-power-automate"></a>Aprovar pedidos no seu dispositivo móvel com o Power Automate

Se um fluxo o identificar como um aprovador e tiver instalado a aplicação móvel do Power Automate, irá receber uma notificação push sempre que a sua aprovação for pedida.

Este artigo explica alguns cenários comuns que poderá encontrar ao gerir pedidos de aprovação na aplicação móvel do Power Automate.

> [!NOTE]
> As imagens deste tópico são de um dispositivo Android; no entanto, a experiência em dispositivos iOS é semelhante.
> 
> 

## <a name="prerequisites"></a>Pré-requisitos
Para concluir estas instruções, precisa de:

* Um dispositivo [Android](https://aka.ms/flowmobiledocsandroid) ou [iOS](https://aka.ms/flowmobiledocsios) com a aplicação móvel do Power Automate.
* Ser designado como o aprovador num fluxo de aprovação.
* Pedidos pendentes para aprovação.

## <a name="view-pending-requests"></a>Ver pedidos pendentes
1. Abra a aplicação móvel para o Power Automate.
   
    ![inicie a aplicação móvel](./media/mobile-approvals/open-app.png)
2. Selecione **APROVAÇÕES** no canto superior direito.
   
    ![selecione as aprovações](./media/mobile-approvals/select-approvals.png)
3. Ver todas as aprovações pendentes:
   
    ![ver pedidos de aprovação pendentes](./media/mobile-approvals/show-pending-approval-requests.png)

Se não tiver pedidos de aprovação pendentes, crie um [fluxo de aprovação](modern-approvals.md), defina-se como um aprovador e, em seguida, acione o fluxo. Os pedidos de aprovação aparecem no centro de aprovação poucos segundos depois de o fluxo acionar e enviar um pedido de aprovação.

## <a name="approve-requests-and-leave-an-optional-comment"></a>Aprovar pedidos e deixar um comentário opcional
1. Se ainda não o fez, siga os passos anteriores para [ver os pedidos pendentes](mobile-approvals.md#view-pending-requests).
2. Selecione **APROVAR** no pedido que quer aprovar.
   
    ![selecione aprovar](./media/mobile-approvals/select-approve.png)
3. (Opcional) selecione **Adicionar comentário (opcional)**.
   
    ![selecione adicionar um comentário](./media/mobile-approvals/select-add-comment.png)
   
    Introduza um comentário no ecrã **Adicionar comentário**.
   
    ![introduza o seu comentário](./media/mobile-approvals/enter-comment-for-approval.png)
4. Selecione **CONFIRMAR** no canto superior direito.
   
    ![confirme que terminou](./media/mobile-approvals/tap-confirm-button.png)
   
    O ecrã de êxito é apresentado depois de o fluxo registar a sua decisão.
   
    ![ecrã de êxito](./media/mobile-approvals/approved.png)

## <a name="reject-requests-and-leave-an-optional-comment"></a>Rejeitar pedidos e deixar um comentário opcional
Siga os [passos para aprovar um pedido](mobile-approvals.md#approve-requests-and-leave-an-optional-comment), mas selecione **REJEITAR** no segundo passo.

## <a name="learn-more"></a>Mais Informações
[Criar fluxos de aprovação moderna](modern-approvals.md).

