---
title: Saiba como automatizar e executar tarefas repetitivas com fluxos de botões | Microsoft Docs
description: Introdução aos fluxos de botões.
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
ms.date: 01/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 136bb90c47a1aeea2f11ef45e35a4957506ad488
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74363919"
---
# <a name="introducing-button-flows"></a>Introdução aos fluxos de botões
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-are-button-flows"></a>O que são fluxos de botões?
Existem muitas tarefas repetitivas que gostaríamos de executar apenas com um toque num botão. Por exemplo, pode ter de enviar um e-mail rapidamente para os elementos da sua equipa para os lembrar de que devem associar-se à equipa de sincronização diária ou pode querer iniciar uma nova compilação do Visual Studio Online da sua base de código após ter sido notificado de que não existem mais registos de entrada planeados para o dia. Os fluxos de botões permitem-lhe realizar estas e muitas outras tarefas simplesmente ao tocar num botão no seu dispositivo móvel.

**Nota**: pode criar fluxos de botões no dispositivo móvel ou no portal do Flow.  
  ![Imagem de descrição geral](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>Porquê criar botões?
Crie botões para executar facilmente tarefas repetitivas em qualquer local e em qualquer altura através do dispositivo móvel. Executar botões poupa tempo e, uma vez que as tarefas executadas são automatizadas, haverá menos erros do que se o fizesse manualmente.  

## <a name="create-a-button"></a>Criar um botão
### <a name="prerequisites"></a>Pré-requisitos
* Aceda ao Flow. O administrador pode conceder esse acesso.
* Uma conta com permissões para utilizar os conectores para criar o botão. Por exemplo, precisa de uma conta do Dropbox para criar um botão que aceda ao Dropbox.

### <a name="from-the-portal"></a>No portal
Nesta demonstração, vamos criar um botão que inicia uma compilação do Visual Studio Online (VSO) e envia notificações para o informar de quando é iniciada a compilação:  

1. Selecione a lista pendente **A mostrar** e escolha a categoria **Botão**. Este procedimento filtra a lista de modelos apenas para os que pode utilizar em fluxos de botões.  
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-1.png)   
2. Selecione o modelo **Acionar uma nova compilação no VSO** na lista de modelos.  
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-2.png)  
3. Selecione o botão **Utilizar este modelo** na página **Acionar uma nova compilação no VSO**.   
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-3.png)  
4. Se não tiver iniciado sessão, ser-lhe-á pedido que o faça neste momento:  
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-4.png)  
5. Depois de ter iniciado sessão no Flow, ser-lhe-á pedido que inicie sessão nos conectores utilizados no modelo selecionado. Neste exemplo, no passo 2 acima, selecionamos o modelo **Acionar uma nova compilação no VSO**, pelo que temos de iniciar sessão no VSO (e em quaisquer outros conectores com os quais está a trabalhar), se ainda não tiver iniciado sessão:  
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. Selecione o botão **Aceito** para autorizar que o Flow aceda à sua conta do VSO.  
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-5.png)   
   **Nota**: terá de autorizar cada conector da mesma forma. O estruturador deverá ser apresentado desta forma quando estiver pronto para avançar para o passo seguinte. Selecione o botão **Continuar** para avançar:  
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-6.png)   
7. Agora, está pronto para configurar as propriedades da compilação que pretende iniciar:    
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-7.png)  
8. Selecione ou introduza o **Nome da conta**, **Nome do projeto**, **Criar ID de definição**, **Ramo de origem** e, opcionalmente, **Parâmetros**, no cartão **Colocar uma nova compilação na fila de espera**:    
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-8.png)  
9. Em seguida, configure as propriedades da notificação push no cartão **Enviar uma notificação push**. Por predefinição, esta notificação push está configurada para enviar uma ligação HTML para uma página Web que apresenta o estado da compilação:  
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-9.png)  
10. Selecione o botão **Criar fluxo** para guardar o fluxo de botão: ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-10.png)  
11. Deverá ver esta mensagem de êxito dentro de momentos:  
    ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-11.png)  

Parabéns, criou um fluxo de botão! Agora, pode executar este fluxo de botão em qualquer altura e qualquer lugar, no separador **Botões** na aplicação Flow. Basta premir o “botão” para ser executado! A aplicação móvel do Power Automate está disponível para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows).

### <a name="from-your-mobile-device"></a>No dispositivo móvel
**Nota**: embora esta demonstração apresente ecrãs de um dispositivo Android, os ecrãs e a experiência num dispositivo iOS são semelhantes.

