---
title: Criar um fluxo automatizado com o conector do Common Data Service (ambiente atual) | Microsoft Docs
description: Criar fluxos de trabalho utilizando um conector do Common Data Service (ambiente atual) e Power Automate
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
ms.openlocfilehash: ca3dc36827423bffaed53b4ce19c50b94e09df81
ms.sourcegitcommit: 2284143cf147beb7d6071fd8005a41298e51e493
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/19/2020
ms.locfileid: "3384969"
---
# <a name="create-an-automated-flow-by-using-common-data-service-current-environment"></a>Criar um fluxo automatizado com o Common Data Service (ambiente atual)

>[!IMPORTANT]
>Existem três conectores disponíveis para ligar ao Common Data Service. Este artigo abrange o [Conector do Common Data Service (ambiente atual)](./connection-cds.md) recomendado para ligar ao Common Data Service. O [conector do Common Data Service](./connection-cds.md) e o [Dynamics 365 Connector](https://docs.microsoft.com/connectors/dynamicscrmonline/) também estão disponíveis para utilização se não for possível utilizar o conector recomendado.


Tem de [criar fluxos com reconhecimento de soluções](./overview-solution-flows.md) para utilizar o conector do Common Data Service (ambiente atual). 

Os fluxos que criar podem ser acionados quando um registo do Common Data Service é criado, atualizado ou eliminado.

Além disso, pode realizar ações de criação, atualização, obtenção e eliminação em registos no Common Data Service.

## <a name="initiate-a-flow-with-common-data-service-current-environment"></a>Iniciar um fluxo com o Common Data Service (ambiente atual)

Utilize o acionador **Quando um registo é criado, atualizado ou eliminado** para iniciar o fluxo:

   ![Selecione um acionador](./media/cds-connector-native/native-trigger.png)

Depois de selecionar um acionador, terá de configurar:

- Uma condição para o acionador.
- O nome da entidade.
- O âmbito do acionador.

### <a name="trigger-condition"></a>Condição de acionador

Pode adicionar qualquer uma destas condições para determinar precisamente quando o fluxo é acionado.

   ![Selecione um acionador](./media/cds-connector-native/trigger-conditions.png)

### <a name="the-entity-name"></a>O nome da entidade

Selecione uma das numerosas entidades disponíveis para indicar a entidade na qual o acionador opera.

   ![Selecione um acionador](./media/cds-connector-native/entity-names.png)

### <a name="scope"></a>Scope

Utilize âmbitos para determinar se o fluxo é executado quando você, alguém na unidade de negócio ou qualquer utilizador na organização cria um registo.

![Escolher âmbito](./media/cds-connector-native/scopes.png)

Seguem-se os detalhes de cada âmbito.

|Scope|Temporização do acionador|
| --- | --- |
|Unidade de Negócio|A ação é realizada num registo que pertence à sua unidade de negócio|
|Organização|A ação é realizada por qualquer pessoa na organização ou base de dados|
|Principal: unidade de negócio subordinada|A ação é realizada num registo que pertence à sua unidade de negócio ou a uma unidade de negócio subordinada|
|User|A ação é realizada num registo que lhe pertence|


Os acionadores que são executados quando um registo é atualizado também podem utilizar atributos de filtragem. Isto garante que o fluxo só é executado quando um dos atributos definidos é atualizado.

> [!IMPORTANT]
> Utilize atributos de filtro para impedir que o seu fluxo seja executado desnecessariamente.

Este fluxo é acionado sempre que o nome próprio ou apelido do contacto que pertence ao utilizador do fluxo é atualizado.

![Filtrar atributos](./media/cds-connector-native/filtering-attributes.png)

## <a name="trigger-privileges"></a>Privilégios do acionador

Para criar um fluxo que é acionado com base na criação, atualização ou eliminação de um registo, o utilizador tem de ter permissões de nível de utilizador para criar, ler, escrever e eliminar na entidade **Callback Registration**. Além disso, dependendo dos âmbitos definidos, o utilizador poderá precisar pelo menos desse nível de leitura na mesma entidade.  [Saiba mais](https://docs.microsoft.com/power-platform/admin/database-security) sobre segurança do ambiente.

## <a name="write-data-into-common-data-service"></a>Gravar dados para o Common Data Service

Utilize qualquer uma das seguintes ações para escrever dados no Common Data Service:

![Filtrar atributos](./media/cds-connector-native/actions.png)

Segue-se um exemplo de um fluxo que envia uma notificação com o nome e a receita anual sempre que uma **conta** é **criada** por qualquer pessoa no **âmbito** da unidade de negócio.

> ![Tarefa de seguimento](./media/cds-connector-native/example-flow.png)

## <a name="advanced-concepts"></a>Conceitos avançados

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Escrever dados nos campos Cliente, Proprietário e Relativo A

Para escrever dados nos campos Cliente, Proprietário e Relativo A, tem de preencher dois campos.

| Categoria do campo | Definições de exemplo |
| --- | --- |
| Relativa a | Relativo A = o ID do registo (por exemplo, ID da conta) e o Tipo de Relativo A conforme selecionado na lista. |
| Cliente | Representa o ID do registo e o tipo de cliente conforme selecionado na lista. |
| Proprietário | Representa o ID da equipa ou utilizador de sistema e o tipo de proprietário conforme selecionado na lista. |

### <a name="enable-upsert-behavior"></a>Ativar o comportamento de upsert

Pode tirar partido da ação **atualizar um registo** para fornecer ações de upsert, que atualizam o registo se ele já existir ou criam um novo registo. Para invocar o upsert, forneça a entidade e uma chave de GUID. Se o registo com a chave e o tipo especificados existir, ocorre uma atualização. Caso contrário, é criado um registo com a chave especificada.

### <a name="trigger-behavior"></a>Comportamento do acionador

Se tiver um acionador registado na atualização de um registo, o fluxo é executado para cada atualização *consolidada* no registo especificado. O serviço invoca o seu fluxo de forma assíncrona e com a payload que captura no momento em que a invocação ocorre.

> [!NOTE]
> Se tiver duas atualizações que ocorrem com uma diferença de segundos entre si, o fluxo pode ser acionado mais do que uma vez com o conteúdo com a versão mais recente.

As execuções do fluxo podem sofrer um atraso se existir um registo de tarefas de sistema pendentes no seu ambiente. Se este atraso ocorrer, o seu fluxo é acionado quando a tarefa de sistema para iniciar o fluxo é executada.



