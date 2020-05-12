---
title: Descrição geral dos fluxos com suporte para soluções | Microsoft Docs
description: Conheça os benefícios da criação de fluxos em soluções.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 56b90ebdf7f3655763b7e40c60b985f06604c47b
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298292"
---
# <a name="overview"></a>Descrição Geral


Quando aloja os fluxos numa [solução](https://docs.microsoft.com/powerapps/maker/common-data-service/solutions-overview), estes tornam-se portáteis, o que os permite mover facilmente, junto com os seus componentes, de um ambiente para outro. Um caso de utilização típico será o de um fabricante independente de software (ISV) que desenvolve fluxos num ambiente de sandbox e, em seguida, move esses fluxos para um ambiente de teste. Depois de realizar os testes, o ISV pode, em seguida, migrar os fluxos para o ambiente de produção dos clientes que comprarem estes fluxos. Este processo é muito mais fácil quando cria os seus fluxos em soluções e, em seguida, move as soluções e os seus conteúdos.

Os fluxos que criar dentro de uma solução são conhecidos como fluxos *com suporte para soluções*. Pode adicionar vários fluxos a uma única solução.

> [!NOTE] 
> Não pode mover fluxos sem suporte para soluções (ou seja, fluxos que não foram criados numa solução) para uma solução.

## <a name="prerequisites"></a>Pré-requisitos

Tem de ter os seguintes componentes para criar soluções e fluxos com suporte para soluções:

- [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- Um ambiente com a versão 9.1.0.267 ou posterior.

  Para verificar a versão, aceda ao  [Centro de administração do Power Automate](https://admin.flow.microsoft.com), selecione **Ambientes**, selecione o ambiente que lhe interessa e, em seguida, selecione o separador **Detalhes**.

## <a name="create-a-solution"></a>Criar uma solução

Siga estes passos para criar uma solução:

1. Inicie sessão em [Power Automate](https://flow.microsoft.com).
1. Selecione **Soluções** na barra de navegação.

   ![](./media/overview-solution-flows/select-solutions-from-left-nav.png)

1. Selecione **+ Nova solução**.

   ![](./media/overview-solution-flows/select-new-solution.png)

1. Introduza todas as informações necessárias para a nova solução, incluindo o **Nome a Apresentar**, o **Publicador**, a **Versão** e o **Nome**. Também é recomendável introduzir uma descrição da solução.

   ![](./media/overview-solution-flows/new-solution.png)

1. Selecione **Guardar e Fechar** no menu superior.

   ![](./media/overview-solution-flows/save-and-close-solution.png)

   A nova solução pode parecer semelhante a esta imagem:

   ![](./media/overview-solution-flows/new-solution-created.png)

   > [!TIP]
   > Se não for apresentada a nova solução, selecione **Soluções** para atualizar a lista de soluções.

## <a name="learn-more"></a>Mais Informações

- [Criar um fluxo numa solução](./create-flow-solution.md)
- [Exportar uma solução](./export-flow-solution.md)
- [Importar uma solução](./import-flow-solution.md)
- [Editar um fluxo com suporte para soluções](./edit-solution-aware-flow.md)
- [Remover um fluxo com suporte para soluções](./remove-solution-aware-flow.md)
