---
title: Pedidos de Fecho de Conta de Titulares de Dados do RGPD no Power Automate para Contas Microsoft (MSA) | Microsoft Docs
description: Saiba como utilizar o Power Automate para responder a Pedidos de Fecho de Conta de Titulares de Dados do RGPD para Contas Microsoft.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 277765754683a6690b186a5f592517482b32666f
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74366380"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-power-automate"></a>Responder a Pedidos de Fecho de Conta de Titulares de Dados do RGPD no Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

O **direito de apagamento** de dados pessoais constitui uma proteção fundamental do RGPD. Este direito inclui remover todos os dados pessoais, exceto as informações dos registos de auditoria. Quando um utilizador decide fechar a Conta Microsoft (MSA), os dados subjacentes também serão eliminados.

Os seguintes recursos contêm dados pessoais que são automaticamente eliminados quando um utilizador fecha uma MSA:

|Recursos com dados pessoais|
|------|
|Atividade de produtos e serviços|
|Histórico de execuções|
|Fluxos|
|Feed de Atividades|
|Detalhes do utilizador|
|Ligações|

## <a name="account-close-requests"></a>Pedidos de Fecho de Conta

Os seguintes passos descrevem como gerir pedidos de Fecho de Conta de forma autónoma, de acordo com o RGPD.

1. Inicie sessão no [Portal de Fecho de Contas Microsoft](https://go.microsoft.com/fwlink/?LinkId=523898) com a sua Conta Microsoft e selecione **Seguinte**.

    > [!NOTE]
    > Será alertado para cancelar subscrições existentes ou para exportar dados de serviços existentes que possa ter subscrito.
    >
    >

    ![Cancelar subscrições](./media/gdpr-dsr-delete-msa/accountclose.png)

1. Confirme que compreende o impacto de fechar a sua MSA e, em seguida, selecione **Marcar conta para fecho**.

    É apresentada uma notificação a indicar que a conta será fechada dentro de 30 dias. Poderá reabrir esta conta em qualquer altura durante este período de 30 dias.

    ![Conta Fechada](./media/gdpr-dsr-delete-msa/accountclosed.png)

    No fim deste período de 30 dias, é iniciado o processo para eliminar todos os recursos do Power Automate desta MSA.

## <a name="learn-more"></a>Saiba mais

* Introdução ao [Power Automate](getting-started.md)
* Conheça as [novidades](release-notes.md) do Power Automate
