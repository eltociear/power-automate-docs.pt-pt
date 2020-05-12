---
title: Criar um fluxo de aprovação que requer a aprovação de todas as pessoas | Microsoft Docs
description: Crie um fluxo de aprovação que requer a aprovação de todas as pessoas ou que uma pessoa rejeite um pedido.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/07/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3f668d4462c06e061efe2a03b4e5e842364c4b6e
ms.sourcegitcommit: 5b1965a0c319c4294b7dc0c829120ed1f4f90444
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/25/2020
ms.locfileid: "3299304"
---
# <a name="create-an-approval-flow-that-requires-everyone-to-approve"></a>Criar um fluxo de aprovação que requer a aprovação de todas as pessoas


Estas instruções mostram como criar um fluxo de trabalho de aprovação que requer que todos os utilizadores (todos os aprovadores atribuídos) aceitem que um pedido de férias seja aprovado, mas em que qualquer aprovador pode rejeitar inteiramente o pedido.

Este tipo de fluxo de trabalho de aprovação é útil numa organização que exige que o gestor de uma pessoa e o gestor do gestor concordem relativamente a um pedido de férias, para que este seja aprovado. No entanto, qualquer um dos dois gestores pode recusar o pedido sem o parecer da outra pessoa.

> [!NOTE]
> Embora estas instruções realcem um cenário de aprovação de férias, pode utilizar este tipo de fluxo de aprovação em qualquer situação em que múltiplos aprovadores têm de aprovar um pedido.
>
>

## <a name="prerequisites"></a>Pré-requisitos

