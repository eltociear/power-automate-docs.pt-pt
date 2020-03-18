---
title: Criar um fluxo de aprovação que requer a aprovação de todas as pessoas | Microsoft Docs
description: Crie um fluxo de aprovação que requer a aprovação de todas as pessoas ou que uma pessoa rejeite um pedido.
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
ms.date: 02/27/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: abf7be642e1c8e62db54bd7b5472ce29a330ad3a
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193548"
---
# <a name="create-an-approval-flow-that-requires-everyone-to-approve"></a>Criar um fluxo de aprovação que requer a aprovação de todas as pessoas


Estas instruções mostram como criar um fluxo de trabalho de aprovação que requer que todos os utilizadores (todos os aprovadores atribuídos) aceitem que um pedido de férias seja aprovado, mas em que qualquer aprovador pode rejeitar inteiramente o pedido.

Este tipo de fluxo de trabalho de aprovação é útil numa organização que exige que o gestor de uma pessoa e o gestor do gestor concordem relativamente a um pedido de férias, para que este seja aprovado. No entanto, qualquer um dos dois gestores pode recusar o pedido sem o parecer da outra pessoa.

> [!NOTE]
> Embora estas instruções realcem um cenário de aprovação de férias, pode utilizar este tipo de fluxo de aprovação em qualquer situação em que múltiplos aprovadores têm de aprovar um pedido.
>
>

## <a name="prerequisites"></a>Pré-requisitos

