---
title: Trabalhar com fluxos do processo de negócio através de código | Microsoft Docs
description: Saiba como trabalhar programaticamente com fluxos do processo de negócio para criar processos de negócio mais eficientes e otimizados.
ms.custom: ''
ms.date: 07/09/2018
ms.reviewer: ''
ms.service: flow
ms.topic: article
ms.assetid: 67d8cf80-9f77-4804-97a1-cf9f61417e83
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: d65be1552c3e748e4910c4fb942a60322f6f1e19
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74363275"
---
# <a name="work-with-business-process-flows-using-code"></a>Trabalhar com fluxos do processo de negócio através de código
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Os *fluxos do processo de negócio* permitem criar vendas, serviços e outros processos de negócio mais eficientes e otimizados. Criam uma visualização do seu processo de negócio ao colocar controlos especiais na parte superior dos formulários de entidade. Os utilizadores são orientados ao longo de várias fases dos processos de vendas, marketing ou serviço até os concluírem. Cada processo suporta múltiplas fases e passos. Pode adicionar ou remover passos, alterar a ordem das fases ou adicionar novas entidades ao fluxo do processo de negócio.  
  
É possível executar simultaneamente diferentes instâncias de fluxo do processo de negócio no mesmo registo de entidade. Os utilizadores podem alternar entre instâncias paralelas do processo de negócio e retomar o trabalho numa fase atual do processo. 

Este tópico fornece informações sobre a forma como pode trabalhar programaticamente com fluxos do processo de negócio.

> [!NOTE]
> Não tem de escrever código para trabalhar com fluxos do processo de negócio. Para obter informações sobre como pode utilizar a IU para criar e gerir fluxos do processo de negócio, veja [Descrição Geral dos Fluxos do Processo de Negócio](../business-process-flows-overview.md).  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>Pré-requisitos dos fluxos do processo de negócio 

As entidades personalizadas e as entidades com formulários de IU atualizados podem participar no fluxo do processo de negócio. As entidades de IU atualizadas têm a propriedade <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated> definida para `true`. 

Para ativar uma entidade para o fluxo do processo de negócio, defina a propriedade <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> para `true`.

> [!IMPORTANT]
>  A ativação de uma entidade para o fluxo do processo de negócio é um processo unidirecional. Não é possível revertê-lo.

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>Definir fluxos do processo de negócio
  
Utilize o estruturador de fluxo do processo de negócio visual para definir um fluxo do processo de negócio. Mais informações: [Criar um fluxo de processo de negócio](../create-business-process-flow.md)

Por predefinição, é criado um registo de fluxo do processo de negócio no estado `Draft`.  

É armazenada uma definição de fluxo do processo de negócio na entidade <xref:Microsoft.Dynamics.CRM.workflow>, ao passo que as informações da fase do fluxo do processo de negócio são armazenadas na entidade <xref:Microsoft.Dynamics.CRM.processstage>.
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>Ativar fluxos do processo de negócio  
 Antes de poder utilizar o fluxo do processo, tem de o ativar. Para o ativar, tem de ter o privilégio `prvActivateBusinessProcessFlow` para a entidade `Workflow`. Utilize a mensagem <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> para definir o estado do registo de entidade `Workflow` para `Activated`. Mais informações: [Perform specialized operations using Update](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update) (Realizar operações especializadas com o método Update) 

 > [!NOTE]
 > Também pode utilizar o estruturador de fluxo do processo de negócio para ativar um fluxo do processo de negócio. 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>Entidade de fluxo do processo de negócio 
 Depois de ativar uma definição de fluxo do processo de negócio através da alteração do estado do registo de entidade `Workflow` correspondente ou com recurso ao estruturador de fluxo do processo de negócio, é automaticamente criada uma entidade personalizada com o seguinte nome, para armazenar as instâncias de fluxo do processo de negócio ativadas: " *\<prefixodasoluçãoativa>* _ *\<nomeexclusivo>* ", em que "nomeexclusivo" deriva do nome que especificar.  
  
 Por exemplo, se tiver atribuído o nome "My Custom BPF" à definição de fluxo do processo de negócio e estiver a utilizar o publicador predefinido (novo) para a sua solução ativa, o nome da entidade personalizada criada para armazenar instâncias do processo será "novo_mycustombpf".  
  
 Se o valor `uniquename` não estiver disponível para uma definição de fluxo do processo de negócio (por exemplo, caso o fluxo do processo de negócio tenha sido importado como parte da solução a partir de uma versão anterior), o nome predefinido da entidade personalizada será "`\<activesolutionprefix>_bpf_<GUID_BPF_Definition>`":  
  
