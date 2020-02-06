---
title: Integrar o Power Automate com os sites e as aplicações | Microsoft Docs
description: Incorpore as experiências do Power Automate no site ou na aplicação.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2019
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 6ca077b6a7b0d04f184ddf8a716dd677713e0667
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74364632"
---
# <a name="integrate-power-automate-with-websites-and-apps"></a>Integrar o Power Automate com os sites e as aplicações
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Incorpore o Power Automate na aplicação ou site com *widgets de fluxo* para fornecer aos utilizadores uma forma simples de automatizar as tarefas pessoais ou profissionais.

Os widgets de fluxo são iframes localizados num documento anfitrião. Este documento aponta para uma página no estruturador do Power Automate. Estes widgets integram funcionalidades específicas do Power Automate numa aplicação de terceiros.

Os widgets podem ser simples. Por exemplo, um widget que apresenta uma lista de modelos sem comunicação entre o anfitrião e o iframe. Os widgets também podem ser complexos. Por exemplo, um widget que aprovisiona um fluxo a partir de um modelo e, em seguida, aciona o fluxo através de uma comunicação bidirecional entre o anfitrião e o widget.

## <a name="prerequisites"></a>Pré-requisitos

- Uma **Conta Microsoft** ou
- Uma conta escolar ou profissional

## <a name="use-the-unauthenticated-widget"></a>Utilizar o widget autenticado
Para utilizar o widget de modelos não autenticado, incorpore-o diretamente na aplicação anfitriã através de um iframe. Não precisa do SDK do JS ou de um token de acesso. 

