---
title: Os fluxos são agora armazenados no Common Data Service e utilizam a API Web avançada
description: Os fluxos são agora armazenados no Common Data Service e utilizam a API Web avançada.
author: stepsic-microsoft-com
ms.reviewer: deonhe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: business-applications
ms.technology: ''
ms.author: stepsic
audience: Power user
ms.openlocfilehash: f446b1b4147b8531ee808447a18058628c2ac0cf
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298358"
---
# <a name="power-automate-web-api"></a>API Web do Power Automate


A partir de agora, todos os fluxos serão armazenados no Common Data Service e será utilizada [a API Web avançada](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/perform-operations-web-api).

Este conteúdo abrange a gestão de fluxos incluídos no separador **Soluções** no Power Automate. Atualmente, os fluxos em **Os Meus Fluxos** não são suportados por estas APIs.

## <a name="compose-http-requests"></a>Compor pedidos HTTP

Para começar a criar pedidos, primeiro necessita de criar o URL. O formato do URL base na API Web do Power Automate é: `https://{Organization ID}.{Regional Subdomain}.dynamics.com/api/data/v9.1/`. Estes dois parâmetros são:

- O **ID da Organização** é um nome exclusivo para o ambiente que armazena o seu fluxo. Pode ver o ID da Organização no botão para alternar de ambiente no canto superior direito do Power Automate. Tenha em atenção que o **ID da Organização** é diferente do **ID do Ambiente** (que é o GUID apresentado no URL do fluxo).

     ![Alternador de ambiente](media/web-api/get-organization-id.png "Alternador de ambiente")

- O **Subdomínio Regional** depende da localização do seu ambiente. Quando inicia sessão no Power Automate, pode ver a região do seu ambiente no URL da página Web. Utilize esse nome de região para encontrar o respetivo subdomínio na tabela seguinte:

     ![URL do fluxo](media/web-api/get-region-name.png "URL do fluxo")

     | Região         | Subdomínio   |
     | -------------- | ----------- |
     | Estados Unidos  | crm         |
     | América do Sul  | crm2        |
     | Canadá         | crm3        |
     | Europa         | crm4        |
     | Ásia-Pacífico   | crm5        |
     | Austrália      | crm6        |
     | Japão          | crm7        |
     | Índia          | crm8        |
     |  US Government  | crm9        |
     | Reino Unido | crm11       |