* Acesso ao [Power Automate](https://flow.microsoft.com), Outlook do Microsoft Office 365 e Utilizadores do Microsoft Office 365.
* Uma [lista](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) do SharePoint.

    Estas instruções pressupõem que criou uma lista do SharePoint que é utilizada para pedir férias. Veja as instruções de [aprovações paralelas](parallel-modern-approvals.md) para obter um exemplo que explica em detalhe o aspeto que a sua lista do SharePoint pode ter.
* Familiaridade com as noções básicas de criação de fluxos.

    Pode rever como adicionar [ações, acionadores](multi-step-logic-flow.md#add-another-action) e [condições](add-condition.md). Os seguintes passos pressupõem que sabe como realizar estas ações.

> [!NOTE]
> Embora utilizemos o SharePoint e o Outlook do Office 365 nestas instruções, pode utilizar outros serviços, como o Zendesk, o Salesforce o Gmail ou qualquer um dos mais de [200 serviços](https://flow.microsoft.com/connectors/) suportados pelo Power Automate.
>
>

## <a name="create-the-flow"></a>Criar o fluxo

> [!NOTE]
> Se não tiver criado anteriormente uma ligação para o SharePoint ou Office 365, siga as instruções quando lhe for pedido para iniciar sessão.
>
>

Estas instruções utilizam tokens. Para apresentar a lista de tokens, toque ou clique em qualquer controlo de entrada e procure o token na lista **Conteúdo dinâmico** que é aberta.

Inicie sessão no [Power Automate](https://flow.microsoft.com) e execute os seguintes passos para criar o fluxo.

1. Selecione **Os meus fluxos** > **Criar do zero**, no canto superior direito do ecrã.
1. Adicione o acionador **SharePoint - Quando um item é criado ou modificado**.
1. Introduza o **Endereço do Site** do SharePoint que aloja a lista de pedidos de férias e selecione a lista em **Nome da Lista**.
1. Adicione a ação **Utilizadores do Office 365 - Obter gestor V2**, selecione a caixa **Utilizador (UPN)** e, em seguida, adicione o token **Criado por E-mail** à mesma.

    O token **Criado por E-mail** está localizado na categoria **Quando um item é criado ou modificado** da lista **Conteúdo dinâmico**. Este token fornece de forma dinâmica acesso a dados sobre o gestor à pessoa que criou o item no SharePoint.

1. Adicione outra ação **Utilizadores do Office 365 - Obter gestor V2** e adicione o token **Correio** à caixa **Utilizador (UPN)** .

    O token **Correio** está localizado na categoria **Obter gestor V2 2** da lista **Conteúdo dinâmico**. Este token fornece de forma dinâmica acesso ao endereço de e-mail do gestor.

    Pode também mudar o nome do cartão **Obter gestor V2 2** para algo com significado, como "Ignorar nível do gestor".
1. Adicione a ação **Iniciar uma aprovação** e selecione **Todos os utilizadores da lista atribuída** na lista **Tipo de aprovação**.

   > [!IMPORTANT]
   > Se qualquer um dos aprovadores rejeitar o pedido de aprovação, este é considerado rejeitado por todos os aprovadores.
   >
   >
1. Utilize a tabela seguinte como guia para preencher o cartão **Iniciar aprovação**.

   | Campo | Descrição |
   | --- | --- |
   |  Tipo de aprovação |Utilize **Qualquer pessoa da lista atribuída** para indicar que qualquer um dos aprovadores pode aprovar ou rejeitar o pedido. </p>Utilize **Todos os utilizadores da lista atribuída** para indicar que um pedido só é aprovado se todas as pessoas concordarem, e o pedido é negado se uma única pessoa o rejeitar. |
   |  Título |O título do pedido de aprovação. |
   |  Atribuído a |Os endereços de e-mail dos aprovadores. |
   |  Detalhes |Quaisquer informações adicionais que pretenda que sejam enviadas para os aprovadores listados no campo **Atribuído a**. |
   |  Hiperligação de item |Um URL para o item de aprovação. Neste exemplo, esta é uma hiperligação para o item no SharePoint. |
   |  Descrição da hiperligação de item |Uma descrição de texto para a **Hiperligação de item**. |

   > [!TIP]
   > A ação **Iniciar uma aprovação** fornece vários tokens, incluindo **Resposta** e **Resumo de resposta**. Utilize estes tokens no seu fluxo para a criação de relatórios avançados dos resultados da execução de um fluxo de pedido de aprovação.
   >
   >

    O cartão **Iniciar uma aprovação** é um modelo para o pedido de aprovação que é enviado para os aprovadores. Configure-o de forma a ser útil para a sua organização. Eis um exemplo.

    ![iniciar uma aprovação](media/all-assigned-must-approve/start-an-approval-card.png)

1. Adicione a ação **Outlook do Office 365 - Enviar um e-mail** e configure-a para enviar um e-mail com os resultados do pedido.

    Eis um exemplo de como o cartão **Enviar um e-mail** pode ser.

    ![enviar um e-mail](media/all-assigned-must-approve/send-an-email-card.png)

> [!NOTE]
> Qualquer ação após a ação **Iniciar uma aprovação** é executada com base na seleção da lista **Tipo de aprovação** do cartão **Iniciar uma aprovação**. A tabela seguinte lista o comportamento com base na sua seleção.
>
>

| Tipo de aprovação | Comportamento |
| --- | --- |
| Qualquer pessoa na lista atribuída |As ações após a ação **Iniciar uma aprovação** são executadas depois de qualquer um dos aprovadores decidir. |
| Todos os utilizadores da lista atribuída |As ações após a ação **Iniciar uma aprovação** são executadas depois de um aprovador aceitar ou recusar o pedido. |

Na parte superior do ecrã, introduza um nome para o fluxo na caixa **Nome de fluxo** e selecione **Criar fluxo** para guardá-lo.

Parabéns, o fluxo está concluído! Se seguiu o procedimento, o fluxo é semelhante a esta imagem.

![imagem de fluxo geral](media/all-assigned-must-approve/overall-flow.png)

Agora, sempre que um item da lista do SharePoint for adicionado, ou se um item for alterado, o fluxo aciona e envia pedidos de aprovação a todos os aprovadores que estão listados na caixa **Atribuído a** do cartão **Iniciar uma aprovação**. O fluxo envia pedidos de aprovação através da aplicação móvel do Power Automate e por e-mail. A pessoa que cria o item no SharePoint obtém uma mensagem de e-mail que resume os resultados, indicando claramente se o pedido foi aprovado ou rejeitado.

Eis um exemplo do pedido de aprovação que é enviado para cada aprovador.

![pedido de aprovação](media/all-assigned-must-approve/approval-request.png)

Eis um exemplo de uma resposta e um resumo da resposta depois de o fluxo ser executado.

![tokens de resposta](media/all-assigned-must-approve/response-output.png)

## <a name="learn-more-about-approvals"></a>Saiba mais sobre as aprovações

* [Aprovações modernas com um único aprovador](modern-approvals.md)
* [Aprovações modernas sequenciais](sequential-modern-approvals.md)
* [Aprovações modernas paralelas](parallel-modern-approvals.md)
* [Aprovações e o Microsoft Common Data Service](common-data-model-approve.md)
* [Aprovar pedidos em viagem](mobile-approvals.md)
