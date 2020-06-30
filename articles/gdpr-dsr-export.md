---
title: Pedidos de Exportação dos Titulares dos Dados RGPD do Power Automate | Microsoft Docs
description: Saiba como utilizar o Power Automate para responder a Pedidos de Exportação dos Titulares dos Dados RGPD.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/24/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: f9fee8a217cdec28f6a3b49dee6335c4f13a3d45
ms.sourcegitcommit: 2284143cf147beb7d6071fd8005a41298e51e493
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/19/2020
ms.locfileid: "3384945"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-power-automate"></a>Responder aos Pedidos de Exportação dos Titulares de Dados RGPD para o Power Automate


Como parte do nosso compromisso de parceria consigo no seu percurso para o Regulamento Geral sobre a Proteção de Dados (RGPD), desenvolvemos documentação para o ajudar a preparar-se. A documentação não só descreve o que estamos a fazer para nos prepararmos para o RGPD, como também partilha exemplos de passos que pode seguir neste momento com a Microsoft para suportar a conformidade com o RGPD quando utilizar o Power Automate.

## <a name="manage-export-requests"></a>Gerir Pedidos de exportação

O *direito de portabilidade dos dados* permite que um titular dos dados solicite uma cópia dos seus dados pessoais num formato eletrónico (isto é, um “formato estruturado interoperável frequentemente utilizado e legível pelo computador”) que possa ser transmitido a outro responsável pelo tratamento de dados.

O Power Automate proporciona as seguintes experiências para localizar ou exportar dados pessoais para um utilizador específico:

