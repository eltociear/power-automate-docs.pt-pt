---
title: Utilize a ação aplicar a cada um para percorrer uma matriz de itens. | Microsoft Docs
description: Utilize o Power Automate para executar ciclos através de uma matriz de itens para verificar várias condições e realizar ações com base nessas condições.
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
ms.date: 03/16/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9eb1707da3f0aa365750cbed4e69715ce818aaff
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193778"
---
# <a name="use-the-apply-to-each-action-in-power-automate-to-process-a-list-of-items-periodically"></a>Utilizar a ação aplicar a cada um no Power Automate para processar uma lista de itens periodicamente

Muitos acionadores podem iniciar um fluxo imediatamente com base num evento, como, por exemplo, quando um novo e-mail entra na sua caixa de entrada. Estes acionadores são ótimos, mas, por vezes, quer executar um fluxo que consulte uma origem de dados com base numa agenda predefinida, realizando determinadas ações com base nas propriedades dos itens na origem de dados. Para o efeito, pode iniciar o seu fluxo com base numa agenda (por exemplo, uma vez por dia) e utilizar uma ação de ciclo como **Aplicar a cada um** para processar uma lista de itens. Por exemplo, pode utilizar a ação **Aplicar a cada um** para atualizar os registos de uma base de dados ou uma lista de itens a partir do Microsoft SharePoint.

Nestas instruções, vamos criar um fluxo que é executado a cada 15 minutos e que faz o seguinte:

1. Obtém as últimas 10 mensagens não lidas na sua Caixa de Entrada do Outlook do Office 365.
2. Verifica cada uma das 10 mensagens para confirmar se alguma delas tem **participar agora** no assunto.
3. Verifica se o e-mail foi enviado pelo seu chefe ou se está marcado com importância alta.
4. Envia uma notificação push e marca como lido todos os e-mails que tenham **participar agora** no assunto, sejam estes do seu chefe ou marcados com importância alta.

Este diagrama apresenta os detalhes do fluxo que vamos criar nestas instruções:

![descrição geral do fluxo que está a ser criado](./media/apply-to-each/foreach-flow-visio.png)

## <a name="prerequisites"></a>Pré-requisitos
Eis os requisitos para realizar com êxito os passos nestas instruções:

* Uma conta registada para utilizar o [Power Automate](https://flow.microsoft.com).
* Uma conta do Outlook do Office 365.
* A aplicação móvel do Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows).
* Ligações ao Outlook do Office 365 e o serviço de notificações push.

