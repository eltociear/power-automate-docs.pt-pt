---
title: Pedidos de Eliminação de Titulares de Dados do GDPR no Power Automate | Microsoft Docs
description: Saiba como utilizar o Power Automate para responder a Pedidos de Eliminação de Titulares de Dados do GDPR.
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
ms.date: 4/07/2020
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 16d92a2d8aad6e39ff5e2eb446438dc769b1baf8
ms.sourcegitcommit: 27ee91452be26cf5c96397c39f9f5b8bede14cdb
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/08/2020
ms.locfileid: "80862682"
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-power-automate"></a>Responder a Pedidos de Eliminação de Titulares de Dados do GDPR no Power Automate


O “direito de apagamento” através da remoção dos dados pessoais dos Dados do Cliente de uma organização constitui uma proteção fundamental do GDPR. A remoção dos dados pessoais inclui remover todos os dados pessoais e registos gerados pelo sistema, exceto as informações dos registos de auditoria.

O Power Automate permite aos utilizadores criar fluxos de trabalho de automatização que são fundamentais para as operações diárias da organização. Sempre que um utilizador sai da organização, um administrador deve rever manualmente e determinar se determinados dados e recursos criados pelo utilizador devem ser eliminados. Existem outros dados pessoais que são automaticamente eliminados sempre que a conta de utilizador é eliminada do Azure Active Directory.

A tabela seguinte mostra os dados pessoais que são automaticamente eliminados e os dados que necessitam da revisão e da eliminação manuais por um administrador:

|Necessária a revisão e a eliminação manuais|Eliminado automaticamente quando o utilizador é eliminado do Azure Active Directory|
|------|------|
|Ambiente*|Registos gerados pelo sistema|
|Permissões do ambiente**|Histórico de execuções|
|Fluxos|Feed de Atividades|
|Permissões dos fluxos|Gateway |
|Detalhes do utilizador|Permissões dos gateways|
|Ligações*||
|Permissões de ligação||
|Conector personalizado*||
|Permissões do conector personalizado||

\* Cada um destes recursos contém os registos "Criado por" e "Modificado por", que incluem dados pessoais. Por motivos de segurança, estes registos são mantidos até que o recurso seja eliminado.

