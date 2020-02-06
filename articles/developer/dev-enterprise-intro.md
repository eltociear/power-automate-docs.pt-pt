---
title: Power Automate para programadores empresariais, ISVs e parceiros | Microsoft Docs
description: Introdução ao desenvolvimento de soluções do Power Automate.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: ca815ad5949da494c1a50c193c040acdd948d3a2
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74362861"
---
# <a name="power-automate-for-enterprise-developers-isvs-and-partners"></a>Power Automate para programadores empresariais, ISVs e parceiros
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Enquanto programador, pode expandir o Power Automate, o que permitirá soluções ainda mais poderosas para as organizações e os clientes.

## <a name="power-automate-for-enterprise-developers"></a>Power Automate para programadores empresariais

Como programador empresarial, permita à sua organização criar soluções personalizáveis robustas no Power Automate:

- **Criar conectores personalizados**: desenvolva conectores personalizados para ligar aos dados e serviços Web da sua organização através do Power Automate. [Saiba mais](https://docs.microsoft.com/connectors/custom-connectors/)

- **Criar Funções do Azure**: Crie Funções do Azure para expandir as aplicações com a lógica personalizada do lado do servidor. [Saiba mais](/azure/azure-functions/app-service-export-api-to-powerapps-and-flow)

- **Incorporar o Power Automate**: incorpore o Power Automate diretamente nas experiências dos sites para criar soluções integradas, através de fluxos de trabalho ou processos onde as pessoas na sua organização já fazem o trabalho. [Saiba mais](embed-flow-dev.md)

## <a name="power-automate-for-isvs-and-microsoft-partners"></a>Power Automate para ISVs e parceiros Microsoft

Enquanto parceiro da Microsoft ou Fabricante Independente de Software (ISV), pode acelerar a adoção por parte dos clientes ao expandir os seus produtos de forma a integrarem-se nos processos de negócio e dados dos seus clientes. Além disso, pode adicionar e personalizar fluxos de trabalho para automatizar os processos de negócio como parte da sua aplicação. Após concluir os sete passos abaixo, a sua aplicação poderá tirar partido de um motor de fluxo de trabalho robusto à escala da cloud, com capacidade de ligar a mais de 200 serviços diferentes.

| Fase | Passo | Quando é que é necessário? |
| --- | --- | --- |
| Desenvolvimento | 1. Criar um conector personalizado para os seus dados | Se quiser expor os dados de ISV ao Power Apps ou Power Automate |
| Desenvolvimento | 2. Adicionar suporte na sua aplicação para autenticar utilizadores com o Azure Active Directory (Azure AD) | Se quiser incorporar a IU do Power Automate ou criar uma listagem no Microsoft AppSource | 
| Desenvolvimento | 3. Incorporar a IU do Power Automate na aplicação com a nossa iframe baseada na Web | Se quiser incluir a criação ou gestão de fluxos na sua aplicação | 
| Desenvolvimento | 4. Criar e publicar modelos de fluxos | Se quiser pré-criar fluxos para os seus clientes | 
| Desenvolvimento | 5. Adicionar lógica de aplicação para implementar fluxos de forma programática | Se quiser implementar automaticamente os seus modelos de fluxos para os seus clientes | 
| Distribuição | 6. Conceder licenças do Microsoft Flow aos seus clientes através do programa Fornecedor de Soluções Cloud da Microsoft | Se os seus clientes não tiverem licenças do Office 365 ou do Dynamics 365 |
| Distribuição | 7. Listar a sua solução no Microsoft AppSource | Recomendado para aumentar a visibilidade da sua solução de ISV |

### <a name="1-connecting-to-your-apis-or-enabling-customers-to-connect-to-your-apis"></a>1. Ligar às suas APIs OU Permitir que os seus clientes liguem às suas APIs

Enquanto ISV, tem frequentemente dados de proprietário aos quais pretende que os seus clientes acedam através dos seus fluxos. Pode expor o acesso aos seus dados através de um conector personalizado. [Saiba mais](https://docs.microsoft.com/connectors/custom-connectors/)

Após ser criado, existem duas formas de tornar um conector disponível para os seus clientes:
- O conector pode ser implementado no inquilino do cliente através de APIs REST ou do PowerShell.
- Para tornar o conector personalizado publicamente disponível para todos os utilizadores, pode submeter o seu conector para certificação. [Saiba mais](https://docs.microsoft.com/connectors/custom-connectors/submit-certification)

### <a name="2-authentication"></a>2. Autenticação 

Para chamar APIs REST e incorporar IU autenticada, a sua aplicação precisa de utilizar o início de sessão único federado do Azure AD para autenticar utilizadores finais e clientes. [Clique aqui](https://identity.microsoft.com/) para obter informações sobre como ativar o SSO federado do AAD. Não temos suporte para o acesso não autenticado ou acesso com outros fornecedores de identidade que não o Azure AD. 

### <a name="3-embedding-ui-components"></a>3. Componentes de incorporação de IU

Incorpore o Power Automate na aplicação para ativar a integração contextual aprofundada entre a aplicação e todos os outros serviços suportados pelo Power Automate. [Saiba mais](embed-flow-dev.md)

### <a name="4-create-and-publish-flow-templates"></a>4. Criar e publicar modelos de fluxos

Depois de ter um conector, deve publicar modelos que demonstrem como utilizar o seu serviço. Estes modelos irão servir de exemplos que os utilizadores podem utilizar para conhecerem e expandirem os seus próprios fluxos de trabalho exclusivos. [Saiba mais](../publish-a-template.md)

### <a name="5-deployment"></a>5. Implementação

Para dar aos utilizadores finais acesso a fluxos que os mesmos possam utilizar automaticamente, implemente os fluxos no inquilino do Azure AD do utilizador. Utilize um pacote de implementações com as nossas APIs REST ou o PowerShell. [Saiba mais](https://docs.microsoft.com/powerapps/export-import-packages)

### <a name="6-licensing"></a>6. Licensing

Se os seus clientes já tiverem o Office 365 ou o Dynamics 365 e estas licenças estiverem associadas às identidades com que os utilizadores iniciam sessão no Azure AD, não existem requisitos de licenciamento adicionais para si. No entanto, se os seus clientes não utilizarem o Office 365 ou o Dynamics 365, terá de adquirir os direitos de utilização do Power Automate em nome deles, para que tenham licença para tirar partido desses componentes incorporados na aplicação.

Oferecemos o programa [Fornecedor de Soluções Cloud da Microsoft](https://partner.microsoft.com/cloud-solution-provider) para que possa adquirir licenças em nome dos seus clientes. Existem dois [planos de preços](https://flow.microsoft.com/pricing/) disponíveis para o Power Automate, que deverá consultar para obter detalhes sobre o planeamento e as funcionalidades.

### <a name="7-list-on-appsource"></a>7. Listar no AppSource

Depois de ter integrado o Power Automate na aplicação, poderá listá-la no AppSource. Com o AppSource, pode gerar novas oportunidades potenciais para a sua empresa ao criar uma aplicação e ao publicá-la no AppSource para ser testada pelos novos clientes. [Saiba mais](dev-appsource-test-drive.md)
