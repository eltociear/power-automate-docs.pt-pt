---
title: Filtrar e copiar dados | Microsoft Docs
description: Saiba como filtrar e copiar dados da origem para o destino com o Power Automate
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
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
ms.openlocfilehash: 4e0e827b24b81ead79cb1fec73916e625b715eea
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74375833"
---
# <a name="filter-and-copy-data-with-power-automate"></a>Filtrar e copiar dados com o Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Estas instruções mostram como criar um fluxo que monitoriza itens novos ou alterados numa origem e, em seguida, copia essas alterações para um destino. Pode criar um fluxo como este, se os seus utilizadores introduzirem dados numa única localização, mas a sua equipa precisa deles numa localização ou formato diferentes.

Embora estas instruções copiem dados de uma [lista](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) do Microsoft SharePoint (a origem) para uma tabela da [Base de Dados SQL do Azure](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview) (o destino), pode copiar dados entre qualquer dos mais de [150 serviços](https://flow.microsoft.com/connectors/) suportados pelo Power Automate.

> [!IMPORTANT]
> As alterações efetuadas no destino não são copiadas para a origem porque as sincronizações bidirecionais não são suportadas. Se tentar configurar uma sincronização bidirecional, irá criar um ciclo infinito em que as alterações são enviadas infinitamente entre a origem e o destino.
> 
> 

## <a name="prerequisites"></a>Pré-requisitos
* Acesso a uma origem de dados e um destino. Estas instruções não incluem passos para criar a origem e o destino.
* Acesso ao [Power Automate](https://flow.microsoft.com).
* Uma compreensão básica do modo como os dados são armazenados.
* Familiaridade com as noções básicas de criação de fluxos. Pode rever como adicionar [ações, acionadores](multi-step-logic-flow.md#add-another-action) e [condições](add-condition.md). Os seguintes passos pressupõem que sabe como realizar estas ações.

> [!TIP]
> Os nomes de coluna na origem e no destino não têm de corresponder, mas tem de fornecer dados para todas as colunas *obrigatórias* ao inserir ou atualizar um item. O Power Automate identifica automaticamente os campos obrigatórios.
> 
> 

## <a name="quick-overview-of-the-steps"></a>Descrição geral rápida dos passos
Se estiver familiarizado com o Power Automate, siga estes passos rápidos para copiar dados de uma origem de dados para outra:

1. Identifique a origem que irá monitorizar e o destino para o qual irá copiar os dados alterados. Certifique-se de que tem acesso a ambos.
2. Identifique, pelo menos, uma coluna que identifica exclusivamente itens na origem e no destino. No exemplo que se segue, utilizamos a coluna **Título**, mas pode utilizar as colunas que quiser.
3. Configure um acionador que monitoriza alterações na origem.
4. Procure o destino para determinar se o item alterado existe.
5. Utilize uma **Condição** como esta:
   * Se o item novo ou alterado não existir no destino, crie-o.
   * Se o item novo ou alterado existir no destino, atualize-o.
6. Acione o fluxo e confirme que os itens novos ou alterados estão a ser copiados da origem para o destino.

> [!NOTE]
> Se não tiver criado anteriormente uma ligação para o SharePoint ou a Base de Dados SQL do Azure, siga as instruções quando lhe for pedido para iniciar sessão.
> 
> 

Eis os passos detalhados para criar o fluxo.

## <a name="monitor-the-source-for-changes"></a>Monitorizar alterações na origem
1. Inicie sessão no [Power Automate](https://flow.microsoft.com), selecione **Os meus fluxos** > **Criar do zero**.
2. Procure o **SharePoint** > selecione o acionador **SharePoint - Quando um item é criado ou modificado** da lista de acionadores.
3. Introduza o **Endereço do Site** e selecione o **Nome da Lista** no cartão **Quando um item é criado ou modificado**.
   
    Forneça o **Endereço do Site** e o **Nome da Lista** da lista do SharePoint que o seu fluxo monitoriza relativamente a itens novos ou atualizados.
   
    ![configurar acionador do sharepoint](media/odata-filters/configure-sharepoint-trigger.png)

## <a name="search-the-destination-for-the-new-or-changed-item"></a>Procurar o destino do item novo ou alterado
Utilizamos a ação **SQL Server - Obter linhas** para procurar o destino do item novo ou alterado.

1. Selecione **Novo passo** > **Adicionar uma ação**.
2. Procure **Obter linhas**, selecione **SQL Server - Obter linhas** e selecione a tabela que pretende monitorizar na lista **Nome da tabela**.
3. Selecione **Mostrar opções avançadas**.
4. Na caixa **Consulta de Filtro**, introduza **título eq '** , selecione o token **Título** na lista de conteúdo dinâmico e introduza **'** .
   
    O passo anterior pressupõe que está a corresponder os títulos das linhas na origem e no destino.
   
    O cartão **Obter linhas** deverá agora ser semelhante a esta imagem:
   
    ![tentar obter o item da base de dados de destino](media/odata-filters/configure-sql-get-rows-action.png)

## <a name="check-if-the-new-or-changed-item-was-found"></a>Verificar se o item novo ou alterado foi encontrado
Selecione **Novo passo** > **Adicionar uma condição** para abrir o cartão **Condição**.

No cartão da condição:

1. Selecione a caixa à esquerda.
   
    A lista **Adicionar conteúdo dinâmico a partir das aplicações e dos conectores utilizados neste fluxo** é aberta.
2. Selecione **valor** na categoria **Obter linhas**.
   
   > [!TIP]
   > Confirme que selecionou **valor** na categoria **Obter linhas**. Não selecione **valor** na categoria **Quando um item é criado ou modificado**.
   > 
   > 
3. Selecione **é igual a** na lista da caixa ao centro.
4. Introduza **0** (zero) na caixa no lado direito.
   
    O cartão **Condição** é agora semelhante a esta imagem:
   
    ![configurar uma condição](media/odata-filters/configure-condition.png)
5. Selecione **Editar no modo avançado**.
   
    Quando o modo avançado é aberto, verá a expressão **\@equals(body('Get_rows')?['value'], 0)** na caixa. Edite esta expressão, adicionando **length()** à volta da função **(body('Get_rows')?['value'], 0)** . A expressão completa assemelha-se agora a isto: **@equals(length(body('Get_rows')?['value']), 0)**
   
    O cartão **Condição** é agora semelhante a esta imagem:
   
    ![configurar uma condição](media/odata-filters/configure-condition-add-length.png)
   
   > [!TIP]
   > Adicionar a função **length()** permite ao fluxo verificar a lista **valor** e determinar se contém quaisquer itens.
   > 
   > 

Quando o fluxo "obtém" itens do destino, existem dois resultados possíveis.

| Resultado | Passo seguinte |
| --- | --- |
| O item existe |[Atualizar o item](odata-filters.md#update-the-item-in-the-destination) |
| O item não existe |[Criar um novo item](odata-filters.md#create-the-item-in-the-destination) |

> [!NOTE]
> As imagens dos cartões **Inserir linha** e **Atualizar linha** mostrados a seguir podem divergir das suas porque estes cartões mostram os nomes das colunas na tabela da Base de Dados SQL do Azure que está a ser utilizada no fluxo.
> 
> 

## <a name="create-the-item-in-the-destination"></a>Criar o item no destino
Se o item não existir no destino, crie-o com a ação **SQL Server - Inserir linha**.

No ramo **Se sim** da **Condição**:

1. Selecione **Adicionar uma ação**, procure **inserir linha** e selecione **SQL Server - Inserir linha**.
   
    O cartão **Inserir linha** é aberto.
2. Na lista **Nome da tabela**, selecione a tabela na qual o novo item será inserido.
   
    O cartão **Inserir linha** expande e apresenta todos os campos da tabela selecionada. Os campos com um asterisco (*) são obrigatórios e têm de ser preenchidos para a linha ser válida.
3. Selecione todos os campos que pretende preencher e introduza os dados.
   
    Pode introduzir os dados manualmente, selecionando um ou mais tokens do **Conteúdo dinâmico**, ou introduzindo uma combinação de texto e tokens nos campos.
   
    O cartão **Inserir linha** é agora semelhante a esta imagem:
   
    ![configurar uma condição](media/odata-filters/insert-row.png)

## <a name="update-the-item-in-the-destination"></a>Atualizar o item no destino
Se o item existir no destino, atualize-o com as alterações.

1. Adicione a ação **SQL Server - Atualizar linha** ao ramo **Se não** da **Condição**.
2. Siga os passos na secção [criar o item](odata-filters.md#create-the-item-in-the-destination) deste documento para preencher os campos da tabela.
   
    ![ver ambientes](media/odata-filters/update-row.png)
3. Na parte superior da página, introduza um nome para o fluxo na caixa **Nome do fluxo** e selecione **Criar fluxo** para guardá-lo.
   
    ![dar um nome ao fluxo](media/odata-filters/give-the-flow-a-name.png)

Agora, sempre que um item for alterado na lista do SharePoint (origem), o fluxo aciona e ou insere um novo item ou atualiza um item existente na Base de Dados SQL do Azure (destino).

> [!NOTE]
> O fluxo não é acionado quando um item é eliminado da origem. Se for um cenário importante, considere adicionar uma coluna separada que indica quando um item já não é necessário.
> 
> 

## <a name="learn-more"></a>Saiba mais
Utilize [operações de dados](data-operations.md) nos seus fluxos.

