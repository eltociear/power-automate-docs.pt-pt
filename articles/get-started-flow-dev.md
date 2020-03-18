---
title: Criar conectores personalizados e incorporar fluxos | Microsoft Docs
description: Crie um conector personalizado, partilhe-o, incorpore um fluxo e muito mais.
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
ms.date: 11/22/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 74a7bdb451771dd11e88dbf824c3d92383b5a66d
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79194123"
---
# <a name="start-to-build-with-power-automate"></a>Começar a criar com o Power Automate


Veja a seguir algumas das formas de expandir a sua aplicação com o Power Automate:

* Criar e ligar a um conector personalizado.
* Partilhar o conector personalizado com todos os utilizadores do Power Automate.
* Incorporar a experiência de fluxo numa aplicação.
* Realçar todos os conectores personalizados para que os utilizadores possam interagir com o Power Automate da melhor forma.

## <a name="prerequisites"></a>Pré-requisitos

* Uma conta do [Power Automate](https://flow.microsoft.com).

## <a name="create-a-custom-connector"></a>Criar um conector personalizado

Caso tenha um serviço Web ao qual se pretende ligar a partir do Power Automate, primeiro terá de criar um conector personalizado. Ao registar um conector personalizado, indica ao Power Automate as características do serviço Web, incluindo a autenticação necessária, os acionadores e as ações que suporta, bem como os parâmetros e saídas de cada uma dessas ações.

Siga este tutorial para saber como pode [Registar e utilizar conectores personalizados](https://powerapps.microsoft.com/tutorials/register-custom-api/). Após registar o seu conector personalizado, pode partilhá-lo na sua organização para ser testado.

## <a name="share-a-custom-connector-with-all-power-automate-users"></a>Partilhar um conector personalizado com todos os utilizadores do Power Automate

Depois de testar totalmente o conector personalizado, inicie o [processo de revisão](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) para que o conector seja aprovado pela Microsoft para a partilha com todos os outros utilizadores do Power Automate.

Eis o que precisa para o processo de revisão:

* Um ficheiro OpenAPI que representa a API e as informações de autenticação.
* Um ícone para o seu conector.
* Uma descrição do seu conector.
* Aproximadamente 10 ideias sobre como o seu conector poderia beneficiar outros utilizadores através de modelos.

Depois de submeter estas informações, a Microsoft dá início à avaliação da funcionalidade da API no Power Automate e no Microsoft Power Apps.

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>Incorporar a experiência de fluxo no seu site ou aplicação

Pode [incorporar](developer/embed-flow-dev.md) o Power Automate na aplicação para ativar a integração contextual aprofundada entre a aplicação e todos os outros serviços suportados pelo Power Automate. Por exemplo, você pode:

* Procurar todos os modelos relacionados com o seu serviço e permitir que os utilizadores selecionem um modelo.
* Gerir os fluxos que os utilizadores têm em relação à sua aplicação.

## <a name="next-steps"></a>Próximos passos

Saiba como [incorporar](developer/embed-flow-dev.md) o Power Automate na aplicação.