Também pode obter a lista de instâncias disponíveis através de programação com o método [Obter instâncias](https://docs.microsoft.com/rest/api/admin.services.crm.dynamics.com/instances/getinstances) na API de Gestão Online.

Cada pedido da API Web tem de ter os cabeçalhos `Accept` e `Content-type` definidos como `application/json`.

Por fim, preencha o cabeçalho `Authorization` com um token de portador do Azure AD. Pode [aprender](https://docs.microsoft.com/powerapps/developer/common-data-service/authenticate-oauth) a adquirir um token de portador do Azure AD para o Common Data Service. Por exemplo, este pedido:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
```

A resposta contém a lista de fluxos dentro daquele ambiente:

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#workflows",
    "value": [{
        "@odata.etag": "W/\"12116760\"",
        "category": 5,
        "statecode": 0,
        "workflowidunique": "00000000-0000-0000-0000-000000000001",
        "workflowid" : "00000000-0000-0000-0000-000000000002",
        "createdon": "2018-11-15T19:45:51Z",
        "_ownerid_value": "00000000-0000-0000-0000-000000000003",
        "modifiedon": "2018-11-15T19:45:51Z",
        "ismanaged": false,
        "name": "Sample flow",
        "_modifiedby_value": "00000000-0000-0000-0000-000000000003",
        "_createdby_value": "00000000-0000-0000-0000-000000000003",
        "type": 1,
        "description": "This flow updates some data in Common Data Service.",
        "clientdata": "{\"properties\":{\"connectionReferences\":{\"shared_commondataservice\":{\"source\":\"NotSpecified\",\"id\":\"/providers/Microsoft.PowerApps/apis/shared_commondataservice\",\"tier\":\"NotSpecified\"}},\"definition\":{...}},\"schemaVersion\":\"1.0.0.0\"}"
    }]
}
```

## <a name="list-flows"></a>Lista de fluxos

Conforme apresentado acima, pode obter a lista de fluxos de trabalho ao chamar `GET` em `workflows`. Cada fluxo de trabalho possui várias propriedades, mas as mais relevantes são:

| Nome da propriedade     | Descrição                                              |
| ----------------- | -------------------------------------------------------- |
| category          | A categoria do fluxo. Os diferentes tipos são: 0 – fluxos de trabalho do Common Data Service clássico, 1 – caixas de diálogo do Common Data Service clássico, 2 – regras de negócio, 3 – ações do Common Data Service clássico, 4 – fluxos de processo de negócio e 5 – fluxos automatizados, instantâneos ou agendados. |
| statecode         | O estado do fluxo. O estado pode ser **0** – desativado ou **1** – ativado.|
| workflowuniqueid  | O identificador exclusivo desta instalação do fluxo. |
| workflowid        | O identificador exclusivo de um fluxo em todas as importações. |
| createdon         | A data em que o fluxo foi criado. |
| _ownerid_value    | O identificador exclusivo do utilizador ou equipa proprietário do fluxo. É um ID da entidade systemusers no Common Data Service. |
| modifiedon        | A última vez que o fluxo foi atualizado. |
| ismanaged         | Indica se o fluxo foi instalado através de uma solução gerida. |
| nome              | O nome a apresentar que deu ao fluxo. |
| _modifiedby_value | O último utilizador que atualizou o fluxo. É um ID da entidade systemusers no Common Data Service. |
| _createdby_value  | O utilizador que criou o fluxo. É um ID da entidade systemusers no Common Data Service. |
| tipo              | Indica se o fluxo é um fluxo em execução ou um modelo que pode ser utilizado para criar fluxos adicionais. 1 - fluxo, 2 - ativação ou 3 - modelo. |
| descrição       | A descrição inserida pelo utilizador do fluxo. |
| clientdata        | Uma cadeia JSON codificada de um objeto que contém connectionReferences e a definição do fluxo. |

Também pode pedir propriedades específicas, filtrar a lista de fluxos e muito mais, tal como descrito em [Documentação da API do Common Data Service para realizar consultas de dados](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/query-data-web-api). Por exemplo, esta consulta devolve apenas os fluxos automatizados, instantâneos ou agendados que estão atualmente ativos:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows?$filter=category eq 5 and statecode eq 1
Accept: application/json
Authorization: Bearer ey...
```

## <a name="create-a-flow"></a>Criar um fluxo

Chame `POST` na coleção `workflows` para criar um fluxo. As propriedades obrigatórias para fluxos automatizados, instantâneos ou agendados são: category, name, type, primaryentity, e clientdata. Utilize `none` como primaryentity para este tipo de fluxos.

Também pode fornecer uma description e um statecode.

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
        "category": 5,
        "statecode": 0,
        "name": "Sample flow name",
        "type": 1,
        "description": "This flow reads some data from Common Data Service.",
        "primaryentity":"none",
        "clientdata": "{\"properties\":{\"connectionReferences\":{\"shared_commondataservice\":{\"connectionName\":\"shared-commondataser-00000000-0000-0000-0000-000000000004\",\"source\":\"Invoker\",\"id\":\"/providers/Microsoft.Power Apps/apis/shared_commondataservice\"}},\"definition\":{\"$schema\": \"https:\/\/schema.management.azure.com\/providers\/Microsoft.Logic\/schemas\/2016-06-01\/workflowdefinition.json#\",\"contentVersion\": \"1.0.0.0\",\"parameters\": {\"$connections\": {\"defaultValue\": {},\"type\": \"Object\"},\"$authentication\": {\"defaultValue\": {},\"type\": \"SecureObject\"}},\"triggers\": {\"Recurrence\": {\"recurrence\": {\"frequency\": \"Minute\",\"interval\": 1},\"type\": \"Recurrence\"}},\"actions\": {\"List_records\": {\"runAfter\": {},\"metadata\": {\"flowSystemMetadata\": {\"swaggerOperationId\": \"GetItems_V2\"}},\"type\": \"ApiConnection\",\"inputs\": {\"host\": {\"api\": {\"runtimeUrl\": \"https:\/\/firstrelease-001.azure-apim.net\/apim\/commondataservice\"},\"connection\": {\"name\": \"@parameters('$connections')['shared_commondataservice']['connectionId']\"}},\"method\": \"get\",\"path\": \"\/v2\/datasets\/@{encodeURIComponent(encodeURIComponent('default.cds'))}\/tables\/@{encodeURIComponent(encodeURIComponent('accounts'))}\/items\",\"queries\": {\"$top\": 1},\"authentication\": \"@parameters('$authentication')\"}}},\"outputs\": {}}},\"schemaVersion\":\"1.0.0.0\"}"
}
```

A secção mais importante é `clientdata`, que contém as connectionReferences que o fluxo utiliza e a [definição](https://docs.microsoft.com/azure/logic-apps/logic-apps-workflow-definition-language) do fluxo. As connectionReferences são os mapeamentos a cada ligação que o fluxo utiliza.

Existem três propriedades:

| Nome da propriedade  | Descrição                                                 |
| -------------- | ----------------------------------------------------------- |
| connectionName | Identifica a ligação. Pode ver o connectionName ao aceder à página **Ligações** e, em seguida, copiá-lo do URL da ligação. |
| origem         | `Embedded` ou `Invoker`. `Invoker` é apenas válido para fluxos instantâneos (aqueles onde um utilizador seleciona um botão para executar o fluxo) e indica que o utilizador final irá fornecer a ligação. Neste caso, o connectionName é apenas utilizado na estruturação. Se a ligação for `Embedded`, significa que o connectionName que especificou é sempre utilizado. |
| ID             | O identificador do conector. O id começa sempre por `/providers/Microsoft.PowerApps/apis/` e, seguido pelo nome do conector, o qual pode copiar do URL da ligação ou ao selecionar o conector a partir da página **Conectores**. |

Uma vez executado o pedido `POST`, irá obter o cabeçalho `OData-EntityId`, que contém o `workflowid` do seu novo fluxo.

## <a name="update-a-flow"></a>Atualizar um fluxo

Pode chamar `PATCH` no fluxo de trabalho para atualizar, ativar ou desativar um fluxo. Utilize a propriedade `workflowid` para realizar estas chamadas. Por exemplo, pode atualizar a descrição e o proprietário do fluxo com a seguinte chamada:

```http
PATCH https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "description" : "This flow will ensure consistency across systems.",
    "ownerid@odata.bind": "systemusers(00000000-0000-0000-0000-000000000005)",
}
```

> [!NOTE]
> A sintaxe para alterar o proprietário utiliza o formato `odata.bind`. Isto significa que, em vez de aplicar patches ao campo\_ownerid_value diretamente, anexa `@odata.bind` ao nome da propriedade e, em seguida, coloca o ID em `systemusers()`.

Noutro exemplo, pode ativar um fluxo com esta chamada:

```http
PATCH https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "statecode" : 1
}
```

### <a name="delete-a-flow"></a>Eliminar um fluxo

Eliminar um fluxo com uma simples chamada `DELETE`:

```http
DELETE https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
```

> [!NOTE]
> Não é possível eliminar um fluxo que esteja ativado. Primeiro, tem de desativar o fluxo (veja a secção anterior **Atualizar um fluxo**) ou ser-lhe-á apresentado este erro: `Cannot delete an active workflow definition.`

## <a name="get-all-users-with-whom-a-flow-is-shared"></a>Obter todos os utilizadores com quem um fluxo foi partilhado

Para listar os utilizadores com acesso utiliza uma *função* no Common Data Service. Esta função utiliza um único parâmetro `Target`:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/RetrieveSharedPrincipalsAndAccess(Target=@tid)?@tid={'@odata.id':'workflows(00000000-0000-0000-0000-000000000002)'}
Accept: application/json
Authorization: Bearer ey...
```

O parâmetro `Target` é uma cadeia semelhante a JSON com uma única propriedade chamada `@odata.id`. Substitua a ID do fluxo de trabalho no exemplo acima. É devolvido:

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#Microsoft.Dynamics.CRM.RetrieveSharedPrincipalsAndAccessResponse",
    "PrincipalAccesses": [
        {
            "AccessMask": "ReadAccess",
            "Principal": {
                "@odata.type": "#Microsoft.Dynamics.CRM.systemuser",
                "ownerid": "00000000-0000-0000-0000-000000000005"
            }
        }
    ]
}
```

## <a name="share-or-unshare-a-flow"></a>Partilhar ou deixar de partilhar um fluxo

Pode partilhar um fluxo através da ação `GrantAccess`.

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/GrantAccess
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "Target" : {
        "@odata.type": "Microsoft.Dynamics.CRM.workflow",
        "workflowid" : "00000000-0000-0000-0000-000000000002"
    },
    "PrincipalAccess": {
        "Principal": {
            "@odata.type" : "Microsoft.Dynamics.CRM.systemuser",
            "ownerid" : "00000000-0000-0000-0000-000000000005"
        },
        "AccessMask": "ReadAccess"
    }
}
```

O parâmetro `AccessMask` é um campo com os seguintes valores para diferentes níveis de permissão:

| Nome         | Descrição                                          |
| ------------ | ---------------------------------------------------- |
| Nenhum         | Sem acesso.                                           |
| ReadAccess   | Tem direito a ler o fluxo.                          |
| WriteAccess  | Tem direito a atualizar o fluxo.                        |
| DeleteAccess | Tem direito a eliminar o fluxo.                        |
| ShareAccess  | Tem direito a partilhar o fluxo.                         |
| AssignAccess | Tem direito a alterar o proprietário do fluxo.           |

Pode combinar permissões com uma vírgula. Por exemplo, pode fornecer a possibilidade de ler e atualizar um fluxo ao introduzir `ReadAccess,WriteAccess`.

Pode *deixar de partilhar* um fluxo com a ação `RevokeAccess`. Eis um exemplo:

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/RevokeAccess
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "Target" : {
        "@odata.type": "Microsoft.Dynamics.CRM.workflow",
        "workflowid" : "00000000-0000-0000-0000-000000000002"
    },
    "Revokee": {
        "@odata.type" : "Microsoft.Dynamics.CRM.systemuser",
        "ownerid" : "00000000-0000-0000-0000-000000000005"
    }
}
```

A ação `RevokeAccess` remove todas as permissões concedidas no `AccessMask`.

## <a name="export-flows"></a>Exportar fluxos

Utilize a ação `ExportSolution` para exportar fluxos para um ficheiro .zip. Primeiro, adicione os fluxos que pretende a uma [solução](https://flow.microsoft.com/blog/solutions-in-microsoft-flow/).

Quando o fluxo estiver numa solução, chame a seguinte ação:

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/ExportSolution
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "SolutionName" : "Awesome solution 1",
    "Managed": false
}
```

`ExportSolution` devolve uma cadeia com codificação Base 64 na propriedade `ExportSoutionFile`.

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#Microsoft.Dynamics.CRM.ExportSolutionResponse",
    "ExportSolutionFile": "UEsDBBQAAgAI..."
}
```

Pode, em seguida, guardar este ficheiro no controlo de origem e/ou utilizar qualquer gestão de versões ou sistema de distribuição que quiser.

## <a name="import-flows"></a>Importar fluxos

Chame a ação `ImportSolution` para importar uma solução.

| Nome da propriedade                    | Descrição                               |
| -------------------------------- | ----------------------------------------- |
| OverwriteUnmanagedCustomizations | Se existirem instâncias destes fluxos no Common Data Service, este sinalizador necessita de ser definido como `true` para importá-los. Caso contrário, não serão substituídos. |
| PublishWorkflows                 | Indica se o Common Data Service clássico será ativado na importação. Esta definição não é aplicável a outros tipos de fluxos. |
| ImportJobId                      | Fornece um novo GUID exclusivo para controlar a tarefa de importação. |
| CustomizationFile                | Um ficheiro zip com codificação Base 64 que contém a solução. |

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/ImportSolution
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "OverwriteUnmanagedCustomizations": false,
    "PublishWorkflows" : true,
    "ImportJobId" : "00000000-0000-0000-0000-000000000006",
    "CustomizationFile" : "UEsDBBQAAgAI..."
}
```

Uma vez que a importação é uma operação de longa execução, a resposta à ação ImportSolution será `204 No content`. Para controlar o processo, chame `GET` no objeto `importjobs` e forneça o `ImportJobId` que incluiu na ação `ImportSolution` original.

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/importjobs(00000000-0000-0000-0000-000000000006)
Accept: application/json
Authorization: Bearer ey...
```

Esta chamada devolve o estado da operação de importação, incluindo `progress` (a percentagem de conclusão), `startedon` e `completedon` (se a importação tiver sido concluída).

Assim que a importação tiver sido concluída com êxito, necessita de configurar as ligações para o fluxo, uma vez que o `connectionNames` será provavelmente diferente no ambiente de destino (se as ligações existirem). Se estiver a configurar novas ligações no ambiente de destino, o proprietário dos fluxos tem de criá-las no estruturador do Power Automate. Se as ligações já estiverem configuradas no novo ambiente, então pode chamar `PATCH` no `clientData` do fluxo com os nomes das ligações.
