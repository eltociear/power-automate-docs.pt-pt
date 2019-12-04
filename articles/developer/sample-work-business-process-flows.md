---
title: 'Exemplo: Trabalhar com fluxos de processo de negócio | MicrosoftDocs'
description: O exemplo demonstra como trabalhar programaticamente com fluxos de processo de negócio, tal como obter as instâncias do fluxo do processo de negócio de um registo de entidade, obter o caminho ativo de uma instância do fluxo do processo de negócio e as respetivas fases do processo, e alterar a fase ativa.
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
ms.assetid: 7d378504-b4b2-4a09-838c-69ee094072ef
caps.latest.revision: 15
author: msftman
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 4f7566c6d6430c9167c0d1b7cc082792d0939780
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74364724"
---
# <a name="sample-work-with-business-process-flows"></a>Exemplo: trabalhar com fluxos de processo de negócio
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Este exemplo demonstra como trabalhar programaticamente com fluxos de processo de negócio, tal como obter as instâncias do fluxo do processo de negócio de um registo de entidade, obter o caminho ativo de uma instância do fluxo do processo de negócio e as respetivas fases do processo e alterar a fase ativa. Para obter informações sobre estes conceitos, veja [Trabalhar com fluxos de processo de negócio através de código](business-process-flows-code.md)  

 Este exemplo está disponível para transferência em [Exemplo: trabalhar com fluxos de processo de negócio](https://go.microsoft.com/fwlink/p/?LinkId=846108).  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>Pré-requisitos  
 Antes de poder executar o exemplo:  

1. Tem de ter acesso ao ambiente do Common Data Service.  

2. Tem de ter os privilégios adequados nas entidades Lead, Opportunity e Workflow, e os registos de entidade de definição do fluxo do processo de negócio utilizados neste exemplo.  

3. Tem de ter o Visual Studio 2015 ou posterior para executar o exemplo.  

4. Tem de ter ligação à Internet para transferir o projeto de exemplo e restaurar os pacotes NuGet utilizados no projeto de exemplo.  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>O que faz este exemplo  

1.  Cria um registo Oportunidade potencial de exemplo. Esta ação cria automaticamente uma instância do fluxo do processo de negócio "Processo de Vendas da Oportunidade Potencial" para o registo Oportunidade potencial.  

2.  Converte um registo Oportunidade potencial num registo Oportunidade.  


4.  Obtém as instâncias do fluxo do processo de negócio associadas ao registo "Oportunidade" com a mensagem `RetrieveProcessInstances`. O primeiro registo na coleção devolvida é a instância do fluxo do processo de negócio do registo de oportunidade, que é "Processo de Vendas da Oportunidade Potencial" neste caso.  

5.  Obtém o caminho ativo e as fases do processo da instância "Processo de Vendas da Oportunidade Potencial" com a mensagem `RetrieveActivePath`.  

6.  Obtém a fase atualmente ativa da instância "Processo de Vendas da Oportunidade Potencial" e pergunta ao utilizador se quer avançar para a próxima fase. No caso de confirmação para avançar, define a próxima fase no caminho ativo como a fase ativa da instância "Processo de Vendas da Oportunidade Potencial".  

7.  Por fim, pergunta ao utilizador se quer eliminar os registos criados durante a execução de exemplo.  

     Eis o resultado do exemplo:  

    ![Saída de exemplo](media/work-with-bpf-sample-output.png "Saída de exemplo")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>Executar o exemplo  

1. [Transfira](https://go.microsoft.com/fwlink/p/?LinkId=846108) o projeto de exemplo do Visual Studio do WorkWithBPF e extraia-o para uma pasta no seu computador.  

2. Localize o ficheiro `WorkWithBPF.sln` na sua pasta extraída e abra-o no Visual Studio.  

3. O projeto de exemplo utiliza pacotes NuGet que têm de ser restaurados antes de executar o exemplo. Certifique-se de que o restauro automático de pacotes NuGet está ativado no Visual Studio. Mais informações: [Ativar e desativar o restauro de pacotes NuGet](https://go.microsoft.com/fwlink/?linkid=846106)  

    Em alternativa, selecione **Projeto** > **Gerir Pacotes NuGet** e selecione **Restaurar** para restaurar manualmente os pacotes utilizados no exemplo.  

4. Prima F5 ou selecione **Depurar** > **Iniciar Depuração**.  

5. Se não tiver executado anteriormente um dos exemplos, terá de introduzir as informações para executar o código, caso contrário, introduza o número de uma das instâncias que configurou anteriormente.  


   |                                 Pedido                                  |                                                                                             Descrição                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Introduza um nome de servidor e uma porta do Dynamics 365 [crm.dynamics.com]       | Escreva o nome do seu servidor do Dynamics 365. A predefinição é o Dynamics 365 (online) (crm.dynamics.com) na América do Norte.<br /><br /> Exemplo: <br />crm5.dynamics.com |
   | Esta organização é aprovisionada no Microsoft Online Services (y/n) [n] |                                                 Escreva **y** se esta for uma organização aprovisionada do Microsoft Online Services. Caso contrário, escreva **n**.                                                  |
   |                          Introduzir o domínio\nome de utilizador                          |                                                                                    Escreva a sua conta Microsoft.                                                                                     |
   |                             Introduzir a palavra-passe                              |                      Escreva a sua palavra-passe. Os carateres serão apresentados como "\*" na janela. A sua palavra-passe é guardada em segurança no Gestor de Credenciais da Microsoft para reutilização posterior.                       |
   |                Especificar o número da organização (1-n) [1]                 |                      Na lista de organizações a que pertence, escreva o número correspondente. A predefinição é 1, indicando a primeira organização na lista.                       |


6. O exemplo irá efetuar as operações descritas em [O que faz este exemplo](#what-this-sample-does) e poderá apresentar-lhe opções adicionais.  

7. Quando o exemplo for concluído, prima Enter para fechar a janela da consola.  

