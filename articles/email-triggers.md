---
title: Executar fluxos com base nas propriedades de e-mail | Microsoft Docs
description: Inicie um fluxo com base em propriedades como o assunto, o endereço do remetente ou o endereço do destinatário de um e-mail.
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
ms.date: 06/08/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f7588a3ca1db5c62a4e60380575542671e8d408d
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79192322"
---
# <a name="trigger-a-flow-based-on-email-properties"></a>Acionar um fluxo com base nas propriedades de e-mail

Utilize o acionador **Quando é recebida uma nova mensagem de e-mail** para criar um fluxo que é executado quando uma ou mais das seguintes propriedades de e-mail correspondem aos critérios fornecidos:

| Propriedade | Quando utilizar |
| --- | --- |
| Pasta |Acionar um fluxo sempre que são recebidos e-mails numa pasta específica. Esta propriedade pode ser útil se tiver regras para encaminhar e-mails para pastas diferentes. |
| Para |Acionar um fluxo com base no endereço para o qual foi enviado um e-mail. Esta propriedade pode ser útil se receber e-mails que foram enviados para diferentes endereços de e-mail na mesma caixa de entrada. |
| A partir do |Acionar um fluxo com base no endereço de e-mail do remetente. |
| Importância |Acionar um fluxo com base na importância de envio dos e-mails. Os e-mails podem ser enviados com prioridade alta, normal ou baixa. |
| Tem Anexo |Acionar um fluxo com base na presença de anexos nos e-mails recebidos. |
| Filtro de Assunto |Pesquisar a presença de palavras específicas no assunto de um e-mail. O fluxo executa então as *ações* com base nos resultados da pesquisa. |

> [!IMPORTANT]
> Cada [plano do Power Automate](https://flow.microsoft.com/pricing/) inclui uma quota de execução. Marque as propriedades do acionador do fluxo sempre que possível. Ao fazê-lo, evita que a quota de execução seja utilizada desnecessariamente. Se marcar uma propriedade numa condição, cada execução é deduzida da quota de execução do seu plano, mesmo se a condição de filtro definida não for cumprida. 

Por exemplo, se marcar um endereço *de* um e-mail numa condição, cada execução é deduzida da quota de execução do seu plano, mesmo se não for *do* endereço que lhe interessa.
> 
> 

Nas instruções seguintes, marcamos todas as propriedades no acionador **Quando é recebida uma nova mensagem de e-mail**. Saiba mais ao consultar as [perguntas frequentes sobre faturação](billing-questions.md#what-counts-as-a-run) e a página de [preços](https://ms.flow.microsoft.com/pricing/).

## <a name="prerequisites"></a>Pré-requisitos
* Uma conta que tenha acesso ao [Power Automate](https://flow.microsoft.com)
* Uma conta do Outlook do Office 365
* A aplicação móvel do Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows)
* Ligações ao Office, Outlook e ao serviço de notificações push

## <a name="trigger-a-flow-based-on-an-emails-subject"></a>Acionar um fluxo com base no assunto de um e-mail
Nestas instruções, criamos um fluxo que envia uma notificação push para o telemóvel se o assunto de qualquer e-mail novo incluir a palavra “lottery” (lotaria). O fluxo marca estes e-mails como *lidos*.

>[!NOTE]
>Embora estas instruções enviem uma notificação push, pode utilizar qualquer outra ação que seja mais adequada às necessidades do seu fluxo de trabalho. Por exemplo, poderia armazenar os conteúdos de e-mail noutro repositório, como o Google Sheets ou um ficheiro do Microsoft Excel armazenado no Dropbox.

Bem, vamos começar:

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. Na caixa **Filtro de Assunto**, introduza o texto que o fluxo utiliza para filtrar os e-mails recebidos.
   
     Neste exemplo, interessam-nos todos os e-mails com a palavra "lottery" no assunto.
   
    ![Opções avançadas](./media/email-triggers/email-triggers-subject-text.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Introduza os detalhes da notificação por telemóvel que pretende receber quando for recebido um e-mail que corresponda ao **Filtro de Assunto** que especificou anteriormente.
   
    ![Detalhes da notificação](./media/email-triggers/email-triggers-4.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Dê um nome ao seu fluxo. Em seguida, guarde-o ao selecionar **Criar fluxo** na parte superior da página.
   
    ![Guardar fluxo](./media/email-triggers/email-triggers-subject-notification.png)

Parabéns! Agora irá receber uma notificação push sempre que receber um e-mail que contenha a palavra "lottery" no assunto.

## <a name="trigger-a-flow-based-on-an-emails-sender"></a>Acionar um fluxo com base num remetente de e-mail
Nestas instruções, criamos um fluxo que envia uma notificação push para o telemóvel se for recebido qualquer e-mail novo de um remetente específico (endereço de e-mail). O fluxo também marca e-mails deste tipo como *lidos*.

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. Na caixa **De**, introduza o endereço de e-mail do remetente. 
   
     O fluxo age em todos os e-mails que forem enviados por este endereço.
   
    ![Propriedade de e-mail](./media/email-triggers/email-triggers-from.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Introduza os detalhes da notificação por telemóvel que gostaria de receber sempre que for recebida uma mensagem do endereço de e-mail que introduziu anteriormente.
   
    ![Detalhes da notificação](./media/email-triggers/email-triggers-sender-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Dê um nome ao fluxo e, em seguida, guarde-o selecionando **Criar fluxo** na parte superior da página.
   
    ![Guardar fluxo](./media/email-triggers/email-triggers-sender-5.png)

## <a name="trigger-a-flow-when-emails-arrive-in-a-specific-folder"></a>Acionar um fluxo quando são recebidos e-mails numa pasta específica
Se tiver regras de encaminhamento de e-mails para pastas diferentes com base em determinadas propriedades, como o endereço, este tipo de fluxo poderá interessar-lhe.

Vamos começar:

> [!NOTE]
> Se ainda não tiver uma regra que encaminha para uma pasta diferente além da caixa de entrada, crie essa regra e certifique-se de que funciona, enviando um e-mail de teste.
> 
> 

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-specific-folder](includes/sign-in-use-blank-select-email-trigger-and-specific-folder.md)]

1. Selecione a pasta para a qual está a encaminhar e-mails específicos. Para apresentar as pastas de e-mail, em primeiro lugar selecione o ícone **Mostrar Seletor**, que está localizado no lado direito da caixa **Pasta** do cartão **Ao receber um novo e-mail**.
   
    ![Selecionar pasta](./media/email-triggers/email-triggers-2.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Introduza os detalhes da notificação por telemóvel que gostaria de receber quando for recebido um e-mail na pasta que selecionou anteriormente. Se ainda não o tiver feito, introduza as credenciais do serviço de notificações.
   
    ![Detalhes da notificação](./media/email-triggers/email-triggers-folder-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Dê um nome ao fluxo e, em seguida, guarde-o selecionando **Criar fluxo** na parte superior da página.
   
    ![Guardar fluxo](./media/email-triggers/email-triggers-7.png)

Teste o fluxo, enviando um e-mail que é encaminhado para a pasta que selecionou anteriormente nestas instruções.

