---
title: Saiba como criar Fluxos de IU com o WinAutomation | Microsoft Docs
description: Saiba como criar Fluxos de IU com o WinAutomation.
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
ms.date: 05/19/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1b9bd3a1f79885d17406e882b4432eff930d342c
ms.sourcegitcommit: 549224cf13fc761f473c880e8d0d8f2741cc7b0f
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/08/2020
ms.locfileid: "3435046"
---
# <a name="use-softomotives-winautomation-with-ui-flows"></a>Utilizar o Softomotive WinAutomation com fluxos da IU

A sua licença do Power Automate Attended RPA (paga ou avaliação trial) dá-lhe agora acesso total à aplicação [WinAutomation](https://www.winautomation.com/) da Softomotive. Este documento irá orientá-lo para executar os processos WinAutomation com o Power Automate.

Os utilizadores existentes do WinAutomation podem saber mais na [página de suporte da Softomotive](https://support.softomotive.com/support/home)

## <a name="overview-for-existing-ui-flows-users"></a>Descrição geral para os utilizadores do Fluxos de IU existentes

[Transfira](https://aka.ms/rpaDesktopAutomationInstallPage), instale e inicie sessão no WinAutomation com a mesma conta escolar ou profissional que no Power Automate. Depois de criar um processo no WinAutomation, pode executá-lo com ou sem assistência a partir do Power Automate através de um fluxo de IU. Para o fazer, siga estes passos:

1. Inicie uma gravação de ambiente de trabalho dos fluxos de IU.
1. Abra a linha de comandos.
1. Introduza o comando para acionar o processo.
   - Para um processo que não exija variáveis de entrada, introduza *"%programfiles%\WinAutomation\WinAutomationController.exe" /start "/My Robots/MyAutomationName"*.
   - Para um processo que exija variáveis de entrada, introduza-as após o nome do processo. Por exemplo, se um processo denominado *MyAutomationName* exigir *VariableA* e *VariableB*, coloque os respetivos valores da seguinte forma: *"%programfiles%\WinAutomation\WinAutomationController.exe" /start "/My Robots/MyAutomationName" ValueA ValueB.*

   >[!TIP] 
   >Pode utilizar entradas de fluxos de IU e conteúdo Dinâmico para alterar o processo de WinAutomation de destino a partir do Power Automate.

1. Prima Enter na linha de comandos e, em seguida, pare a gravação dos fluxos de IU. 
   Os fluxos de IU captam todas as informações necessárias no momento em que o processo winAutomation começa.
   
1. Adicione o fluxo de IU a um fluxo e, em seguida, selecione *com assistência* ou *sem assistência* como tipo de execução.

   >[!TIP] 
   >No processo WinAutomation, utilize a ação *Get Command Line Arguments* para obter os argumentos da linha de comandos. Os argumentos estão numa matriz. Utilize o respetivo índice para referenciar cada argumento.
   
## <a name="set-up-winautomation"></a>Configurar o WinAutomation

>[!TIP]
>Os scripts de automatização no WinAutomation são denominados **processos**. No Power Automate, os scripts de automatização são denominados *fluxos* ou *Fluxos de IU*.

Antes de criar um processo do WinAutomation, verifique a [lista de conectores](https://flow.microsoft.com/connectors/) para ver se a aplicação que quer automatizar já tem um conector. Se já tiver, considere criar um fluxo em vez de um fluxo de IU. Também poderá [criar o seu próprio conetor](https://docs.microsoft.com/connectors/custom-connectors/). Normalmente, os conectores baseados em APIs proporcionam uma melhor experiência global do que a automatização da IU em termos de escalabilidade, fiabilidade e custo mais reduzido.

>[!TIP]
>Para executar scripts do WinAutomation a partir do Power Automate, primeiro tem de iniciar a reprodução dos scripts a partir de fluxos de IU.

## <a name="prerequisites"></a>Pré-requisitos 

Para executar o WinAutomation como parte do Power Automate, terá de:
1. Certifique-se de que a sua máquina cumpre os [requisitos para os fluxos de IU](https://docs.microsoft.com/power-automate/ui-flows/setup#prerequisites).
1. Instale a aplicação [Fluxos de IU](https://docs.microsoft.com/power-automate/ui-flows/setup), e instale e configure o gateway de dados no local.

## <a name="licensing"></a>Licenciamento

Tem de ter um *Plano por utilizador com RPA com assistência* para utilizar os Fluxos de IU e o WinAutomation. Se não tiver um plano pago, pode iniciar uma versão experimental do *Plano por utilizador com RPA com assistência* no Power Automate e, em seguida, selecionar o separador **Fluxos de IU** em **Os meus fluxos**. Verá a caixa de diálogo da versão de avaliação onde pode iniciar a avaliação.

![Iniciar uma avaliação ou comprar uma licença](../media/create-processes/trial.png)

Se já tiver um plano pago ou utilizou anteriormente uma versão de avaliação, não poderá iniciar uma nova versão de avaliação. Neste caso, terá de pedir ao seu administrador para comprar ou iniciar uma versão experimental do *Plano por utilizador com RPA com assistência* do Power Automate. Poderá fazer a compra em **Faturação** > **Adquirir serviços** no centro de administração do Microsoft 365 e, em seguida, procurar o plano certo.

![Plano por utilizador com RPA com assistência](../media/create-processes/license-plan.png)

Finalmente, depois de adquirido um plano ou obtida uma avaliação gratuita, é necessário atribuir esse plano a um utilizador. 

>[!NOTE]
>Quando atribui um plano a um utilizador, pode demorar alguns minutos até a atribuição entrar em vigor.

>[!WARNING]
>É necessária a versão mais recente de cada componente para gravar, testar ou executar a automatização da IU.

## <a name="install-winautomation"></a>Instalar o WinAutomation

Depois de instalados os Fluxos de IU na sua máquina, poderá instalar o WinAutomation para gravar, editar e testar scripts de automatização para ambiente de trabalho através destes passos:

1.  Transfira o [instalador do WinAutomation](https://aka.ms/rpaDesktopAutomationInstallPage).

1.  Abra o ficheiro **WinAutomationSetup.exe**. Este ficheiro deve estar na sua pasta **Transferências**.

1.  Siga as instruções do programa de instalação do WinAutomation para concluir a instalação. Durante a instalação, certifique-se de que o **Tipo de Licença** está definido como **Microsoft Power Automate**.

## <a name="sign-in-to-winautomation"></a>Iniciar sessão no WinAutomation 

Após a conclusão da instalação, inicie a Consola do WinAutomation a partir do menu Iniciar do Windows. A aplicação é iniciada e pede para iniciar sessão. Se já tiver uma licença *Plano por utilizador com RPA com assistência* para o Power Automate ou se tiver uma licença de avaliação do Power Automate, introduza as credenciais de utilizador que utiliza para o [Power Automate](https://flow.microsoft.com). Também pode visitar a [página de preços](https://flow.microsoft.com/pricing/) para saber mais sobre esta licença ou para obter uma licença de avaliação.

Se não tiver uma licença válida, verá esta mensagem de erro.

![Erro de licença](../media/create-processes/license-error.png)


>[!WARNING]
>Precisará que o administrador do inquilino conceda o consentimento para utilizar a conta escolar ou profissional do Power Automate com o WinAutomation. Para tal, poderão instalar o WinAutomation, iniciar sessão com a respetiva conta de administrador do inquilino e dar o consentimento.

![Pedido de permissões](../media/create-processes/permissions-request.png)

Depois de iniciar sessão, verá a consola WinAutomation com alguns processos de exemplo. Para começar, pode ir para **Opções** > **Ajuda** > **Introdução** e analise alguns exemplos de criação de processos simples. Além disso, estão disponíveis vários [tutoriais de introdução do WinAutomation](https://www.winautomation.com/support/tutorials/).

## <a name="run-winautomation-processes-from-power-automate"></a>Executar processos do WinAutomation a partir do Power Automate

Depois de definir o script de automatização no WinAutomation, poderá executá-lo a partir de um fluxo no Power Automate através do suporte dos Fluxos da IU para iniciar aplicações com a linha de comandos. Para saber mais sobre como criar e testar Fluxos de IU, pode ir para [aqui](https://docs.microsoft.com/power-automate/ui-flows/create-desktop).

### <a name="running-winautomation-processes"></a>Executar processos do WinAutomation 

Para executar um processo do WinAutomation sem o ambiente da Consola, poderá utilizar o comando WinAutomationController.EXE. Este processo está localizado na pasta de instalação do WinAutomation e poderá ser iniciado a partir do da **Linha de Comandos** no Windows. Apesar de ter vários parâmetros úteis para iniciar a automatização, utilize o sinalizador ‘/start’ que iniciará o processo especificado. Segue-se um exemplo do comando: **WinAutomationController /start processPath**

*processPath* é o caminho na Consola do WinAutomation para o Processo, a partir de um diretório de base Os Meus Processos no Painel de Pastas no lado esquerdo. Se colocou o Processo numa subpasta, terá de incluir essa informação no processPath. Note que, se o processPath contiver espaços, deve estar entre aspas (por exemplo, WinAutomationController /start "/Os Meus Processos/../../processName").

### <a name="launching-winautomation-processes-from-ui-flows"></a>Iniciar processos do WinAutomation a partir dos Fluxos de IU

Depois de identificar com êxito o comando para executar os processos do WinAutomation acima, poderá agora invocar este comando diretamente a partir dos Fluxos de IU. Para tal:

1.  Adicione um novo passo na experiência de gravação do fluxo de IU ao clicar em **Iniciar gravador** se tiver um Fluxo de IU em branco. Se já tiver passos predefinidos no fluxo de IU, poderá clicar em **Novo Passo** e, em seguida, em **Gravar aplicação** para iniciar o gravador. Estão disponíveis mais informações sobre a experiência de gravação [aqui](https://docs.microsoft.com/power-automate/ui-flows/create-desktop).

1.  Selecione **Gravar** no gravador iniciado.

1.  Abra a aplicação **Linha de Comandos** no Windows.

1.  Digite o comando WinAutomationController que criou anteriormente (por exemplo, WinAutomationController /start "/Os Meus Processos/../../process").

1.  Selecione **Concluído** no gravador.

Repare que o gravador adiciona novos passos ao seu fluxo de IU que agora inclui o lançamento do WinAutomationController.


>[!TIP]
>Os Fluxos de IU podem ser executados em modo de automatização com e sem assistência. Também pode executar WinAutomationController em ambos os casos. Se estiver a executar Fluxos de IU num cluster sem assistência, certifique-se de que o comando WinAutomationController acima especificado funcionará em todas as máquinas no cluster. Para mais informações sobre os Fluxos de IU com e sem assistência, clique [aqui](https://docs.microsoft.com/power-automate/ui-flows/run-ui-flow).

## <a name="waiting-for-a-winautomation-process-to-complete-in-ui-flows"></a>Aguardar a conclusão de um processo do WinAutomation nos Fluxos de IU

Por predefinição, WinAutomationController.exe executa os processos em segundo plano. Se pretende que os Fluxos de IU aguardem pela conclusão da automatização do processo, pode gerar uma caixa de mensagem informativa no final do processo WinAutomation através do comando **Apresentar Mensagem** e, em seguida, aguardar nos Fluxos de IU para clicar nesse botão de caixa de mensagem. Para tal:

1.  Adicione um comando "Apresentar Mensagem" como último passo no seu Processo do WinAutomation. Para tal, filtre o painel Ações à esquerda para localizar Apresentar Mensagem, e arrastar e largar esse comando no editor de scripts do Processo. Pode atribuir-lhe um título e descrição intuitivos e deixar a seleção de botões predefinida que mostra o botão OK.
1.  Execute o Processo WinAutomation até a caixa de mensagem ser mostrada. 
1.  Adicione uma nova gravação do Fluxo de IU, clique no título da caixa de Apresentar Mensagem e, em seguida, clique em OK. 
1.  Pare a gravação ao clicar em Concluído. Verá agora que o script no fluxo de IU tem um novo conjunto de ações para clicar na caixa de diálogo e eliminar a caixa de mensagens.
1.  E, finalmente, terás de indicar ao Fluxo de IU para dar a WinAutomation um determinado tempo para ser concluído. Para tal, expanda o comando Enviar Teclas anterior que inicia o comando WinAutomationController.exe, expanda para ver as opções avançadas e defina a propriedade Aguardar Após para aguardar o tempo máximo que o script do Processo WinAutomation demora a ser executado.


## <a name="uninstall-winautomation"></a>Desinstalar o WinAutomation

1.  Abra o menu **Iniciar** \> **Definições** \> **Aplicações**.

1.  Procure **WinAutomation** e selecione essa opção.

1.  Selecione **Desinstalar**.

## <a name="troubleshooting-winautomation-licensing-issues"></a>Resolver problemas de licenciamento do WinAutomation

Se forem apresentados erros de licenciamento durante o lançamento do WinAutomation, certifique-se de que o utilizador com o qual está a iniciar sessão tem uma licença válida para Fluxos de IU. Para tal: 

1.  Vá para [Power Automate](https://flow.microsoft.com) e inicie sessão.
1.  Selecione Os meus fluxos na barra de navegação esquerda.
1.  Selecione os Fluxos de IU à direita. Poderá precisar de começar uma versão de avaliação ou pedir ao administrador para o fazer.

Para redefinir as informações de licença armazenadas pelo WinAutomation, pode eliminar o seguinte ficheiro: %localappdata%\Softomotive\WinAutomation\msalcache.bin3

>[!NOTE]
>Esta licença está em cache quando os utilizadores iniciam o WinAutomation quando estão ligados à Internet. 


## <a name="learn-more"></a>Mais Informações

- Saiba mais sobre a [Aquisição do WinAutomation](https://flow.microsoft.com/blog/microsoft-acquires-softomotive-to-expand-low-code-robotic-process-automation-capabilities-in-microsoft-power-automate/)
- Obtenha suporte para o [WinAutomation](https://support.softomotive.com/support/home).
- Comece com os [tutoriais do WinAutomation](https://www.winautomation.com/support/tutorials/).
- Saiba como [criar fluxos de IU para computador](https://docs.microsoft.com/power-automate/ui-flows/create-desktop).
- Saiba como [executar fluxos de IU](https://docs.microsoft.com/power-automate/ui-flows/run-ui-flow).
- Saiba como [gerir fluxos de IU](https://docs.microsoft.com/power-automate/ui-flows/manage)
- Saiba mais sobre o [gateway no local](https://docs.microsoft.com/power-automate/gateway-reference#use-a-gateway).