### <a name="show-templates-for-your-scenarios"></a>Visualize modelos para os cenários
Para começar, adicione este código para mostrar os modelos do Power Automate no site:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}&category={category}"></iframe>
```

| Parâmetro | Descrição |
| --- | --- |
| região |O idioma de quatro letras e o código da região para a vista do modelo. Por exemplo, `en-us` representa inglês americano, e `de-de` representa alemão. |
| termo de pesquisa |O termo de pesquisa para os modelos que pretende visualizar na vista. Por exemplo, procure `wunderlist` para visualizar modelos para Wunderlist. |
| número de modelos |O número de modelos que pretende visualizar na vista. |
| destino |A página que é aberta quando os utilizadores selecionam o modelo. Introduza `details` para mostrar os detalhes sobre o modelo ou introduza `new` para abrir o estruturador do Power Automate. |
| category |Filtros para a categoria de modelo especificada. | 
| parâmetros.{name} |Contexto adicional a transmitir o fluxo. |


Se o parâmetro de destino for `new`, o estruturador do Power Automate será aberto quando os utilizadores selecionarem um modelo. Em seguida, os utilizadores podem criar um fluxo no estruturador. Se quiser ter a experiência completa do widget, veja a secção seguinte.

### <a name="passing-additional-parameters-to-the-flow-template"></a>Transmitir parâmetros adicionais ao modelo de fluxo

Se o utilizador estiver num determinado contexto no site ou aplicação, poderá querer transmitir o contexto ao fluxo. Por exemplo, um utilizador pode abrir um modelo para *Notificar-me quando um item é adicionado a uma lista* ao olhar para uma determinada lista no Wunderlist. Siga estes passos para transmitir o ID de lista como um *parâmetro* ao fluxo:

1. Defina o parâmetro no modelo de fluxo antes de o publicar. Um parâmetro assemelha-se a `@{parameters('parameter_name')}`.
1. Transmitir o parâmetro na cadeia de consulta do src iframe. Por exemplo, adicione `&parameters.listName={the name of the list}` se tiver um parâmetro denominado **listName**.

### <a name="full-sample"></a>Exemplo completo

Para mostrar os quatro modelos principais do Wunderlist em alemão e para o utilizador começar a utilizar o **myCoolList**, utilize este código:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="use-the-authenticated-flow-widgets"></a>Utilizar widgets de fluxo autenticados

A seguinte tabela mostra a lista de widgets do Power Automate que suportam a experiência completa no widget através do token de acesso de autenticação de utilizador. Terá de utilizar o SDK do JS (Software Developer Kit do JavaScript) do Power Automate para incorporar os widgets e fornecer o token de acesso de utilizador necessário.

| Tipo de widget    | Funcionalidade suportada                                                                                                                  | 
|----------------|------------------------------------------------------------------------------------------------------------------------------------| 
| fluxos          | Mostra uma lista de fluxos num separador para fluxos pessoais e partilhados. Edite um fluxo existente ou crie um novo fluxo em branco ou a partir de um modelo. | 
| flowCreation   | Cria um fluxo a partir de um ID de modelo que a aplicação anfitriã fornece.                                                                | 
| runtime        | Aciona um fluxo de acionamento híbrido ou manual que a aplicação anfitriã fornece.                                                        | 
| approvalCenter | Incorpora pedidos de aprovação e aprovações enviadas.                                                                                        | 
| modelos      | Mostra uma lista de modelos. O utilizador escolhe um para criar um novo fluxo.                                                                         | 

Utilize o SDK de Fluxo autenticado para permitir que os utilizadores criem e façam a gestão de fluxos diretamente a partir do site ou da aplicação (em vez de navegar para o Power Automate). Terá de iniciar a sessão do utilizador com a respetiva Conta Microsoft ou do Azure Active Directory para utilizar o SDK autenticado.

> [!NOTE]
> Não existe nenhuma forma de ocultar a imagem corporativa do Power Automate quando utiliza widgets.

## <a name="widget-architecture"></a>Arquitetura dos widgets

Os widgets do Power Automate funcionam ao incorporar um iframe que faz referência ao Power Automate numa aplicação anfitriã. O anfitrião fornece o token de acesso exigido pelo widget do Power Automate. O SDK do JS do Power Automate permite que a aplicação anfitriã inicialize e faça a gestão do ciclo de vida do widget.

![arquitetura dos widgets](../media/embed-flow-dev/Architecture.png)

### <a name="js-sdk-details"></a>Detalhes de SDK do JS

A equipa do Power Automate fornece o SDK do JS para facilitar a integração de widgets do Flow em aplicações de terceiros. O SDK do JS do Flow está disponível como uma ligação pública no serviço Flow e permite que a aplicação anfitriã processe eventos do widget e interaja com a aplicação Flow ao enviar ações para o widget. Os eventos e ações de widgets são específicos ao tipo de widget.

### <a name="widget-initialization"></a>Inicialização de widget

A referência do SDK do JS do Flow tem de ser adicionada à aplicação anfitriã antes de inicializar o widget.

```html
<script src="https://flow.microsoft.com/Content/msflowsdk-1.1.js"></script>
```

Crie uma instância do SDK do JS ao transmitir os valores hostName e locale opcionais num objeto de JSON.

```javascript
var sdk = new MsFlowSdk({
    hostName:'https://flow.microsoft.com',
    locale:'en-US'
}); 
```

| Nome     | Obrigatório/Opcional | Descrição                                                    | 
|----------|-------------------|----------------------------------------------------------------| 
| `hostName` | Opcional          | Nome do anfitrião do Power Automate, por exemplo, https://flow.microsoft.com        | 
| `locale`   | Opcional          | Região do cliente do widget (a predefinição será `en-Us` se não for especificado) | 


Assim que a instância do SDK do JS for criada, poderá inicializar e incorporar um widget do Power Automate num elemento principal na aplicação anfitriã. Para tal, adicione um div HTML:

```html
<div id="flowDiv" class="flowContainer"></div>
```

Em seguida, inicialize o widget do Power Automate com o método `renderWidget()` do SDK do JS. Certifique-se de que fornece o tipo de widget e definições correspondentes.

```javascript
var widget = sdk.renderWidget('<widgettype>', {
        container: 'flowDiv',
        flowsSettings: {},
        templatesSettings: {},
        approvalSettings: {},
        widgetStyleSettings: {}
});
```

Eis um estilo de exemplo para o contentor que pode modificar para corresponder às dimensões da aplicação anfitriã.

```html
<head>
    <style>
        .flowContainer iframe {
            width: 400px;
            height: 1000px;
            border: none;
            overflow: hidden;
    }
    </style>