Na aplicação Flow:

1. Selecione o separador **Procurar** e desloque-se até à categoria **Botão**.  
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. Selecione a ligação **Ver tudo**. Serão apresentados todos os modelos de botão prontos.     
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. Selecione o modelo **Enviar um e-mail para notificar a equipa para participar numa reunião**    
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. Selecione a ligação **UTILIZAR ESTE MODELO** na parte inferior da página.    
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. Terá de iniciar sessão em todos os serviços que este modelo utiliza:    
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. Selecione a ligação **Seguinte** depois de ter iniciado sessão em todos os serviços.      
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. Selecione a ligação **Criar**. Aqui, também pode rever o fluxo e fazer as alterações necessárias para personalizar o e-mail, por exemplo.        
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. Após alguns instantes, é criado o fluxo de botão. Selecione **VER O MEU FLUXO**:   
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. Veja todos os seus fluxos no separador **Os meus fluxos**.  
   ![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

Parabéns, criou um fluxo de botão! Agora, pode executar este fluxo de botão em qualquer altura e qualquer lugar, no separador **Botões** na aplicação Flow. Basta premir o “botão” para ser executado! Atualmente, a aplicação Flow está disponível nos dispositivos móveis Android e iOS.  

![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-a-button-flow"></a>Acionar um fluxo de botão
Agora que criou um fluxo de botão, está na altura de o executar. Uma vez que só pode executar fluxos de botões na aplicação Flow, confirme se instalou o Flow no dispositivo móvel Android ou iOS.  

1. Agora, inicie a aplicação Flow, toque no separador **Botões**, localizado na parte inferior da página, e toque no *botão* que representa o fluxo de botão que pretende acionar:  
   ![Imagem de descrição geral](./media/introduction-to-button-flows/trigger-button-1.png)   
2. Veja o progresso enquanto executa o fluxo:  
   ![Imagem de descrição geral](./media/introduction-to-button-flows/trigger-button-2.png)   
3. Por fim, a página é atualizada, o que indica que o fluxo de botão foi concluído:  
   ![Imagem de descrição geral](./media/introduction-to-button-flows/trigger-button-3.png)   

Basta realizar estes passos para executar um fluxo. 

Agora, deverá receber a notificação push, que indica que o e-mail foi enviado.  

## <a name="monitor-your-button-flow-runs"></a>Monitorizar a execução do fluxo de botão
Pode monitorizar os fluxos de botões no separador **Atividade** da aplicação Flow:   
![Imagem de descrição geral](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

**Nota**: toque numa atividade para explorar os resultados da execução para saber mais sobre a mesma.  

![Imagem de descrição geral](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-button-flows"></a>Gerir fluxos de botões
Tem controlo total sobre os fluxos de botões para que possa ativar/desativar, editar ou eliminar um botão em qualquer altura em qualquer lugar. Na aplicação móvel ou no portal do fluxo, selecione **Os meus fluxos** para começar a gerir os fluxos.    

No separador **Os meus fluxos** da aplicação Flow:

1. Selecione o fluxo que pretende gerir:    
   ![Imagem de descrição geral](./media/introduction-to-button-flows/trigger-button-4.png)   
2. Pode tocar em qualquer uma destas opções, com base no que pretende realizar:    
   ![Imagem de descrição geral](./media/introduction-to-button-flows/manage-flow-1.png)  
3. Toque em **Eliminar fluxo** para eliminar um fluxo.  

**Nota**: todo o histórico da execução é eliminado quando elimina um fluxo:   
![Imagem de descrição geral](./media/introduction-to-button-flows/manage-flow-2.png)   

1. Toque em **Atualizar** depois de terminar de editar um fluxo de botão para guardar as alterações:   
   ![Imagem de descrição geral](./media/introduction-to-button-flows/manage-flow-3.png)   
2. Toque em **Histórico da execução** para ver os resultados de todas as execuções de um fluxo de botão específico:    
   ![Imagem de descrição geral](./media/introduction-to-button-flows/manage-flow-4.png)  
3. Se desativar um fluxo, deixará de estar disponível no separador **Botões**:    
   ![Imagem de descrição geral](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>Próximos passos
* [Partilhe fluxos de botões](share-buttons.md).
* Aprenda a utilizar [tokens de acionador de botão](introduction-to-button-trigger-tokens.md) para enviar dados em tempo real quando os fluxos de botão são executados.
* Instale a aplicação móvel do Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows).

