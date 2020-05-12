---
title: Saiba como adicionar outros proprietários a um fluxo e como criar fluxos de equipa | Microsoft Docs
description: O Power Automate simplifica a automatização de tarefas repetitivas. Pode adicionar utilizadores ou grupos como proprietários e colaborar com os mesmos para criar e gerir os fluxos.
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
ms.date: 11/15/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b4479c2df6b8c7a1d5c269a8e0a48f15c1dda275
ms.sourcegitcommit: 5b1965a0c319c4294b7dc0c829120ed1f4f90444
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/25/2020
ms.locfileid: "3299326"
---
# <a name="create-team-flows"></a>Criar fluxos de equipa

Crie um fluxo de equipa adicionado outras pessoas à organização como proprietários. Todos os proprietários de um fluxo de equipa podem desempenhar estas ações:

* Ver o histórico do fluxo (ou seja, cada execução).
* Gira as propriedades do fluxo (por exemplo, iniciar ou parar o fluxo, adicionar proprietários ou atualizar as credenciais para uma ligação).
* Editar a definição do fluxo (por exemplo, adicionar ou remover uma ação ou condição).
* Adicionar e remover outros proprietários (mas não o criador do fluxo).
* Eliminar o fluxo.

Se for o criador ou um proprietário de um fluxo de equipa, vai encontrá-lo listado no separador **Fluxos de equipa** no [Power Automate](https://flow.microsoft.com).

![separador fluxos de equipa](./media/create-team-flows/addowner5.png)

> [!NOTE]
> As ligações partilhadas podem ser utilizadas **apenas** no fluxo no qual foram criadas.
> 
> 

Os proprietários podem utilizar serviços num fluxo, mas não podem modificar as credenciais de uma ligação criada por outro proprietário.

## <a name="prerequisites"></a>Pré-requisitos
Deve ter um plano [plano do Power Automate pago](https://flow.microsoft.com/pricing/) para criar um fluxo de equipa. Além disso, deve ser o criador ou o proprietário para adicionar/remover os proprietários de um fluxo de equipa.

## <a name="create-a-team-flow"></a>Criar um fluxo de equipa
Siga estes passos para criar um fluxo de equipa ou para adicionar mais proprietários a um fluxo de equipa.

1. Inicie sessão no [Power Automate](https://flow.microsoft.com) e, em seguida, selecione **Os meus fluxos**.
2. Selecione **Mais comandos** e, em seguida, selecione o botão **Partilhar** para o fluxo que pretende partilhar:
   
    ![ícone da equipa](./media/create-team-flows/addowner1.png)
3. Introduza o nome, o endereço de e-mail ou o nome do grupo da pessoa ou grupo que quer adicionar como proprietário:
   
    ![procure o utilizador](./media/create-team-flows/addowner2.png)
4. Na lista que é apresentada, selecione o utilizador ao qual quer conceder o nível de proprietário:
   
    ![selecione o utilizador](./media/create-team-flows/addowner3.png)
   
     O utilizador ou grupo que selecionou torna-se um proprietário do fluxo:
   
    ![novo proprietário](./media/create-team-flows/addowner4.png)
   
     Parabéns &mdash; criou um fluxo de equipa!

## <a name="add-a-list-as-a-co-owner"></a>Adicionar uma lista como coproprietário

Pode adicionar listas do SharePoint como coproprietário a um fluxo para que todas as pessoas com acesso de edição à lista obtenham automaticamente acesso de edição ao fluxo. Quando o fluxo for partilhado, pode distribuir uma ligação para o mesmo.

> [!TIP]
> Utilize uma lista quando o fluxo estiver ligado ao SharePoint e utilize um grupo noutros casos.
>

## <a name="remove-an-owner"></a>Remover um proprietário

> [!IMPORTANT]
> Ao remover um proprietário cujas credenciais são utilizadas para aceder a serviços do Power Automate, deve atualizar as credenciais dessas ligações para que o fluxo continue a ser executado corretamente.
> 
> 

1. Selecione **Mais comandos** e, em seguida, selecione o botão **Partilhar** para o fluxo que pretende partilhar:
   
    ![selecione o ícone pessoas](./media/create-team-flows/addowner1.png)
2. Selecione o ícone **Eliminar** para o proprietário que quer remover:
   
    ![selecione eliminar](./media/create-team-flows/removeowner2.png)
3. Na caixa de diálogo de confirmação, selecione **Remover este proprietário**:
   
    ![confirmar remoção](./media/create-team-flows/removeowner3.png)
4. Parabéns &mdash; o utilizador ou grupo que removeu já não está listado como proprietário do fluxo.


## <a name="update-connection-owner"></a>Atualizar proprietário da ligação

Poderá ter de alterar o proprietário de uma ligação num fluxo se remover o proprietário existente. Siga estes passos para mudar o proprietário de um fluxo:

1. Selecione **Dados** no painel esquerdo.
1. Selecione **Ligações**.
1. Procure a ligação que quer atualizar e, em seguida, selecione-a.
1. Selecione **...** (mais comandos) na ligação selecionada e, em seguida, **Mudar de conta**.
1. Siga os passos para utilizar uma conta diferente para a ligação.

## <a name="embedded-and-other-connections"></a>Ligações incorporadas e outras ligações

As ligações utilizadas num fluxo abrangem duas categorias:

* **Incorporadas** &mdash; Estas ligações são utilizadas no fluxo.
* **Outras** &mdash; Estas ligações foram definidas para um fluxo, mas não são utilizadas no mesmo.

Se parar de utilizar uma ligação num fluxo, a mesma é apresentada na lista de ligações **Outras**, onde permanece até um proprietário a incluir novamente no fluxo.

Siga os passos para [atualizar um proprietário da ligação](./create-team-flows.md#update-connection-owner) para fazer alterações em ligações incorporadas.

A lista de ligações é apresentada abaixo da lista de proprietários nas propriedades de um fluxo:

![ligações incorporadas](./media/create-team-flows/embeddedconnections.png)

