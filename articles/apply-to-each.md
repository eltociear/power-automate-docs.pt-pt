---
title: Utilize a ação Aplicar a cada um para fazer um ciclo de uma matriz de itens. | Microsoft Docs
description: Utilize o Power Automate para percorrer uma matriz de itens para verificar várias condições e realizar ações com base nessas condições.
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
ms.date: 05/06/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: fcd99ea786c03eeac6ceabdf9a97886a8bbee022
ms.sourcegitcommit: 8714786a5b632dfd60099871629cf369a31c4125
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346615"
---
# <a name="use-the-apply-to-each-action-in-power-automate-to-process-a-list-of-items-periodically"></a>Utilize a ação aplicar a cada um no Power Automate para processar uma lista de itens periodicamente

Muitos acionadores podem iniciar um fluxo imediatamente com base num evento, como quando um novo e-mail entra na sua caixa de entrada. Estes acionadores são ótimos, mas, por vezes, pretende executar um fluxo que consulte uma origem de dados com base numa agenda predefinida, executando determinadas ações com base nas propriedades dos itens na origem de dados. Para o efeito, o seu fluxo pode ser iniciado com base numa agenda (por exemplo, uma vez por dia) e utilizar uma ação de ciclo, tal como **Aplicar a cada um** para processar uma lista de itens. Por exemplo, pode utilizar a ação **Aplicar a cada um** para atualizar os registos de uma base de dados ou uma lista de itens a partir do Microsoft SharePoint.

Nestas instruções, vamos criar um fluxo que é executado a cada 15 minutos e que faz o seguinte:

1. Obtém as últimas 10 mensagens não lidas na sua Caixa de Entrada do Office 365 Outlook.
2. Verifica cada uma das 10 mensagens para confirmar se alguma tem **participar agora** no assunto.
3. Verifica se o e-mail foi enviado pelo seu chefe ou se está marcado com importância alta.
4. Envia uma notificação push e marca como lidos todos os e-mails que tenham **participar agora** no assunto, sejam eles do seu chefe ou marcados com importância alta.

Este diagrama apresenta os detalhes do fluxo que vamos criar:

![descrição geral do fluxo que está a ser criado](./media/apply-to-each/foreach-flow-visio.png)

## <a name="prerequisites"></a>Pré-requisitos
Seguem-se os requisitos para efetuar com êxito os passos nestas instruções:

* Uma conta registada para utilizar o [Power Automate](https://flow.microsoft.com).
* Uma conta do Office 365 Outlook.
* A aplicação móvel do Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows).
* Ligações ao Office 365 Outlook e ao serviço de notificações push.

