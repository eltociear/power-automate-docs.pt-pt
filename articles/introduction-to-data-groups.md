---
title: Grupos de dados para o Power Automate | Microsoft Docs
description: Introdução aos Grupos de dados para o Microsoft Power Apps e Power Automate.
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
ms.openlocfilehash: ca3271f7c61c6835c856bc363f64882802f1556f
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298182"
---
# <a name="learn-all-about-data-groups"></a>Saiba tudo sobre grupos de dados

## <a name="what-is-a-data-group"></a>O que é um grupo de dados?
Os grupos de dados são uma forma simples de categorizar serviços numa [política de prevenção de perda de dados (DLP)](prevent-data-loss.md). Os dois grupos de dados disponíveis são o grupo **dados de negócio apenas** e o grupo **sem dados de negócios permitidos**. As organizações são livres para determinar quais os serviços colocados num determinado grupo de dados. Uma boa forma de categorizar os serviços é colocá-los em grupos, com base no impacto na organização. Por predefinição, todos os serviços são colocados no grupo de dados **sem dados de negócios permitidos** . É possível gerir os serviços num grupo de dados quando cria ou modifica as propriedades de uma política DLP a partir do centro de administração.

## <a name="how-data-is-shared-between-data-groups"></a>Como é que os dados são partilhados entre grupos de dados
Os dados não podem ser partilhados entre serviços localizados em grupos diferentes. Por exemplo, se colocar o SharePoint e o Salesforce no grupo **Apenas dados de negócio** e colocar o Facebook e Twitter no grupo **Nenhum dado de negócio permitido**, não poderá criar um fluxo que move os dados entre o SharePoint e o Facebook. Apesar de os dados não poderem ser partilhados entre serviços de diferentes grupos, pode partilhar dados entre os serviços dentro de um grupo específico. Deste modo, voltando ao exemplo anterior, uma vez que o SharePoint e o Salesforce foram colocados no mesmo grupo de dados, os fluxos que os utilizadores finais criam podem partilhar dados entre o SharePoint e o Salesforce. Da mesma forma, os utilizadores finais podem criar fluxos e Power Apps que partilham dados entre o Facebook e o Twitter. O ponto-chave é que os serviços num grupo específico podem partilhar dados, enquanto os serviços em grupos diferentes não podem partilhar dados.  

Além disso, um grupo de dados tem de ser designado como grupo *predefinido*. Inicialmente, o grupo **sem dados de negócios permitidos** é o grupo *predefinido* e todos os serviços encontram-se no grupo de dados. Um Administrador pode alterar o grupo de dados predefinido para o grupo de **dados de negócios apenas**. **Nota**: os novos serviços adicionados ao fluxo são colocados no grupo *predefinido* designado. Por esta razão, recomendamos que mantenha os **dados de negócio não permitidos** como o grupo predefinido e adicione manualmente serviços ao grupo de **dados de negócio apenas** depois de a sua organização ter avaliado o impacto de permitir que os dados de negócio sejam partilhados com o novo serviço.

## <a name="add-services-to-a-data-group"></a>Adicionar serviços a um grupo de dados
Neste passo a passo, vamos adicionar o SharePoint e o Salesforce ao grupo de **dados de negócios apenas** de uma política de prevenção de perda de dados (DLP). 

1. Selecione a hiperligação **+ Adicionar** na caixa do grupo de **dados de negócios apenas** de uma política DLP:    
   ![Adicionar imagem](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Selecione SharePoint e Salesforce e, em seguida, selecione **Adicionar serviços** para adicionar ambos ao grupo de dados de negócio apenas:    
   ![Adicionar imagem de serviços](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Selecione **guardar política** no menu localizado na parte superior:  
   ![Guardar política](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Note que o SharePoint e o Salesforce agora estão no grupo dados de negócio apenas :  
   ![Grupo de dados de negócio atualizado](./media/introduction-to-data-groups/add-to-data-group-3.png)   

Neste passo a passo, adicionou o SharePoint e o Salesforce ao grupo de **dados de negócios apenas** de uma política DLP. Se uma pessoa que faz parte do ambiente da política DLP criar uma aplicação que partilhe dados entre o SharePoint ou o Salesforce e qualquer serviço no grupo de dados **Nenhum dado de negócio permitido**, a aplicação não terá permissão para ser executada.

## <a name="remove-services-from-a-data-group"></a>Remover serviços de um grupo de dados
Uma vez que todos os serviços têm de estar num dos grupos de dados disponíveis, para remover um serviço de um grupo específico, basta adicionar o serviço a outro grupo e, em seguida, guardar a política.  

## <a name="change-the-default-data-group"></a>Alterar o grupo de dados predefinido
Neste passo-a-passo, iremos alterar o grupo de dados predefinido do grupo **sem dados de negócio permitidos** para o grupo de **dados de negócio apenas**.  

**Importante**: os novos serviços adicionados ao fluxo são colocados no grupo *predefinido* designado. Por esta razão, recomendamos que mantenha o grupo **sem dados de negócio permitidos** como o grupo predefinido e adicione manualmente serviços ao grupo de **dados de negócio apenas**.

1. Selecione **...** localizado no canto superior direito do grupo de dados que pretende designar como o grupo de dados predefinido:    
   ![Alterar grupo Predefinido](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Selecionar **Definir como grupo predefinido**:  
   ![Alterar grupo Predefinido](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Selecione **guardar política** no menu localizado na parte superior:  
   ![Alterar grupo Predefinido](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Note que o grupo de dados está agora designado como o grupo de dados predefinido:  
   ![Alterar grupo Predefinido](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Passos seguintes
* [Obter mais informações sobre políticas de prevenção de perda de dados (DLP)](prevent-data-loss.md)
* [Saiba mais sobre os ambientes](environments-overview-admin.md)   