* Acesso a [Power Automate](https://flow.microsoft.com), Microsoft Office 365 Outlook e Utilizadores do Microsoft Office 365.
* Uma [lista](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) do SharePoint.

    Estas instruções pressupõem que criou uma lista do SharePoint que é utilizada para pedir férias. Veja as instruções de [aprovações paralelas](parallel-modern-approvals.md) para obter um exemplo que explica em detalhe o aspeto que a sua lista do SharePoint pode ter.
* Ter conhecimento das noções básicas da criação de fluxos.

    Pode rever como adicionar [ações, acionadores](multi-step-logic-flow.md#add-another-action) e [condições](add-condition.md). Os seguintes passos pressupõem que sabe como realizar estas ações.

> [!NOTE]
> Embora utilizemos o SharePoint e o Office 365 Outlook nestas instruções, pode utilizar outros serviços, como o Zendesk, Salesforce, Gmail, ou até mesmo muitos dos mais de [200 serviços](https://flow.microsoft.com/connectors/) suportados pelo Power Automate.
>
>

## <a name="create-the-flow"></a>Criar o fluxo

> [!NOTE]
> Se não tiver criado anteriormente uma ligação para o SharePoint ou Office 365, siga as instruções quando lhe for pedido para iniciar sessão.
>
>

Estas instruções utilizam tokens. Para apresentar a lista de tokens, toque ou clique em qualquer controlo de entrada e procure o token na lista **Conteúdo dinâmico** que é aberta.

Inicie sessão no [Power Automate](https://flow.microsoft.com) e execute os seguintes passos para criar o fluxo.

1. Selecione **Os meus fluxos** > **Novo** > **Automatizado do zero**, no canto superior esquerdo do ecrã.
1. Atribua um nome ao fluxo e adicione o acionador **SharePoint – quando um item é criado ou modificado**.
1. Introduza o **Endereço do Site** do SharePoint que aloja a lista de pedidos de férias e selecione uma lista do **Nome da Lista**.
1. Selecione **Novo passo**, adicione o Office 365, ação **Obter gestor (V2)**, selecione a caixa **Utilizador (UPN)** e, em seguida, adicione o token **Criado por E-mail** à mesma.

    O token **Criado por E-mail** está localizado na categoria **Quando um item é criado ou modificado** da lista **Conteúdo dinâmico**. Este token fornece de forma dinâmica acesso a dados sobre o gestor à pessoa que criou o item no SharePoint.

1. Selecione **Novo passo**, adicione outra ação **Obter gestor (V2)** do Office 365 e, em seguida, adicione o token **Correio** à caixa **Utilizador (UPN)**.

    O token **Correio** está localizado na categoria **Obter gestor (V2)** da lista **Conteúdo dinâmico**. Este token fornece de forma dinâmica acesso ao endereço de e-mail do gestor.

    Pode também mudar o nome do cartão **Obter gestor (V2) 2** para algo com significado, como "Ignorar nível do gestor".
1. Selecione **Novo passo**, adicione a ação **Iniciar e esperar por uma aprovação** e, em seguida, selecione **Aprovar/Rejeitar – Todos têm de aprovar** na lista **Tipo de aprovação**.

   > [!IMPORTANT]
   > Se qualquer um dos aprovadores rejeitar o pedido de aprovação, este é considerado rejeitado por todos os aprovadores.
   >
   >
1. Utilize a tabela seguinte como guia para preencher o cartão **Iniciar e aguardar por uma aprovação**.

   | Campo | Descrição |
   | --- | --- |
   | Tipo de aprovação |Consulte os [tipos de aprovação](#approval-types-and-their-behaviors). |
   |  Cargo |O título do pedido de aprovação. |
   |  Atribuído a |Os endereços de e-mail dos aprovadores. |
   |  Detalhes |Quaisquer informações adicionais que pretenda que sejam enviadas para os aprovadores listados no campo **Atribuído a**. |
   |  Ligação ao item |Um URL para o item de aprovação. Neste exemplo, esta é uma ligação para o item no SharePoint. |
   |  Descrição da hiperligação de item |Uma descrição de texto para a **Hiperligação de item**. |

   > [!TIP]
   > A ação **Iniciar e esperar por uma aprovação** fornece vários tokens, incluindo **Respostas** e **Resultado**. Utilize estes tokens no seu fluxo para a criação de relatórios avançados dos resultados da execução de um fluxo de pedido de aprovação.
   >
   >

    O cartão **Iniciar e aguardar por uma aprovação** é um modelo para o pedido de aprovação que é enviado para os aprovadores. Configure-o de forma a ser útil para a sua organização. Eis um exemplo.

    ![Iniciar e aguardar por uma aprovação](media/all-assigned-must-approve/start-an-approval-card.png)

    Quando um fluxo com a ação **Iniciar e aguardar por uma aprovação** estiver configurada com **Aprovar/Rejeitar – Todos têm de aprovar**, aguarda até que todos os **Atribuído a** aprovem ou, pelo menos, um **Atribuído a** rejeite o pedido de aprovação.

    >[!TIP]
    >Adicione um passo de **Condição** se pretender que o fluxo verifique a resposta ao pedido de aprovação e efetue ações diferentes com base no **Resultado**. O **Resultado** pode ser **Aprovar** ou **Rejeitar**. 

    Continuemos com o fluxo e enviar uma e-mail quando for tomada uma decisão sobre o pedido de aprovação.

1. Selecione **Novo Passo**, procure por "enviar um e-mail", adicione a ação **Enviar e-mail (V2)** do Office 365 Outlook e, em seguida, configure a ação para enviar um e-mail com os resultados do pedido para a pessoa que pretende ir de férias.

    Eis um exemplo de como o cartão **Enviar um e-mail (V2)** pode ser.

    ![enviar um e-mail](media/all-assigned-must-approve/send-an-email-card.png)

> [!NOTE]
> Qualquer ação após a ação **Iniciar e aguardar por uma aprovação** é executada com base na seleção da lista **Tipo de aprovação** do cartão **Iniciar e aguardar por uma aprovação**. A tabela seguinte lista o comportamento com base na sua seleção.
>
>

### <a name="approval-types-and-their-behaviors"></a>Tipos de aprovação e respetivos comportamentos

| Tipo de aprovação | Comportamento |
| --- | --- |
| Aprovar/Rejeitar – Todos têm de aprovar | A aprovação ou rejeição é necessária para que **todos** os aprovadores concluam o pedido. </p> As ações que se seguem à ação **Iniciar e aguardar por uma aprovação** são executadas depois de **todos** os aprovadores aprovarem ou quando é efetuada uma única rejeição.|
| Aprovar/Rejeitar – Primeiro a responder | A aprovação ou rejeição por qualquer aprovador conclui o pedido.  </p> As ações após a ação **Iniciar e aguardar por uma aprovação** são executadas depois de qualquer um dos aprovadores decidir.|
| Respostas personalizadas – Aguardar por todas as respostas | Todos os aprovadores têm de responder para concluir o processo. |
| Respostas personalizadas – Aguardar por uma resposta | Uma resposta de qualquer aprovador conclui o processo. |

No topo do ecrã, selecione **Guardar** para guardar o seu fluxo.

Parabéns, o fluxo está concluído! Se seguiu o procedimento, o fluxo é semelhante a esta imagem.

![imagem de fluxo geral](media/all-assigned-must-approve/overall-flow.png)

Agora, sempre que um item da lista do SharePoint for adicionado, ou se um item for alterado, o fluxo aciona e envia pedidos de aprovação a todos os aprovadores que estão listados na caixa **Atribuído a** do cartão **Iniciar e aguardar por uma aprovação**. O fluxo envia pedidos de aprovação através da aplicação móvel do Power Automate e por e-mail. A pessoa que cria o item no SharePoint obtém uma mensagem de e-mail que resume os resultados, indicando claramente se o pedido foi aprovado ou rejeitado.

Eis um exemplo do pedido de aprovação que é enviado para cada aprovador.

![pedido de aprovação](media/all-assigned-must-approve/approval-request.png)

Eis um exemplo de uma resposta e um resumo da resposta depois de o fluxo ser executado.

![tokens de resposta](media/all-assigned-must-approve/response-output.png)

## <a name="learn-more-about-approvals"></a>Saiba mais sobre as aprovações

* [Aprovações modernas com um único aprovador](modern-approvals.md)
* [Aprovações modernas sequenciais](sequential-modern-approvals.md)
* [Aprovações modernas paralelas](parallel-modern-approvals.md)
* [Aprovações e o Common Data Service](common-data-model-approve.md)
* [Aprovar pedidos em viagem](mobile-approvals.md)