## <a name="create-a-flow"></a>Criar um fluxo
1. Iniciar sessão no [Power Automate](https://flow.microsoft.com).
1. Selecione **Os meus fluxos** > **Novo** > **Agendado - do zero**
1. Atribua um nome ao seu fluxo em **Nome do fluxo** no ecrã **Criar um fluxo agendado**. 
1. Defina a agenda para ser executada a cada 15 minutos. 
1. Selecione as execuções da agenda **Criar** 
   
    ![.](./media/apply-to-each/foreach-3.png) 

1. Selecione **+ Novo passo** e, em seguida, digite **outlook** na caixa de pesquisa para localizar todos os conectores e ações relacionados com o Microsoft Outlook.
1. Selecione a ação **Obter e-mails (V3)**:
1. É aberto o cartão **Obter e-mails (V3)**. Configure o cartão **Obter e-mails (V3)** para selecionar os 10 principais e-mails não lidos na pasta Caixa de Entrada. Não inclua os anexos, pois estes não serão utilizados no fluxo:
   
    ![configurar o cartão de e-mail](./media/apply-to-each/foreach-5.png)
   
   > [!NOTE]
   > Até ao momento, criou um fluxo simples que obtém alguns e-mails da sua caixa de entrada. Estes e-mails serão devolvidos numa matriz. A ação **Aplicar a cada um** requer uma matriz, pelo que isto é exatamente aquilo de que necessita.

## <a name="add-actions-and-conditions"></a>Adicionar ações e condições
1. Selecione a ação **Novo passo** > **Incorporado** > **Aplicar a cada**.
1. Insira o token **valor** no campo **Selecionar uma saída dos passos anteriores** no cartão **Aplicar a cada um**. Esta ação obtém o corpo dos e-mails a utilizar na ação **Aplicar a cada um**:
   
    ![adicionar o token corpo](./media/apply-to-each/foreach-7.png)
1. Selecione **Novo passo** > **Controlo** > **Condição**.
1. Configure o cartão **Condição** para procurar no assunto da cada e-mail as palavras "participar agora":
   
   * Insira o token **Assunto** no primeiro campo do cartão **Condição**.
   * Selecione **contém** na lista de operadores.
   * Introduza **participar agora** no terceiro campo.
     
     ![configurar condição](./media/apply-to-each/foreach-subject-condition.png)
1. Selecione **Adicionar uma ação** > **Condição** a partir do ramo **Se sim**. Esta ação abre o cartão **Condição 2**. Configure esse cartão da seguinte forma:
   
   * Insira o token **Importância** no primeiro campo.
   * Selecione **é igual a** na lista de operadores.
   * Introduza **alta** no campo do lado direito.
     
     ![adicionar condição](./media/apply-to-each/foreach-importance-condition.png)
1. Selecione **Adicionar uma ação** na secção **Se sim**.     
   Esta ação abre o cartão **Escolher uma ação**, onde irá definir o que acontece se a condição de pesquisa (o e-mail **participar agora** foi enviado com importância alta) for verdadeira:
1. Procure **notificação** e, em seguida, selecione a ação **Enviar-me uma notificação por telemóvel**:
   
    ![procurar e selecionar notificação](./media/apply-to-each/foreach-10.png)
1. No cartão **Enviar-me uma notificação por telemóvel**, forneça os detalhes da notificação push que será enviada se o assunto de um e-mail contiver "participar agora" e **Importância** for **alta**.
   
    ![configurar notificação](./media/apply-to-each/foreach-11.png)

1. Volte ao cartão **Condição 2**, no ramo **Se não**:
    
    * Selecione **Adicionar uma ação** e, em seguida, escreva **obter gestor** na caixa de pesquisa.
    * Selecione a ação **Obter gestor (V2)** na lista de resultados da pesquisa.
    * Introduza o token **Para** na caixa **Utilizador (UPN)** do cartão **Obter Gestor (V2)**.
      
      ![adicionar e configurar a ação obter gestor](./media/apply-to-each/foreach-get-manager.png)
1. Selecione **Adicionar uma ação** no ramo **Se não**.
1. Selecione **Condição** a partir do cartão **Escolher uma ação**. Esta ação abre o cartão **Condição 3**. Configure o cartão para verificar se o endereço de e-mail do remetente da mensagem de e-mail (o token De) corresponde ao endereço de e-mail do seu chefe (o token E-mail):
    
    * Insira o token **De** na primeira caixa.
    * Selecione **contém** na lista de operadores.
    * Introduza o token **correio** na caixa mais à direita.
      
      ![configurar a condição de pesquisa](./media/apply-to-each/foreach-condition3-card.png)
1. Selecione **Adicionar uma ação** na secção **Se sim** do cartão **Condição 3**.
    
Em seguida, irá definir o que deve acontecer se a condição de pesquisa (o e-mail foi enviado pelo seu chefe) for verdadeira:

1. Procure **notificação** e, em seguida, selecione a ação **Enviar-me uma notificação por telemóvel**:
    
     ![procurar a ação notificação](./media/apply-to-each/foreach-10.png)
1. No cartão **Enviar-me uma notificação por telemóvel 2**, forneça os detalhes da notificação push que será enviada se o e-mail for do seu chefe e, em seguida, selecione **Adicionar uma ação**:
    
     ![configurar o cartão notificação](./media/apply-to-each/foreach-boss-notification.png)
1. Adicione a ação **Marcar como lido ou não lido (V2)**.
1. Adicione o token **ID da mensagem** ao cartão **Marcar como lido ou não lido (V2)**. Poderá ter de selecionar **Ver mais** para encontrar o token **ID da mensagem**. O **ID da Mensagem** é o ID da mensagem que será marcada como lido.
1. Selecione **Ler** a partir da lista **Marcar como** no cartão **Marcar como lido ou não lido (V2)**.
    
     ![configurar ação marcar como lido](./media/apply-to-each/foreach-mark-as-read2.png)
1. Selecione **Guardar** para guardar o fluxo.

## <a name="run-the-flow"></a>Executar o fluxo
1. Envie para si próprio um e-mail de importância alta que inclua **participar agora** no assunto (ou peça a alguém na sua organização para lhe enviar esse e-mail).
1. Confirme que o e-mail está na sua caixa de entrada com o estado não lido.
1. Inicie sessão no Power Automate, selecione **Os meus fluxos**.
   
    É apresentada uma lista dos seus fluxos. 
    
1. Selecione o fluxo que acabou de criar e, em seguida, selecione **Executar**.

   ![executar agora](./media/apply-to-each/run-flow.png)

1. Selecione **Página de Execuções de Fluxo** e, em seguida, selecione a execução de fluxo da qual está interessado em ver os resultados.
   
    ![resultados da execução](./media/apply-to-each/foreach-run-3.png)

## <a name="view-results-of-the-run"></a>Ver os resultados da execução
Agora que executou o fluxo com êxito, deverá receber a notificação push no seu dispositivo móvel.
   
> [!NOTE]
> Se não receber a notificação push, certifique-se de que o seu dispositivo móvel tem uma ligação de dados de trabalho.
 

