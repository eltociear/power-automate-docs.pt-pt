---
title: Criar um fluxo para automatizar tarefas | Microsoft Docs
description: Crie um fluxo para realizar automaticamente uma ou mais ações, como o envio de correio, quando ocorrem eventos, tal como alguém adicionar uma linha a uma lista do SharePoint.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/04/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9b0d2986e33aa65f9c5a0abc06d3beda116dbdc1
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79192099"
---
# <a name="create-a-flow-in-power-automate"></a>Criar um fluxo no Power Automate


> [!VIDEO https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]

Crie um fluxo que realize uma ou mais tarefas automaticamente depois de ser acionado por um evento. Por exemplo, crie um fluxo que o notifique por e-mail quando alguém lhe enviar um tweet que contenha uma palavra-chave que especificar. Neste exemplo, enviar um tweet é o evento e enviar correio é a ação.

## <a name="prerequisites"></a>Pré-requisitos

* Uma conta no [flow.microsoft.com](https://flow.microsoft.com)
* Uma conta do Twitter
* Credenciais do Office 365

## <a name="specify-an-event-to-start-the-flow"></a>Especifique um evento para iniciar o fluxo

Em primeiro lugar, terá de selecionar qual o evento ou *acionador*, que inicia o fluxo.

1. Em [flow.microsoft.com](https://flow.microsoft.com), selecione **Os meus fluxos** na barra de navegação superior e, em seguida, selecione **Criar do zero**.

    ![Opção dos fluxos na barra de navegação à esquerda](./media/get-started-logic-flow/create-logic-flow.png)
1. Selecione a caixa **Procurar entre centenas de conectores e acionadores** na parte inferior do ecrã, introduza **Twitter** na caixa que diz **Procurar todos os conectores e acionadores** e, em seguida, selecione **Twitter - Quando um novo tweet é publicado**.

    ![Evento do Twitter](./media/get-started-logic-flow/twitter-search.png)

   >[!TIP]
   >Os conectores suportam vários tipos de autenticação. Por exemplo, o SQL Server suporta o Azure Active Directory, a autenticação do SQL Server, a autenticação do Windows e a cadeia de ligação do SQL. Os utilizadores escolhem que tipo de autenticação querem utilizar ao configurar um conector.

1. Se ainda não ligou a sua conta do Twitter ao Power Automate, selecione **Iniciar sessão no Twitter** e forneça as suas credenciais.

1. Na caixa **Texto de consulta**, escreva a palavra-chave que pretende localizar.

    ![Palavra-chave do Twitter](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Especificar uma ação

1. Selecione **Novo passo** e, em seguida, selecione **Adicionar uma ação**.

    ![Adicionar ação](./media/get-started-logic-flow/add-action-icon.png)

1. Na caixa que mostra **Pesquisar por todos os conectores e ações**, escreva ou cole **enviar e-mail**e, em seguida, selecione**Office 365 Outlook - enviar um e-mail**.

    ![Lista de ações](./media/get-started-logic-flow/send-email.png)

1. Se lhe for pedido, selecione o botão de início de sessão e, em seguida, forneça as credenciais.

1. No formulário que aparece, escreva ou cole o seu endereço de e-mail na caixa **Para** e, em seguida, selecione o seu nome na lista de contactos que aparece.

    ![Mensagem de e-mail em branco](./media/get-started-logic-flow/blank-email.png)
1. Na caixa de **Assunto**, escreva ou cole **Novo tweet a partir de:** , em seguida, escreva um espaço.

    ![Linha do assunto com marcador de posição](./media/get-started-logic-flow/message-token.png)
1. Na lista de tokens, selecione o token **Tweeted by** para adicionar um marcador de posição para o mesmo.

    ![Adicionar parâmetro](./media/get-started-logic-flow/add-parameter.png)
1. Selecione a caixa **Corpo** e, em seguida, selecione o token **Texto do Tweet** para adicionar um marcador de posição para o mesmo.
1. (opcional) Adicione mais tokens, outros conteúdos ou ambos ao corpo da mensagem de e-mail.
1. Perto da parte superior do ecrã, dê um nome ao seu fluxo e selecione **Criar fluxo**.

    ![Selecione o botão Criar fluxo](./media/get-started-logic-flow/create-button.png)
1. Selecione **Concluído** para atualizar a lista dos fluxos.

     ![Selecione o botão concluído](./media/get-started-logic-flow/done-button.png)
1. Envie um tweet com a palavra-chave que indicou ou aguarde que alguém publique um tweet desse género.

     Dentro de um minuto após o tweet ser publicado, uma mensagem de e-mail notifica-o do novo tweet.

> [!TIP]
> Utilize a ação **Enviar e-mail (V2)** para formatar o e-mail e personalizar o tipo de letra, utilizar negrito, itálico ou sublinhado, personalizar a cor e o realce e criar listas ou ligações e muito mais.

![Editar a formatação do e-mail](media/get-started-logic-flow/email-rich-text.png)

## <a name="manage-a-flow"></a>Gerir um fluxo

1. No [flow.microsoft.com](https://flow.microsoft.com), selecione **Meus fluxos** na barra de navegação superior.
1. Na lista de fluxos, efetue um dos seguintes procedimentos:

   * Para colocar em pausa um fluxo, defina o botão de alternar como **Desligado**.

       ![Colocar um fluxo em pausa](./media/get-started-logic-flow/pause-flow.png)
   * Para retomar um fluxo, defina o botão de alternar como **Ligado**.

       ![Retomar o fluxo](./media/get-started-logic-flow/resume-flow.png)
   * Para editar um fluxo, selecione o ícone de lápis que corresponde ao fluxo que pretende editar.

       ![Selecionar fluxo](./media/get-started-logic-flow/select-flow.png)
   * Para eliminar um fluxo, selecione o ícone **...** , selecione **Eliminar**e, em seguida, selecione **Eliminar** na caixa de mensagem que é apresentada.

       ![Ícone eliminar](./media/get-started-logic-flow/delete-icon.png)
   * Para ver o histórico de execução de um fluxo, selecione o fluxo da página **Os meus fluxos** e, em seguida, veja o histórico na secção **HISTÓRICO DE EXECUÇÕES** da página que abre.

       ![histórico de execuções](./media/get-started-logic-flow/run-history.png)

     Selecione uma execução de fluxo da lista de execuções para ver as entradas e saídas de cada passo.

> [!NOTE]
> Pode ter até 600 fluxos na sua conta. Se já tiver 600, elimine um fluxo para poder criar outro.
>
>

## <a name="next-steps"></a>Próximos passos

* [Adicione passos](multi-step-logic-flow.md), tais como diferentes formas de ser notificado, ao fluxo.
* [Execute tarefas com base numa agenda](run-scheduled-tasks.md), quando pretender que uma ação ocorra diariamente, numa determinada data, ou após um determinado número de minutos.
* [Adicione um fluxo a uma aplicação](https://powerapps.microsoft.com/tutorials/using-logic-flows/) para permitir que a aplicação inicie a lógica na cloud.
* [Comece a trabalhar com fluxos de equipa](create-team-flows.md) e convide outras pessoas para colaborar consigo na criação de fluxos.
