---
title: Introdução às políticas de prevenção de perda de dados (DLP). | Microsoft Docs
description: Introdução às políticas de prevenção de perda de dados do Power Automate.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/26/2020
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 722cf0c0f56a67b46f7f20ae76c2e98a86121f69
ms.sourcegitcommit: e709e8c4a62df6fdb0ca06f3f8afb5c639c76632
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/26/2020
ms.locfileid: "82159567"
---
# <a name="data-loss-prevention-dlp-policies"></a>Políticas de prevenção de perda de dados (DLP)


Este documento apresenta-lhe políticas de prevenção de perda de dados, que ajudam a proteger os dados organizacionais de serem partilhados com uma lista de conectores que define.

## <a name="whats-a-data-loss-prevention-policy"></a>O que é uma política de prevenção de perda de dados?

Os dados de uma organização são essenciais para o seu sucesso. Os dados têm de estar prontamente disponíveis para tomada de decisões, mas têm de estar protegidos para não serem partilhados com pessoas que não devem ter acesso aos mesmos. Para proteger estes dados, o Power Automate permite-lhe criar e impor políticas que definem que conectores do consumidor conseguem aceder e partilhar os dados de negócio. Estas políticas que definem a forma como os dados podem ser partilhados são referidas como políticas de prevenção de perda de dados (DLP).

## <a name="why-create-a-dlp-policy"></a>Por quê criar uma política DLP?

Pode criar uma política DLP para definir claramente que conectores do consumidor podem aceder e partilhar os seus dados de negócio. Por exemplo, uma organização que utilize o Power Automate pode não querer que os dados empresariais no SharePoint sejam automaticamente publicados no feed do Twitter. Para evitar esta situação, pode criar uma política DLP que impeça que esses dados do SharePoint sejam utilizados como a origem de tweets.

## <a name="benefits-of-a-dlp-policy"></a>Vantagens de uma política DLP

* Garante que os dados são geridos de forma uniforme em toda a organização.
* Impede que os dados empresariais importantes sejam publicados acidentalmente em conectores, tais como sites de redes sociais.

## <a name="managing-dlp-policies"></a>Gerir políticas DLP

### <a name="prerequisites-for-managing-dlp-policies"></a>Pré-requisitos para gerir políticas DLP

* Permissões de administração do inquilino ou administrador do ambiente.

    Pode saber mais sobre as permissões no [artigo ambientes](environments-overview-admin.md).


## <a name="create-a-dlp-policy"></a>Criar uma política DLP

### <a name="prerequisites-for-creating-dlp-policies"></a>Pré-requisitos para criar políticas DLP

Para criar uma política DLP, tem de ter permissões para, pelo menos, um ambiente.

Siga estes passos para criar uma política DLP que impede que os dados no site do SharePoint da sua empresa sejam publicados no Twitter:

