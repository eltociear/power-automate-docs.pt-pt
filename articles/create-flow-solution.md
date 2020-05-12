---
title: Saiba como criar fluxos com suporte para soluções | Microsoft Docs
description: Saiba como criar fluxos com suporte para soluções.
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
ms.date: 11/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d74cbdb6c03d65a7902a81194491ef67feda6bb2
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297478"
---
# <a name="create-a-flow-in-a-solution"></a>Criar um fluxo numa solução


Os fluxos que criar numa solução são conhecidos como fluxos *com suporte para soluções*. Siga estes passos para criar um fluxo com suporte para soluções.

## <a name="prerequisites"></a>Pré-requisitos

Tem de ter, pelo menos, uma solução para poder criar um fluxo com suporte para soluções.

## <a name="create-the-flow"></a>Criar o fluxo 

1. Inicie sessão em [Power Automate](https://flow.microsoft.com).
1. Selecione **Soluções** na barra de navegação.

   ![](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. Selecione a solução na qual vai criar o fluxo.

   ![](./media/create-flow-solution/new-solution-created.png)

1. Selecione **+ Novo** e, em seguida, **Fluxo**.

   ![](./media/create-flow-solution/select-new-flow.png)

   A caixa Power Automate é aberta.

1. Utilize os conectores e os acionadores disponíveis para criar o seu fluxo.

   Neste exemplo, vamos criar um fluxo simples que envia uma notificação quando recebe um e-mail na caixa de entrada.
1. Procure e, em seguida, selecione **Office 365 Outlook**.
1. Selecione o acionador **Quando é recebido um novo e-mail **.
1. Selecione **+ Novo passo**.
1. Selecione a ação**Enviar-me uma notificação por telemóvel**.
1. Adicione o token dinâmico **Assunto** ao campo **Texto** na caixa **Enviar-me uma notificação por telemóvel**.
1. Dê um nome ao fluxo e guarde-o.

   O fluxo deve ser apresentado desta forma:

   ![](./media/create-flow-solution/new-email-notification-flow.png)
   
1. Selecione **Soluções** para ver o fluxo na solução:

   ![](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>Mais Informações

* [Criar uma solução](./overview-solution-flows.md)
* [Exportar uma solução](./export-flow-solution.md)
* [Importar uma solução](./import-flow-solution.md)
* [Editar um fluxo com suporte para soluções](./edit-solution-aware-flow.md)
* [Remover um fluxo com suporte para soluções](./remove-solution-aware-flow.md)
