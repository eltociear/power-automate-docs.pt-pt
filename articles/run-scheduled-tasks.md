---
title: Executar fluxos com base numa agenda | Microsoft Docs
description: Automatize tarefas periódicas executando fluxos com base numa agenda, tal como diariamente ou de hora a hora.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/14/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4970554dee8e031a746cf604e2a628f41056b46c
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193686"
---
# <a name="run-flows-on-a-schedule"></a>Executar fluxos com base numa agenda

Crie um fluxo que realize uma ou mais tarefas (como enviar um relatório num e-mail):

* uma vez por dia, por hora ou por minuto
* numa data que especificar
* após um número de dias, horas ou minutos que especificar

## <a name="create-a-recurring-flow"></a>Criar um fluxo periódico
1. Inicie sessão no [Power Automate](https://flow.microsoft.com) e selecione **Os meus fluxos** na barra de navegação superior.
   
    ![opção Os meus fluxos](./media/run-scheduled-tasks/create-flow.png)
2. Selecione **Criar do zero**.
   
    ![Criar um fluxo a partir do valor em branco](./media/run-scheduled-tasks/create-from-blank.png)
3. Na caixa **Procurar todos os conectores e acionadores**, escreva **Periodicidade** e, em seguida, selecione **Agenda - Periodicidade**.
   
    ![Localizar acionador de periodicidade](./media/run-scheduled-tasks/select-recurrence.png)
4. Na caixa de diálogo **Periodicidade**, especifique a frequência com que pretende que o fluxo seja executado.
   
    Por exemplo, especifique **2** em **Intervalo** e **Semana** em **Frequência** se quiser que o fluxo seja executado de duas em duas semanas.
   
    ![Especificar periodicidade](./media/run-scheduled-tasks/specify-recurrence.png)

## <a name="specify-advanced-options"></a>Especificar opções avançadas
1. Siga os passos na secção anterior e, em seguida, selecione **Mostrar opções avançadas**.
   
    **Nota**: estas opções mudam com base nos valores para os quais **Intervalo** e **Frequência** estão definidos. Se o seu ecrã não corresponder ao gráfico abaixo, certifique-se de que **Intervalo** e **Frequência** estão definidos para os mesmos valores que o gráfico apresenta.
2. Selecione um **Fuso horário** para especificar se a **Hora de início** reflete um fuso horário local, Hora Universal Coordenada (UTC), etc.
3. Especifique uma **Hora de início** neste formato:
   <br>AAAA-MM-DDTHH:MM:SSZ
4. Se tiver especificado **Dia** em **Frequência**, especifique a hora do dia em que o fluxo deve ser executado.
5. Se tiver especificado **Semana** em **Frequência**, especifique o dia ou dias da semana e a hora ou horas do dia em que o fluxo deve ser executado.
   
    Por exemplo, configure as opções conforme apresentado para iniciar um fluxo não antes do meio-dia (Hora do Pacífico) na segunda-feira, 1 de Janeiro de 2018 e executá-lo de duas em duas semanas às terças-feiras às 17:30 (Hora do Pacífico).
   
    ![Especificar opções avançadas](./media/run-scheduled-tasks/advanced-options.png)
6. Adicione a ação ou ações que pretende que o fluxo efetue, como descreve [Criar um fluxo do zero](get-started-logic-flow.md).

## <a name="delay-a-flow"></a>Atrasar um fluxo
1. Inicie sessão no [Power Automate](https://flow.microsoft.com) e selecione **Os meus fluxos** na barra de navegação superior.
   
    ![Criar um fluxo a partir do valor em branco](./media/run-scheduled-tasks/create-flow.png)
2. Selecione **Criar do zero**.
   
    ![Criar um fluxo a partir do valor em branco](./media/run-scheduled-tasks/create-from-blank.png)
3. Especifique um evento como descreve [Criar um fluxo do zero](get-started-logic-flow.md).
4. Selecione **Novo passo** e, em seguida, selecione **Adicionar uma ação**.
   
    ![Opção para adicionar uma ação a um fluxo](./media/run-scheduled-tasks/add-action.png)
5. Na lista de ações, efetue um dos seguintes procedimentos:
   
   * Selecione **Atraso**, especifique uma **Contagem** e especifique uma **Unidade** de tempo, como segundo, minuto ou hora.
   * Selecione **Atraso até** e, em seguida, especifique uma data neste formato.<br>AAAA-MM-DDTHH:MM:SSZ
     
     ![Adicionar um atraso](./media/run-scheduled-tasks/add-delay.png)
     ![Especificar o atraso em unidades de tempo](./media/run-scheduled-tasks/delay.png)
     ![Especificar atraso até](./media/run-scheduled-tasks/delay-until.png)

## <a name="learn-more"></a>Saiba mais

Saiba mais sobre as [opções avançadas](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) e como as configurar.