## <a name="create-a-flow"></a>Criar um fluxo
1. Inicie sessão no [Power Automate](https://flow.microsoft.com):
2. Selecione o separador **Os meus fluxos** e, em seguida, crie um fluxo a partir de um valor em branco:
   
    ![criar a partir de um valor em branco](./media/apply-to-each/foreach-1.png)
3. Introduza "agenda" na caixa de pesquisa para pesquisar todos os serviços e acionadores que estejam relacionados com o agendamento.
4. Selecione o acionador **Agenda - Periodicidade** para indicar que o fluxo será executado com base numa agenda que irá fornecer em seguida:
   
    ![ação de periodicidade da agenda](./media/apply-to-each/foreach-2.png)
5. Defina a agenda para ser executada a cada 15 minutos:
   
    ![execuções da agenda](./media/apply-to-each/foreach-3.png)
6. Selecione **+ Novo passo**, **Adicionar uma ação** e, em seguida, escreva **outlook** na caixa de pesquisa para procurar todas as ações relacionadas com o Microsoft Outlook.
7. Selecione a ação **Outlook do Office 365 - Obter e-mails**:
   
    ![selecionar a ação obter e-mails](./media/apply-to-each/foreach-4.png)
8. Esta ação abre o cartão **Obter e-mails**. Configure o cartão **Obter e-mails** para selecionar os 10 principais e-mails não lidos na pasta Caixa de Entrada. Não inclua os anexos, pois estes não serão utilizados no fluxo:
   
    ![configurar o cartão de e-mail](./media/apply-to-each/foreach-5.png)
   
   > [!NOTE]
   > Até ao momento, criou um fluxo simples que obtém alguns e-mails da sua caixa de entrada. Estes e-mails serão devolvidos numa matriz. A ação **Aplicar a cada um** requer uma matriz, pelo que isto é exatamente aquilo de que necessita.
   > 
   > 

## <a name="add-actions-and-conditions"></a>Adicionar ações e condições
1. Selecione **+ Novo passo**, **Mais** e, em seguida, a ação **Adicionar aplicar a cada um**:
   
    ![selecionar aplicar a cada um](./media/apply-to-each/foreach-6.png)
2. Insira o token **Corpo** na caixa **Selecionar uma saída dos passos anteriores** no cartão **Aplicar a cada um**. Esta ação obtém o corpo dos e-mails a utilizar na ação **Aplicar a cada um**:
   
    ![adicionar o token corpo](./media/apply-to-each/foreach-7.png)
3. Selecione **Adicionar uma condição**:
   
    ![adicionar condição](./media/apply-to-each/foreach-8.png)
4. Configure o cartão **Condição** para procurar no assunto da cada e-mail as palavras "participar agora":
   
   * Insira o token **Assunto** na caixa **Nome do Objeto**.
   * Selecione **contém** na lista **Relação**.
   * Introduza **participar agora** na caixa **Valor**.
     
     ![configurar condição](./media/apply-to-each/foreach-subject-condition.png)
5. Selecione **Mais** e, em seguida, selecione **Adicionar uma condição** a partir do ramo **SE SIM, NÃO FAZER NADA**. Esta ação abre o cartão **Condição 2**. Configure esse cartão da seguinte forma:
   
   * Insira o token **Importância** na caixa **Nome do Objeto**.
   * Selecione **é igual a** na lista **Relação**.
   * Introduza **Alta** na caixa **Valor**.
     
     ![adicionar condição](./media/apply-to-each/foreach-importance-condition.png)
6. Selecione **Adicionar uma ação** na secção **SE SIM, NÃO FAZER NADA**. Esta ação abre o cartão **Escolher uma ação**, onde irá definir o que deve acontecer se a condição de pesquisa (o e-mail **participar agora** foi enviado com importância alta) for verdadeira:
   
    ![adicionar ação](./media/apply-to-each/foreach-9.png)
7. Procure **Notificação** e, em seguida, selecione a ação **Notificações - Enviar-me uma notificação por telemóvel**:
   
    ![procurar e selecionar notificação](./media/apply-to-each/foreach-10.png)
8. No cartão **Enviar-me uma notificação por telemóvel**, forneça os detalhes da notificação push que será enviada se o assunto de um e-mail contiver "participar agora" e, em seguida, selecione **Adicionar uma ação**:
   
    ![configurar notificação](./media/apply-to-each/foreach-11.png)
9. Introduza **lido** como termo de pesquisa e, em seguida, selecione a ação **Outlook do Office 365 - Marcar como lido**. Esta ação marca todos os e-mails como lidos após o envio da notificação push:
   
    ![adicionar ação marcar como lido](./media/apply-to-each/foreach-12.png)
10. Adicione o token **ID da mensagem** na caixa **ID da mensagem** do cartão **Marcar como lido**. Poderá ter de selecionar **Ver mais** para encontrar o token **ID da mensagem**. Isto indica o ID da mensagem que será marcada como lida:
    
     ![adicionar id da mensagem](./media/apply-to-each/foreach-13.png)
11. Volte ao cartão **Condição 2** e, no ramo, **SE NÃO, NÃO FAZER NADA**:
    
    * Selecione **Adicionar uma ação** e, em seguida, escreva **obter gestor** na caixa de pesquisa.
    * Selecione a ação **Utilizadores do Office 365 - Obter gestor** na lista de resultados da pesquisa.
    * Introduza o seu endereço de e-mail *completo* na caixa **Utilizador** do cartão **Obter Gestor**.
      
      ![adicionar e configurar a ação obter gestor](./media/apply-to-each/foreach-get-manager.png)
12. Selecione **Mais** e, em seguida, selecione **Adicionar uma condição** a partir do ramo **SE NÃO**. Esta ação abre o cartão **Condição 3**. Configure o cartão para verificar se o endereço de e-mail do remetente da mensagem de e-mail (o token De) corresponde ao endereço de e-mail do seu chefe (o token E-mail):
    
    * Insira o token **De** na caixa **Nome do Objeto**.
    * Selecione **contém** na lista **Relação**.
    * Introduza o token **E-mail** na caixa **Valor**.
      
      ![configurar a condição de pesquisa](./media/apply-to-each/foreach-condition3-card.png)
13. Selecione **Adicionar uma ação** na secção **SE SIM, NÃO FAZER NADA** do cartão **Condição 3**. Esta ação abre o cartão **SE SIM**, onde irá definir o que deve acontecer se a condição de pesquisa (o e-mail foi enviado pelo seu chefe) for verdadeira:
    
     ![configurar condição](./media/apply-to-each/foreah-condition3-add-action.png)
14. Procure **Notificação** e, em seguida, selecione a ação **Notificações - Enviar-me uma notificação por telemóvel**:
    
     ![procurar a ação notificação](./media/apply-to-each/foreach-10.png)
15. No cartão **Enviar-me uma notificação por telemóvel 2**, forneça os detalhes da notificação push que será enviada se o e-mail for do seu chefe e, em seguida, selecione **Adicionar uma ação**:
    
     ![configurar o cartão notificação](./media/apply-to-each/foreach-boss-notification.png)
16. Adicione a ação **Outlook do Office 365 - Marcar como lido**. Esta ação marca todos os e-mails como lidos após o envio da notificação push:
    
     ![adicionar ação marcar como lido](./media/apply-to-each/foreach-12.png)
17. Adicione o token **ID da mensagem** ao cartão **Marcar como lido 2**. Poderá ter de selecionar **Ver mais** para encontrar o token **ID da mensagem**. Isto indica o ID da mensagem que será marcada como lida:
    
     ![configurar ação marcar como lido](./media/apply-to-each/foreach-mark-as-read2.png)
18. Dê um nome ao seu fluxo e, em seguida, crie-o:
    
     ![dar um nome ao fluxo e guardá-lo](./media/apply-to-each/foreach-14.png)

Se tiver seguido todos os passos, o fluxo deverá ter um aspeto semelhante a este diagrama:

![descrição geral do fluxo criado](./media/apply-to-each/foreach-flow-finished.png)

## <a name="run-the-flow"></a>Executar o fluxo
1. Envie para si próprio um e-mail de importância alta que inclua **participar agora** no assunto (ou peça a alguém na sua organização para lhe enviar esse e-mail).
2. Confirme que o e-mail está na sua caixa de entrada com o estado não lido.
3. Inicie sessão no Power Automate, selecione **Os meus fluxos** e, em seguida, **Executar agora**:
   
    ![executar agora](./media/apply-to-each/foreach-run-1.png)
4. Selecione **Executar fluxo** para confirmar que quer realmente executar o fluxo:
   
    ![confirmar execução](./media/apply-to-each/foreach-run-2.png)
5. Após alguns instantes, deverá ver os resultados da execução realizada com êxito:
   
    ![resultados da execução](./media/apply-to-each/foreach-run-3.png)

## <a name="view-results-of-the-run"></a>Ver os resultados da execução
Agora que executou o fluxo com êxito, deverá receber a notificação push no seu dispositivo móvel.

1. Abra a aplicação do Power Automate no dispositivo móvel e selecione o separador **Atividade**. Verá a notificação push acerca da reunião:
   
    ![selecionar o separador atividade](./media/apply-to-each/foreach-notification-1.png)
2. Para ver o conteúdo completo da notificação, poderá ter de selecionar a notificação. Verá a notificação completa, semelhante a esta:
   
    ![detalhes da notificação](./media/apply-to-each/foreach-notification-2.png)
   
   > [!NOTE]
   > Se não receber a notificação push, certifique-se de que o seu dispositivo móvel tem uma ligação de dados de trabalho.
   > 
   > 

