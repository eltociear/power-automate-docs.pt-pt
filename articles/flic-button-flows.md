---
title: Iniciar fluxos com botões do Flic | Microsoft Docs
description: Inicie facilmente fluxos de botões com botões físicos a partir do Flic, da Shortcut Labs.
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
ms.date: 05/19/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 65d9a93215030905f41e082d38789592a4267404
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79194353"
---
# <a name="run-your-flows-by-pressing-a-flic-smart-button-preview"></a>Executar fluxos com botões inteligentes do Flic (Pré-visualização)

Acione os seus fluxos com botões físicos, conhecidos como Flic, da Shortcut Labs. Por exemplo, prima um Flic para controlar o seu horário de trabalho, bloquear o calendário, fazer a contagem de pessoas que visitaram um evento ou guardar localizações geográficas.

> [!IMPORTANT]
> Configure todas as propriedades do Flic com a aplicação móvel do Flic para [Android](https://play.google.com/store/apps/details?id=io.flic.app) ou [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) antes de criar o fluxo.
> 
> 

## <a name="prerequisites"></a>Pré-requisitos
Para utilizar Flics com o Power Automate, precisa de ter:

* Acesso ao [Power Automate](https://flow.microsoft.com).
* Transferido a aplicação móvel do Flic para [Android](https://play.google.com/store/apps/details?id=io.flic.app) ou [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) e utilizá-la para emparelhar um ou mais Flics.

## <a name="configure-flic-properties"></a>Configurar as propriedades do Flic
Utilize a aplicação móvel do Flic para programar os eventos do Flic. Os eventos são:

* clique (premir uma vez rapidamente)
* duplo clique (premir duas vezes rapidamente)
* manter premido (premir sem soltar)

Esta captura de ecrã contém uma amostra de qual poderá ser o aspeto do processo de configuração do Flic:

![configurar Flics](./media/flic-button-flows/configure-flic-actions.png)

Depois de ligar um evento do Flic ao Power Automate, pode selecionar esse Flic como acionador dos fluxos. Vai selecionar acionadores mais adiante nestas instruções.

## <a name="create-a-flow-thats-triggered-by-a-flic"></a>Criar um fluxo acionado por um Flic
Nestas instruções, utilizamos um Flic para executar um fluxo que regista o tempo que um consultor despende com cada cliente. O consultor prime o Flic uma vez quando chega ao local e, no momento em que deixa o cliente, prime-o novamente. Sempre que o Flic é premido, é executado o fluxo ao qual está ligado. O fluxo guarda a hora atual no Google Sheets e, em seguida, envia uma notificação por e-mail. O e-mail contém detalhes sobre a execução do fluxo.

Nota: garanta que utilizou a aplicação móvel Flic para emparelhar e configure, pelo menos, uma ação de **clique** para acionar o Power Automate. Nesta captura de ecrã, configurei a ação de **clique** para acionar o Power Automate. Mais adiante nestas instruções, vamos configurar o nosso fluxo para ser acionado quando o Flic é premido uma vez (clicado).

   ![configuração do flic](./media/flic-button-flows/flic-configured-for-flow.png)

Vamos começar a criar o nosso fluxo.

### <a name="start-with-a-template"></a>Começar com um modelo
1. Inicie sessão no [Power Automate](https://flow.microsoft.com).
   
    ![iniciar sessão](./media/flic-button-flows/sign-into-flow.png)
2. Introduza **flic** na caixa de pesquisa e, em seguida, selecione o ícone de pesquisa.
   
    ![pesquisar flic](./media/flic-button-flows/search-flic.png)
3. Selecione o modelo **Controlar o seu horário de trabalho com o botão inteligente do Flic**.
   
    ![selecionar modelo](./media/flic-button-flows/flic-templates.png)

### <a name="create-a-spreadsheet-in-google-sheets"></a>Criar uma folha de cálculo no Google Sheets
1. Consulte os detalhes do modelo e tenha em atenção que este modelo requer uma folha de cálculo no Google Sheets.
   
   ![consultar detalhes do modelo](./media/flic-button-flows/flic-template-details.png)
2. No Google Sheets, crie uma folha de cálculo que contenha uma folha com colunas denominadas **ClickType** e **TimeStamp**.
   
      Sugestão: para dar nomes a colunas no Google Sheets, introduza o nome da coluna na parte superior da coluna. Portanto, a sua folha deverá aparecer como nesta captura de ecrã:
   
   ![Google Sheet](./media/flic-button-flows/flic-google-sheet.png)
   
   Nota: vai utilizar esta folha mais adiante nestas instruções.

### <a name="add-the-flic-trigger-to-your-flow"></a>Adicionar o acionador do Flic ao fluxo
1. Inicie sessão nos serviços do modelo e, em seguida, selecione **Continuar**.
   
     A opção **Continuar** será ativada depois de iniciar sessão em todos os serviços necessários para o modelo.
   
    ![fornecer credenciais](./media/flic-button-flows/flic-template-services-sign-in.png)
2. Introduza **flic** na caixa de pesquisa e, em seguida, selecione o acionador **Flic - Quando é premido um Flic**.
   
    ![pesquisar o acionador do flic](./media/flic-button-flows/flic-search-trigger.png)
3. Selecione o Flic que quer utilizar na lista **Botão do Flic**, no cartão **Flic - Quando é premido um Flic**.
4. Selecione **clique** na lista **Eventos** para indicar que quer acionar o fluxo quando o Flic é premido uma vez.
   
    ![selecionar ação do flic](./media/flic-button-flows/select-flic.png)
   
   Opcionalmente, pode selecionar **qualquer um** para indicar que cada evento do Flic (clique, duplo clique ou manter premido) aciona o fluxo.
   
   **Duplo clique** indica que o fluxo é acionado quando o Flic é premido duas vezes rapidamente. **Manter premido** indica que premir o Flic sem soltar aciona o fluxo.
   
   Pode criar outros fluxos sem dificuldade e utilizar os outros eventos na lista **Eventos** para os acionar. Por exemplo, pode utilizar o evento **duplo clique** para registar a hora em que deixa um cliente.

### <a name="configure-the-sheet"></a>Configurar a folha
   No cartão **Inserir linha**:

1. Selecione a folha de cálculo que criou anteriormente a partir da lista **Ficheiro**.
2. Selecione a folha na lista **Folha de cálculo**.
   
   Nota: aparecem duas caixas adicionais no cartão **Inserir linha** depois de selecionar a folha. Estas caixas representam as duas colunas na folha que criou anteriormente.
3. Selecione a caixa **ClickType** e, em seguida, selecione o token **Tipo de clique**.
4. Selecione a caixa **Timestamp** e, em seguida, selecione o token **Hora do clique**.
   
    ![configurar dados do Google Sheets](./media/flic-button-flows/flick-insert-row-card.png)

### <a name="confirm-the-email-settings-are-correct"></a>Confirme que as definições de e-mail estão corretas
1. Confirme que o cartão **Enviar-me uma notificação por e-mail** tem o aspeto apresentado nesta captura de ecrã.
   
    ![confirmar notificação por e-mail](./media/flic-button-flows/email-settings.png)

### <a name="save-your-flow-and-test-it"></a>Guardar o fluxo e testá-lo
1. Dê um nome ao seu fluxo e guarde-o.
   
    ![guardar o fluxo](./media/flic-button-flows/save.png)

Se seguiu as instruções até agora, premir o Flic uma vez aciona o fluxo. O fluxo regista o tipo de clique e a hora atual na folha e, em seguida, envia-lhe um e-mail.

1. Prima o Flic uma vez.
2. Abra a sua folha de cálculo no Google Sheets. Deverá ver as colunas **ClickType** e **Timestamp** preenchidas com o “clique” e a hora, respetivamente.
   
    ![ver resultados da execução](./media/flic-button-flows/flic-google-sheet-after-run.png)
3. Também pode ver os resultados da execução no site do Power Automate ou da aplicação móvel do Power Automate. Eis uma captura de ecrã da minha execução de teste.
   
    ![guardar o fluxo](./media/flic-button-flows/flic-test-run-results-portal.png)
4. Eis o aspeto do corpo do e-mail de notificação que recebi da execução do fluxo.
   
    ![guardar o fluxo](./media/flic-button-flows/flic-email-body.png)

Para obter créditos adicionais, considere expandir o fluxo para registar automaticamente a sua localização (latitude e longitude) quando o Flic é premido.

## <a name="more-information"></a>Mais informações
* [Partilhe fluxos de botões](share-buttons.md).
* Saiba como utilizar [tokens de acionador de botão](introduction-to-button-trigger-tokens.md) para enviar dados atuais quando os seus fluxos de botões são executados.
* Instale a aplicação móvel do Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows)

