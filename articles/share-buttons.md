---
title: Partilhe os seus botões com outras pessoas. | Microsoft Docs
description: Partilhe os seus botões com outras pessoas para que possam utilizar os seus botões e poupar tempo.
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
ms.date: 09/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9b5671096bbecd9221d3849cd656548291acd4c9
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296928"
---
# <a name="share-button-flows-in-power-automate"></a>Partilhe fluxos de botões no Power Automate

Na aplicação móvel do Power Automate, pode partilhar [fluxos de botões](introduction-to-button-flows.md) (botões) com outros utilizadores ou grupos da organização. Quando partilha um botão, a pessoa ou o grupo com quem o partilha pode executar o botão da mesma forma que executam os seus próprios botões. Também pode [partilhar uma ligação](share-buttons.md#re-share-a-button) para botões que outra pessoa partilhou consigo. Pode [parar de partilhar](share-buttons.md#stop-sharing-a-button) os seus botões em qualquer altura.

> As capturas de ecrã utilizadas neste documento foram tiradas de um dispositivo Android. Se estiver a utilizar um iPhone, as imagens poderão ser diferentes, mas a funcionalidade é a mesma.
> 
> 

Siga [estes passos](share-buttons.md#use-shared-buttons) para utilizar um botão que alguém tenha partilhado consigo.

## <a name="prerequisites"></a>Pré-requisitos
Para partilhar botões, precisa de:

* Uma conta com acesso ao [Power Automate](https://flow.microsoft.com).
* Um fluxo para partilhar.
* Um dispositivo móvel com a aplicação móvel Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows).
* Um grupo ou utilizador dentro da organização com quem partilhar o botão.

## <a name="share-a-button"></a>Partilhar um botão
Pode partilhar um botão a partir do separador **Botões** da aplicação móvel do Power Automate.

1. Toque no pequeno ícone junto ao botão que quer partilhar.
   
    ![partilhar botão](./media/share-buttons/share-button-flows-buttons-tab.png)
2. Toque em **Convidar outras pessoas** a partir da página **Utilizadores do botão**.
   
    ![partilhar botão](./media/share-buttons/share-button-flows-button-users.png)
3. Procure e, em seguida, selecione o grupo ou pessoa com o qual pretende partilhar o botão.
   
    ![partilhar botão](./media/share-buttons/share-button-flows-invite-others-select.png)
4. Toque em **ENVIAR** na página **Convidar outras pessoas**.
   
    ![partilhar botão](./media/share-buttons/share-button-flows-invite-others-send.png)
5. Toque em **CONCLUÍDO** na página que indica que a operação de partilha do botão foi concluída com êxito.
   
    ![partilhar botão](./media/share-buttons/share-button-flows-invite-others-done.png)

## <a name="require-users-to-use-their-own-connections"></a>Exigir que os utilizadores utilizem as respetivas ligações
> [!NOTE]
> Quando partilha um botão, pode permitir que as pessoas com quem partilhou o botão utilizem todas as ligações utilizadas pelo mesmo. Também pode pedir-lhes para utilizar as respetivas ligações. Se permitir que outras pessoas utilizem as suas ligações, elas não podem aceder às credenciais na sua ligação nem reutilizá-las em qualquer outro fluxo.
> 
> 

Siga estes passos para exigir que as pessoas com quem partilhou os botões utilizem as suas próprias ligações.

1. Selecione **GERIR LIGAÇÕES** no ecrã que é apresentado imediatamente após partilhar um botão.
2. Selecione **EDITAR** no botão que pretende gerir.
3. Selecione **Fornecido pelo utilizador** ou o seu endereço de e-mail.
   
    A sua escolha indica as ligações que têm de ser utilizadas no botão partilhado.
   
    ![partilhar botão](./media/share-buttons/share-button-select-connection-provided-by-user.png)
   
    Pode ver ou alterar a sua escolha em qualquer altura. Para tal, selecione o separador **Fluxos** > o fluxo que partilhou > **Utilizadores e ligações** > o separador **LIGAÇÕES** > **EDITAR** no botão que quer gerir.
   
    ![partilhar botão](./media/share-buttons/share-button-flows-conn-provided-by-user.png)

## <a name="view-the-list-of-button-users"></a>Ver a lista de utilizadores do botão
Pode ver todos os grupos ou utilizadores com quem um botão é partilhado ao seguir estes passos a partir do separador **Botões**:

1. Toque no pequeno ícone junto ao botão em que está interessado.
2. Na página **Utilizadores do botão**, veja todos os grupos ou utilizadores com os quais o botão é partilhado.
   
    ![ver utilizadores do botão](./media/share-buttons/share-button-flows-button-users-list.png)

## <a name="stop-sharing-a-button"></a>Parar de partilhar um botão
Para parar de partilhar um botão, siga estes passos a partir do separador **Botão**:

1. Toque no pequeno ícone junto ao botão que já não quer partilhar.
2. Na página **Utilizadores do botão**, toque no grupo ou utilizador com os quais quer deixar de partilhar o botão.
   
    ![parar de partilhar um botão](./media/share-buttons/share-button-flows-remove-user-list.png)
3. Toque em **Remover utilizador** quando a página do utilizador for apresentada.
   
    ![parar de partilhar um botão](./media/share-buttons/share-button-flows-remove-user.png)
4. Aguarde pela conclusão da operação de remoção. Tenha em atenção que a lista de **Utilizadores do botão** é atualizada e o utilizador ou grupo que removeu já não estará listado.
   
    ![parar de partilhar um botão](./media/share-buttons/share-button-flows-remove-user-result.png)

## <a name="monitor-the-run-history"></a>Monitorizar o histórico de execuções
Todos os históricos de execução, incluindo as execuções iniciadas por uma pessoa com quem um botão foi partilhado, são apresentadas apenas no separador **Atividade** da aplicação móvel do Power Automate do criador do botão.

## <a name="use-shared-buttons"></a>Utilizar botões partilhados
Antes de poder executar um botão que alguém tenha partilhado consigo, tem de o adicionar ao seu separador **Botões** a partir da página **Adicionar botões**.

1. Toque em **OBTER MAIS** (ou na faixa **Estão disponíveis novos botões**, caso a mesma seja apresentada) no separador **Botões**.
   
    ![novo botão partilhado comigo](./media/share-buttons/share-button-flows-banner.png)
2. Toque no botão que quer utilizar.
   
    O botão tocado é adicionado imediatamente ao separador **Botões** da aplicação Power Automate. Em seguida, pode utilizar o botão do separador **Botões** tal como utiliza qualquer outro botão aí apresentado.
   
    ![novo botão partilhado comigo](./media/share-buttons/share-button-flows-buttons-shared-with-me.png)

## <a name="re-share-a-button"></a>Voltar a partilhar um botão
Pode partilhar uma ligação de um botão que foi partilhado consigo.

1. Selecione **...** junto ao botão que quer partilhar.
2. Selecione **Partilhar ligação do botão**.
   
    ![voltar a partilhar a ligação do botão](./media/share-buttons/re-share-button.png)
3. Selecione a aplicação que pretende utilizar para partilhar o botão e, em seguida, siga os passos para enviar o botão para as pessoas com quem pretende partilhá-lo.

## <a name="stop-using-a-shared-button"></a>Parar de utilizar um botão partilhado
Se quiser deixar de utilizar um botão que tenha sido partilhado consigo, remova-o do separador **Botões** através dos passos seguintes:

1. No separador **Botões**, toque em **...** junto ao botão que já não quer utilizar.
   
    ![remover botão](./media/share-buttons/share-button-flows-added-shared-button.png)
2. Toque em **Remover** no menu que aparece.

Já está. O botão já não aparece no separador **Botões** da aplicação do Power Automate.

> [!NOTE]
> Depois de remover um botão partilhado, pode adicioná-lo novamente ao selecionar **OBTER MAIS** a partir do separador **Botões**.
> 
> 