**Para ambientes que incluem uma base de dados do Common Data Service, as permissões do ambiente (por exemplo, os utilizadores aos quais são atribuídas as funções de Administrador e Criador de Ambientes) são armazenadas como registos no Common Data Service. Para obter orientações sobre como responder a DSRs dos utilizadores que utilizam o Common Data Service, veja [Executing DSRs against Common Data Service Customer Data](https://go.microsoft.com/fwlink/?linkid=872251) (Executar DSRs nos Dados do Cliente do Common Data Service).

Para os dados e recursos que exigem uma revisão manual, o Power Automate oferece as seguintes experiências para localizar ou alterar os dados pessoais de um utilizador específico:

* **Acesso ao site:** inicie sessão no [Centro de Administração do Power Apps](https://admin.powerapps.com/) ou no [Centro de Administração do Power Automate](https://admin.flow.microsoft.com/)

* **Acesso ao PowerShell:**  [Cmdlets do PowerShell para Administradores do Power Apps](https://go.microsoft.com/fwlink/?linkid=871804) 

Veja a seguir a divisão das experiências que estão disponíveis para um administrador para eliminar cada tipo de dados pessoais em cada tipo de recurso:

|Recursos com dados pessoais|Acesso ao site|Acesso ao PowerShell|Eliminação Automatizada|
|-----|----|----|----|
|Registos gerados pelo sistema|[Portal de Confiança do Serviço do Office 365](https://servicetrust.microsoft.com/)|||
|Ambiente|Centro de Administração do Power Automate|Cmdlets do Power Apps||
|Permissões do ambiente*|Centro de Administração do Power Automate|Cmdlets do Power Apps||
|Histórico de execuções||| Eliminação através da política de retenção de 28 dias|
|Feed de atividades |||Eliminação através da política de retenção de 28 dias|
|Tarefas do utilizador|| ||
|Fluxos|Portal de Criadores do Power Automate**|||
|Permissões dos fluxos|Portal de Criadores do Power Automate|||
|Detalhes do utilizador||Cmdlets do Power Apps||
|Ligações|Portal de Criadores do Power Automate| ||
|Permissões de ligação|Portal de Criadores do Power Automate| ||
|Conector personalizado|Portal de Criadores do Power Automate| ||
|Permissões do conector personalizado|Portal de Criadores do Power Automate| ||
|Histórico de Aprovação|Portal de Criadores do Microsoft Power Apps*|||

*Com a introdução do Common Data Service, se uma base de dados for criada no ambiente, as permissões do ambiente e as permissões da aplicação condicionada por modelo serão armazenadas como registos no Common Data Service. Para obter orientações sobre como responder a DSRs dos utilizadores que utilizam o Common Data Service, veja [Executing DSRs against Common Data Service Customer Data](https://go.microsoft.com/fwlink/?linkid=872251) (Executar DSRs nos Dados do Cliente do Common Data Service).

\*\* Um administrador apenas poderá aceder a estes recursos do Portal de Criadores do Power Automate se lhe tiver sido atribuído acesso no Centro de Administração do Power Automate.

## <a name="manage-delete-requests"></a>Gerir Pedidos de eliminação

Os passos a seguir descrevem funções administrativas destinadas a servir pedidos de eliminação de acordo com o GDPR. Estes passos devem ser executados pela ordem descrita abaixo.

> [!IMPORTANT]
> Para evitar danos em dados, siga estes passos por ordem.
>
>

## <a name="list-and-re-assign-flows"></a>Listar e reatribuir fluxos

Estes passos copiam os fluxos existentes de um utilizador cessante. Caso atribua uma nova propriedade às cópias, estes fluxos podem continuar a suportar processos empresariais existentes. Copiar estes fluxos é importante para eliminar ligações do identificador pessoal ao utilizador cessante, bem como devem ser estabelecidas novas ligações para que o fluxo estabeleça ligação com outras aplicações de APIs e SaaS.

1. Inicie sessão no [Centro de administração do Power Automate](https://admin.flow.microsoft.com/) e selecione o ambiente com os fluxos do utilizador eliminado.

    ![Ver ambientes](./media/gdpr-dsr-delete/view-environments.png)

1. Selecione **Recursos** > **Fluxos** e, em seguida, selecione o título do fluxo que pretende reatribuir.

    ![Ver fluxos](./media/gdpr-dsr-delete/admin-view-flows.png)

1. Selecione **Gerir partilha**.

    ![Gerir partilha](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. No painel **Partilhar** apresentado próximo do limite direito, adicione-se a si próprio como proprietário e selecione **Guardar**.

    ![Partilhar fluxo](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. Inicie sessão no [Power Automate](https://flow.microsoft.com/), selecione **Os meus fluxos** e, em seguida, **Fluxos da equipa**.

1. Selecione as reticências **(…)** do fluxo que pretende copiar e, em seguida, selecione **Guardar Como**.

    ![Guardar fluxo como](./media/gdpr-dsr-delete/flow-save-as.png)

1. Configure as ligações conforme necessário e, em seguida, selecione **Continuar**.

1. Introduza um nome novo e selecione **Guardar**.

    ![Criar cópia do fluxo](./media/gdpr-dsr-delete/create-copy-flow.png)

1. Esta nova versão do fluxo aparece em **Os meus fluxos**, onde pode partilhá-la com utilizadores adicionais se pretender.

    ![Fluxos de equipa](./media/gdpr-dsr-delete/team-flows.png)

1. Elimine o fluxo original. Para tal, selecione as reticências **(…)** , selecione **Eliminar** e, em seguida, selecione **Eliminar** novamente quando lhe for pedido. Este passo também removerá os identificadores pessoais subjacentes incluídos nas dependências do sistema entre o utilizador e o Power Automate.

    ![Confirmação de eliminação de fluxo](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. Ative a cópia do fluxo ao abrir **Os meus fluxos** e, em seguida, mudar o controlo de alternar para **Ativado**.

    ![Ativar fluxo](./media/gdpr-dsr-delete/toggle-on.png)

1. A cópia efetua agora a mesma lógica do fluxo de trabalho que a versão original.

## <a name="delete-approval-history-from-power-automate"></a>Eliminar o histórico de aprovações do Power Automate

 Os dados de aprovação do Power Automate são armazenados na versão atual ou anterior do Common Data Service. Numa aprovação, as informações pessoais existem sob a forma de atribuições de aprovação e comentários incluídos numa resposta de aprovação. Os administradores podem aceder a esses dados seguindo estes passos:

1. Inicie sessão no [PowerApps](https://make.powerapps.com/).

1. Selecione **Dados** e, em seguida, **Entidades**.

1. Selecione as reticências **(…)** da entidade de **Aprovação do Fluxo** e, em seguida, abra os dados no Microsoft Excel.

1. No Microsoft Excel, procure, filtre e elimine os dados de aprovação, conforme necessário.

Para obter orientações adicionais sobre como responder a DSRs dos utilizadores que utilizam o Common Data Service, veja [Executing DSRs against Common Data Service Customer Data](https://go.microsoft.com/fwlink/?linkid=872251) (Executar DSRs nos Dados do Cliente do Common Data Service).


## <a name="delete-connections-created-by-a-user"></a>Eliminar ligações criadas por um utilizador

As ligações são utilizadas em conjunto com os conectores para estabelecer conectividade com outros sistemas de APIs e de SaaS.  As ligações incluem referências ao utilizador que A criou e, por conseguinte, podem ser eliminadas para remover quaisquer referências ao utilizador em causa.

Cmdlets do PowerShell para Criadores do Power Apps

Um utilizador pode eliminar todas as suas ligações com a função Remove-Connection dos [cmdlets do PowerShell para Criadores do Power Apps](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-AdminPowerAppConnection | Remove-Connection
```

Cmdlets do PowerShell para Administradores do Power Apps

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all connections for the DSR user and deletes them 
Get-AdminPowerAppConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection 

```

## <a name="delete-the-users-permissions-to-shared-connections"></a>Eliminar as permissões do utilizador para ligações partilhadas

Cmdlets do PowerShell para Criadores do Power Apps

Um utilizador pode eliminar todas as suas atribuições de funções de ligação para ligações partilhadas com a função Remove-ConnectionRoleAssignment dos [cmdlets do PowerShell para Criadores do Power Apps](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```

Cmdlets do PowerShell para Administradores do Power Apps

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all shared connections for the DSR user and deletes their permissions 
Get-AdminConnectionRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectionRoleAssignment  

```
> [!NOTE]
> As atribuições de função de proprietário não podem ser eliminadas sem eliminar o recurso de ligação.
>
>

## <a name="delete-custom-connectors-created-by-the-user"></a>Eliminar conectores personalizados criados pelo utilizador

Os Conectores Personalizados complementam os conectores integrados existentes e permitem a conectividade a outros sistemas de APIs, de SaaS e personalizados. Os Conectores Personalizados incluem referências ao utilizador que os criou e, por conseguinte, podem ser eliminados para remover quaisquer referências ao utilizador em causa.

Cmdlets do PowerShell para Criadores do Power Apps

Um utilizador pode eliminar todos os seus conectores personalizados com a função Remove-Connector dos [cmdlets do PowerShell para Criadores do Power Apps](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

Cmdlets do PowerShell para Administradores do Power Apps
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connectors created by the DSR user and deletes them 
Get-AdminConnector -CreatedBy $deleteDsrUserId | Remove-AdminConnector  

```

## <a name="delete-the-users-permissions-to-shared-custom-connectors"></a>Eliminar as permissões do utilizador para conectores personalizados partilhados

Cmdlets do PowerShell para Criadores do Power Apps

Um utilizador pode eliminar todas as suas atribuições de funções de conector para um conector personalizado partilhado com a função Remove-ConnectorRoleAssignment dos [cmdlets do PowerShell para Criadores do Power Apps](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

Cmdlets do PowerShell para Administradores do Power Apps
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connector role assignments for the DSR user and deletes them 
Get-AdminConnectorRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectorRoleAssignment  

```

> [!NOTE]
> As atribuições de função de proprietário não podem ser eliminadas sem eliminar o recurso de ligação.
>
>


## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>Eliminar ou reatribuir todos os ambientes criados pelo utilizador

Como administrador, tem duas decisões a tomar ao processar um pedido de eliminação DSR de um utilizador para cada um dos ambientes criados pelo utilizador em causa:

1. Se determinar que o ambiente não está a ser utilizado por outras pessoas na sua organização, poderá optar por eliminar o ambiente
1. Se determinar que o ambiente ainda é necessário, poderá optar por não eliminar o ambiente e adicionar-se a si próprio (ou a outro utilizador na sua organização) como Administrador do Ambiente.
> [!IMPORTANT]
> Eliminar um ambiente eliminará permanentemente todos os recursos no ambiente, incluindo todas as aplicações, fluxos, ligações, etc. Por isso, reveja os conteúdos de um ambiente antes da eliminação.
>
>

## <a name="give-access-to-a-users-environments-from-the-power-automate-admin-center"></a>Atribuir acesso aos ambientes de um utilizador no Centro de Administração do Power Automate

Um administrador pode conceder acesso de Administrador para um ambiente criado por um utilizador específico no [Centro de Administração do Power Automate](https://admin.flow.microsoft.com/). Para obter mais informações sobre a administração de ambientes, veja [Utilizar ambientes no Power Automate](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-the-users-permissions-to-all-other-environments"></a>Eliminar permissões do utilizador para todos os outros ambientes

Podem ser atribuídas permissões aos utilizadores (por exemplo, Administrador do Ambiente, Criador do Ambiente, etc.) num ambiente, as quais são armazenadas no serviço do Power Automate como uma “atribuição de função”.

Com a introdução do Common Data Service, se uma base de dados for criada no ambiente, estas "atribuições de funções" são armazenadas como registos no Common Data Service.

Para obter mais informações sobre a remoção da permissão de um utilizador num ambiente, navegue para [Utilizar ambientes no Power Automate](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-gateway-settings"></a>Eliminar Definições do Gateway

A forma de responder a Pedidos de Eliminação de Titulares de Dados para Gateways de Dados no Local encontra-se [aqui](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

## <a name="delete-user-details"></a>Eliminar Detalhes do Utilizador

Os detalhes do utilizador proporcionam uma ligação entre um utilizador e um inquilino específico. Antes de executar este comando, certifique-se de que todos os fluxos deste utilizador foram reatribuídos e/ou eliminados. Após a conclusão dessa ação, um administrador pode eliminar os detalhes do utilizador ao chamar o cmdlet **Remove-AdminFlowUserDetails** cmdlet e ao transmitir o ID do Objeto do utilizador.

Cmdlets do PowerShell para Administradores do Power Apps
```PowerShell
Add-PowerAppsAccount
Remove-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

> [!IMPORTANT]
> Se um utilizador ainda tiver fluxos individuais ou de equipa, este comando irá devolver um erro. Para resolver isto, elimine todos os fluxos ou fluxos de equipa restantes para este utilizador e volte a executar o comando.
>
>

## <a name="delete-the-user-from-azure-active-directory"></a>Eliminar o utilizador do Azure Active Directory

Após a conclusão dos passos acima, o passo final é eliminar a conta do utilizador do Azure Active Directory ao seguir os passos descritos na documentação do RGPD relativa aos Pedidos de Titulares de Dados do Azure, que se encontra no [Portal de Confiança de Serviço do Office 365](https://servicetrust.microsoft.com/ViewPage/GDPRDSR).

## <a name="delete-the-user-from-unmanaged-tenant"></a>Eliminar o utilizador de um Inquilino Não Gerido

Caso seja membro de um inquilino não gerido, tem de efetuar uma ação de **Fecho da conta** no [portal Privacidade Profissional e Escolar](https://go.microsoft.com/fwlink/?linkid=873123).

Para determinar se é ou não utilizador de um inquilino gerido ou não gerido, faça o seguinte:

1. Abra o seguinte URL num browser, certificando-se de que substitui o seu endereço de e-mail no URL:[https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1](https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1).
1. Se for membro de um **inquilino não gerido**, verá `"IsViral": true` na resposta.

    {

     "Login": "foobar@unmanagedcontoso.com",

    "DomainName": "unmanagedcontoso.com",

    "IsViral": **true**,
    
    }

1. Caso contrário, pertence a um inquilino gerido.
