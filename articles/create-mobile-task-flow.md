---
title: Criar um fluxo de tarefas móveis com o Power Apps | Microsoft Docs
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 22736d826c6e0448e3d1272aed1b3d4f78fdb23b
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74362079"
---
# <a name="create-a-mobile-task-flow"></a>Criar um fluxo de tarefas móveis
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Crie um fluxo no Dynamics 365 para telemóveis ou no Dynamics 365 para tablets com base em tarefas comuns executadas pelos utilizadores. Por exemplo, se precisarem de efetuar regularmente uma série de etapas de acompanhamento após reuniões com clientes, crie um fluxo de tarefas. Quando os utilizadores tocarem na nova tarefa na aplicação móvel, esta irá guiá-los do início ao fim, para que não se esqueçam de nenhum passo importante.  
  
 Os fluxos de tarefas podem utilizar formulários e lógica de múltiplas entidades, e podem ter uma lógica de formulário que seja executada nas páginas de fluxo de tarefas.  
  
## <a name="create-a-task-flow"></a>Criar um fluxo de tarefas
  
1. Certifique-se de que tem a função de segurança de Administrador de Sistema ou Personalizador de Sistema, ou permissões equivalentes. As funções de segurança de Gestor, Vice-Presidente ou CEO – Gestor Empresarial também podem criar fluxos de tarefas móveis. 
  
2. Abra o [explorador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) e selecione **Processos**.  
  
3.  Na barra de ferramentas **Ações**, selecione **Novo**.  
  
4.  Na caixa de diálogo **Criar Processo**, preencha os campos obrigatórios:  
  
    -   Introduza um nome de processo.  
  
    -   Na lista **Categoria**, selecione **Fluxo de Processo de Negócio**.  
  
    -   Na lista **Entidade**, selecione a entidade que pretende.  
  
5.  Selecione a opção **Executar processo como fluxo de tarefas (apenas móvel)** .  
  
6.  Selecione **OK**.
  
     O estruturador de fluxo de tarefas é aberto numa nova janela.  
  
     ![Janela do estruturador de fluxo de tarefas](media/task-flow-designer-window.png "Janela do estruturador de fluxo de tarefas") 
  
7.  Se os utilizadores progredirem de uma página para outra por ordem, arraste o componente **Página** do separador **Componentes** no lado direito do ecrã e solte-o no sinal + no ponto adequado. Para adicionar um nome para uma página, selecione a página, selecione o separador **Propriedades**, escreva um novo nome e, em seguida, selecione **Aplicar**.  
  
8.  Para adicionar um ramo para o fluxo de tarefas, arraste o componente **Condição** do separador **Componentes** e solte-o no sinal + no ponto adequado. Para definir propriedades para a condição, selecione a condição, defina as propriedades no separador **Propriedades** e, em seguida, selecione **Aplicar**.  
  
    > [!NOTE]
    >  À medida que adiciona páginas e condições ao fluxo de tarefas, verá um minimapa no canto inferior esquerdo da janela que mostra todas as páginas e condições no fluxo de tarefas.  
  
9. Para adicionar um campo, uma etiqueta ou uma etiqueta de secção a uma página, arraste **Campo**, **Etiqueta** ou **Etiqueta de Secção** do separador **Componentes** para a página apropriada. Para alterar as propriedades para um destes itens, selecione o item, defina as propriedades no separador **Propriedades** e, em seguida, selecione **Aplicar**.  
  
10. Para validar o fluxo de tarefa, selecione **Validar** na barra de ação.  
  
11. Para guardar o processo como rascunho, selecione **Guardar** na parte superior do ecrã. (As pessoas não poderão utilizar o processo enquanto este estiver em rascunho.)  
  
12. Para ativar o fluxo de tarefas para que as pessoas possam utilizá-lo, selecione **Ativar**.  
  
> [!TIP]
>  Eis algumas sugestões a ter em conta enquanto trabalha no seu fluxo de tarefas na janela do estruturador:  
>   
> -  Para tirar um instantâneo de toda a janela do fluxo de tarefas, selecione **Instantâneo** na barra de ação.  
> -  Para ligar um componente válido a outro componente válido no estruturador, selecione **Conector** na barra de ação.  
> -  Pode tornar as imagens no ecrã maiores ou menores ao selecionar os botões **Aumentar o nível de zoom** ou **Diminuir o nível de zoom** no canto superior direito do ecrã. Selecione o botão **Ajustar à tela** para expandir as imagens até ao tamanho maior que o ecrã pode conter.  
  
## <a name="next-steps"></a>Passos seguintes  
 [Criar um fluxo de processo de negócio](create-business-process-flow.md)   