> [!IMPORTANT]
>  Os registos do fluxo do processo de negócio de exemplo utilizam entidades do sistema para armazenar os registos de instâncias de fluxo do processo de negócio correspondentes.  
>   
>  No entanto, as novas definições de fluxo do processo de negócio que criar utilizarão entidades personalizadas para armazenar os respetivos registos de instâncias, conforme explicado anteriormente. 

Pode obter o nome da sua entidade de fluxo do processo de negócio de qualquer uma das seguintes formas:

- **Através da IU** – utilize a IU de personalização para navegar para a sua entidade de fluxo do processo de negócio:

    ![](media/bpf-entity-name.png)
- **Através da Web API** – utilize o seguinte pedido:

    **Pedido**

    ```
    GET [Organization URI]/api/data/v9.0/workflows?$filter=name eq 'My Custom BPF'&$select=uniquename HTTP/1.1
    ```

    **Resposta**
    ```
    {  
    "@odata.context":"[Organization URI]/api/data/v9.0/$metadata#workflows(uniquename)",
    "value":[  
         {  
             "@odata.etag":"W/\"1084677\"",
             "uniquename":"new_mycustombpf",
             "workflowid":"2669927e-8ad6-4f95-8a9a-f1008af6956f"
         }
      ]
    }
    ```
- **Através do Serviço de organização** – utilize o seguinte exemplo de código:

    ```c#
    QueryExpression query = new QueryExpression
    {
        EntityName = "workflow",
        ColumnSet = new ColumnSet("uniquename"),
        Criteria = new FilterExpression
        {
            Conditions =
            {
                new ConditionExpression
                {
                    AttributeName = "name",
                    Operator = ConditionOperator.Equal,
                    Values = { "My Custom BPF" }
                }
            }
        }
    };
    Workflow Bpf = (Workflow)_serviceProxy.RetrieveMultiple(query).Entities[0]; 
    ```
> [!NOTE]
> A propriedade <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBPFEntity> é `true` para as entidades de fluxos de processo de negócio. Pode obter todas as entidades de fluxos de processo de negócio na sua instância ao executar o seguinte pedido da Web API:
> ```http
> GET [Organization URI]/api/data/v9.0/EntityDefinitions?$select=SchemaName,LogicalName,DisplayName&$filter=IsBPFEntity eq true HTTP/1.1
> ```

<a name="BPFSecurity"></a>   
## <a name="manage-security-for-business-process-flows"></a>Gerir a segurança de fluxos de processo de negócio

A entidade personalizada criada automaticamente ao ativar um fluxo de processo de negócio para armazenar instâncias de fluxos de processo de negócio cumpre o modelo de segurança padrão, assim como qualquer outra entidade personalizada no Common Data Service. Isto significa que as permissões concedidas nestas entidades definem as permissões de runtime para os utilizadores dos fluxos de processo de negócio.

A entidade personalizada do fluxo do processo de negócio possui um âmbito organizacional. As permissões de criação, obtenção, atualização e eliminação nesta entidade definem a permissão que os utilizadores teriam com base nas suas funções atribuídas. Por predefinição, quando a entidade personalizada do fluxo do processo de negócio é criada, apenas as funções de segurança **Administrador de Sistema** e **Personalizador de Sistemas** possuem acesso. Deve conceder explicitamente permissões à nova entidade do fluxo do processo de negócio (por exemplo, **My Custom BPF**) para outras funções de segurança conforme necessário.

![](media/bpf-privileges.png)

<a name="ManageBPF"></a>   
## <a name="create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances"></a>Criar, obter, atualizar e eliminar registos da entidade do fluxo do processo de negócio (instâncias do processo)  
 A entidade personalizada, criada automaticamente ao ativar uma definição de fluxo de processo de negócio, armazena todas as instâncias do processo na definição de fluxo do processo de negócio. A entidade personalizada suporta a criação através de programação e gestão de registos padrão (instâncias do processo) ao utilizar a API Web e o ponto final do CRM 2011.