1. Inicie sessão no [Centro de administração do Power Automate](https://admin.flow.microsoft.com) (Centro de administração).

1. Selecione o separador Políticas de Dados e, em seguida, selecione a ligação **Nova política**:

    ![Iniciar sessão](./media/prevent-data-loss/create-policy-1.png)
1. Selecione o separador **Grupos de dados**.

1. Introduza o nome da política DLP como *Acesso Seguro aos Dados da Contoso* na etiqueta **Nome da Política de Dados**, na parte superior da página:

    ![Iniciar sessão](./media/prevent-data-loss/create-policy-2.png)

1. Selecione o [ambiente](environments-overview-admin.md) no separador **Ambientes**.

    > [!NOTE]
    > Como administrador de ambientes, pode criar políticas aplicáveis apenas a um único ambiente. Como administrador de inquilinos, pode criar políticas aplicáveis a qualquer combinação de ambientes:
    >
    >

    ![Selecionar o ambiente](./media/prevent-data-loss/create-policy-3.png)

1. Selecione o separador **Grupos de dados**:

    ![selecionar grupos de dados](./media/prevent-data-loss/create-policy-4.png)

1. Selecione a ligação **Adicionar**, localizada dentro da caixa do grupo **Apenas dados de negócio**:

    ![Selecionar Adicionar](./media/prevent-data-loss/create-policy-5.png)

1. Selecione os conectores **SharePoint** e **Salesforce** na página **Adicionar conectores**:

   ![selecionar conectores](./media/prevent-data-loss/create-policy-6.png)

1. Selecione o botão **Adicionar conectores** para adicionar os conectores que podem partilhar dados do negócio.

1. Selecione **Guardar Política** no canto superior direito do ecrã.

1. Após alguns instantes, a nova política DLP será apresentada na lista de políticas de prevenção de perda de dados:

    ![Lista de DLP](./media/prevent-data-loss/create-policy-9.png)

1. **Opcional** Envie um e-mail ou outro tipo de comunicação para a sua equipa a alertá-los de que está agora disponível uma nova política DLP.

Parabéns, acabou de criar uma política DLP que permite que a aplicação partilhe dados entre o SharePoint e o Salesforce e bloqueia a partilha de dados com outros serviços.

> [!NOTE]
> Adicionar um serviço a um grupo de dados remove-o automaticamente do outro grupo de dados. Por exemplo, se o Twitter estiver no grupo de dados **apenas dados de negócio** e não quiser permitir que os dados de negócio sejam partilhados com o Twitter, basta adicionar o serviço Twitter ao grupo de **dados de negócio não permitidos**. Desta forma, o Twitter é removido do grupo de dados apenas dados de negócio.
>
>

## <a name="data-sharing-violations"></a>Violações de partilha de dados

Partindo do princípio de que criou a política DLP descrita acima, se um utilizador criar um fluxo que partilhe dados entre o Salesforce (que se encontra no grupo de dados **apenas dados de negócio**) e o Twitter (que se encontra no grupo de dados **não são permitidos dados de negócio**), o utilizador será informado de que o fluxo está **suspenso** devido a um conflito com a política de prevenção de perda de dados criada por si.

![criar fluxo](./media/prevent-data-loss/10.png)

Se os seus utilizadores o contactarem devido a fluxos suspensos, considere os seguintes aspetos:

1. Neste exemplo, se existir um motivo profissional válido para partilhar dados de negócio entre o SharePoint e o Twitter, pode editar a política DLP.

1. Peça ao utilizador para editar o fluxo para estar em conformidade com a política DLP.

1. Peça ao utilizador para deixar o fluxo no estado suspenso até que se tome uma decisão relativamente à partilha de dados entre estas duas entidades.

## <a name="find-a-dlp-policy"></a>Localizar uma política DLP

### <a name="admins"></a>Administradores

Os administradores podem utilizar a funcionalidade de pesquisa do Centro de administração para localizar políticas DLP específicas.

> [!NOTE]
> Os administradores devem publicar todas as políticas DLP para que os utilizadores na organização estejam cientes das políticas antes de criarem fluxos.
>
>

### <a name="makers"></a>Criadores

Se não tem permissões de administrador e quiser saber mais sobre as políticas DLP na sua organização, contacte o administrador. Também pode saber mais no artigo [ambientes de fabricantes](environments-overview-maker.md)

> [!NOTE]
> Apenas os administradores podem editar ou eliminar políticas DLP.
>
>

## <a name="edit-a-dlp-policy"></a>Editar uma política DLP

1. Inicie o [Centro de administração](https://admin.flow.microsoft.com).

1. No Centro de administração que é iniciado, selecione a ligação **Políticas de dados** no lado esquerdo.

    ![selecionar políticas de dados](./media/prevent-data-loss/2.png)

1. Procure a lista de políticas DLP existentes e selecione o botão Editar junto à política que pretende editar.

1. Faça as alterações necessárias à política. Pode modificar o ambiente ou os serviços nos grupos de dados, por exemplo.

1. Selecione **Guardar Política** para guardar as alterações.

> [!NOTE]
> As políticas DLP criadas por administradores de inquilinos podem ser visualizadas, mas não podem ser editadas, por administradores de ambientes.
>
>

## <a name="delete-a-dlp-policy"></a>Eliminar uma política DLP

1. Inicie o [Centro de administração](https://admin.flow.microsoft.com).

1. Selecione o separador **Políticas de dados** no lado esquerdo.

    ![selecionar o separador políticas de dados](./media/prevent-data-loss/2.png)

1. Procure a lista de políticas DLP existentes e, em seguida, selecione o botão Eliminar junto à política que pretende eliminar:

    ![Selecionar o botão Eliminar](./media/prevent-data-loss/3-delete.png)

1. Confirmar que quer realmente eliminar a política ao selecionar o botão **Eliminar**:

    ![confirmar que pretende eliminar a política](./media/prevent-data-loss/4.png)

## <a name="dlp-policy-permissions"></a>Permissões de políticas DLP

Apenas os inquilinos e os administradores de ambiente podem criar e modificar políticas DLP. Saiba mais sobre as permissões no artigo [ambientes](environments-overview-admin.md).


## <a name="custom-and-http-connectors"></a>Conectores HTTP e personalizados

Os conectores HTTP e personalizados devem ser adicionados às políticas DLP através de um modelo do Power Automate ou de um PowerShell.

> [!TIP]
> Não pode mudar para uma versão anterior à do esquema de 2018-11-01. O suporte para HTTP não pode ser removido de uma política. Se tentar remover o suporte para HTTP, a política DLP poderá ficar danificada. Além disso, se uma política DLP for atualizada para suportar os conectores HTTP, os fluxos atuais que utilizam esses recursos HTTP poderão ser desativados.

Seguem-se os conectores HTTP que podem ser adicionados a uma política:

- HTTP (e HTTP + Swagger)
- HTTP Webhook
- Pedido de HTTP

## <a name="add-connectors-custom-and-http-connectors-with-templates"></a>Adicionar conectores personalizados e conectores HTTP com modelos

Para adicionar um conector personalizado a uma política com um [modelo](https://flow.microsoft.com/galleries/public/templates/ae9683086770420e902c043e5ed4b363/), introduza o nome da política, o grupo ao qual pretende adicionar o conector e o nome, o ID e o tipo do conector. Execute o fluxo uma vez para adicionar o conector personalizado à política e ao grupo atribuído.

Para adicionar os conectores HTTP a uma política existente através do [modelo](https://flow.microsoft.com/galleries/public/templates/834eb1366aa54335a5f979014a9e0477/), introduza o nome da política que pretende e execute o fluxo.

## <a name="add-custom-and-http-connectors-with-powershell"></a>Adicionar conectores HTTP e personalizados com o PowerShell

Para adicionar suporte para conectores personalizados e/ou conectores HTTP a uma política com o PowerShell, [transfira](https://docs.microsoft.com/powerapps/administrator/powerapps-powershell) e importe os scripts mais recentes do PowerShell do Power Apps e, em seguida, utilize estes cmdlets:  “New-AdminDlpPolicy”, “Set-AdminDlpPolicy”, “Add-CustomConnectorToPolicy” e “Remove-CustomConnectorFromPolicy” para modificar a política. Utilize o cmdlet “Get-Help -detailed” como referência.


> [!IMPORTANT]
> Utilize a versão de 2018-11-01 do esquema quando criar ou atualizar uma política DLP para incluir os conectores HTTP. Adicionar suporte para HTTP com o modelo ou o PowerShell só afetará a política especificada. As novas políticas criadas através do Centro de Administração não irão conter os conectores HTTP.



## <a name="next-steps"></a>Próximos passos

* [Saiba mais sobre os ambientes](environments-overview-admin.md)
* [Saiba mais sobre o Power Automate](getting-started.md)
* [Saiba mais sobre o centro de administração](admin-center-introduction.md)
* [Sabia mais sobre a integração de dados](https://docs.microsoft.com/common-data-service/entity-reference/dynamics-365-integration)
