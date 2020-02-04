---
title: Criar fluxos com o Microsoft Visio | Microsoft Docs
description: Aproveite os conhecimentos do Visio da sua organização para criar modelos comuns como um ponto de partida para criar fluxos.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/25/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b22a3b4c3efe294cfd3afa2359c46ee960d1c021
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74370152"
---
# <a name="design-flows-in-microsoft-visio"></a>Criar fluxos no Microsoft Visio
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

O estruturador do Power Automate é uma ferramenta avançada na qual pode configurar todos os detalhes da sua lógica. No entanto, poderá, por vezes, querer apenas esboçar a sua lógica de fluxo antes de começar a criar o fluxo. Para fazer isso, utilize o Microsoft Visio diretamente a partir do Power Automate.

>[!TIP]
> Muitos processos partilham um modelo em comum, mas têm pequenas variações em toda a organização. Pode poupar tempo dentro da sua organização ao utilizar o Visio para criar um modelo de fluxo de trabalho principal que outras pessoas poderão depois ajustar com parâmetros especializados.

## <a name="prerequisites"></a>Pré-requisitos

- Uma conta do Power Automate.
- A aplicação de computador do Microsoft Visio (versão em inglês).
- Conhecimentos na utilização do Microsoft Visio.

## <a name="design-a-workflow-in-visio"></a>Criar um fluxo de trabalho no Visio

1. Inicie sessão no [Power Automate](https://flow.microsoft.com).
1. Selecione **Modelos** no painel esquerdo.

     ![Selecionar modelos no painel esquerdo](./media/visio-flows/templates-from-left-panel.png)

1. Selecione **Visio** na lista.

     ![Filtrar para modelos do Visio](./media/visio-flows/select-visio.png) 

1. Selecione o modelo **Diagrama BPMN de Fluxo Básico** na lista de modelos do **Visio** que é apresentada.

     ![Selecionar um modelo do Visio](./media/visio-flows/visio-templates.png) 

     >[!IMPORTANT]
     >O Visio avisa que os ficheiros da Internet podem danificar o dispositivo. Se confiar, selecione **SIM** na mensagem de aviso.

     ![Nota de aviso sobre ficheiros da Internet](./media/visio-flows/visio-warning.png)

1. O estruturador do Visio é iniciado.

     ![Vista do estruturador do Visio](./media/visio-flows/visio-designer.png)


1. Utilize as formas básicas BPMN para [criar o fluxo de trabalho](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a).

   ![Formas básicas BPMN](./media/visio-flows/bpmn-basic-shapes.png)

## <a name="prepare-to-export-your-workflow-to-power-automate"></a>Preparar para exportar o fluxo de trabalho para o Power Automate

Siga estes passos para preparar o fluxo de trabalho para o exportar para o Power Automate.

1. Selecione o separador **Processo**.
1. Selecione **Preparar para Exportar** no grupo de ícones do **Power Automate**.

   ![Selecionar o ícone Preparar para exportar](./media/visio-flows/prepare-export-icon.png)
   
   O grupo **Preparar para Exportar** é apresentado.

   ![Grupo Preparar para exportar](./media/visio-flows/prepare-export-group.png)

1. No separador **Mapeamento de Fluxos** do grupo **Preparar para Exportar**, mapeie o diagrama BPMN para os controlos do Power Automate. 

1. No separador **Acionadores e Ações** do grupo **Preparar para Exportar**, mapeie o diagrama BPMN para os acionadores e as ações do Power Automate ao selecionar cada forma e, em seguida, ao selecionar um acionador ou uma ação para representar essa forma no Power Automate.

O fluxo de trabalho está pronto para ser exportado quando não existir nenhum problema no controlo **Preparar para Exportar**.

![Não existem problemas](./media/visio-flows/prepare-export-no-issues.png) 

## <a name="export-your-workflow"></a>Exportar o fluxo de trabalho
1. Selecione o botão **Exportar para Fluxo** para exportar o diagrama de fluxo de trabalho para o Power Automate.
1. Dê um nome ao fluxo e, em seguida, selecione o botão **Criar fluxo**.
   
   ![Criar o fluxo](./media/visio-flows/export-create-flow.png)

1. Deverá ver um relatório de êxito semelhante a este.

    ![Êxito](./media/visio-flows/export-create-flow-success.png)

Agora, pode executar ou fazer edições no fluxo a partir do estruturador do Power Automate, à semelhança de qualquer outro fluxo.

>[!TIP]
> Utilize as capacidades de partilha e comentários do Visio para colaborar com vários intervenientes e criar um fluxo de trabalho completo rapidamente.

## <a name="learn-more"></a>Saiba mais

- [Introdução ao Power Automate](getting-started.md) 
- [Criar fluxos de vários passos](multi-step-logic-flow.md)
- [Criar um fluxo com o Microsoft Visio](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a)

     
