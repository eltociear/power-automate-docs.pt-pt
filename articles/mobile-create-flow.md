---
title: Criar um fluxo a partir do telemóvel | Microsoft Docs
description: Crie um fluxo a partir de um modelo que envia, por exemplo, uma notificação push quando receber correio de um endereço que especificou
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/18/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 393ae5f6a86363610c26aea78a04748f34dc4f97
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193617"
---
# <a name="create-a-flow-from-your-phone-by-using-power-automate"></a>Criar um fluxo a partir do telemóvel com o Power Automate

Crie um fluxo a partir do telemóvel com um modelo, que pode localizar ao pesquisar numa lista de serviços, procurar categorias ou especificar palavras-chave. Siga os passos deste tópico para criar um fluxo que envia uma notificação push para o telemóvel quando enviar correio a partir do gestor.

Se não estiver familiarizado com o Power Automate, [veja uma descrição geral](getting-started.md).

## <a name="prerequisites"></a>Pré-requisitos
* Ter uma [conta do Power Automate](sign-up-sign-in.md).
* A aplicação móvel do Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows) instalada num [dispositivo suportado](getting-started.md#use-the-mobile-app). Neste tópico, os gráficos refletem a versão da aplicação do iPhone, mas a interface de um Android ou Windows Phone é semelhante.
* Para utilizar o modelo demonstrado neste tópico, também precisará de:
  
  * Credenciais do Office 365.
  * Notificações push ativadas no telemóvel.

## <a name="find-a-template"></a>Localizar um modelo
1. Abra a aplicação móvel e, em seguida, toque em **Procurar** na parte inferior do ecrã.
   
    ![Ícone Procurar](./media/mobile-create-flow/browse-icon.png)
   
    Pode localizar um modelo de qualquer uma das seguintes formas:
   
   * Especifique uma palavra-chave na caixa de pesquisa na parte superior do ecrã.
   * Toque numa opção da lista de serviços.
   * Desloque para baixo para visualizar uma variedade de categorias e, em seguida, toque num modelo de qualquer categoria.
     
       ![Procurar separador](./media/mobile-create-flow/browse-tab.png)
     
     Para este tutorial, irá abrir o modelo que envia uma notificação push quando tiver correio do gestor.
2. Na lista de serviços, toque em **Ver todos**.
   
    ![Mostrar lista de serviços](./media/mobile-create-flow/list-services.png)
3. Toque no ícone para **Notificação push**.
   
    ![Notificações push](./media/mobile-create-flow/push-notifications.png)
4. Na barra de pesquisa, escreva **e-mail** e, em seguida, toque no modelo para enviar uma notificação push quando receber uma mensagem do gestor.
   
    ![Escolher modelo](./media/mobile-create-flow/choose-template.png)
5. No ecrã que fornece detalhes sobre o modelo que selecionou, toque em **Utilizar este modelo**.
   
    ![Confirmar modelo](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>Concluir fluxo
1. Se lhe for pedido, toque em **Iniciar sessão**, e forneça as credenciais para o Outlook do Office 365, Utilizadores do Office 365 ou ambas.
   
    ![Iniciar sessão no Office 365](./media/mobile-create-flow/office-signin.png)
   
    Quando criar outros fluxos pode utilizar as mesmas ligações.
2. No canto superior direito, toque em **Seguinte**.
   
    ![Toque em Seguinte](./media/mobile-create-flow/next.png)
   
    O ecrã seguinte mostra o evento acionador e todas as ações resultantes.
   
    ![Evento acionador e ações](./media/mobile-create-flow/flow-structure.png)
   
    Para este modelo, a nova mensagem de correio aciona o fluxo, que obtém as informações (incluindo o endereço do gestor) e envia uma notificação push quando tiver correio desse endereço. Alguns modelos precisam de alguma personalização para funcionarem corretamente, mas este não é o caso.
3. (opcional) Perto da parte superior do ecrã, escreva um nome diferente para o fluxo.
   
    ![Mudar o nome do fluxo](./media/mobile-create-flow/rename-flow.png)
4. No canto superior direito, toque em **Criar**.
   
    ![Criar fluxo](./media/mobile-create-flow/create-flow.png)
   
    O fluxo é criado e irá verificar a existência de correio do gestor até colocar em pausa ou eliminar o fluxo.

## <a name="next-steps"></a>Próximos passos
* [Monitorizar a atividade do fluxo](mobile-monitor-activity.md).
* [Gerir as seus fluxos](mobile-manage-flows.md).

