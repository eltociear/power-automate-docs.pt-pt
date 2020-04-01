---
title: Limites e valores de configuração | Microsoft Docs
description: Limites e configuração
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/26/2020
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 959b7876426a78ae86bebe998332fc1846f7421e
ms.sourcegitcommit: 7821cc858dc3fc51e3a44f1fc0c1f83962de8a2c
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/28/2020
ms.locfileid: "80375810"
---
# <a name="limits-and-configuration-in-power-automate"></a>Limites e configuração no Power Automate

Este tópico contém informações sobre os limites atuais e os detalhes de configuração dos fluxos.

## <a name="request-limits"></a>Limites de pedido
Estes são os limites de um único pedido de saída.

### <a name="timeout"></a>Tempo limite

| Nome | Limite |
| --- | --- |
| Tempo Limite do Pedido para chamadas síncronas |120 Segundos |
| Tempo Limite do Pedido para chamadas assíncronas|Configurável. Máximo de 30 dias. |

### <a name="message-size"></a>Tamanho da mensagem

| Nome | Limite | Notas |
| --- | --- | --- |
| Tamanho da mensagem |100 MB |Nem todas as APIs suportam os 100 MB completos. |
| Limite de avaliação da expressão |131 072 carateres |`@concat()`, `@base64()`, `string` não podem exceder este limite. |

### <a name="retry-policy"></a>Política de repetição

| Nome | Limite |
| --- | --- |
| Tentativas de repetição |90 | A predefinição é 4. Alterar as definições de ação de utilização predefinidas | 
| Intervalo máx. de repetição |1 dia | |
| Intervalo mín. de repetição |5 segundos | |

## <a name="run-duration-and-retention"></a>Duração da execução e retenção
Estes são os limites de uma única execução de fluxo.

| Nome | Limite | Notas |
| --- | --- | --- |
| Duração da execução |30 dias |Inclui os fluxos de trabalho com passos pendentes, como aprovações. Após 30 dias, todos os passos pendentes excedem o tempo limite. As aprovações cujo tempo limite foi excedido são removidas do centro de aprovações. Se alguém tentar aprovar um pedido cujo tempo limite foi excedido, receberá uma mensagem de erro. |
| Retenção de armazenamento |30 dias |Isto é a partir da hora de início da execução. |
| Intervalo de periodicidade mínimo |1 minuto | |
| Intervalo de periodicidade máximo |500 dias | |
| Retenção máxima do histórico de execuções |28 dias, conforme regras do GDPR. | |
|Intervalo mínimo de adiamento – Licença Gratuita e Plano 1|5 segundos||
|Intervalo mínimo de adiamento – Licença Plano 2|1 segundo||

