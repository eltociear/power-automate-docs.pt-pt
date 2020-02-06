---
title: Introdução aos tokens de acionador de botão | Microsoft Docs
description: Introdução aos tokens de acionador de botão para fluxos de botão Microsoft.
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
ms.date: 12/12/2016
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b57e9dee27a2d22159a9cd805c65034a5e5bb578
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74363896"
---
# <a name="get-started-with-button-trigger-tokens"></a>Introdução aos tokens de acionador de botão
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-are-button-trigger-tokens"></a>O que são tokens de acionador de botão?
Os tokens de acionador de botão são pontos de dados que são conhecidos e estão disponíveis para o dispositivo no qual um [fluxo de botão](introduction-to-button-flows.md) está em execução. Estes tokens mudam com base em fatores como a hora atual ou a localização geográfica do dispositivo num determinado momento.  

Por exemplo, se estiver a executar um fluxo de botão num smartphone, é provável que o **telemóvel saiba a hora** na sua localização atual, bem como a data e o seu endereço atual. Neste contexto, a hora, a data e o endereço onde se encontra o telemóvel são todos determinados no momento em que o fluxo do botão é executado. Estão automaticamente disponíveis para utilização em quaisquer fluxos de botão que sejam executados no dispositivo. Pode utilizar estes tokens de acionador para criar fluxos úteis que minimizem tarefas repetitivas, como fornecer a sua localização a outra pessoa ou controlar quanto tempo passou numa determinada tarefa/chamada de serviço.

### <a name="list-of-button-trigger-tokens"></a>Lista de tokens de acionador de botão
Eis a lista dos tokens de acionador de botão que pode utilizar ao criar os seus fluxos de botão.

| Parâmetro | Descrição |
| --- | --- |
| Cidade |A cidade em que se encontra o dispositivo que está a executar o fluxo. |
| País/Região |O país/região em que se encontra o dispositivo que está a executar o fluxo. |
| Endereço completo |O endereço completo em que se encontra o dispositivo que está a executar o fluxo. |
| Latitude |A latitude em que se encontra o dispositivo que está a executar o fluxo. |
| Longitude |A longitude em que se encontra o dispositivo que está a executar o fluxo. |
| Código Postal |O código postal em que se encontra o dispositivo que está a executar o fluxo. |
| Estado |O estado em que se encontra o dispositivo que está a executar o fluxo. |
| Rua |A rua em que se encontra o dispositivo que está a executar o fluxo. |
| Carimbo de data/hora |A hora na área em que se encontra o dispositivo que está a executar o fluxo. |
| Data |A data na área em que se encontra o dispositivo que está a executar o fluxo. |
| Nome de utilizador |O nome de utilizador da pessoa com sessão iniciada no dispositivo que está a executar o fluxo. |
| E-mail de utilizador |O e-mail de utilizador da pessoa com sessão iniciada no dispositivo que está a executar o fluxo. |

## <a name="create-a-button-flow-that-uses-trigger-tokens"></a>Criar um fluxo de botão que utilize tokens de acionador
Quando cria um botão, pode utilizar tokens de acionador para adicionar funcionalidades avançadas ao botão.

Nesta demonstração, vamos criar um fluxo de botão num dispositivo Android. O fluxo de botão irá utilizar tokens de acionador para enviar a data e o seu endereço completo num e-mail "**A trabalhar a partir de casa**" para o seu chefe.

Nesta demonstração, verá capturas de ecrã de um dispositivo Android. No entanto, a experiência também é semelhante em dispositivos iOS ou Windows Phone.

### <a name="prerequisites"></a>Pré-requisitos
* Um endereço de e-mail escolar ou profissional ou uma [Conta Microsoft](https://account.microsoft.com/about?refd=www.microsoft.com) com acesso ao Power Automate.
* A aplicação móvel do Power Automate para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows).

Vamos começar:

1. Inicie o Flow e selecione **Procurar**   
   ![token de acionador de botão](./media/introduction-to-button-trigger-tokens/1.png)  
2. Selecione o serviço **Enviar o e-mail “A trabalhar a partir de casa hoje” para o seu gestor** na categoria **Botão**   
   ![token de acionador de botão](./media/introduction-to-button-trigger-tokens/2.png)  
3. Selecione **UTILIZAR ESTE MODELO**  
   ![token de acionador de botão](./media/introduction-to-button-trigger-tokens/3.png)  
4. Selecione **Editar** no cartão **Enviar um e-mail**  
   ![token de acionador de botão](./media/introduction-to-button-trigger-tokens/3-5.png)  
5. Toque na caixa de texto **Assunto** e introduza: " **hoje -** " na caixa de texto a seguir ao texto "A trabalhar a partir de casa". Repare que, quando tocou na caixa de texto, uma lista de parâmetros/tokens também abriu. Vamos utilizar um destes tokens no passo seguinte para adicionar a data ao assunto do e-mail.  
   ![token de acionador de botão](./media/introduction-to-button-trigger-tokens/4.png)  
6. Com o cursor ainda na caixa de texto do assunto, desloque-se para a lista de parâmetros **manual** e toque em **Data**. Tenha em atenção o parâmetro de data agora está na caixa de texto **Assunto**:  
   ![token de acionador de botão](./media/introduction-to-button-trigger-tokens/6.png)  
7. Desloque-se para a caixa de texto **Corpo** e toque no espaço que se segue à mensagem predefinida para aí poder incluir tokens adicionais.  
   ![token de acionador de botão](./media/introduction-to-button-trigger-tokens/7.png)  
8. Toque no parâmetro **Endereço completo** e, em seguida, toque em **Criar**  
   ![token de acionador de botão](./media/introduction-to-button-trigger-tokens/8.png)  
9. Toque em **Concluído**. Acabou de criar um fluxo do botão.  
   ![token de acionador de botão](./media/introduction-to-button-trigger-tokens/9.png)  

## <a name="run-the-button-flow"></a>Executar o fluxo de botão
**NOTA**: este fluxo de botão envia a sua localização atual por e-mail.  

1. Toque na categoria **Botões** na parte inferior do ecrã. Verá uma lista dos botões que tem permissões para utilizar. Toque no botão que representa o fluxo de botão que acabou de criar:  
   ![token de acionador de botão](./media/introduction-to-button-trigger-tokens/10.png)  
2. Toque em **PERMITIR** para deixar que o fluxo do botão aceda às informações de localização do seu dispositivo:  
   ![token de acionador de botão](./media/introduction-to-button-trigger-tokens/11.png)  
3. Dentro de alguns instantes, repare que o e-mail foi enviado para o seu chefe:  
   ![token de acionador de botão](./media/introduction-to-button-trigger-tokens/12.png)  

Parabéns, acabou de criar um fluxo de botão que utiliza os tokens de acionador de data e de endereço completo. 

## <a name="next-steps"></a>Próximos passos
* [Partilhar fluxos de botões](share-buttons.md)
* [Saiba mais sobre fluxos de botão](introduction-to-button-flows.md)
