---
title: Criar um fluxo a partir de um modelo | Microsoft Docs
description: Crie um fluxo a partir de qualquer um dos vários modelos incorporados.
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
ms.date: 02/07/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f2e92d43a33a4a05523ae350a63aa68f9cda2d1f
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74368703"
---
# <a name="create-a-flow-from-a-template-in-power-automate"></a>Criar um fluxo a partir de um modelo no Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Crie um fluxo a partir de um dos diversos modelos incorporados que podem, por exemplo, enviar-lhe uma mensagem Slack quando o gestor envia um e-mail no Office 365.

**Nota:** [crie um fluxo do zero](get-started-logic-flow.md) se já tiver um processo em mente e não conseguir localizar um modelo para ele.

**Pré-requisitos**

* Uma conta no [flow.microsoft.com](https://flow.microsoft.com)
* Uma conta Slack
* Credenciais do Office 365

## <a name="choose-a-template"></a>Escolher um modelo
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZJK8cYdjAic?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Em [flow.microsoft.com](https://flow.microsoft.com), selecione **Modelos** na barra de navegação superior.
2. Na barra de pesquisa, escreva **Slack** e, em seguida, selecione o ícone de pesquisa.
3. Verá apenas modelos relacionados com Slack, pelo que pode agora selecionar **Enviar uma mensagem no Slack quando o gestor me envia e-mails**.
   
    ![Nova opção na barra de navegação à esquerda](./media/get-started-logic-template/select-template.png)
4. Confirme que este modelo irá fazer o que pretende e, em seguida, selecione **Utilizar este modelo**.
5. Se não tem sessão iniciada no Office ou no Slack, selecione **Iniciar sessão** e siga as instruções.
   
    ![Lista de ligações de que o modelo precisa](./media/get-started-logic-template/confirm-connections.png)
6. Depois de confirmar as suas ligações, selecione **Continuar**.
   
    O fluxo aparece e mostra cada ação com uma barra de título cor de laranja.
   
    ![Eventos e ações predefinidas do modelo](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>Personalizar o fluxo
1. Selecione a barra de título para expandir um evento e personalize-o (por exemplo, especificando um filtro no e-mail que lhe interessa).
2. As ações que exigem a intervenção do utilizador serão expandidas automaticamente.
   
    Por exemplo, a ação **Publicar mensagem** é expandida uma vez que tem de introduzir um canal, tal como o seu *\@nome de utilizador*. Também pode personalizar o conteúdo da mensagem. Por predefinição, a mensagem irá conter apenas o assunto, mas pode incluir outras informações.
   
    ![Especifique o canal para Slack](./media/get-started-logic-template/specify-keyword.png)
3. Perto da parte superior do ecrã, especifique um nome para o fluxo e selecione **Criar fluxo**.
4. Por último, se estiver satisfeito com o fluxo, selecione **Concluído**.
   
    ![Botão Concluído](./media/get-started-logic-template/done.png)

Agora, quando o gestor envia um e-mail, irá receber uma mensagem do Slack que contém as informações que especificou.

## <a name="next-steps"></a>Passos seguintes
* [Ver o fluxo em ação](see-a-flow-run.md)
* [Publicar o seu próprio modelo](publish-a-template.md)
* [Utilizar um modelo do Common Data Service](common-data-model-intro.md)
* [Comece a trabalhar com fluxos de equipa](create-team-flows.md) e convide outras pessoas para colaborar consigo na criação de fluxos.

