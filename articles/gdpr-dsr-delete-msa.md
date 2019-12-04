---
title: Pedidos de Eliminação de Titulares de Dados DO RGPD no Power Automate para Contas Microsoft (MSA) | Microsoft Docs
description: Saiba como utilizar o Power Automate para responder a Pedidos de Eliminação de Titulares de Dados DO RGPD para Contas Microsoft.
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
ms.openlocfilehash: b9ef70579798b353ddcd8a961604665a287cd63a
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74368151"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>Responder a Pedidos de Eliminação de Titulares de Dados RGPD
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

O **direito de apagamento** através da remoção de dados pessoais constitui uma proteção fundamental do RGPD. A remoção dos dados pessoais inclui remover todos os dados pessoais, exceto as informações dos registos de auditoria.

O Power Automate permite aos utilizadores criar fluxos de trabalho automatizados. Quando um utilizador decide eliminar os dados pessoais do Power Automate, pode rever os dados os seus pessoais e determinar se quer eliminar alguns ou todos os dados.

A seguinte tabela mostra os dados pessoais que são automaticamente eliminados e os dados que requerem a revisão e a eliminação dos dados por parte do utilizador de uma Conta Microsoft (MSA).

|Requer a revisão e a eliminação por parte do utilizador da MSA|Eliminado automaticamente|
|------|------|
|Atividade de produtos e serviços|Histórico de execuções|
|Fluxos|Feed de Atividades|
|Ligações||

O Power Automate oferece as seguintes experiências para ajudar os utilizadores a localizar, rever ou alterar dados pessoais e recursos que não são eliminados automaticamente:

## <a name="manage-delete-requests"></a>Gerir Pedidos de eliminação

Os passos abaixo descrevem como eliminar pedidos autonomamente, de acordo com o RGPD.

### <a name="delete-product-and-service-activity"></a>Eliminar a atividade de produtos e serviços

1. Inicie sessão no [Dashboard de Privacidade da Microsoft](https://account.microsoft.com/privacy/) com a sua MSA.
1. Selecione a ligação **Histórico de atividades**.

    ![Histórico de Atividades](./media/gdpr-dsr-export-msa/activityhistory.png)

1. No histórico de atividades, pode procurar ou navegar pelas diferentes aplicações e serviços da Microsoft que utiliza, incluindo o Power Automate. Selecione **Eliminar** para remover eventos da atividade de produtos ou serviços específicos.

    ![Eliminar Evento](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. Após alguns instantes, o item é eliminado e removido do dashboard de privacidade.

### <a name="list-and-delete-flows"></a>Ver e eliminar fluxos

Um utilizador pode ver e eliminar os fluxos do [Power Automate](https://flow.microsoft.com) ao seguir estes passos:

1. Inicie sessão no [Power Automate](https://flow.microsoft.com) e selecione **Os meus fluxos**.

1. Selecione **...** junto ao fluxo que pretende eliminar e, em seguida, selecione **Eliminar**.

    ![Eliminar Evento](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>Eliminar Ligações

Os conectores utilizam ligações para comunicar com sistemas SaaS e APIs. As ligações incluem referências para o utilizador que as cria. O utilizador pode eliminar estas referências em qualquer altura ao seguir estes passos:

1. Inicie sessão no [Power Automate](https://flow.microsoft.com), selecione o ícone de engrenagem e, em seguida, **Ligações**.

    ![Eliminar Evento](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. Selecione a ligação que pretende eliminar, selecione **...** e, em seguida, selecione **Eliminar**.

    ![Eliminar Evento](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. Selecione o ícone **Eliminar** no pedido de confirmação.

    ![Eliminar Evento](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> Se outros fluxos utilizarem a ligação que está a eliminar, será notificado de que é necessária uma nova ligação. Caso contrário, selecione **Eliminar** para continuar.
>
>

## <a name="learn-more"></a>Saiba mais

* Introdução ao [Power Automate](getting-started.md)
* Conheça as [novidades](release-notes.md) do Power Automate
