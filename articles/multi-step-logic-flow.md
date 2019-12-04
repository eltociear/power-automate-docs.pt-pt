---
title: Adicionar uma opção avançada e várias ações | Microsoft Docs
description: Expanda um fluxo para incluir uma opção avançada, tal como definir um e-mail com alta prioridade e adicionar outra ação ao mesmo evento.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/20/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: fbc18e31b571149164b7316bdaa02d2840686995
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74376339"
---
# <a name="add-multiple-actions-and-advanced-options-to-a-flow"></a>Adicionar várias ações e opções avançadas a um fluxo
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Personalize um fluxo ao adicionar uma ou mais opções avançadas e várias ações ao mesmo acionador. Por exemplo, adicione uma opção avançada que envia uma mensagem de e-mail como alta prioridade. Para além do envio de correio quando um item é adicionado a uma lista do SharePoint, crie um ficheiro no Dropbox que contenha as mesmas informações.

## <a name="prerequisites"></a>Pré-requisitos
* [Criar um fluxo](get-started-logic-flow.md)

## <a name="add-another-action"></a>Adicionar outra ação
Neste procedimento, terá de adicionar uma ação no meio do fluxo. Esta ação irá guardar um ficheiro no seu Dropbox, arquivando o item na lista.

1. No [flow.microsoft.com](https://flow.microsoft.com), selecione **Meus fluxos** na barra de navegação superior.
2. Na lista de fluxos, selecione o fluxo que quer editar.
3. Selecione **Novo passo** e, em seguida, selecione **Adicionar uma ação**.
   
    ![Adicionar fechado](./media/multi-step-logic-flow/add-action.png)
4. Na lista de ações possíveis, procure **Criar ficheiro** e, em seguida, selecione **Dropbox - Criar ficheiro**.
   
    ![procurar criar ficheiro](./media/multi-step-logic-flow/create-file-search.png)
5. Se lhe for pedido, forneça as credenciais do Dropbox.
6. Selecione o ícone de pasta no lado direito da caixa **Caminho da pasta**.
7. Localize e, em seguida, selecione a pasta na qual quer colocar o novo ficheiro.
   
    ![procurar criar ficheiro](./media/multi-step-logic-flow/create-file-folder.png)
8. Introduza o nome do novo ficheiro na caixa **Nome de ficheiro**. Certifique-se de que acrescenta uma extensão, como, por exemplo, ".txt", ao nome do ficheiro. Aqui, vamos utilizar o **TweetId** no nome do ficheiro para garantir a exclusividade dos ficheiros. Poderá ter de selecionar **Ver mais** para encontrar o token **TweetId**.
9. Adicione o texto que quer que o ficheiro contenha ao escrevê-lo na caixa **Conteúdo do ficheiro**. Também pode adicionar tokens à caixa **Conteúdo do ficheiro**.
   
    ![nome de ficheiro e conteúdo](./media/multi-step-logic-flow/create-file-name-and-contents.png)
   
   > [!IMPORTANT]
   > Se der ao ficheiro um nome que corresponda ao nome de um ficheiro existente (na pasta selecionada), o ficheiro existente será substituído.
   > 
   > 
10. Selecione **Atualizar fluxo**, que se encontra no menu na parte superior do ecrã.
11. Envie um tweet que contenha a palavra-chave que especificou.
    
     Dentro de um minuto, é criado um ficheiro na sua conta Dropbox.

## <a name="reorder-or-delete-an-action"></a>Reordenar ou eliminar uma ação
* Para receber e-mails depois da criação do ficheiro no Dropbox, mova a ação do Dropbox ao arrastar a barra de título por cima da ação de e-mail. Largue a ação do Dropbox por cima da seta entre o acionador (**Quando é publicado um novo tweet**) e a ação de e-mail. (O cursor indica se a ação está posicionada corretamente).
  
  > [!NOTE]
  > Não poderá mover um passo antes de outro, se estiver a utilizar saídas desse passo.
  > 
  > 
  
    ![Eliminar o menu](./media/multi-step-logic-flow/draggingaction.png)
* Para eliminar uma ação, selecione as reticências (…) junto do limite direito da barra de título para a ação que pretende eliminar, selecione **Eliminar**, e, em seguida, selecione **OK**.
  
    ![Eliminar o menu](./media/multi-step-logic-flow/deletemenu.png)
  
     **Nota:** não poderá eliminar uma ação se estiver a utilizar saídas da mesma em qualquer lugar no fluxo. Primeiro, remova essas saídas dos campos e, em seguida, pode eliminar a ação.


## <a name="copy-and-paste-actions"></a>Copiar e colar ações

Se quiser duplicar ações durante a criação de um fluxo, poderá copiar e colar ações. Por exemplo, se estiver a criar uma condição e desejar ações semelhantes no lado **Se sim** e no lado **Se não**, em vez de criar as duas ações do zero, poderá criar a primeira ação de um lado e, em seguida, copiar a ação para o outro lado.


### <a name="to-copy-an-action"></a>Para copiar uma ação
1. Selecione o menu de ação (os ... na parte superior direita da ação).
1. Selecione **Copiar para a minha área de transferência**. 
1. Selecione **Novo passo** no local onde quer que a ação fique. 

     Observe como o separador **A minha área de transferência** permite escolher de entre todas as ações que copiou.
1. Selecione o item que quer colar.

## <a name="add-advanced-options"></a>Adicionar opções avançadas
Comece com um fluxo que tenha a ação **Enviar e-mail**.

1. Selecione **Mostrar opções avançadas**, que se encontra na parte inferior do cartão **Envie um e-mail**.
   
     Em seguida, verá as opções avançadas para enviar uma mensagem de e-mail.
   
    ![Acionadores do SharePoint](./media/multi-step-logic-flow/advanced.png)
2. Selecione **Elevada** na lista **Importância** e, em seguida, selecione **Ocultar opções avançadas** para ocultar as opções avançadas.
3. Selecione **Atualizar fluxo**, que se encontra no menu na parte superior do ecrã.
   
     Este passo guarda as suas alterações.

