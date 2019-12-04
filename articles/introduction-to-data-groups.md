---
title: Grupos de dados do Power Automate | Microsoft Docs
description: Introdução aos Grupos de dados do Microsoft Power Apps e do Power Automate.
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
ms.date: 10/26/2016
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 205857821402a629bebffe005525536ed42f9669
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74355248"
---
# <a name="learn-all-about-data-groups"></a>Saiba tudo sobre os grupos de dados
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-is-a-data-group"></a>O que é um grupo de dados?
Os grupos de dados são uma forma simples de categorizar serviços dentro de uma [política de prevenção de perda de dados (DLP)](prevent-data-loss.md). Os dois grupos de dados disponíveis são o grupo **Apenas dados de negócio** e o grupo **Nenhum dado de negócio permitido**. As organizações têm a liberdade para determinar que serviços são colocados num grupo de dados específico. Uma boa forma de categorizar serviços é colocá-los em grupos, com base no impacto na organização. Por predefinição, todos os serviços são colocados no grupo de dados **Nenhum dado de negócio permitido**. Realiza a gestão dos serviços num grupo de dados quando cria ou modifica as propriedades de uma política DLP a partir do centro de administração.

## <a name="how-data-is-shared-between-data-groups"></a>Como os dados são partilhados entre grupos de dados
Não pode partilhar dados entre serviços localizados em grupos diferentes. Por exemplo, se colocar o SharePoint e o Salesforce no grupo **Apenas dados de negócio** e colocar o Facebook e Twitter no grupo **Nenhum dado de negócio permitido**, não poderá criar um fluxo que move os dados entre o SharePoint e o Facebook. Apesar de os dados não poderem ser partilhados entre serviços de diferentes grupos, pode partilhar dados entre os serviços dentro de um grupo específico. Deste modo, voltando ao exemplo anterior, uma vez que o SharePoint e o Salesforce foram colocados no mesmo grupo de dados, os fluxos que os utilizadores finais criam podem partilhar dados entre o SharePoint e o Salesforce. Da mesma forma, os utilizadores finais podem criar fluxos e Power Apps que partilham dados entre o Facebook e o Twitter. O ponto-chave é que os serviços num grupo específico podem partilhar dados, enquanto os serviços em grupos diferentes não podem partilhar dados.  

Além disso, um grupo de dados tem de ser designado como o grupo *predefinido*. Inicialmente, o grupo **Nenhum dado de negócio permitido** é o grupo *predefinido* e todos os serviços estão no grupo de dados. Um administrador pode alterar o grupo de dados predefinido para o grupo de dados **penas dados de negócio**. **Nota**: os novos serviços adicionados ao fluxo são colocados no grupo *predefinido* designado. Por este motivo, recomendamos que mantenha o grupo **Nenhum dado de negócio permitido** como o grupo predefinido e adicione manualmente os serviços no grupo **Apenas dados de negócio** após a sua organização avaliar o impacto de permitir que os dados de negócio sejam partilhados com o novo serviço.

## <a name="add-services-to-a-data-group"></a>Adicionar serviços a um grupo de dados
Nesta demonstração, vamos adicionar o SharePoint e o Salesforce ao grupo de dados **Apenas dados de negócio** de uma política de prevenção de perda de dados (DLP). 

1. Selecione a ligação **+ Adicionar**, localizada dentro da caixa do grupo **Apenas dados de negócio** de uma política DLP:    
   ![Adicionar imagem](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Selecione o SharePoint e o Salesforce e, em seguida, selecione **Adicionar serviços** para adicionar ambos ao grupo Apenas dados de negócio:    
   ![Adicionar imagem de serviços](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Selecione **Guardar Política** no menu superior:  
   ![Guardar política](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Repare que o SharePoint e o Salesforce estão agora no grupo Apenas dados de negócio:  
   ![grupo de dados de negócio atualizado](./media/introduction-to-data-groups/add-to-data-group-3.png)   

Nesta demonstração, adicionou o SharePoint e o Salesforce ao grupo de dados **Apenas dados de negócio** de uma política DLP. Se uma pessoa que faz parte do ambiente da política DLP criar uma aplicação que partilhe dados entre o SharePoint ou o Salesforce e qualquer serviço no grupo de dados **Nenhum dado de negócio permitido**, a aplicação não terá permissão para ser executada.

## <a name="remove-services-from-a-data-group"></a>Remover serviços de um grupo de dados
Uma vez que todos os serviços têm de estar num dos grupos de dados disponíveis, para remover um serviço de um grupo específico, basta adicionar o serviço a outro grupo e, em seguida, guardar a política.  

## <a name="change-the-default-data-group"></a>Alterar o grupo de dados predefinido
Nesta demonstração, vamos alterar o grupo de dados predefinido do grupo de dados **Nenhum dado de negócio permitido** para o grupo de dados **Apenas dados de negócio**.  

**Importante**: os novos serviços adicionados ao fluxo são colocados no grupo *predefinido* designado. Por este motivo, recomendamos que mantenha **Nenhum dado de negócio permitido** como o grupo predefinido e adicione manualmente os serviços no grupo **Apenas dados de negócio**.

1. Selecione o ícone **…** localizado no canto superior direito do grupo de dados que pretende designar como o grupo de dados predefinido:    
   ![alterar grupo predefinido](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Selecione **Selecionar como grupo predefinido**:  
   ![alterar grupo predefinido](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Selecione **Guardar Política** no menu superior:  
   ![alterar grupo predefinido](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Repare que o grupo de dados está agora designado como o grupo de dados predefinido:  
   ![alterar grupo predefinido](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Passos seguintes
* [Saiba mais sobre as políticas de prevenção de perda de dados (DLP)](prevent-data-loss.md)
* [Saiba mais sobre os ambientes](environments-overview-admin.md)   

