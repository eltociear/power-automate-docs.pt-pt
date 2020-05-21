---
title: Tudo sobre ambientes do Power Automate | Microsoft Docs
description: Saiba como utilizar ambientes para isolar os fluxos
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/07/2020
ms.author: sunayv
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b797fc6e4a2e7835a7322f9fc55d50c96d113031
ms.sourcegitcommit: 27ee91452be26cf5c96397c39f9f5b8bede14cdb
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/08/2020
ms.locfileid: "3299062"
---
# <a name="choosing-an-environment"></a>Escolher um ambiente

Este artigo apresenta os **ambientes** do Power Automate em que pode criar e isolar, de forma segura, os fluxos, os gateways, as ligações e outros recursos.

Irá aprender sobre:

* As funcionalidades que os ambientes oferecem.
* Mudar entre ambientes.
* Como criar um fluxo no ambiente certo.

## <a name="environments-overview"></a>Descrição geral de ambientes

Quando cria um fluxo, pode escolher um ambiente no qual vai alojar o fluxo e os recursos utilizados por esse fluxo. Pode utilizar ambientes em separado para diferentes cenários.

## <a name="here-are-a-few-scenarios-for-using-environments"></a>Seguem-se alguns cenários de utilização de ambientes

Cenário|Recomendação
-----|-----
Pretende criar um fluxo que utiliza uma ligação para o Common Data Service.|Coloque o fluxo e o Common Data Service no mesmo ambiente. Isto garante que todos os dados estão isolados nesse ambiente (limite de isolamento).
Está a criar um fluxo para o departamento de Recursos Humanos. Pretende garantir que apenas os utilizadores do departamento de Recursos Humanos têm acesso ao fluxo.|Crie um ambiente e adicione apenas os utilizadores de RH ao mesmo. Coloque o fluxo e quaisquer outros recursos que o fluxo utiliza neste ambiente.
Existem utilizadores na Europa que utilizam um fluxo para mostrar dados do SharePoint.|Crie um ambiente na Europa e, em seguida, crie o seu fluxo e a ligação do SharePoint ao mesmo. Este ambiente da Europa proporciona aos utilizadores europeus o melhor desempenho, uma vez que todos os recursos estão localizados na Europa (localidade de dados).

Para criar ambientes, tem de ser um administrador do Power Automate. Os administradores controlam quem tem acesso a ambientes. Para obter informações sobre como pode criar e gerir ambientes, veja o tópico [administrar ambientes](environments-overview-admin.md).

## <a name="switching-environments"></a>Mudança de ambientes

O Power Automate permite alternar mais facilmente entre ambientes. Quando mudar ambientes, são apresentados apenas os itens que são criados nesse ambiente específico; o utilizador não vê nem tem acesso aos itens em qualquer outro ambiente.

Eis um exemplo.

Criou um fluxo com o nome *NewEmployee* no ambiente *Recursos Humanos*. No [Power Automate](https://flow.microsoft.com), abra o ambiente *Vendas*. O fluxo *NewEmployee* não está listado. Para ver o fluxo *NewEmployee*, abra o ambiente *Recursos Humanos*. Lembre-se que se aplicam as mesmas regras a todos os itens que criar no ambiente, incluindo ligações, gateways, fluxos e muito mais.

Siga estes passos para mudar ambientes:

1. Iniciar sessão no [Power Automate](https://flow.microsoft.com).
1. No canto superior direito, verá uma imagem que representa o seu perfil.

   ![imagem de perfil](./media/environments-overview-maker/default-environment.png)

1. Selecione a imagem. Uma lista pendente que apresenta todos os ambientes disponíveis para si. O ambiente em que tem atualmente sessão iniciada está marcado:

   ![lista de imagem de ambientes](./media/environments-overview-maker/all-environments.png)
1. Para mudar para outro ambiente, selecione esse ambiente na lista:

   ![selecione um ambiente para o qual pretende mudar](./media/environments-overview-maker/select-europe.png)
1. O Power Automate muda para o novo ambiente.

## <a name="create-flows-in-the-right-environment"></a>Criar fluxos no ambiente certo

Antes de criar um fluxo, selecione o ambiente no qual irá adicionar o fluxo e os respetivos recursos.

> [!NOTE]
> Se criar um fluxo no ambiente errado, terá de o eliminar e, em seguida, criá-lo no ambiente correto.

Ao escolher o ambiente no qual pretende alojar os seus fluxos, considere os seguintes fatores:

* Pode criar apenas gateways no ambiente predefinido. Se pretender utilizar um gateway para ligar o seu fluxo a dados no local, terá de utilizar o ambiente predefinido.
* O Common Data Service está ligado a um ambiente específico. Por isso, se pretender criar um fluxo que utiliza o Common Data Service, tem de criar o fluxo no ambiente que aloja a base de dados.
* Irá ver todos os ambientes nos quais pode editar recursos. No entanto, terá de pedir a um administrador para o adicionar como um criador a todos os ambientes nos quais pretende criar fluxos.

> [!NOTE]
> Poderá sempre criar fluxos no ambiente predefinido.

## <a name="next-steps"></a>Passos seguintes

* [Criar um fluxo a partir de um modelo](get-started-logic-template.md)
* [Criar um fluxo](get-started-logic-flow.md)
* [Descrição geral do ambiente para Administradores](environments-overview-admin.md)