## <a name="looping-and-debatching-limits"></a>Ciclos e limites de anulação de lotes
Estes são os limites de uma única execução de fluxo. Para saber os limites diários, veja [Requests limits and allocations](https://aka.ms/platformlimits) (Limites e alocações de pedidos).

| Nome | Limite | Notas |
| --- | --- | --- |
| Aplicar a cada item – Licenças do Office 365 e Gratuitas|5000 |Pode utilizar a ação de filtro para filtrar matrizes maiores, consoante as suas necessidades. |
| Aplicar a cada item – Licenças Plano 1, Plano 2, Por Utilizador e Por Fluxo|100.000 |Pode utilizar a ação de filtro para filtrar matrizes maiores, consoante as suas necessidades. |
| Iterações Until |5000 | |
| Itens SplitOn – Licenças do Office 365 e Gratuitas |5000 ||
| Itens SplitOn – Licenças Plano 1, Plano 2, Por Utilizador e Por Fluxo |100.000 ||
| Aplicar a cada Paralelismo |50 |Por predefinição, os ciclos são executados em sequência (essencialmente, o paralelismo é 1). Pode configurar até 50 paralelamente. |
| Execuções de ações por 5 minutos – Licenças Gratuita, Office 365, Plano 1 e versões de avaliação | 2000 | Além disso, pode distribuir uma carga de trabalho em mais do que um fluxo, conforme necessário. |
|Execuções de ações por 5 minutos – Licenças Plano Pago 2, Por utilizador e Por fluxo|100.000|Além disso, pode distribuir uma carga de trabalho em mais do que um fluxo, conforme necessário.|
| Chamadas efetuadas de ações em simultâneo – Licenças Gratuita, Office 365, Plano 1 e versões de avaliação | ~500 | Reduza o número de pedidos simultâneos ou reduza a duração, conforme necessário. |
| Chamadas efetuadas de ações em simultâneo – Licenças Plano 2, Por Utilizador e Por Fluxo | ~2500 | Reduza o número de pedidos simultâneos ou reduza a duração, conforme necessário. | 

## <a name="throughput-limits"></a>Limites de débito

|Nome|Limite|Notas|
|---|---|---|
|Ponto final de runtime – Número de chamadas de leitura permitidas por 5 minutos – Licenças Gratuita, Office 365, Plano 1 e versões de avaliação|6000||
|Ponto final de runtime – Número de chamadas de leitura por 5 minutos – Licenças Plano Pago 2, Por Utilizador e Por Fluxo|60 000||
|Ponto final de runtime: chamadas de invocação por 5 minutos – Licenças Gratuitas, Office 365, Plano 1 e versões de avaliação|4500||
|Ponto final de runtime: número de chamadas de invocação por 5 minutos – Licenças Pagas do Plano 2, Por Utilizador e Por Fluxo|45 000||
|Quantidade de débito permitido por 5 minutos – Licenças Gratuita, Office 365 e Plano 1 e versões de avaliação|600 MB||
|Quantidade de débito permitido por 5 minutos – Licenças Plano Pago 2, Por Utilizador e Por Fluxo|6 GB||
|Quantidade de fluxos de conteúdo que estão autorizados a produzir (entradas/saídas de ações) por hora – Licenças Gratuita, Office 365, Plano 1, Plano 2, Por Utilizador e Por Fluxo|200 GB||


## <a name="definition-limits"></a>Limites de definição
Estes são os limites de um único fluxo.

| Nome | Limite | Notas |
| --- | --- | --- |
| Ações por fluxo de trabalho |500|Pode adicionar fluxos de trabalho aninhados para expandir conforme necessário. |
| Profundidade de aninhamento de ação permitida |8 |Pode adicionar fluxos de trabalho aninhados para expandir conforme necessário. |
| Máximo de carateres por expressão |8192 | |
| `action`/`trigger` limite de nome |80 | |
| `description` limite de comprimento |256 | |

## <a name="sharepoint-limits"></a>Limites do SharePoint
Existem [limitações](https://docs.microsoft.com/connectors/sharepointonline/#limits) sobre como pode utilizar o Microsoft SharePoint com o Power Automate e o Power Apps.

## <a name="ip-address-configuration"></a>Configuração do endereço IP
O endereço IP a partir do qual os pedidos do Power Automate são enviados depende da [região](regions-overview.md) onde o [ambiente](environments-overview-admin.md) que contém o fluxo se encontra. De momento, não publicamos FQDNs disponíveis para cenários de fluxo.

>[!IMPORTANT]
> Algumas chamadas feitas por um fluxo podem ser provenientes de endereços IP que estão listados na documentação do [Logic Apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses). Alguns exemplos destas chamadas incluem HTTP ou HTTP + OpenAPI.

### <a name="logic-apps"></a>Logic Apps
As chamadas feitas a partir de um fluxo passam diretamente pelo serviço de Aplicação Lógica do Azure. Alguns exemplos destas chamadas incluem HTTP ou HTTP + OpenAPI. Consulte a [documentação do Logic Apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) para saber quais são os endereços IP utilizados por esse serviço.

### <a name="connectors"></a>Conectores
As chamadas feitas a partir de um conector num fluxo (por exemplo, a API SQL ou a API do SharePoint) serão provenientes do endereço IP listado abaixo:

| Region | IP de saída |
| --- | --- |
| Ásia-Pacífico | 13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19 |
| Austrália  | 13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174 |
| Canadá | 13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152|
| Europa | 13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 137.117.161.181 |
| Índia  | 104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218 |
| Japão | 13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248 |
| América do Sul | 191.233.203.192 - 191.233.203.207, 104.214.19.48 - 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Reino Unido | 51.140.148.0 - 51.140.148.15, 51.140.80.51, 51.140.211.0 - 51.140.211.15, 51.141.47.105 |
| Estados Unidos | 13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49|
| Pré-visualização (Estados Unidos)  | 13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157 |

Por exemplo, se tiver de autorizar endereços IP para a sua base de dados SQL do Azure, deve utilizar estes endereços.

### <a name="required-services"></a>Serviços necessários
A tabela seguinte lista os serviços ao qual se liga o Power Automate. Certifique-se de que nenhum destes serviços estão bloqueados na sua rede.

Domínios | Protocolos | Utiliza
--------|  ---------| -----
management.azure.com|https|Aceder ao Azure Resource Manager.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Acesso à Biblioteca de Autenticação do Active Directory (ADAL).
graph.microsoft.com </br>graph.windows.net</br>|https|Acesso à API do Azure AD Graph - para obter informações do utilizador, como uma fotografia do perfil.
*.azure-apim.net|https|Acesso ao Runtime para os Conectores.
*.flow.microsoft.com|https|Acesso ao site do Power Automate.
*.powerapps.com|https|Acesso ao site do Power Apps.
*.azureedge.net|https|Acesso à CDN do Power Automate.
nps.onyx.azure.net|https|Acesso ao NPS (Net Promoter Score).
webshell.suite.office.com|https|Acesso ao Office para cabeçalho e pesquisa. Veja [os URLs e os intervalos do Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) para obter mais detalhes