* **Acesso ao site:** inicie sessão no [Centro de Administração do Power Apps](https://admin.powerapps.com/) ou no [Centro de Administração do Power Automate](https://admin.flow.microsoft.com/).

* **Acesso ao PowerShell:**  [Cmdlets do PowerShell para Administradores do Power Apps](https://go.microsoft.com/fwlink/?linkid=871804).

|**Dados do cliente**|**Acesso ao site**|**Acesso ao PowerShell**|
|-----------------|------------------|-------------------|
|Registos gerados pelo sistema|[Portal de Confiança do Serviço do Office 365](https://servicetrust.microsoft.com/)|
|Histórico de execuções|Portal do criador do Power Automate||
|Fluxos|Portal do criador do Power Automate||
|Permissões dos fluxos| Portal do Power Automate Maker e Centro de Administração do Power Automate||
|Detalhes do utilizador||Cmdlets do Power Apps|
|Ligações|Portal do criador do Power Automate|Cmdlets do Power Apps |
|Permissões de ligação|Portal do criador do Power Automate|Cmdlets do Power Apps |
|Conectores personalizados|Portal do criador do Power Automate|Cmdlets do Power Apps |
|Permissões de conector personalizado|Portal do criador do Power Automate|Cmdlets do Power Apps |
|Gateway|Portal do criador do Power Automate|Cmdlets do PowerShell do Gateway de Dados no local|
|Permissões de gateway|Portal do criador do Power Automate|Cmdlets do PowerShell do Gateway de Dados no local|

## <a name="export-a-flow"></a>Exportar um fluxo

Um utilizador final ou um administrador, que tenha concedido para si próprio acesso ao fluxo, pode exportar o fluxo seguindo estes passos:

1. Iniciar sessão no [Power Automate](https://flow.microsoft.com/).

1. Selecione a ligação **Os meus fluxos** e, em seguida, o fluxo a exportar.

1. Selecione **... Mais** e, em seguida, **Exportar**.

    ![Exportar fluxo](./media/gdpr-dsr-export/export-flow.png)

1. Selecione **Pacote (.zip)**.

O fluxo estará agora disponível como um pacote zipado. Para obter mais informações, veja a mensagem de blogue sobre [como exportar e importar um fluxo](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Exportar histórico de execuções

O histórico de execuções inclui uma lista de todas as execuções ocorridas para um fluxo. Estes dados incluem o estado do fluxo, a hora de início, a duração e os dados de entrada/saída dos acionadores e das ações.

Um utilizador final ou um administrador, ao qual tenha sido concedido acesso ao fluxo através do Centro de Administração do Power Automate, pode seguir estes passos para exportar esses dados:

1. Iniciar sessão no [Power Automate](https://flow.microsoft.com/).
1. Selecione a ligação **Os meus fluxos** e, em seguida, o fluxo cujo histórico de execuções pretende exportar.
1. No painel **HISTÓRICO DE EXECUÇÕES**, selecione **Ver tudo**.

    ![Histórico de execuções](./media/gdpr-dsr-export/run-history.png)

1. Selecione **Transferir CSV**.

    ![Transferir CSV](./media/gdpr-dsr-export/download-csv.png)

O histórico de execuções é transferido como um ficheiro .csv para que possa abri-lo no Microsoft Excel ou num editor de texto e analisar os resultados em maior detalhe.

## <a name="export-a-users-activity-feed"></a>Exportar o feed de atividades de um utilizador

No [Power Automate](https://flow.microsoft.com/), o feed de atividades mostra o histórico das atividades, as falhas e as notificações de um utilizador. Qualquer utilizador pode ver o seu feed de atividades seguindo estes passos:

1. Inicie sessão no [Power Automate](https://flow.microsoft.com/), selecione o ícone de campainha próximo do canto superior direito e, em seguida, selecione **Mostrar todas as atividades**.

    ![Mostrar feed de atividades](./media/gdpr-dsr-export/show-activity-feed.png)

1. No ecrã **Atividade**, copie os resultados e cole-os num editor de documentos tal como o Microsoft Word.

    ![Mostrar feed de atividades](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Exportar as ligações de um utilizador

As ligações permitem que os fluxos se liguem a APIs, a aplicações SaaS e a outros sistemas de terceiros. Siga estes passos para ver as ligações:

1. Inicie sessão no [Power Automate](https://flow.microsoft.com/), selecione o ícone de engrenagem próximo do canto superior direito e, em seguida, selecione **Ligações**.

    ![Mostrar Ligações](./media/gdpr-dsr-export/show-connections.png)
1. Copie os resultados e cole-os num editor de documentos tal como o Microsoft Word.

Power Apps Cmdlets do PowerShell para admin

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnection -CreateBy $userId | ConvertTo-Json |Out-File -FilePath "UserConnections.txt"
```

## <a name="export-a-list-of-a-users-connection-permissions"></a>Exportar uma lista de permissões da ligação de um utilizador

Um utilizador pode exportar as atribuições de funções de ligação para todas as ligações às quais tem acesso através da função de Get-ConnectionRoleAssignment nos [cmdlets do PowerShell do Power Apps](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt"
```
Power Apps Cmdlets do PowerShell para admin

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt" 
```

## <a name="export-a-users-custom-connectors"></a>Exportar conectores personalizados de um utilizador

Os conectores personalizados complementam os conectores integrados e permitem a conectividade a outros APIs, SaaS e sistemas personalizados. Pode transferir a propriedade de um conector personalizado ou eliminá-lo.

Siga estes passos para exportar uma lista de conectores personalizados:

1. Navegue para [Power Automate](https://flow.microsoft.com).
1. Selecione o ícone de **engrenagem** das definições.
1. Selecione **Conectores Personalizados**.
1. Copie e cole a lista de conectores personalizados num editor de texto tal como o Microsoft Word.

    ![Exportar os conectores personalizados](./media/gdpr-dsr-export/export-custom-connectors.png)

Além da experiência proporcionada pelo Power Automate, pode utilizar a função Get-Connector dos [cmdlets do PowerShell do Power Apps](https://go.microsoft.com/fwlink/?linkid=871804) para exportar todos os conectores personalizados.

~~~~
Add-PowerAppsAccount
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "CustomConnectors.txt"
~~~~

Power Apps Cmdlets do PowerShell para admin

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserCustomConnectors.txt"  
```

## <a name="export-a-users-custom-connector-permissions"></a>Exportar as permissões dos conectores personalizados de um utilizador

Um utilizador pode exportar todas as permissões dos conectores personalizados criados através da função Get-ConnectorRoleAssignment nos [cmdlets do PowerShell do Power Apps](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"
```

Power Apps Cmdlets do PowerShell para admin

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"   
```

## <a name="export-approval-history"></a>Exportar o histórico de aprovação

O Histórico de Aprovações do Power Automate captura um registo histórico das aprovações que foram recebidas ou enviadas para um utilizador. Qualquer utilizador pode ver o seu histórico de aprovação. Para tal:

1. Inicie sessão no [Power Automate](https://flow.microsoft.com/), selecione **Aprovações** e, em seguida, selecione **Histórico**.

    ![Ver o histórico de aprovação](./media/gdpr-dsr-export/view-approval-history.png)

1. Uma lista mostra as aprovações que o utilizador recebeu. Os utilizadores podem mostrar as aprovações que enviaram ao selecionar a seta para baixo próxima de **Recebidas** e, em seguida, selecionar **Enviadas**.

    ![Ver aprovações recebidas](./media/gdpr-dsr-export/view-received-approvals.png)

## <a name="export-user-details"></a>Exportar Detalhes do Utilizador
Os detalhes do utilizador proporcionam uma ligação entre um utilizador e um inquilino específico. Um administrador pode exportar estas informações ao chamar o cmdlet **Get-AdminFlowUserDetails** e ao transmitir o ID do Objeto do utilizador.

Power Apps Cmdlets do PowerShell para admin

```PowerShell
Add-PowerAppsAccount

Get-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

## <a name="export-gateway-settings"></a>Exportar Definições do Gateway
A forma de responder a Pedidos de Exportação dos Titulares dos Dados para Gateways de Dados no Local pode ser encontrada [aqui](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