> [!IMPORTANT]
> A mudança para outra instância de processo num registo de entidade é apenas suportada através de IU (cliente) ou através de programação com as informações disponíveis nesta secção. Já não pode utilizar a mensagem `SetProcess` (<xref href="Microsoft.Dynamics.CRM.SetProcess?text=SetProcess Action" /> ou <xref:Microsoft.Crm.Sdk.Messages.SetProcessRequest>) para alternar entre processos através de programação (definir outro fluxo de processo de negócio como a instância de processo ativa) no registo de entidade de destino. 

 Consideremos o seguinte exemplo onde temos um fluxo de processo de negócio entre entidades, "My Custom BPF", com 3 fases: F1: Conta, F2: Conta e F3: Contacto. 

 ![](media/sample-bpf.png)
 
### <a name="retrieve-all-the-records-instances-for-a-business-process-flow-entity"></a>Obtenha todos os registos (instâncias) de uma entidade de fluxo de processo de negócio
 Se o nome da sua entidade de fluxo do processo de negócio for "new_mycustombpf", utilize a seguinte consulta para obter todos os registos (instâncias do processo) da sua entidade de fluxo do processo de negócio:  
  
```http
GET [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
```

Neste momento, poderá não obter nenhuma instância na sua resposta devido à inexistência de instâncias. Execute este pedido depois de criar uma instância da sua definição de fluxo do processo de negócio mais à frente neste tópico.

> [!NOTE]
> Para saber como pode obter o nome da sua entidade de fluxo do processo de negócio, veja a secção anterior, [Entidade de fluxo do processo de negócio](#business-process-flow-entity).
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>Criar um registo de entidade de fluxo do processo de negócio (instância do processo) 

Se quiser mudar para outro fluxo do processo de negócio para um registo de entidade sem recorrer à IU, crie programaticamente um registo de entidade de fluxo do processo de negócio (instância do processo). 

Para criar um registo de entidade de fluxo do processo de negócio, tem de especificar os seguintes valores: 
- Associe o registo de entidade de fluxo do processo de negócio a um registo de entidade primária ao definir a propriedade de navegação de valor único através da anotação `@odata.bind`. Para ficar a saber o nome da propriedade de navegação que aponta para o registo de entidade primária da sua definição de fluxo do processo de negócio, utilize o [documento de metadados CSDL](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document). 
- Associe o registo de entidade de fluxo do processo de negócio a uma fase válida especificada na definição de fluxo do processo de negócio ao definir a propriedade de navegação de valor único através da anotação `@odata.bind`. Para ficar a saber o nome da propriedade de navegação (normalmente, `activestageid`) que aponta para o registo da fase da sua definição de fluxo do processo de negócio, utilize o [documento de metadados CSDL](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document).

    Além disso, pode obter informações sobre todas as fases de uma definição de fluxo do processo de negócio através do pedido da API Web que se segue, partindo do princípio de que o ID da sua definição de fluxo do processo de negócio é 2669927e-8ad6-4f95-8a9a-f1008af6956f:

    **Pedido**

    ```http
    GET [Organization URI]/api/data/v9.0/processstages?$select=stagename&$filter=processid/workflowid eq 2669927e-8ad6-4f95-8a9a-f1008af6956f HTTP/1.1
    ```

    **Resposta**

    ```http
    {
        "@odata.context": "[Organization URI]/api/data/v9.0/$metadata#processstages(stagename)",
        "value": [
            {
                "@odata.etag": "W/\"858240\"",
                "stagename": "S1",
                "processstageid": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b"
            },
            {
                "@odata.etag": "W/\"858239\"",
                "stagename": "S3",
                "processstageid": "a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a"
            },
            {
                "@odata.etag": "W/\"858238\"",
                "stagename": "S2",
                "processstageid": "19a11fc0-3398-4214-8522-cb2a97f66e4b"
            }
        ]
    }
    ```

Em seguida, utilize o seguinte pedido para criar uma instância da sua definição de fluxo do processo de negócio para um registo de conta (ID=a176be9e-9a68-e711-80e7-00155d41e206) e a fase ativa definida como a primeira fase da instância do processo, S1 (ID=9a9185f5-b75b-4bbb-9c2b-a6626683b99bb):

**Pedido**

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(a176be9e-9a68-e711-80e7-00155d41e206)",
    "activestageid@odata.bind": "/processstages(9a9185f5-b75b-4bbb-9c2b-a6626683b99b)"    
}
```

**Resposta**

```http
HTTP/1.1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.0/new_mycustombpfs(cc3f721b-026e-e811-80ff-00155d513100)
```

Tenha em atenção que, se quiser criar uma instância da sua definição de fluxo do processo de negócio com a fase ativa definida como ***outra*** fase que não a primeira, também deve fornecer `traversedpath` no seu pedido. O caminho percorrido é a cadeia de carateres delimitada por vírgulas de IDs de fases do processo que representam as fases visitadas da instância do fluxo do processo de negócio. O seguinte pedido cria uma instância para um registo de conta (ID=679b2464-71b5-e711-80f5-00155d513100) e a fase ativa definida como a segunda fase, S2 (ID=19a11fc0-3398-4214-8522-cb2a97f66e4b).

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(679b2464-71b5-e711-80f5-00155d513100)",
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"   
}
```

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>Atualizar um registo de entidade de fluxo do processo de negócio (instância do processo)

