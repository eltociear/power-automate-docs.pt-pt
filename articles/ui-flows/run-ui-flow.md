---
title: Executar fluxos de IU a partir de outros fluxos | Microsoft Docs
description: Executar fluxos de IU a partir de outros fluxos em modo assistido ou automático.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/24/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f893000afea0d554ab911303cbdac2549170f554
ms.sourcegitcommit: aefd1ebedfbd8c6cc3d08397ac171cb4ba5b5315
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/30/2020
ms.locfileid: "3412964"
---
# <a name="run-attended-and-unattended-ui-flows"></a>Executar os fluxos de UI com e sem assistência

Depois de ter criado e testado um fluxo de IU, poderá executá-lo a partir de um evento, agendamento ou botão. Para tornar isto possível, adicione o fluxo de IU a um [Fluxo automatizado](../get-started-logic-flow.md), um [Fluxo de botão](../introduction-to-button-flows.md), um [Fluxo agendado](../run-scheduled-tasks.md) ou um [fluxo de processo de negócio](../business-process-flows-overview.md).

## <a name="prerequisites"></a>Pré-requisitos

- Precisa do [gateway de dados no local](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409) para que o dispositivo possa ter o fluxo de IU acionado pelo Power Automate.
   
   O gateway é uma ligação segura a nível empresarial entre o Power Automate e o dispositivo (onde o fluxo de IU é executado). O Power Automate utiliza o gateway para aceder ao dispositivo no local, de forma a poder acionar os fluxos de IU a partir de um evento, um agendamento ou um botão.
- Uma conta escolar ou profissional. 

   >[!IMPORTANT]
   >Terá de utilizar a mesma conta escolar ou profissional para configurar o gateway, para iniciar sessão no Power Automate e para iniciar sessão no dispositivo Windows.
   

## <a name="run-your-ui-flow-from-an-event-button-schedule-or-business-process-flow"></a>Execute o fluxo de IU a partir de um fluxo de evento, botão, agendamento ou processo de negócio

Neste exemplo, vamos utilizar um fluxo automatizado para acionar um fluxo de IU quando chega um novo e-mail.

