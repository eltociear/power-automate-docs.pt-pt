---
title: Common Data Service | Microsoft Docs
description: Crie um fluxo para importar dados, exportar dados ou compilar aprovações com o Common Data Service.
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
ms.date: 10/22/2016
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2b536263d90af7b0bbdcdec30d1b00bc7bae2a9e
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74361205"
---
# <a name="create-a-flow-that-uses-the-common-data-service"></a>Criar um fluxo que utilize o Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Melhore a eficiência operacional com uma vista unificada de dados de negócio ao criar um fluxo que utilize o [Common Data Service](https://powerapps.microsoft.com/tutorials/data-platform-intro/). Implemente esta base de dados de negócio segura que abrange as entidades de negócio padrão corretamente formado (por exemplo, Vendas, Compra, Suporte ao Cliente e Produtividade) na organização. Armazene dados organizacionais numa ou mais [entidades personalizadas](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/), que oferecem vários benefícios no que respeita a origens de dados externas, tais como o Microsoft Excel e o Salesforce.

Por exemplo, tire partido do Common Data Service no Power Automate das seguintes formas:

* Crie um fluxo para importar dados, exportar dados ou efetuar a ação na parte superior de dados (tal como enviar uma notificação). Tenha em atenção que esta abordagem não é um serviço de sincronização completa; permite-lhe unicamente mover os dados para dentro ou para fora por entidade.
  
    Para obter passos detalhados, veja os procedimentos mais adiante neste tópico.
* Em vez de [criar um ciclo de aprovação através do e-mail](wait-for-approvals.md), crie um fluxo que armazene o estado de aprovação numa entidade e compile uma aplicação personalizada na qual os utilizadores possam aprovar ou rejeitar itens.
  
    Para obter passos detalhados, veja [Compilar um ciclo de aprovação com o Common Data Service](common-data-model-approve.md).

**Pré-requisitos**

* Inscrição no [Power Automate](https://flow.microsoft.com) e no [PowerApps](https://make.powerapps.com).
  
    Se tiver problemas, verifique se o [Power Automate](sign-up-sign-in.md) e o [Power Apps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) suportam o tipo de conta que tem e se a organização não bloqueou a inscrição.
* Se ainda não utilizou o Common Data Service, abra o separador **Entidades** de [powerapps.com](https://web.powerapps.com/#/entities) e, em seguida, clique ou toque em **Criar a minha base de dados**.

## <a name="sign-in-to-your-environment"></a>Iniciar sessão no seu ambiente
1. Abra o [portal do Power Automate](https://flow.microsoft.com) e clique ou toque em **Iniciar sessão** no canto superior direito.
   
    **Nota**: Poderá ter de abrir o menu superior à esquerda para mostrar o botão **Iniciar sessão**.
   
    ![Iniciar sessão](./media/common-data-model-intro/signin-flow.png)
2. No menu superior à direita, selecione o ambiente no qual criou a base de dados em powerapps.com.
   
    **Nota**: Se não selecionar o mesmo ambiente, não verá as suas entidades.
   
    ![Selecionar o ambiente](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>Abrir um modelo
1. Na caixa **Procurar modelos** na parte superior do ecrã, escreva ou cole **comuns**, e, em seguida, prima Enter.
   
    ![Procurar modelos](./media/common-data-model-intro/template-search.png)
2. Na lista de modelos, clique ou toque no modelo que importa dados da origem que pretende para a entidade (ou *objeto*) que pretende.
   
    Por exemplo, clique ou toque no modelo que copia as informações de contacto do Dynamics 365 para o Common Data Service.
   
    ![Escolher um modelo](./media/common-data-model-intro/choose-template.png)
3. Clique ou toque em **Utilizar este modelo**.
   
    ![Utilizar modelo](./media/common-data-model-intro/use-template.png)
4. Se ainda não tiver criado uma ligação do Power Automate para o Dynamics 365, clique ou toque em **Iniciar sessão** e forneça as credenciais se lhe forem pedidas.
   
    ![Iniciar sessão no Dynamics 365](./media/common-data-model-intro/dynamics-signin.png)
5. Clique ou toque em **Continuar**.
   
    ![Confirmar contas](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>Compilar o fluxo
1. No primeiro cartão, especifique o evento que acionará o fluxo.
   
    Por exemplo, está a compilar um fluxo que copiará novos contactos de uma instância do Dynamics 365 para o Common Data Service. Em **Quando é criado um registo**, especifique a instância clicando ou tocando na seta para baixo e, em seguida, clique ou toque numa opção da lista que é apresentada.
   
    ![Especificar a instância do Dynamics 365](./media/common-data-model-intro/specify-instance.png)
2. (opcional) Junto da parte superior do ecrã, especifique um nome diferente para o fluxo que está a criar.
   
    **Nota**: se a janela do browser não estiver maximizada, a IU poderá parecer ligeiramente diferente.
   
    ![Fluxo do nome](./media/common-data-model-intro/name-flow.png)
3. Clique ou toque em **Criar fluxo**.
   
    **Nota**: se a janela do browser não estiver maximizada, poderá aparecer apenas a marca de verificação.
   
    ![Criar fluxo](./media/common-data-model-intro/create-flow.png)

Agora, sempre que esse objeto for criado no sistema de origem, será importado para o Common Data Service. Se não conseguir encontrar um modelo que faça o que precisa, poderá [compilar um fluxo do zero](get-started-logic-flow.md) que funciona por cima do Common Data Service.

Pode realizar ações sobre alterações na base de dados. Pode, por exemplo, enviar correio de notificação sempre que houver alteração dos dados.

