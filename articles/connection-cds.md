---
title: Criar um fluxo automatizado com o Common Data Service | Microsoft Docs
description: Criar fluxos de trabalho com uma ligação do Common Data Service e o Power Automate
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/26/2020
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 18719ac34d84298dd813b0241d00b652ae172ef6
ms.sourcegitcommit: e58c8e6954c8e666497a66dc945fdc16c7c845a9
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/02/2020
ms.locfileid: "82727913"
---
# <a name="create-an-automated-flow-by-using-common-data-service"></a>Criar um fluxo automatizado com o Common Data Service

>[!IMPORTANT]
>Estão disponíveis três conectores para ligar ao Common Data Service. Utilize o [conector do Common Data Service (ambiente atual)](./connection-cds-native.md) recomendado. O **conector do Common Data Service**, abordado neste artigo, e o [conector do Dynamics 365](https://docs.microsoft.com/connectors/dynamicscrmonline/) estão disponíveis caso não consiga utilizar o conector recomendado.


Com o conector do Common Data Service, pode criar fluxos que são iniciados ao criar e atualizar eventos no Common Data Service. Além disso, pode realizar ações de criação, atualização, obtenção e eliminação em registos no Common Data Service.

## <a name="initiate-a-flow-from-common-data-service"></a>Iniciar um fluxo a partir do Common Data Service

Pode utilizar qualquer um dos seguintes acionadores para iniciar o seu fluxo:

- Quando um registo é selecionado
- Quando um registo é criado
- Quando um registo é eliminado
- Quando um registo é atualizado


> [!div class="mx-imgBorder"]
> ![Selecione um acionador](./media/cds-connector/Triggers.png)

Se o acionador selecionado exigir que um ambiente seja selecionado, poderá selecionar `(Current)`, que irá utilizar sempre a base de dados no ambiente em que o Power Automate é executado. Se quiser que o seu fluxo seja sempre acionado com base num evento num ambiente específico, selecione esse ambiente.

> [!div class="mx-imgBorder"]
> ![Selecione o ambiente](./media/cds-connector/Environments.png)

Pode utilizar âmbitos para determinar se o seu fluxo é executado se criar um novo registo, se um novo registo é criado por um utilizador na sua unidade de negócio ou se um novo registo é criado por qualquer utilizador na sua organização.

> [!div class="mx-imgBorder"]
> ![Selecione o âmbito](./media/cds-connector/Scopes.png)

|Âmbito|Temporização do acionador|
| --- | --- |
|Unidade de Negócio|A ação é realizada num registo que pertence à sua unidade de negócio|
|Organização|A ação é realizada por qualquer pessoa na organização ou base de dados|
|Nível Principal: unidade de negócio subordinada|A ação é realizada num registo que pertence à sua unidade de negócio ou a uma unidade de negócio subordinada|
|Utilizador|A ação é realizada num registo que lhe pertence|

Os acionadores que são executados quando um registo é atualizado também podem utilizar atributos de filtragem. Isto garante que o fluxo só é executado quando um dos atributos definidos é atualizado.

> [!IMPORTANT]
> Utilize atributos de filtro para impedir que o seu fluxo seja executado desnecessariamente.

Este fluxo é acionado sempre que o nome próprio ou apelido do contacto que pertence ao utilizador do fluxo é atualizado.

> [!div class="mx-imgBorder"]
> ![Atributos de filtro](./media/cds-connector/FilterAttributes.png)

## <a name="trigger-privileges"></a>Privilégios do acionador

Para criar um fluxo que é acionado com base na criação, atualização ou eliminação de um registo, o utilizador tem de ter permissões de nível de utilizador para criar, ler, escrever e eliminar na entidade Callback Registration. Além disso, dependendo dos âmbitos definidos, o utilizador poderá precisar pelo menos desse nível de leitura na mesma entidade.  [Saiba mais](https://docs.microsoft.com/power-platform/admin/database-security) sobre segurança do ambiente.

## <a name="write-data-into-common-data-service"></a>Escrever dados no Common Data Service

Utilize qualquer uma das seguintes ações para escrever dados no Common Data Service:

- Criar um novo registo
- Atualizar um registo

Eis um exemplo de como criar uma tarefa de seguimento quando um utilizador especificado cria um novo registo de conta.  

> [!div class="mx-imgBorder"]
> ![Tarefa de seguimento](./media/cds-connector/Regarding.png)

## <a name="advanced-concepts"></a>Conceitos avançados

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Escrever dados nos campos Cliente, Proprietário e Relativo A

Para escrever dados nos campos Cliente, Proprietário e Relativo A, tem de preencher dois campos.

| Categoria do campo | Definições de exemplo |
| --- | --- |
| Relativo A | Relativo A = o ID do registo (por exemplo, ID da conta) e o Tipo de Relativo A conforme selecionado na lista. |
| Cliente | Representa o ID do registo e o tipo de cliente conforme selecionado na lista. |
| Proprietário | Representa o ID da equipa ou utilizador de sistema e o tipo de proprietário conforme selecionado na lista. |

### <a name="enable-upsert-behavior"></a>Ativar o comportamento de upsert

Pode tirar partido do comando **atualizar um registo** para fornecer ações de upsert, que atualizam o registo se ele já existir ou criam um novo registo. Para invocar o upsert, forneça a entidade e uma chave de GUID. Se o registo com a chave e o tipo especificados existir, ocorre uma atualização. Caso contrário, é criado um registo com a chave especificada.

### <a name="trigger-behavior"></a>Comportamento do acionador

Se tiver um acionador registado na atualização de um registo, o fluxo é executado para cada atualização *consolidada* no registo especificado. O serviço invoca o seu fluxo de forma assíncrona e com a payload que captura no momento em que a invocação ocorre.

> [!NOTE]
> Se tiver duas atualizações que ocorrem com uma diferença de segundos entre si, o fluxo pode ser acionado mais do que uma vez com o conteúdo com a versão mais recente.

As execuções do fluxo podem sofrer um atraso se existir um registo de tarefas de sistema pendentes no seu ambiente.  Se este atraso ocorrer, o seu fluxo é acionado quando a tarefa de sistema para invocar o fluxo é executada.