1. Navegue para [Power Automate](https://flow.microsoft.com/).
1. Selecione **Os meus fluxos** na barra de navegação esquerda.
1. Selecione **Novo** e, em seguida, **Automatizado – do zero**.

   >[!TIP]
   >Pode escolher qualquer outro tipo de fluxo que se adeque às suas necessidades.

1. Dê um nome ao fluxo na caixa **Nome do fluxo**.
1. Procure “novo e-mail” e, em seguida, selecione **Quando chega um novo e-mail (V3)** na lista de acionadores. 
    
   ![Selecione um acionador](../media/run-ui-flow/select-email-trigger.png "Selecione um acionador")

1. Selecione **Criar** e, em seguida, **Novo passo**.

1. Procure **Fluxos de IU** e, em seguida, selecione **Executar um fluxo de IU para computador** na lista de **Ações**. 

   ![Procurar ação](../media/run-ui-flow/search-action.png "Procurar ação")

1. Forneça as informações do gateway e as credenciais do dispositivo. 

   Terá de fazer isto uma vez para cada dispositivo:

    - **Gateway**: selecione o gateway que criou anteriormente ou utilize **Novo gateway** para criar um novo gateway.   
    - **Domínio e Nome de Utilizador**: apresenta a conta escolar ou profissional do dispositivo.
       >[!Important]
        >Certifique-se de que consegue iniciar sessão no dispositivo com estas credenciais.  
    - **Palavra-passe**: forneça a palavra-passe da conta escolar ou profissional.

      ![Definições de ligação](../media/run-ui-flow/uiflow-connection-card.png "Definições de ligação")

      >[!TIP]
      >Se não vir o seu gateway, poderá estar num ambiente cuja região difere da região do gateway. Selecione **Resolução de problemas de um gateway em falta** na lista de nomes de gateway para saber mais. Também pode confirmar que as regiões do seu gateway e do Power Automate estão [mapeadas corretamente](../regions-overview.md#region-mappings-for-power-automate-and-gateways).

      >[!TIP]
      >Caso não veja o gateway, é possível que tenha de selecionar uma ligação diferente. Para o fazer, selecione **...** no canto superior direto do cartão **Executar um fluxo de IU para computador** ou **Executar um fluxo de IU para a Web** e, em seguida, selecione a ligação em **As minhas ligações**.


      ![Selecionar uma nova ligação](../media/run-ui-flow/select-new-connection.png "Selecionar uma nova ligação")

1. Selecione o fluxo de IU que criou anteriormente.

   ![Selecionar fluxo de IU](../media/run-ui-flow/select-ui-flow.png "Selecionar fluxo de IU")

1. Selecione **Guardar** para guardar o fluxo automatizado.
 
    >[!TIP]
    >Antes de testar, confirme que o seu gateway está online. Aceda a **Dados** > **Gateways** no painel de navegação, selecione o nome do gateway, clique em **...**, aceda a **Detalhes** e verifique se o **estado do gateway** apresentado é **online**. Se **o estado do gateway** apresentado for **offline**, confirme que o dispositivo está em funcionamento e ligado à Internet. 

1. Teste o fluxo ao enviar um e-mail para o acionar. Verá o fluxo de IU a reproduzir os passos que gravou. 

   ![Execução bem-sucedida que chama um fluxo de IU](../media/run-ui-flow/successful-run.png "Execução bem-sucedida que chama um fluxo de IU")

   >[!TIP]
   >Não interaja com o dispositivo enquanto o fluxo estiver a ser executado.

## <a name="use-inputs-and-outputs"></a>Utilizar entradas e saídas

Quando define entradas e saídas num fluxo de IU, pode transmitir informações de e para essas entradas.

1. Ao adicionar um fluxo de IU a um fluxo, poderá ver a lista de entradas que foram definidas no fluxo de IU.

   ![Entradas de fluxo de IU](../media/run-ui-flow/inputs.png "Entradas de fluxo de IU")

1. Pode povoar cada campo de texto no fluxo de IU com os valores dos passos anteriores no fluxo. Para isso, selecione o campo de texto e, em seguida, selecione uma entrada no seletor de tokens.


1. Também pode utilizar saídas do fluxo de IU como entradas para ações que surgem posteriormente no fluxo. Para isso, selecione o campo de texto e, em seguida, selecione uma entrada no seletor de tokens.


## <a name="use-sensitive-text-inputs"></a>Use entradas de texto sensível

Algumas entradas, como palavras-passe, precisam de ser ocultadas e omitidas do registo durante a utilização na aplicação. Os fluxos de IU suportam entradas chamadas **Entradas de texto sensível** para armazenar estes valores "privados". 

Para obter mais informações sobre como criar este tipo de entradas, clique aqui.


Para obter conteúdo sensível de outro conector, ative **Entradas Seguras** e **Saídas Seguras** seguindo estes passos:
1.  Selecione **…** no canto superior direito da ação.
1.  Selecione **Definições**.

    ![A opção de definições ](../media/run-ui-flow/settings.png "A opção de definições ")

1. Ative as propriedades **Entradas Seguras (Pré-visualização)** e **Saídas Seguras (Pré-visualização)** para evitar que estas definições sejam mostradas nos registos.

   ![Entradas e saídas seguras](../media/run-ui-flow/secure-outputs-secure-inputs.png "Entradas e saídas seguras")

1.  Selecione **Concluído**.
   
    Irá notar que a ação tem agora um ícone de bloqueio no topo direito, indicando um manuseamento especial para valores de entrada e saída.

      ![O ícone de bloqueio](../media/run-ui-flow/lock-icon.png "O ícone de bloqueio")

   
      >[!TIP]
      >Siga os mesmos passos para configurar as entradas dadas anteriormente neste artigo para passar a saída deste conector para um fluxo de IU e, em seguida, ative **Texto Seguro (Pré-Visualização)** nas **Definições**.

      ![Passar as saídas para o fluxo de IU ](../media/run-ui-flow/pass-to-ui-flow.png "Entradas de fluxo de IU")


## <a name="run-ui-flows-unattended-or-attended"></a>Executar fluxos de IU automáticos ou assistidos

Ao criar fluxos de IU, execute-os em modo **assistido** ou **automático**. O modo automático é melhor para aplicações que não necessitam de supervisão humana.

Ao executar de forma automática, os fluxos de IU iniciam sessão automaticamente nos dispositivos de destino com o Windows 10, Windows Server 2016 ou Windows Server 2019. Quando a automatização for concluída, os fluxos de IU terminarão sessão no dispositivo e comunicarão a sua atividade no Power Automate.

Ao serem executados de forma assistida, os fluxos de IU utilizarão uma sessão de utilizador do Windows existente.

Quando adiciona um fluxo de IU a um fluxo, pode escolher se quer que o seu fluxo de IU seja assistido ou automático. Seguem-se algumas das principais diferenças entre execuções assistidas e automáticas.

### <a name="unattended-mode"></a>Modo não assistido

Para executar fluxos de IU automáticos, a máquina de destino tem de estar disponível, com todas as sessões de utilizadores terminadas. 

>[!IMPORTANT]
>As sessões de utilizador do Windows bloqueadas impedirão a execução dos fluxos de IU.

Os fluxos de IU realizam o seguinte:
1. Os fluxos de IU criam, gerem e depois disponibilizam a sessão de utilizador do Windows em dispositivos de destino.

1. Os fluxos de IU automáticos são executados em dispositivos com o ecrã bloqueado para que ninguém consiga ver o fluxo durante a execução do mesmo.

1. Os dispositivos com o Windows 10 não podem ser executados de forma automática se existirem sessões de utilizador do Windows ativas (mesmo que estejam bloqueadas). Receberá este erro: *Não é possível executar o fluxo de IU. Existe uma sessão de utilizador do Windows bloqueada ou inativa no dispositivo de destino*.

1. No Windows Server, se tiver uma sessão de utilizador do Windows bloqueada aberta com o mesmo utilizador como o fluxo de IU é suposto ser executado, receberá o mesmo erro: *Não é possível executar o fluxo de IU. Existe uma sessão de utilizador do Windows bloqueada ou inativa no dispositivo de destino*.

### <a name="attended-mode"></a>Modo assistido
Para executar um fluxo de IU assistido, é necessário ter uma sessão de utilizador do Windows ativa que corresponda ao nome do utilizador configurado para a sua ligação. A sessão não deve estar bloqueada.

Quando um fluxo de IU assistido começar na máquina de destino, recomendamos que evite interagir com o seu dispositivo até a execução terminar.


## <a name="schedule-multiple-ui-flows-on-the-same-device"></a>Agendar múltiplos fluxos de IU no mesmo dispositivo

Pode agendar a execução de múltiplos fluxos de IU num ou mais dispositivos. Se for acionado mais do que um fluxo de IU para ser executado no mesmo dispositivo, o Power Automate seguirá as regras abaixo.

1.  O primeiro fluxo de IU será executado no dispositivo de destino.

1.  Coloca outros fluxos de IU em fila e apresenta-os como **Em espera** na página de detalhes dos fluxos de IU ou do gateway.

1.  Escolhe o fluxo de IU seguinte quando cada execução é concluída.

>[!NOTE]
>Estas regras de orquestração aplicam-se às execuções de fluxos de IU que são agendadas pelo mesmo utilizador ou por diferentes utilizadores no mesmo dispositivo.

>[!IMPORTANT]
>Se existirem demasiados fluxos de IU na fila de execução, o tempo pode ser excedido. A execução do fluxo de IU falhará se este não for executado 30 minutos após ser acionado.

## <a name="load-balance-requests-across-gateways-in-a-cluster"></a>Pedidos de balanceamento de carga em vários gateways num cluster

Pode optar por distribuir execuções de fluxo de IU de forma uniforme por vários gateways num cluster. Por predefinição, a seleção de um gateway durante o balanceamento de carga é aleatória.

Siga [estes passos para adicionar um gateway para criar um cluster](https://docs.microsoft.com/data-integration/gateway/service-gateway-install#add-another-gateway-to-create-a-cluster)

>[!NOTE]
>Os membros de gateway offline dentro de um cluster afetarão negativamente o desempenho. Desative ou remova estes membros.

Para proporcionar balanceamento de carga a partir da página de detalhes do gateway do Power Automate, navegue para **Dados** -> **Gateways** e, em seguida, selecione o seu cluster de gateways. 

Na página de detalhes do gateway, ative "Executar em todos os gateways do cluster". Isto distribuirá as execuções de fluxos de IU em todos os gateways dentro desse cluster.

   ![Distribuir uma execução de fluxo de IU no cluster de gateways](../media/run-ui-flow/gw_cluster.png "Distribuir uma execução de fluxo de IU no cluster de gateways")
   
>[!IMPORTANT]
>Se estiver a utilizar contas Windows locais, todas as máquinas no cluster têm de ter a mesma conta local com a mesma palavra-passe. Utilize estas credenciais quando criar a ligação do fluxo de IU.
>Se estiver a utilizar máquinas associadas ao Azure AD ou o Active Directory, confirme que a conta de utilizador que vai utilizar na ligação de fluxo de IU pode aceder a todas as máquinas no cluster.
   
## <a name="best-practices-to-avoid-timeouts-and-distribute-load-across-machines"></a>Melhores práticas para evitar tempos limite e distribuir carga por várias máquinas

Se tencionar executar múltiplos fluxos de IU, há um conjunto de estratégias que pode adotar para distribuir carga e garantir que todos os seus fluxos de IU são executados com sucesso sem sobrecarregar a(s) máquina(s) de destino ou atingir tempos limite devido ao facto de haver múltiplos fluxos de IU em execução ao mesmo tempo. Pode:

1. planear a execução dos seus fluxos de IU em diferentes horas do dia para distribuir a carga ao longo do tempo. Isto funciona melhor se tiver um conjunto único ou limitado de máquinas que podem executar cargas de trabalho e se conseguir controlar os acionadores (por exemplo, fluxos agendados) que iniciam os seus fluxos de IU;
1. criar clusters de máquinas que consigam executar fluxos de IU com configurações idênticas em paralelo; 
1. criar múltiplos fluxos que utilizem uma ligação separada para visar diferentes máquinas. 

Se adotar estas estratégias, pode evitar que os fluxos de IU compitam entre si para serem executados no mesmo dispositivo e, em alguns casos, falhem devido à existência de tempos limite. 

>[!NOTE]
>Se estiver a executar fluxos de IU em modo automático, terá de prever o número de fluxos de IU que a sua organização tenciona executar em paralelo e, em seguida, comprar uma quantidade adequada de Suplementos Automáticos. 


## <a name="rerun-failed-ui-flows"></a>Voltar a executar fluxos de IU com falhas

Se a execução de um fluxo de IU falhar, corrija o problema e, em seguida, experimente seguir os passos que se seguem para a voltar a executar: 

   1. Aceda à página de detalhes e identifique a execução que falhou.

   1. Selecione o botão **Voltar a submeter** no menu Ação.

## <a name="troubleshoot-failures"></a>Resolver falhas

1. Se o seu fluxo de IU automático falhar com a mensagem **Não é possível criar uma nova sessão**, siga estes passos para resolver o problema:

    - No Windows 10, confirme se não tem uma sessão de utilizador ativa bloqueada ou desbloqueada no seu dispositivo de destino.
    - No Windows Server 2016 ou no Windows Server 2019, confirme que não atingiu o número máximo de sessões de utilizadores ativas configuradas para o seu dispositivo. Os fluxos de IU não serão executados se não for possível criar novas sessões.

1. Se estiver a executar fluxos de IU num sistema operativo cujo idioma não seja o inglês e receber uma mensagem *502 - Pedido incorreto*, confirme que seguiu os [passos para atualizar os seus fluxos de IU a partir da pré-visualização](upgrade.md).


1. Se o **estado do gateway** for **offline**, confirme se o dispositivo está ligado e ligado à Internet. Também pode [resolver problemas do gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot).

1. Se o **estado do gateway** for **online**, experimente as seguintes ações:

   - Confirmar se os serviços e a aplicação de fluxos de IU estão em execução no seu dispositivo.

   - Reiniciar o serviço de fluxo de IU no seu dispositivo.

## <a name="learn-more"></a>Mais Informações

 - Instalar o [gateway de dados no local](https://docs.microsoft.com/data-integration/gateway/service-gateway-app).
 - Documentação para [utilizar a aplicação de gateway de dados no local](https://docs.microsoft.com/flow/gateway-manage).
 - [Resolução de problemas](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot) do gateway de dados no local.



