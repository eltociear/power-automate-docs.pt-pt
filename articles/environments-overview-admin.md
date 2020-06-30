---
title: Descrição geral do ambiente para Administradores | Microsoft Docs
description: Utilizar, criar e gerir ambientes no Power Automate
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/07/2020
ms.author: sunayv
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: e1c2a93fb011b6f20ecaf79fb0bf95212a2506d4
ms.sourcegitcommit: 2c9cffb59ef2382648a80966ebbf0fe8eafebe64
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/09/2020
ms.locfileid: "3354443"
---
# <a name="using-environments-within-power-automate"></a>Utilizar ambientes no Power Automate


## <a name="benefits"></a>Benefícios

Os ambientes oferecem as seguintes vantagens:

* **Localidade de dados**: os ambientes podem ser criados em regiões diferentes e estão vinculados a essa localização geográfica. Quando cria um fluxo num ambiente, esse fluxo é encaminhado para todos os datacenters nessa localização geográfica. Isto também proporciona vantagens em termos de desempenho.

    Se os seus utilizadores estiverem na Europa, crie e utilize o ambiente na região da Europa. Se os seus utilizadores estiverem nos Estados Unidos, crie e utilize o ambiente nos E.U.A. 

    > [!IMPORTANT]
    > Se eliminar o ambiente, todos os fluxos dentro desse ambiente serão eliminados também. Isto aplica-se a todos os itens que criar nesse ambiente, incluindo ligações, gateways, Power Apps e muito mais.
* **Prevenção de perda de dados**: como Administrador, não quer fluxos que obtenham dados de uma localização interna (como o *OneDrive para Empresas* ou uma lista do SharePoint que contenha informações salariais) e, em seguida, publiquem esses dados (tal como no *Twitter*). Utilize a prevenção de perda de dados para controlar quais são os serviços que podem partilhar dados dentro da implementação do Power Automate.

    Por exemplo, pode adicionar os serviços *SharePoint* e *OneDrive para Empresas* a uma política só de dados de negócio. Todos os fluxos criados neste ambiente podem utilizar os serviços *SharePoint* e *OneDrive para Empresas*. No entanto, não poderão partilhar os dados com outros serviços que não estão incluídos na política só de dados de negócio.

  > [!NOTE]
  > A prevenção de perda de dados está disponível com alguns skus de licença, incluindo a licença P2.

* **Limite de isolamento para todos os recursos**: quaisquer fluxos, gateways, ligações, conectores personalizados, etc., residem num ambiente específico. Não existem em quaisquer outros ambientes.
* **Common Data Service**: seguem-se as opções disponíveis se quiser criar um fluxo para inserir dados num serviço:

  * Inserir dados para um ficheiro Excel e armazenar o ficheiro Excel numa conta de armazenamento na cloud, como o OneDrive.
  * Crie uma Base de Dados SQL e, em seguida, armazene os dados nela.
  * Utilize o Common Data Service para armazenar os seus dados.

    Cada ambiente pode ter, no máximo, uma base de dados para os seus fluxos no Common Data Service. O acesso ao Common Data Service depende da licença que adquiriu; o Common Data Service não está incluído com a licença Gratuita.

## <a name="limitations"></a>Limitações

Embora os ambientes ofereçam inúmeras vantagens, também introduzem novas limitações. O facto de os ambientes serem um limite de isolamento significa que nunca pode ter recursos que façam referência a recursos *entre* ambientes. Por exemplo, não poderá criar um conector personalizado num ambiente e, em seguida, criar um fluxo que utilize esse conector personalizado num ambiente diferente.

## <a name="use-the-default-environment"></a>Utilize o ambiente predefinido

O ambiente **predefinido** é partilhado por todos os utilizadores e qualquer utilizador pode criar fluxos no ambiente **predefinido**.