Pode atualizar uma instância do processo para navegar para a fase anterior ou seguinte, bem como para abandonar, reativar ou concluir uma instância do processo. 

#### <a name="stage-navigation"></a>Navegação pelas fases

Para navegar para uma fase diferente, terá de atualizar um registo de instância do processo para alterar o respetivo ID da fase ativa e atualizar o caminho percorrido. Tenha em atenção que tem de navegar para a fase anterior ou seguinte apenas durante a atualização de uma instância de fluxo do processo de negócio.

Para navegar pelas fases, necessitará do ID da instância de fluxo do processo de negócio que pretende atualizar. Para obter todas as instâncias do seu fluxo do processo de negócio, veja a secção acima [Obter todos os registos (instâncias) para uma entidade de fluxo do processo de negócio](#retrieve-all-the-records-instances-for-a-business-process-flow-entity).

Partindo do princípio de que o ID da instância do processo que pretende atualizar é dc2ab599-306d-e811-80ff-00155d513100, utilize o seguinte pedido para atualizar a fase ativa de S1 para S2:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
Content-Type: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0

{
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"
}
```

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>Altere o estado de uma instância de processo: Abortar, Reativar ou Concluir 

Uma instância do processo pode ter um dos seguintes estados: **Ativa**, **Concluída** ou **Abortada**. O estado é determinado pelos seguintes atributos no registo de instância do processo:

- **statecode**: apresenta o estado da instância do processo.

    |Valor|Etiqueta|
    |-----|-----|
    |0    |Ativo|
    |1    |Inativa|

- **statuscode**: apresenta informações sobre o estado da instância do processo.

    |Valor|Etiqueta|
    |-----|-----|
    |1    |Ativo|
    |2    |Concluída|
    |3    |Abortada|

Portanto, para **Abortar** uma instância do processo, utilize o seguinte pedido para definir adequadamente os valores `statecode` e `statuscode`:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{ 
    "statecode" : "1", 
    "statuscode": "3" 
}
```
 
> [!NOTE]
> Pode abortar uma instância do processo em qualquer fase.

Da mesma forma, para reativar uma instância do processo, substitua os valores `statecode` e `statuscode` no código acima por **0** e **1**, respetivamente.

Por fim, para definir um estado de instância do processo para **Concluída**, o que só é possível na última fase de uma instância do processo, substitua os valores `statecode` e `statuscode` no código acima por **0** e **2**, respetivamente.

#### <a name="cross-entity-navigation"></a>Navegação entre entidades

No caso da navegação entre entidades deste exemplo, tem de definir a fase ativa da instância do processo para a última fase, S3 (ID=a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a), atualizar o caminho percorrido e definir um registo de contacto como registo de entidade primária de acordo com a definição de fluxo do processo de negócio.

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{
    "activestageid@odata.bind": "/processstages(a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b,a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a",
    "bpf_contactid@odata.bind": "/contacts(0e3f10b0-da33-e811-80fc-00155d513100)"
}
``` 

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>Eliminar um registo de entidade de fluxo do processo de negócio (instância do processo)

Utilize o seguinte pedido da API Web:

**Pedido**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**Resposta**

Se o registo existir, receberá uma resposta normal com o estado 204 para indicar que a eliminação foi bem-sucedida. Se a entidade não for encontrada, receberá uma resposta com o estado 404.

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>Utilizar as mensagens RetrieveProcessInstances e RetrieveActivePath

Utilize a mensagem `RetrieveProcessInstances` (<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> ou <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>) para obter todas as instâncias de fluxo do processo de negócio de um registo de entidade em todas as definições de processo de negócio. As instâncias de fluxo do processo de negócio devolvidas para uma entidade são ordenadas com base no atributo `modifiedon` da instância. Por exemplo, a instância de fluxo do processo de negócio modificada mais recentemente será o *primeiro* registo da coleção devolvida. A instância de fluxo do processo de negócio modificada mais recentemente é a que está ativada na IU de um registo de entidade.  
  
Cada registo de instância de fluxo do processo de negócio devolvido para um registo de entidade devido à utilização da mensagem `RetrieveProcessInstances` armazena o ID da fase ativa no atributo `processstageid`, que pode ser utilizado para localizar a fase ativa, e navega para a fase anterior ou seguinte. Para tal, primeiro tem de localizar o caminho ativo de uma instância de fluxo do processo de negócio e as fases disponíveis na instância de fluxo do processo através da mensagem `RetrieveActivePath` (<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> ou <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>).   
  
 Quando tiver a fase ativa e as informações do caminho ativo de uma instância de fluxo do processo de negócio, poderá utilizar as informações para navegar para uma fase anterior ou seguinte no caminho ativo. A navegação de avanço entre fases deve ser realizada sequencialmente, ou seja, só deve avançar para a próxima fase do caminho ativo.   
  
 Para ver o exemplo completo que demonstra a utilização desses dois métodos e da navegação entre fases com recurso ao [Serviço de organização](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata), veja [Exemplo: trabalhar com fluxos de processo de negócio](sample-work-business-process-flows.md). 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>Aplicar um fluxo do processo de negócio durante a criação de um registo de entidade

Esta secção fornece informações sobre o comportamento predefinido para aplicar automaticamente fluxos do processo de negócios em novos registos de entidade criados no Common Data Service, bem como sobre a forma como o pode substituir para aplicar um fluxo do processo de negócio da sua preferência a novos registos de entidade.

Por predefinição, no caso das entidades que têm múltiplos fluxos do processo de negócio definidos para as mesmas, o sistema aplica um fluxo do processo de negócio ao novo registo de entidade com recurso à seguinte lógica de vários passos:
1. Identifique todos os fluxos do processo de negócio aplicáveis ao novo registo de entidade com base no atributo **Workflow.PrimaryEntity** dos registos de definição de fluxo do processo de negócio.
2. Identifique as definições de fluxo do processo de negócio às quais o utilizador atual tem acesso. Para obter informações sobre como o acesso a um fluxo do processo de negócio é determinado e gerido, veja a secção acima, [Manage security for business process flows](#BPFSecurity) (Gerir segurança para fluxos do processo de negócio).<br/>  
3. Todas as definições de fluxo do processo de negócio no sistema estão sujeitas a uma ordem global por entidade. A ordem do fluxo do processo de negócio é armazenada no atributo **Workflow.ProcessOrder**. As definições de fluxo do processo de negócio de uma entidade são ordenadas com base nesta ordem. É escolhida a que tem o menor valor de ordem.
4. Por fim, se o registo de entidade for criado a partir de uma aplicação empresarial (módulo de aplicação), é aplicado um nível de filtragem adicional com vista à escolha do fluxo do processo de negócio que vai ser aplicado automaticamente ao novo registo de entidade. Quando trabalharem numa aplicação, os utilizadores só poderão aceder às entidades, aos fluxos do processo de negócio, às vistas e aos formulários relevantes aos quais têm acesso devido às funções de segurança atribuídas à aplicação empresarial. 
    - Se a aplicação empresarial não contiver nenhum fluxo do processo de negócio, o fluxo do processo de negócio será aplicado conforme explicado até ao passo 3.
    - Se a aplicação empresarial tivesse um ou mais fluxos do processo de negócio, apenas os fluxos do processo de negócio presentes na aplicação seriam aplicáveis. Neste caso, quando o utilizador está a trabalhar no contexto de uma aplicação empresarial, a lista de fluxos do processo de negócio do passo 3 é filtrada para os fluxos que fazem parte da aplicação empresarial e que estão presentes no módulo de aplicação. Além disso, a lista é ordenada com base na ordem do processo. 
    - Se não estiver disponível nenhum fluxo do processo de negócio numa aplicação empresarial para a entidade ou nenhum fluxo ao qual o utilizador tem acesso, não será aplicado nenhum fluxo do processo de negócio ao novo registo de entidade.

Pode substituir a lógica predefinida de fluxos do processo de negócio que são aplicados automaticamente aos novos registos de entidade. Para tal, defina o atributo **ProcessId** da entidade para um dos seguintes valores quando criar um novo registo de entidade:
- Defina para **Guid.Empty** para ignorar a definição de um fluxo do processo de negócio para novos registos de entidade. É recomendado que o faça se estiver a criar registos de entidade em massa, mas não quiser que o fluxo do processo de negócio seja aplicado aos mesmos.
- Defina-o para uma entidade de fluxo do processo de negócio específica (como uma referência de entidade). Neste caso, o sistema aplicará o fluxo do processo de negócio especificado em vez da lógica predefinida.

Se não definir um valor para o atributo **ProcessId** quando criar um novo registo de entidade, o sistema aplicará a lógica predefinida, conforme explicado anteriormente.

> [!NOTE]
> A substituição da lógica predefinida de fluxos do processo de negócio que são aplicados automaticamente a novos registos de entidade só é suportada programaticamente. Não é possível fazê-lo com recurso à IU.

## <a name="legacy-process-related-attributes-in-entities"></a>Atributos herdados relacionados com processos em entidades

Os atributos herdados relacionados com processos (tais como **ProcessId**, **StageId** e **TraversedPath**) em entidades ativadas para fluxos do processo de negócio já foram preteridos. A manipulação destes atributos herdados relacionados com processos para registos de entidade visados não garante a consistência do estado do fluxo do processo de negócio e ***não*** é um cenário suportado. É recomendado utilizar os atributos da entidade de fluxo do processo de negócio conforme explicado anteriormente na secção [Create, retrieve, update, and delete business process flow entity records (process instances)](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances) (Criar, obter, atualizar e eliminar registos de entidade de fluxo do processo de negócio [instâncias do processo]).

A única exceção consiste em modificar programaticamente o atributo **ProcessId** quando criar um registo de entidade para substituir a aplicação predefinida do fluxo do processo de negócio no novo registo conforme explicado na secção anterior: [Aplicar um fluxo do processo de negócio durante a criação de um registo de entidade](#ApplyBPF).

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>Suporte de programação do lado do cliente para fluxos do processo de negócio  
 Há um objeto do lado do cliente que pode utilizar para interagir com fluxos do processo de negócio nos seus scripts de formulário. Os fluxos do processo de negócio acionam eventos do lado do cliente sempre que um processo é aplicado a um registo, que uma fase do mesmo é alterada ou que o respetivo estado é alterado para `Active`, `Finished` ou `Aborted`. Mais informações: [formContext.data.process (Client API reference)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md) (formContext.data.process [referência da API de Cliente])  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>Número máximo de processos, fases e passos  
 O valor predefinido para o número máximo de fluxos do processo de negócio ativados por entidade é 10. Pode especificar um valor diferente através do atributo `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity`. No entanto, se o valor for superior a 10, o desempenho do seu sistema poderá diminuir quando mudar de processos ou abrir um registo que tem um fluxo do processo de negócio atribuído. Isto poderá ser especialmente percetível se os processos abrangerem múltiplas entidades.  
  
 As seguintes definições não são personalizáveis:  
  
-   O número máximo de fases por entidade no processo é 30.  
  
-   O número máximo de passos em cada fase é 30.  
  
-   O número máximo de entidades que podem participar no fluxo do processo é 5.  

