---
title: Saiba como automatizar e executar tarefas repetitivas com fluxos instantâneos | Microsoft Docs
description: Introdução aos fluxos instantâneos.
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
ms.date: 03/17/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: de691667b2c3b50d2bcbddf1684a0b1ed4608294
ms.sourcegitcommit: d6c12fe9b38201519003fdf7754a5404eb4efea5
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/19/2020
ms.locfileid: "79542543"
---
# <a name="introducing-instant-flows"></a>Introdução aos fluxos instantâneos

## <a name="what-are-instant-flows"></a>O que são fluxos instantâneos?
Existem muitas tarefas repetitivas que gostaríamos de executar apenas com um toque num botão. Por exemplo, pode ter de enviar um e-mail rapidamente para os elementos da sua equipa para os lembrar de que devem associar-se à equipa de sincronização diária ou pode querer iniciar uma nova compilação do Visual Studio Online da sua base de código após ter sido notificado de que não existem mais registos de entrada planeados para o dia. Os fluxos instantâneos permitem-lhe realizar estas e muitas outras tarefas simplesmente ao tocar num botão no seu dispositivo móvel.

**Nota**: pode criar fluxos instantâneos no seu dispositivo móvel ou no Power Automate.  
  ![Imagem de descrição geral](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>Porquê criar botões?
Crie botões para executar facilmente tarefas repetitivas em qualquer local e em qualquer altura através do dispositivo móvel. Executar botões poupa tempo e, uma vez que as tarefas executadas são automatizadas, haverá menos erros do que se o fizesse manualmente.  

## <a name="create-a-button"></a>Criar um botão
### <a name="prerequisites"></a>Pré-requisitos
* Aceda ao Flow. O administrador pode conceder esse acesso.
* Uma conta com permissões para utilizar os conectores para criar o botão. Por exemplo, precisa de uma conta do Dropbox para criar um botão que aceda ao Dropbox.

### <a name="from-the-portal"></a>No portal
Nesta demonstração, vamos criar um botão que inicia uma compilação do Visual Studio Online (VSO) e envia notificações para o informar de quando é iniciada a compilação:  

1. Selecione a lista pendente **A mostrar** e escolha a categoria **Botão**. Este procedimento filtra a lista de modelos apenas para os que pode utilizar em fluxos instantâneos.  
   ![Imagem a mostrar categorias](./media/introduction-to-button-flows/create-button-1.png)   
2. Selecione o modelo **Acionar uma nova compilação no VSO** na lista de modelos.  
   ![Imagem a mostrar modelos ](./media/introduction-to-button-flows/create-button-2.png)  
3. Selecione o botão **Utilizar este modelo** na página **Acionar uma nova compilação no VSO**.   
   ![Imagem a mostrar o modelo a utilizar ](./media/introduction-to-button-flows/create-button-3.png)  
4. Se não tiver iniciado sessão, ser-lhe-á pedido que o faça neste momento:  
   ![Imagem a mostrar opções de início de sessão](./media/introduction-to-button-flows/create-button-4.png)  
5. Depois de ter iniciado sessão no Flow, ser-lhe-á pedido que inicie sessão nos conectores utilizados no modelo selecionado. Neste exemplo, no passo 2 acima, selecionamos o modelo **Acionar uma nova compilação no VSO**, pelo que temos de iniciar sessão no VSO (e em quaisquer outros conectores com os quais está a trabalhar), se ainda não tiver iniciado sessão:  
   ![Imagem a mostrar botão de início de sessão](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. Selecione o botão **Aceitar** para autorizar o Power Automate a aceder à sua conta do VSO.  
   ![Imagem a mostrar opções para autorizar o acesso à sua conta do Visual Studio](./media/introduction-to-button-flows/create-button-5.png)   
   **Nota**: terá de autorizar cada conector da mesma forma. O estruturador deverá ser apresentado desta forma quando estiver pronto para avançar para o passo seguinte. Selecione o botão **Continuar** para avançar:  
   ![Botão Continuar](./media/introduction-to-button-flows/create-button-6.png)   
7. Agora, está pronto para configurar as propriedades da compilação que pretende iniciar:    
   ![Ecrã Propriedades](./media/introduction-to-button-flows/create-button-7.png)  
8. Selecione ou introduza o **Nome da conta**, **Nome do projeto**, **Criar ID de definição**, **Ramo de origem** e, opcionalmente, **Parâmetros**, no cartão **Colocar uma nova compilação na fila de espera**:    
   ![Ecrã Nova compilação](./media/introduction-to-button-flows/create-button-8.png)  
9. Em seguida, configure as propriedades da notificação push no cartão **Enviar uma notificação push**. Por predefinição, esta notificação push está configurada para enviar uma ligação HTML para uma página Web que apresenta o estado da compilação:  
   ![Ecrã Notificação push](./media/introduction-to-button-flows/create-button-9.png)  
10. Selecione o botão **Criar fluxo** para guardar o fluxo instantâneo: ![Botão Criar fluxo](./media/introduction-to-button-flows/create-button-10.png)  
11. Deverá ver esta mensagem de êxito dentro de momentos:  
    ![Mensagem de êxito](./media/introduction-to-button-flows/create-button-11.png)  

Parabéns, criou um fluxo instantâneo! Agora, pode executar este fluxo instantâneo em qualquer altura e lugar a partir do separador **Botões** na aplicação Flow. Basta premir o “botão” para ser executado! A aplicação móvel do Power Automate está disponível para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows).

### <a name="from-your-mobile-device"></a>No dispositivo móvel

>[!NOTE]
>embora esta demonstração apresente ecrãs de um dispositivo Android, os ecrãs e a experiência num dispositivo iOS são semelhantes.

Na aplicação:

1. Selecione o separador **Procurar** e desloque-se até à categoria **Botão**.  
   ![Ecrã de destino](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. Selecione a ligação **Ver tudo**. Serão apresentados todos os modelos de botão prontos.     
   ![Ligação Ver tudo](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. Selecione o modelo **Enviar um e-mail para notificar a equipa para participar numa reunião**    
   ![Imagem do modelo Enviar um e-mail para notificar a equipa para participar numa reunião](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. Selecione a ligação **UTILIZAR ESTE MODELO** na parte inferior da página.    
   ![imagem a mostrar a ligação UTILIZAR ESTE MODELO](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. Terá de iniciar sessão em todos os serviços que este modelo utiliza:    
   ![Imagem a mostrar a ligação Iniciar sessão em serviços ou atualizar serviços](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. Selecione a ligação **Seguinte** depois de ter iniciado sessão em todos os serviços.      
   ![Ligação Seguinte](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. Selecione a ligação **Criar**. Aqui, também pode rever o fluxo e fazer as alterações necessárias para personalizar o e-mail, por exemplo.        
   ![Ligação Criar](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. Após alguns instantes, é criado o fluxo instantâneo. Selecione **VER O MEU FLUXO**:   
   ![Imagem do botão VER O MEU FLUXO](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. Veja todos os seus fluxos no separador **Os meus fluxos**.  
   ![Imagem do botão Ver todos os fluxos](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

Parabéns, criou um fluxo instantâneo! Agora, pode executar este fluxo instantâneo em qualquer altura e lugar a partir do separador **Botões** na aplicação Flow. Basta premir o “botão” para ser executado! Atualmente, a aplicação Flow está disponível nos dispositivos móveis Android e iOS.  

![Imagem de novo fluxo instantâneo](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-an-instant-flow"></a>Acionar um fluxo instantâneo
Agora que criou um fluxo instantâneo, está na altura de o executar. Uma vez que só pode executar fluxos instantâneos na aplicação Flow, confirme se instalou o Flow no seu dispositivo móvel Android ou iOS.  

1. Agora, inicie a aplicação Flow, toque no separador **Botões**, localizado na parte inferior da página, e toque no *botão* que representa o fluxo instantâneo que pretende acionar:  
   ![Acionar o fluxo](./media/introduction-to-button-flows/trigger-button-1.png)   
2. Veja o progresso enquanto executa o fluxo:  
   ![Imagem do fluxo em execução](./media/introduction-to-button-flows/trigger-button-2.png)   
3. Por fim, a página é atualizada, o que indica que o fluxo instantâneo foi concluído:  
   ![Imagem de fluxo concluído](./media/introduction-to-button-flows/trigger-button-3.png)   

Basta realizar estes passos para executar um fluxo. 

Agora, deverá receber a notificação push, que indica que o e-mail foi enviado.  

## <a name="monitor-your-instant-flow-runs"></a>Monitorizar as suas execuções de fluxo
Pode monitorizar os fluxos instantâneos no separador **Atividade** da aplicação Flow:   
![Imagem do separador Atividade](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

>[SUGESTÃO!] Toque numa atividade para explorar os resultados da execução e saber mais sobre a mesma.  

![Imagem a mostrar detalhes da atividade](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-instant-flows"></a>Gerir fluxos instantâneos
Tem controlo total sobre os fluxos instantâneos para que possa ativar/desativar, editar ou eliminar um botão em qualquer altura e lugar. Na aplicação móvel ou no portal do fluxo, selecione **Os meus fluxos** para começar a gerir os fluxos.    

No separador **Os meus fluxos** da aplicação Flow:

1. Selecione o fluxo que pretende gerir:    
   ![Imagem de todos os fluxos](./media/introduction-to-button-flows/trigger-button-4.png)   
2. Pode tocar em qualquer uma destas opções, com base no que pretende realizar:    
   ![Opções para gerir fluxos](./media/introduction-to-button-flows/manage-flow-1.png)  

   Toque em **Eliminar fluxo** para eliminar um fluxo.  

      >[!WARNING]
      >Todo o histórico de execuções é eliminado quando elimina um fluxo.

      ![Imagem de aviso para eliminar fluxo](./media/introduction-to-button-flows/manage-flow-2.png)   

   Toque em **Atualizar** depois de terminar de editar um fluxo instantâneo para guardar as alterações:   
   ![Imagem a mostrar o botão para atualizar o fluxo](./media/introduction-to-button-flows/manage-flow-3.png)   

   Toque em **Histórico da execução** para ver os resultados de todas as execuções de um fluxo instantâneo específico:    
   ![Ver o histórico de execuções](./media/introduction-to-button-flows/manage-flow-4.png)  

   Se desativar um fluxo, deixará de estar disponível no separador **Botões**:    
   ![Os fluxos desativados não estão no separador Botões](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>Próximos passos
* [Partilhar fluxos instantâneos](share-buttons.md).
* Aprenda a utilizar [tokens de acionador de botão](introduction-to-button-trigger-tokens.md) para enviar dados em tempo real quando os fluxos instantâneos são executados.
* Instale a aplicação móvel do Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows)

