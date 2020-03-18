---
title: Aguardar a aprovação num fluxo | Microsoft Docs
description: Os fluxos podem aguardar a ocorrência de um evento externo, tal como um utilizador aprovar ou rejeitar uma alteração, antes de efetuar uma ação, tal como enviar notificação da decisão.
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
ms.date: 02/15/2018
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 34e17dbb8fdc1c3b3f6ba835b80c687504b9abd6
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195848"
---
# <a name="wait-for-approval-in-power-automate"></a>Aguardar a aprovação no Power Automate


> [!VIDEO https://www.youtube.com/embed/W6oxcYRtW-8?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]
>


Crie um fluxo que, caso crie um item no SharePoint, envia um e-mail de aprovação e, em seguida, notifica-o quer o item tenha sido aprovado ou rejeitado. Para seguir este tutorial exatamente, crie uma lista simples do SharePoint como uma ação de acionador, mas pode utilizar outra origem de dados, tal como Dropbox ou OneDrive.

**Pré-requisitos**

* Crie uma lista simples do SharePoint com o nome **Controlador do Projeto**, adicione uma coluna chamada **Título** e, em seguida, adicione uma coluna para Pessoa ou Grupo chamada **Atribuído a**.

   ![Imagem para lista do Controlador de Projeto do SPO](./media/wait-for-approvals/project-tracker.png)

## <a name="add-an-event-to-trigger-the-flow"></a>Adicionar um evento para acionar o fluxo

1. Inicie sessão no [Power Automate](https://flow.microsoft.com), selecione **Os meus fluxos** na barra de navegação superior e, em seguida, selecione **Criar do zero**.

1. Selecione a caixa **Procurar entre centenas de conectores e acionadores**, introduza **novo item** e, em seguida, navegue até **SharePoint - Quando um item é criado**.

1. Se lhe for pedido, inicie sessão no SharePoint.
1. Em **Endereço do Site**, introduza o URL do site do SharePoint que contém a sua lista.

1. Em **Nome da Lista**, selecione a lista que criou anteriormente. Se estiver a acompanhar, o nome é **Controlador do Projeto**.

    ![Imagem de nome de lista do SPO](./media/wait-for-approvals/SPO-list-name.png)

## <a name="add-the-resulting-action"></a>Adicionar a ação resultante

1. Selecione o botão **Novo passo** e, em seguida, selecione **Adicionar uma ação.**

1. Na caixa **Procurar todos os conectores e ações**, escreva ou cole **enviar e-mail** e, em seguida, selecione **Office 365 Outlook - enviar um e-mail com opções**.

1. Se lhe for pedido, inicie sessão no Outlook do Office 365.

1. Selecione o campo **Para** e, em seguida, selecione o token **Atribuído ao E-Mail**.

    O utilizador na coluna **Atribuído a** recebe o e-mail para aprovar ou rejeitar os itens. Quando cria um item para testar o fluxo, tem de definir-se manualmente neste campo. Dessa forma, não só aprova ou rejeita o item, mas também recebe o e-mail de notificação.

    > [!NOTE]
    > Pode personalizar os campos **Assunto** e **Opções do Utilizador** para se adequarem às suas necessidades.

    ![Imagem para enviar e-mail de aprovação para campo](./media/wait-for-approvals/send-approval-email-to.png)

## <a name="add-a-condition"></a>Adicionar uma condição

1. Selecione o botão **Novo passo** e, em seguida, selecione **Adicionar uma condição**.

    ![Imagem para adicionar uma condição](./media/wait-for-approvals/add-a-condition.png)
1. Selecione a primeira caixa e, em seguida, selecione o token **SelectedOption**.
1. Selecione a última caixa e, em seguida, escreva **Aprovar**.

    ![Imagem do cartão da condição](./media/wait-for-approvals/condition-card-2.png)

1. Na área **Se sim**, selecione **Adicionar uma ação**.

1. Na caixa **Procurar todos os conectores e ações**, escreva ou cole **enviar e-mail**e, em seguida, selecione **Office 365 Outlook - enviar um e-mail**.

1. No campo **Para**, introduza um destinatário tal como **Criado por E-mail**.

1. Na caixa **Assunto**, especifique um assunto.

    Por exemplo, selecione **Atribuído A DisplayName**, escreva **aprovou** com um espaço em cada lado e, em seguida, selecione **Título**.

1. Na caixa **Corpo**, especifique um corpo de e-mail tal como **Preparado para avançar para a fase seguinte do projeto.**

    > [!NOTE]
    > A pessoa que criou o item na lista do SharePoint irá ser notificada quer o projeto tenha sido aprovado ou rejeitado.

    ![Imagem para sim enviar e-mail](./media/wait-for-approvals/if-yes-send-email-card-3.png)

1. Na área **Se não**, repita os últimos cinco passos exceto alteração do **Assunto** e **Corpo** para refletir que o projeto foi rejeitado.

     ![Imagem para não enviar e-mail](./media/wait-for-approvals/no-send-email-2.png)

## <a name="finish-and-test-your-flow"></a>Concluir e testar o fluxo

1. Dê um nome ao fluxo e, em seguida, selecione **Criar fluxo**.

     ![Imagem para criar fluxo](./media/wait-for-approvals/create-flow.png)
1. Crie um item na lista do SharePoint.

    É enviado um e-mail de aprovação ao destinatário que especificou. Quando o destinatário seleciona **Aprovar** ou **Rejeitar** nesse e-mail, recebe um e-mail a indicar a resposta.

## <a name="learn-more"></a>Saiba mais

* [Instruções para aprovações modernas com um único aprovador](modern-approvals.md)
* Criar [aprovações sequenciais](sequential-modern-approvals.md)
* Criar [aprovações paralelas](parallel-modern-approvals.md)
* Aprovar [pedidos em viagem](mobile-approvals.md)
