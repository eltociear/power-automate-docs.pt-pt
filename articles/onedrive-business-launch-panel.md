---
title: Criar fluxos a partir do painel de iniciação do OneDrive para Empresas | Microsoft Docs
description: Criar fluxos a partir do painel de iniciação do OneDrive para Empresas.
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
ms.date: 08/25/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7458b3cb08ca1ce3e29a9d0d29e1bec91d46f7ea
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193203"
---
# <a name="create-flows-from-the-onedrive-for-business-launch-panel"></a>Criar fluxos a partir do painel de iniciação do OneDrive para Empresas


À semelhança do [Painel de Iniciação do Power Automate no SharePoint](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/), pode executar fluxos em ficheiros específicos no OneDrive para Empresas. 

Esta funcionalidade permite que a pessoa que está a executar o fluxo utilize as suas próprias credenciais, o que se aplica especialmente aos fluxos que foram criados por um departamento de TI. 

Os utilizadores também podem receber pedidos para entradas de runtime como **Aprovador** ou **Mensagem**, que podem ser do tipo texto, ficheiro, e-mail, booleano ou número.

Nestas instruções, vamos criar um fluxo simples que utiliza um dos muitos [modelos do OneDrive para Empresas](https://flow.microsoft.com/search/?q=OneDrive) para pedir a aprovação de um ficheiro pelo gestor do requerente.

## <a name="create-a-flow-that-requests-manager-approval-for-a-file-in-onedrive-for-business"></a>Criar um fluxo que pede a aprovação do gestor relativamente a um ficheiro no OneDrive para Empresas

1. Inicie sessão no OneDrive para Empresas.
1. Localize e selecione o ficheiro no qual quer criar o fluxo.
1. Selecione a ligação **Mostrar ações** (reticências).
1. Selecione **Fluxo** > **Criar um fluxo**.

     ![Criar fluxo](./media/onedrive-launch-panel/create-flow.png) 

1. Selecione um dos modelos.

    Neste exemplo, selecione o modelo **Pedir aprovação do meu gestor para o ficheiro selecionado**.

     >[!TIP]
     >Inicie sessão em qualquer conector que peça que inicie sessão.

1. Selecione **Continuar**.
1. Faça as alterações desejadas no modelo e guarde o fluxo com um nome do qual se lembre facilmente.

## <a name="run-the-flow"></a>Executar o fluxo

1. Inicie sessão no OneDrive para Empresas.
1. Localize e selecione o ficheiro no qual pede a aprovação do gestor.
1. Selecione a ligação **Mostrar ações** (reticências).
1. Selecione **Fluxo**. Verá o fluxo que criou anteriormente.
1. Selecione o fluxo que criou anteriormente.

     ![Executar o fluxo](./media/onedrive-launch-panel/run-flow.png)


>[!TIP]
>Apesar de estas instruções mostrarem como criar um fluxo a partir de um modelo, também é possível criar um fluxo do zero para utilizar qualquer um das centenas de conectores disponíveis no Power Automate.

## <a name="learn-more"></a>Saiba mais

- [Introdução ao Power Automate](getting-started.md) 
- [Criar fluxos de vários passos](multi-step-logic-flow.md)