> [!TIP]
> Se for um Utilizador de pré-visualização, todos os fluxos existentes residem no ambiente predefinido. Um *Utilizador de pré-visualização* é alguém que utilizava o Power Automate antes do seu lançamento para Disponibilidade Geral (DG).

## <a name="the-admin-center"></a>O centro de administração

Os administradores utilizam o centro de administração para criar e gerir ambientes. Existem duas formas de abrir o centro de administração:

### <a name="option-1-select-settings"></a>Opção 1: Selecionar Definições

1. Iniciar sessão em [flow.microsoft.com](https://flow.microsoft.com).
1. Selecione o ícone de engrenagem de Definições e escolha **Centro de Administração** na lista:

   ![Definições e Portal de Administrador](./media/environments-overview-admin/settings.png)
1. O centro de administrador abre.

### <a name="option-2-open-adminflowmicrosoftcom"></a>Opção 2: Abrir admin.flow.microsoft.com

Aceda a [admin.flow.microsoft.com](https://admin.flow.microsoft.com) e inicie sessão com a sua conta profissional.

## <a name="create-an-environment"></a>Criar um ambiente

1. No [Centro de administração do Power Automate](https://admin.flow.microsoft.com), selecione **Ambientes**. Verá todos os ambientes existentes: ![Ambientes](./media/environments-overview-admin/environments-list.png)
2. Selecione **Novo ambiente** e, em seguida, introduza as informações necessárias:


   |     Propriedade     |                                                 Descrição                                                 |
   |------------------|-------------------------------------------------------------------------------------------------------------|
   | Nome do Ambiente |              Introduza o nome do ambiente, tal como `Human Resources` ou `Europe flows`.              |
   |      Região      | Escolha a localização para alojar o seu ambiente. Para obter o melhor desempenho, utilize a região mais próxima dos utilizadores. |
   | Tipo de Ambiente |                  Escolha um tipo de ambiente com base na sua licença: Produção ou Avaliação.                   |

     ![definições de ambiente](./media/environments-overview-admin/new-environment-dialog.png)
3. Clique em **Criar ambiente**.
4. Agora, pode optar por **Criar base de dados** ou **Ignorar**.
5. Se optar por **Criar base de dados**, ser-lhe-á solicitado que introduza uma **Moeda** e um **Idioma** para a Base de Dados. Além disso, também pode optar por implementar exemplos de aplicações e de dados.

   ![definições de configuração da base de dados](./media/environments-overview-admin/create-database-dialog2.png)


Pode agora adicionar utilizadores ao ambiente.

## <a name="manage-your-existing-environments"></a>Gerir os ambientes existentes

1. No [Centro de administração do Power Automate](https://admin.flow.microsoft.com), selecione **Ambientes**:

   ![item do menu ambientes](./media/environments-overview-admin/select-environments.png)
1. Selecione um ambiente para abrir as propriedades dele.
1. Utilize o separador **Detalhes** para ver informações adicionais sobre um ambiente, incluindo quem criou o ambiente, a localização geográfica e muito mais:

   ![detalhes do separador](./media/environments-overview-admin/open-environment.png)
1. Selecione **Segurança**.

    Se não tiver selecionado **Criar Base de Dados** nos passos anteriores, existem duas opções em **Funções de ambiente**: **Administrador do Ambiente** e **Criador do Ambiente**:

    ![as funções de administração](./media/environments-overview-admin/environment-roles.png)

    Um **Criador** pode criar novos recursos num ambiente, tais como fluxos, ligações de dados e gateways.

   > [!NOTE]
   > Um utilizador não tem de ser um **Criador** para *editar* recursos num ambiente. Cada Criador determina quem pode editar os recursos ao conceder permissões a utilizadores que não são Criadores do ambiente.
   > 
   > 

    Um **Admin** pode criar políticas de prevenção de perda de dados e ainda realizar outras tarefas administrativas, tais como criar ambientes, adicionar utilizadores aos ambiente e atribuir privilégios de administrador/criador.

   1. Selecione a função **Criador de Ambiente** e, em seguida, selecione **Utilizadores**: ![função de criador](./media/environments-overview-admin/add-environment-maker.png)
   1. Introduza um nome, um endereço de e-mail ou um grupo de utilizadores a que pretende atribuir a função **Criador**.
   1. Selecione **Guardar**.

1. Em **Segurança**, selecione **Funções de Utilizador**:

    ![funções de utilizador](./media/environments-overview-admin/security-user-roles.png)

    Todas as funções existentes estão listadas, incluindo as opções para editar ou eliminar a função.

    Selecione **Nova função** para criar uma nova função.
1. Em **Segurança**, selecione **Conjuntos de Permissões**:

    ![definições de permissões](./media/environments-overview-admin/security-permission-set.png)

    Verá todos os conjuntos de permissões existentes e as opções para editar ou eliminar funções.

    Selecione **Novo conjunto de permissões** para criar um novo conjunto de permissões.
1. Se tiver optado por **Criar Base de Dados** para armazenar os dados, essa base de dados fará parte do Common Data Service. Quando clica no separador **Segurança**, ser-lhe-á pedido para navegar para o **Centro de gestão de instâncias do Dynamics 365**, onde poderá aplicar segurança baseada em funções.
![definições de segurança do Dynamics](./media/environments-overview-admin/Security-Link-D365.png)

1. Selecione o utilizador na lista de utilizadores no ambiente/instância.
  ![definições de segurança do Dynamics](./media/environments-overview-admin/D365-Select-User.png)

1. Atribuir função ao utilizador.

   ![atribuir função a utilizador](./media/environments-overview-admin/D365-Assign-Role.png)

> [!NOTE]
> Os utilizadores ou grupos atribuídos a estas funções de ambiente não recebem automaticamente acesso à base de dados do ambiente (se existir) e têm de receber acesso separadamente por um proprietário da base de dados. 
>
>

### <a name="database-security"></a>Segurança da base de dados
A capacidade de criar e modificar um esquema de base de dados e de ligar aos dados armazenados numa base de dados que é provisionada no ambiente é controlada pelas funções de utilizador e conjuntos de permissões da base de dados. Pode gerir as funções de utilizador e os conjuntos de permissões da base de dados do seu ambiente a partir da secção **Funções de utilizador** e **Conjuntos de permissões** do separador **Segurança**. 

   ![atribuir função a utilizador](./media/environments-overview-admin/D365-Assign-Role.png)

## <a name="frequently-asked-questions"></a>Perguntas mais frequentes

### <a name="can-i-move-a-flow-between-environments"></a>Posso mover um fluxo entre ambientes?

Sim. Os fluxos podem ser exportados de um ambiente e importados para outro ambiente.

### <a name="which-license-includes-common-data-service"></a>Que licença inclui Common Data Service?

Pode aceder ao Common Data Service com qualquer uma das [licenças](https://flow.microsoft.com/pricing) do Power Automate.

Veja o documento [Perguntas sobre faturação](billing-questions.md) para obter respostas a perguntas frequentes sobre faturação.

### <a name="can-common-data-service-be-used-outside-of-an-environment"></a>Pode o Common Data Service ser utilizado fora de um ambiente?

Não. O Common Data Service requer um ambiente. [Leia mais](common-data-model-intro.md) sobre ele.

### <a name="what-regions-include-power-automate"></a>Quais as regiões incluem o Power Automate?

O Power Automate suporta a maioria das regiões que o Office 365 suporta; veja [a descrição geral das regiões](regions-overview.md) para obter mais detalhes.

### <a name="whats-needed-to-create-my-own-custom-environment"></a>Quais os elementos necessários para criar o meu próprio ambiente personalizado?

Todos os utilizadores com a licença Power Automate Plano 2 podem criar os seus próprios ambientes. Todos os utilizadores do Power Automate podem utilizar os ambientes criados por administradores de Plano 2, mas não podem criar os seus próprios ambientes.