</head>
```

Estes são os parâmetros para `renderWidget()`: 

| Parâmetro        | Obrigatório/Opcional | Descrição                                                                                 | 
|------------------|-------------------|---------------------------------------------------------------------------------------------| 
| `container`        | Obrigatório          | ID de um elemento DIV na página anfitriã onde o widget será incorporado                   | 
| `environmentId`    | Opcional          | Os widgets precisam de um ID de ambiente. Se não fornecer um ID, é utilizado um ambiente predefinido. | 
| `flowsSettings`    | Opcional          | Objeto de definições do Power Automate                                                                        | 
| `templateSettings` | Opcional          | Objeto de definições do modelo                                                                    | 
| `approvalSettings` | Opcional          | Objeto de definições de aprovação                                                                    | 

### <a name="access-tokens"></a>Tokens de acesso

Após o `renderWidget()` do SDK do JS ser executado, o SDK do JS inicializa um iframe que aponta para o URL do widget do Power Automate. Este URL contém todas as definições nos parâmetros de cadeia de consulta. A aplicação anfitriã tem de obter um token de acesso do Power Automate para o utilizador (token JWT do Azure Active Directory com audiência https://service.flow.microsoft.com) antes de inicializar o widget. O widget gera um evento `GET_ACCESS_TOKEN` para pedir um token de acesso do anfitrião. O anfitrião tem de processar o evento e transmitir o token ao widget:

```javascript
widget.listen("GET_ACCESS_TOKEN", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
        token:  '<accesstokenFromHost>'
    });
});
```

A aplicação anfitriã é responsável por manter o token e transmiti-lo com uma data de expiração válida ao widget quando for pedido. Se o widget estiver aberto por períodos mais longos, o anfitrião deve verificar se o token expirou e atualizar o token, se for necessário, antes de transmiti-lo ao widget.

### <a name="detecting-if-the-widget-is-ready"></a>Detetar se o widget está pronto

Após a inicialização com êxito, o widget gera um evento para notificar que o widget está pronto. O anfitrião pode escutar o evento `WIDGET_READY` e executar qualquer código de anfitrião adicional.

```javascript
widget.listen("WIDGET_READY", function() {
    console.log("The flow widget is now ready.");
    // other host code on widget ready
});
 ```

## <a name="widget-settings"></a>Definições do widget

### <a name="flowssettings"></a>FlowsSettings 

O FlowsSettings pode ser utilizado para personalizar a funcionalidade do widget do Power Automate.

```javascript
flowsSettings?: {
    createFromBlankTemplateId?: string;
    flowsFilter?: string;sc
    tab?: string;
};
 ```

| Parâmetro | Obrigatório/Opcional | Descrição | 
|-----------|-------------------|-------------| 
| `createFromBlankTemplateId` | Obrigatório | Utilize o GUID do modelo quando o utilizador seleciona o botão **Criar do zero** no widget do Flow | 
| `flowsFilter` | Opcional | O widget do Power Automate aplica o filtro fornecido ao indicar fluxos. Por exemplo, mostra fluxos que fazem referência a um site do SharePoint específico. <br /> ```flowFilter: "operations/any(operation: operation/sharepoint.site eq 'https://microsoft.sharepoint.com/teams/ProcessSimple' )"   ``` |                 
| `tab` | Opcional | Predefine o separador ativo para mostrar no widget do Power Automate. <br /> Por exemplo, <br /> ```tab:'sharedFlows' ``` apresenta o separador Equipa<br /> e ``` tab:'myFlows' ``` apresenta o separador Os meus fluxos. |   

### <a name="templatessettings"></a>TemplatesSettings 

Isto aplica-se a todos os widgets que lhe permitem criar fluxos a partir de um modelo, incluindo os widgets Flows, FlowCreation e Templates.

```javascript
templatesSettings?: {
    defaultParams?: any;
    destination?: string;
    pageSize?: number;
    searchTerm?: string;
    templateCategory?: string;
    useServerSideProvisioning?: boolean;
    enableDietDesigner?: boolean;
};
 ```

| Parâmetro |Obrigatório/Opcional | Descrição                                                                        
|-----------|-------------------|-----------------| 
|`defaultParams` | Opcional          | Crie parâmetros de hora para utilizar ao criar um fluxo a partir de um modelo, por exemplo: <br /> ``` defaultParams: {'parameters.sharepoint.site': 'https://microsoft.sharepoint.com/teams/ProcessSimple', 'parameters.sharepoint.list': 'b3a5baa8-fe94-44ca-a6f0-270d9f821668'   } ```| 
| `destination` | Opcional          | Os valores válidos são "new" ou "details". Quando está definido como "details", uma página de detalhes é apresentada ao criar um fluxo a partir de um modelo.     |
| `pageSize` | Opcional          | Número de modelos a apresentar. Tamanho predefinido = 6 | 
| `searchTerm` | Opcional          | Apresente modelos que correspondem com o termo de pesquisa fornecido| 
| `templateCategory` | Opcional          | Apresente modelos numa categoria específica| 
 
### <a name="approvalcentersettings"></a>ApprovalCenterSettings

Aplica-se a widgets ApprovalCenter.

 ```javascript
 approvalCenterSettings?: {
    approvalsFilter?: string;
    tab?: string;but
    autoNavigateToDetails?: boolean;
    showSimpleEmptyPage? boolean;
    hideLink?: boolean
};
 ```
| Parâmetro | Obrigatório/Opcional | Descrição | 
|------------|-------------------|--------------| 
| `hideLink`| Opcional | Quando está definido como `true`, o widget oculta as ligações de aprovação recebidas e enviadas | 
| `autoNavigateToDetails`| Opcional | Quando está definido como `true`, o widget abre automaticamente os detalhes de aprovação quando existe apenas uma aprovação | 
| `approvalsFilter`| Opcional | O widget de aprovação irá aplicar o filtro de aprovação especificado ao indicar as aprovações, por exemplo:    O widget de aprovação irá aplicar o filtro de aprovação especificado ao indicar as aprovações, por exemplo: <br/> ``` approvalsFilter: 'properties/itemlink eq \'https://microsoft.sharepoint.com/teams/ProcessSimple/_layouts/15/listform.aspx?PageType=4&ListId=737e30a6-5bc4-4e9c-bcdc-d34c5c57d938&ID=3&ContentTypeID=0x010010B708969A9C16408696FD23801531C6\'' ```  <br/> <br/>``` approvalsFilter: 'properties/itemlinkencoded eq \'{Your base64 encoded item link url} \'' ```|
| `tab`| Opcional | Separador ativo predefinido para mostrar no widget do Flow. <br/> Valores válidos: "receivedApprovals", "sentApprovals" | 
| `showSimpleEmptyPage`| Opcional | Mostra uma página vazia quando não existem aprovações | 
| `hideInfoPaneCloseButton` | Opcional | Oculta o botão Fechar (ou o anfitrião já tem um botão Fechar) | 

<!-- why isn't this: hideInfoPaneCloseButton listed in the approvalCenterSettings? call since other optionals are there -->

## <a name="widget-events"></a>Eventos de widget

O widget do Power Automate suporta eventos que permitem ao anfitrião escutar eventos de ciclo de vida do widget. O widget do Power Automate suporta dois tipos de eventos: eventos de notificação unidirecionais (por exemplo, Widget\_Ready) e eventos gerados a partir do widget para obter dados do anfitrião (Get\_Access\_Token). O anfitrião tem de utilizar o método widget.listen() para escutar eventos específicos gerados a partir do widget.

### <a name="usage"></a>Usage

```javascript
widget.listen("<WIDGET_EVENT>", function() {
    console.log("The flow widget raised event");
});
```

### <a name="supported-events-by-widget-type"></a>Eventos suportados por tipo de widget

| Evento de widget      | Detalhes                                                         | 
|-------------------|-----------------------------------------------------------------| 
| `WIDGET_READY`      | O widget foi carregado com êxito                                      | 
| `WIDGET_RENDERED`   | O widget foi carregado e a composição da IU foi concluída                      | 
| `GET_ACCESS_TOKEN`  | Pedido de widget para incorporar token de acesso de utilizador                      | 
| `GET_STRINGS`       | Permite que o anfitrião substitua um conjunto de cadeias de IU apresentadas no widget | 

### <a name="runtime-widget"></a>Widget Runtime

| Evento de widget                    | Detalhes                                     | Dados                                              | 
|---------------------------------|---------------------------------------------|-----------| 
| `RUN_FLOW_STARTED`                | Foi acionado e a execução de fluxo foi iniciada      |           | 
| `RUN_FLOW_COMPLETED`              | A execução de fluxo foi acionada com êxito             |           | 
| `RUN_FLOW_DONE_BUTTON_CLICKED`    | O utilizador selecionou o botão Concluído na execução de fluxo       |           | 
| `RUN_FLOW_CANCEL_BUTTON_CLICKED`  | O utilizador selecionou o botão Cancelar na execução de fluxo     |           | 
| `FLOW_CREATION_SUCCEEDED`         | O fluxo foi criado com êxito           |`{ flowUrl: string, flowId: string, fromTemplate: string } `|
| `WIDGET_CLOSE`                    | Acionado quando o anfitrião deve fechar o widget |       | 

### <a name="flow-creation-widget"></a>Widget de Criação de Fluxo

| Evento de widget             | Detalhes                                  | Dados  | 
|--------------------------|------------------------------------------|-------| 
| `FLOW_CREATION_FAILED`     | Falha na criação do fluxo                     |       | 
| `WIDGET_CLOSE`             | Acionado quando o anfitrião deve fechar o widget  |       | 
| `TEMPLATE_LOAD_FAILED`     | Falha ao carregar o modelo              |       | 
| `FLOW_CREATION_SUCCEEDED`  | O fluxo foi criado com êxito        |` { flowUrl: string, flowId: string,fromTemplate?: string } `| 

### <a name="approval-widget"></a>Widget de aprovação

| Evento de widget                      | Detalhes                             | 
|-----------------------------------|-------------------------------------| 
| `RECEIVED_APPROVAL_STATUS_CHANGED`  | O estado de aprovação recebido foi alterado  | 
| `SENT_APPROVAL_STATUS_CHANGED`      | O estado de aprovação enviado foi alterado      | 

O evento **GET\_STRINGS** permite personalizar o texto de alguns elementos de IU apresentados no widget. As seguintes cadeias podem ser personalizadas:

| Chave de cadeia                     | Utilização no widget                                                                                                                  | 
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------| 
| `FLOW_CREATION_CREATE_BUTTON`    | O texto apresentado no botão Criar fluxo no widget de criação de fluxo e de runtime                                                | 
| `FLOW_CREATION_CUSTOM_FLOW_NAME` | O valor inicial a utilizar para o nome do fluxo no widget de criação de fluxo. Só é utilizado quando a definição allowCustomFlowName está ativada. | 
| `FLOW_CREATION_HEADER`           | Cabeçalho a utilizar ao criar um fluxo no widget de criação de fluxo e de runtime                                                    | 
| `INVOKE_FLOW_HEADER`             | Cabeçalho a utilizar ao invocar um fluxo no widget de runtime                                                                           | 
| `INVOKE_FLOW_RUN_FLOW_BUTTON`    | O texto apresentado no botão utilizado para invocar/executar um fluxo no widget de runtime                                                       | 

### <a name="example"></a>Exemplo

Chame `widgetDoneCallback` ao transmitir um objeto de JSON com pares chave-valor de chave de cadeia e texto para substituir o valor predefinido.

```javascript
widget.listen("GET_STRINGS", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
         "FLOW_CREATION_HEADER": "<string override would go here>",
        "INVOKE_FLOW_RUN_FLOW_BUTTON":  "<string override would go here>"
    });
});
```

## <a name="widget-actions"></a>Ações de widget

O anfitrião utiliza ações de widget para enviar uma ação ou mensagem específica para o widget. O SDK do JS do widget fornece o método `notify()` para enviar uma mensagem ou um payload de JSON para o widget. Cada ação de widget suporta uma assinatura de payload específica.

### <a name="usage"></a>Utilização

```javascript
widget.notify('<WIDGET_ACTION>', parameterMatchingParameterInterface)
    .then(result => console.log(result))
    .catch(error => console.log(error))
 ```

### <a name="example"></a>Exemplo 

Invoque um fluxo ao enviar o seguinte comando para um widget de runtime 

```javascript
widget.notify('triggerFlow', { flowName: flowName, implicitData:implicitData });  
 ```

### <a name="runtime-widget"></a>Widget Runtime

| Ação de widget                               | Detalhes                                                      | Interface do parâmetro  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `triggerFlow`                                 | Aciona uma execução de fluxo                                          | `{ flowName: string, implicitData?: string } `| 
| `triggerFlowByTemplate`                       | Aciona uma execução de fluxo por modelo                              | `{ templateId: string, implicitData?: string, designTimeParameters?: Record<string, any> }` |
| `getTriggerSchema`                            | Obtém o esquema de acionador de um fluxo                               | `{   flowName: string, }` | 
| `closeWidget`                                 | Cancela qualquer atividade pendente e gera um evento WIDGET_CLOSE |                      | 

### <a name="flow-creation-widget"></a>Widget de Criação de Fluxo

| Ação de widget                               | Detalhes                                                      | Interface do parâmetro  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `createFlowFromTemplate`                      | Cria um fluxo para o modelo selecionado                     | `{ templateName: string, designTimeParameters?: Record<string, any> }`| 
| `createFlowFromTemplateDefinition`            | Cria um fluxo para a definição de modelo selecionada          | `{ templateDefinition: string }` | 
| `closeWidget`                                 | Cancela qualquer atividade pendente e gera um evento WIDGET_CLOSE |                      | 

### <a name="approval-widget"></a>Widget de aprovação

| Ação de widget  | Detalhes                                           | Interface do parâmetro  | 
|----------------|---------------------------------------------------|----------------------| 
| `closeInfoPane`  | Fecha o painel de informações que apresenta os detalhes de aprovação  | N/D                  | 

## <a name="configuring-your-client-application"></a>Configurar a aplicação cliente

Terá de configurar a sua aplicação cliente com Âmbitos do Serviço Flow (Permissões Delegadas). Se a aplicação do Azure Active Directory (AAD) utilizada para a integração do widget utilizar um fluxo de autorização de “concessão de código”, a aplicação do ADD terá de ser pré-configurada com permissões delegadas que são suportadas pelo Power Automate. Esta ação fornece permissões delegadas que permitem que a aplicação:

-   Faça a gestão de aprovações
-   Leia aprovações
-   Leia atividades
-   Faça a gestão de fluxos
-   Leia fluxos

Siga estes passos para selecionar uma ou mais permissões delegadas:

1.  Aceda a https://portal.azure.com. 
2.  Selecione **Azure Active Directory**.
3.  Selecione **Registos das aplicações** em **Gerir**.
4.  Introduza a aplicação de terceiros a ser configurada para os âmbitos do serviço Flow.
5.  Selecione **Definições**.
      ![arquitetura do widget](../media/embed-flow-dev/AAD-App-Settings.png)
6. Selecione **Permissões obrigatórias** em **Acesso à API**/
7. Selecione **Adicionar**.
8. Escolha **Selecionar uma API**.
      ![arquitetura do widget](../media/embed-flow-dev/AAD-App-Select-an-API.png)
9. Procure o **serviço do Power Automate** e selecione-o. Nota: para poder ver o serviço do Power Automate, o inquilino tem de ter pelo menos um utilizador do AAD com sessão iniciada no portal do Flow (<https://flow.microsoft.com>)
10. Selecione os âmbitos do Flow necessários para a aplicação e, em seguida, selecione **Guardar**.
      ![arquitetura do widget](../media/embed-flow-dev/AAD-App-DelegatedPermissions.png)

A sua aplicação irá obter um token do Serviço Flow que contém permissões delegadas na afirmação \'scp' no token JWT.

## <a name="sample-application-embedding-flow-widgets"></a>Aplicação de exemplo a incorporar widgets de fluxo 

Uma Aplicação de Página Única (SPA) de JavaScript de exemplo é fornecida na secção de recursos para que possa experimentar a incorporação de widgets de fluxo numa página anfitrião. Utilizar a aplicação de exemplo requer que registe uma aplicação do AAD com fluxo de concessão implícita ativado.

### <a name="registering-an-aad-app"></a>Registar uma aplicação do AAD

1.  Inicie sessão no [portal do Azure](https://portal.azure.com/).
2.  No painel de navegação esquerdo, selecione **Azure Active Directory** e, em seguida, selecione **Registos de aplicações** (Pré-visualização) \> Novo registo.
3.  Quando a página **Registar uma aplicação** for apresentada, introduza um nome para a sua aplicação.
4.  Em **Tipos de contas suportadas**, selecione **Contas** em qualquer diretório organizacional.
5.  Na secção **URL de Redirecionamento**, selecione a plataforma Web e defina o valor para o URL da aplicação com base no servidor Web.  Configure este valor para http://localhost:30662/ para executar a aplicação de exemplo.
6.  Selecione **Registar**.
7.  Na página **Descrição geral** da aplicação, tenha em atenção o valor do ID da aplicação (cliente).
8.  O exemplo requer que o [fluxo de concessão implícita](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-implicit-grant-flow) esteja ativado. No painel de navegação esquerdo da aplicação registada, selecione **Autenticação**.
9.  Em **Definições avançadas**, em **Concessão implícita**, ative as caixas de verificação **Tokens de ID** e **Tokens de acesso**. Os tokens de ID e os tokens de acesso são necessários, uma vez que esta aplicação tem de iniciar a sessão de utilizadores e chamar a API do Flow.
10. Selecione **Guardar**.

### <a name="running-the-sample"></a>Executar o exemplo
<!-- todo where should I download from? -->
1.  Transfira o exemplo e copie para uma pasta local no seu dispositivo.
2.  Abra o ficheiro index.html na pasta FlowSDKSample e modifique o `applicationConfig` para atualizar o `clientID` para o ID da aplicação que registou anteriormente.
    ![arquitetura do widget](../media/embed-flow-dev/SampleApp-ApplicationConfig.png)
3.  A aplicação de exemplo está configurada para utilizar os âmbitos **Flows.Read.All** e **Flow.Manage.All.** do Flow. Pode configurar âmbitos adicionais ao atualizar a propriedade **flowScopes** no objeto **applicationConfig**.
4.  Execute estes comandos para instalar a dependência e executar a aplicação de exemplo:
    > \> npm install \> node server.js
5. Abra o browser e, em seguida, introduza http://localhost:30662
6. Selecione o botão **Sign in** (Iniciar sessão) para se autenticar no AAD e adquirir um token de acesso de fluxo.
7. A caixa de texto **Access Token** (Token de Acesso) contém o token de acesso.
    ![arquitetura do widget](../media/embed-flow-dev/SampleApp-AccessToken.png)
8. Selecione **Load Flows widget** (Carregar o widget Flows) ou **Load Templates widget** (Carregar o widget Templates) para incorporar os widgets correspondentes.
    ![arquitetura do widget](../media/embed-flow-dev/SampleApp-TemplatesWidget.png)

[Ligação de transferência](https://procsi.blob.core.windows.net/docs/FlowWidgetSampleApp.zip) da aplicação de exemplo

## <a name="resources"></a>Recursos

### <a name="widget-test-pages"></a>Páginas de teste de widget

Saiba mais sobre a integração e definições do widget:

- Widget Templates: <[https://flow.microsoft.com/test/templateswidget/](https://flow.microsoft.com/test/templateswidget/)>
- Widget FlowCreation: <[https://flow.microsoft.com/test/flowcreationwidget/](https://flow.microsoft.com/test/flowcreationwidget/)>
- Widget Runtime: <[https://flow.microsoft.com/test/runtimewidget/](https://flow.microsoft.com/test/runtimewidget/)>
- Widget ApprovalsCenter: <[https://flow.microsoft.com/test/approvalcenterwidget/](https://flow.microsoft.com/test/approvalcenterwidget/)>
- Widget Flows: <[https://flow.microsoft.com/test/managewidget/](https://flow.microsoft.com/test/managewidget/)>

### <a name="supported-widget-locales"></a>Regiões de widget suportadas

Se a região inicializada não estiver indicada, o Flow utilizará por predefinição a região suportada mais próxima.

| Região     | Idioma                   | 
|------------|----------------------------| 
| bg-bg      | Búlgaro (Bulgária)       | 
| ca-es      | Catalão (Espanha)            | 
| cs-cz      | Checo (República Checa)     | 
| da-dk      | Dinamarquês (Dinamarca)           | 
| de-de      | Alemão (Alemanha)           | 
| el-gr      | Grego (Grécia)             | 
| en-Us      | Inglês (Estados Unidos)    | 
| es-es      | Espanhol (Castelhano)        | 
| et-ee      | Estónio (Estónia)         | 
| eu-es      | Basco (Espanha)             | 
| fi-fi      | Finlandês (Finlândia)          | 
| fr-fr      | Francês (França)            | 
| gl-es      | Galego (Espanha)           | 
| hi-HU      | Húngaro (Hungria)        | 
| hi-in      | Hindi (Índia)              | 
| hr-hr      | Croata (Croácia)         | 
| id-Id      | Indonésio (Indonésia)     | 
| it-It      | Italiano (Itália)            | 
| jp-Jp      | Japonês (Japão)           | 
| kk-kz      | Cazaque (Cazaquistão)        | 
| ko-kr      | Coreano (Coreia)             | 
| lt-LT      | Lituano (Lituânia)     | 
| lv-lv      | Letão (Letónia)           | 
| ms-my      | Malaio (Malásia)           | 
| nb-no      | Norueguês (Bokmål)         | 
| nl-nl      | Neerlandês (Países Baixos)        | 
| pl-pl      | Polaco (Polónia)            | 
| pt-br      | Português (Brasil)        | 
| pt-pt      | Português (Portugal)      | 
| ro-ro      | Romeno (Roménia)         | 
| ru-ru      | Russo (Rússia)           | 
| sk-sk      | Eslovaco (Eslováquia)          | 
| sl-si      | Esloveno (Eslovénia)       | 
| sr-cyrl-rs | Sérvio (Cirílico, Sérvia) | 
| sr-latn-rs | Sérvio (Latim, Sérvia)    | 
| sv-se      | Sueco (Suécia)           | 
| th-th      | Tailandês (Tailândia)            | 
| tr-tr      | Turco (Turquia)           | 
| uk-ua      | Ucraniano (Ucrânia)        | 
| vi-vn      | Vietnamita (Vietname)      |
