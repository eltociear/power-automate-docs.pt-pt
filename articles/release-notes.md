---
title: Notas de versão | Microsoft Docs
description: Problemas comuns e novidades nas versões do Power Automate
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
ms.date: 08/31/2018
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e617e6928d5295a9485c55e1efa57a945abf870f
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "74374315"
---
# <a name="release-notes"></a>Release notes
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="top-questions"></a>Principais perguntas?
1. O meu fluxo falhou. Como posso corrigi-lo?
   
   1. Identifique a falha. Comece por ir ao ícone de notificações na parte superior do portal Web ou por selecionar o separador **Atividade** na aplicação móvel. Deverá ver aí o seu fluxo e poderá selecioná-lo.
   2. Agora, está a ver os detalhes do fluxo. Localize o passo com o ícone de exclamação vermelho para ver aí a mensagem de erro do seu fluxo.
   3. Dependendo da mensagem de erro, deverá conseguir **Editar** o fluxo e corrigi-lo. [Saiba mais sobre como corrigir falhas comuns do fluxo](fix-flow-failures.md).
2. Como utilizo uma condição avançada ou uma expressão?
   
   * Saiba mais sobre como [adicionar condições](add-condition.md).
   * Se quiser vários casos num fluxo, selecione **Adicionar condição** dentro de uma condição existente.
   * Crie uma expressão avançada ao referenciar [uma função no Logic Apps](https://docs.microsoft.com/rest/api/logic/definition-language).
3. Como funciona o licenciamento com o Office 365?
   
   * Se for utilizador do Office 365, obterá acesso total através do plano Power Automate para Office 365. Para obter mais informações, veja os [planos de preços do Power Automate](https://flow.microsoft.com/pricing/).
   * Se for um administrador, veja as informações sobre o [licenciamento do Power Automate](organization-q-and-a.md), incluindo com o Office 365.

## <a name="known-issues"></a>Problemas conhecidos
1. As listas do SharePoint em Os Meus Sites e que não são do tipo *Lista Personalizada* não são suportadas. A solução deste problema consiste em criar uma lista personalizada num site do SharePoint padrão.
2. Os acionadores de ficheiro não serão acionados para os ficheiros que estão a ser adicionados dentro de pastas aninhadas dentro da pasta selecionada.

## <a name="whats-new"></a>Novidades

> [!IMPORTANT]
>
> **Anúncio das notas de versão**
>
> Está curioso relativamente às funcionalidades futuras e lançadas recentemente no Power Automate?
>[Veja as notas de versão de outubro de 2018](https://docs.microsoft.com/business-applications-release-notes/October18/microsoft-flow/). Recolhemos, de forma específica e rigorosa, todos os detalhes que pode utilizar para planeamento. Para obter mais detalhes, veja [cada versão semanal](https://docs.microsoft.com/business-applications-release-notes/powerplatform/released-versions/flow) com as funcionalidades e os melhoramentos que esta contém.
>
> As notas de versão anteriores à versão de outubro de 2018 vão permanecer aqui para referência futura, mas as novas versões apenas serão incluídas nas localizações acima e não nesta página.

### <a name="release-2018-09-24"></a>Versão de 24-09-2018

- **Acesso de administrador à ajuda e ao suporte** – abra pedidos de suporte para o Power Automate no centro de administração da plataforma Power e indique detalhes adicionais sobre a falha do fluxo de trabalho.
- **Comunidade do Flow reestruturada** – é agora mais fácil encontrar o que precisa na Comunidade do Flow.
- **Melhoramentos no conector do Microsoft Teams** – novos acionadores para o Microsoft Teams para que possa executar um fluxo quando existirem novas mensagens num canal.
- **Mais ações do SharePoint** – existem novas ações para mover ficheiros e mais no conector do SharePoint.
- **Novos relatórios de análise de administrador** – análise ao nível do Ambiente e do Inquilino adicionada ao Centro de administração da Plataforma de Aplicações Empresariais.
- **Integração do Power Query** – está a ser criada uma experiência do Power Query que vai permitir que os criadores formem mashups de dados a partir do SQL Server.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/support-tickets-teams-sharepoint/) sobre esta versão.

### <a name="release-2018-08-31"></a>Versão 2018-08-31

- **Teste o fluxo ao utilizar dados de exemplo** – utilize dados de exemplo de conectores para testar o fluxo à medida que o cria a partir do estruturador do Power Automate. Ao testar o seu fluxo com dados de exemplo, está a confirmar que o fluxo será executado conforme esperado quando for implementado para produção.
- **Cinco novos conectores** – adicionamos cinco novos conectores de gestão: Power Apps for App Makers, Power Platform for Admins, Power Apps for Admins, Power Automate for Admins e Microsoft School Data Sync.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/test-data-management-connectors/) sobre esta versão.

### <a name="release-2018-08-24"></a>Versão 2018-08-24

- **Novos modelos de sincronização do calendário** – novos modelos de calendário que copiam eventos entre o Calendário Google e o Office 365 ou Outlook.com.
- **Suporte de múltiplos valores para o SharePoint** – leitura e escrita para campos de múltiplos valores no SharePoint que são do tipo Escolha, Pessoa ou Pesquisa.
- **Enviar aprovações em nome de outros utilizadores na sua organização** – envie aprovações em nome de outros utilizadores na sua organização, por exemplo, a pessoa que carregou o ficheiro na lista do SharePoint em vez da pessoa que criou o fluxo.
- **Mais tipos de entrada de botões** – os botões têm dois novos tipos de entrada: Número e Sim/Não.
- **Atualizações de conector** – um novo conector NetDocuments, melhorias dos conectores do Azure e muito mais.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/button-types-more/) sobre esta versão.

### <a name="release-2018-08-02"></a>Versão 2018-08-02

O programa de Pré-visualização do Power Automate é a forma de aceder antecipadamente às futuras funcionalidades e atualizações do Power Automate. Para aceder antecipadamente às mais recentes funcionalidades, basta criar e utilizar um ambiente na região de Pré-visualização.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/flow-preview-program/) sobre esta versão.

### <a name="release-2018-07-23"></a>Versão 2018-07-23

- **Criar e executar fluxos no Excel** – com o novo botão **Fluxo** (acedido no separador **Dados** do friso), pode criar e acionar automatizações do Power Automate nos dados da tabela no Excel. Automatize o processamento de dados ou a cópia/importação de dados.
- **Criar um fluxo de processo de negócio** – um fluxo de processo de negócio é um novo tipo de fluxo dinâmico e de interação humana com base no Common Data Service. Utilize estes novos fluxos para definir um conjunto de fases e passos para as pessoas a seguir. Podem ser movidos para frente e para trás, conforme seja preciso.
- **Criar um fluxo para o Microsoft To-Do no Outlook Web App** – Se alguém for \@mencionado no Outlook Web App, verá um atalho para criar um fluxo. Este fluxo cria automaticamente tarefas para a \@pessoa mencionada no Microsoft To-Do, com base no conteúdo da mensagem de e-mail.
- **Suporte de vista do SharePoint** – O conector do SharePoint agora apoia a seleção de uma vista do SharePoint específica sobre os acionadores e ações. Este procedimento filtra as colunas para apenas os campos que estão na vista selecionada.
- **Quatro novos conectores** – Adicionado o Azure IoT Central – uma solução de software-como-serviço (SaaS) altamente dimensionável da IoT – Survey 123, LMS365 e ProjectWise Design Integration.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/excel-bpf-todo-and-more/) sobre esta versão.

### <a name="release-2018-06-29"></a>Versão 2018-06-29

- **Fluxo de pedido de aprovação incorporado no SharePoint** – Quando seleciona um ficheiro ou item no SharePoint, verá um novo fluxo **Pedido de aprovação**. Este fluxo não requer qualquer tipo configuração ou definição e envia um pedido de aprovação com um único clique.
- **Dois novos conectores** – Adicionado o Cloud Connect Studio e o PoliteMail.
- **Melhorias no histórico e a página de criação** – Vamos atualizar lista do Histórico de execuções ao incluir runtimes exatos e a página de criação por adicionou um novo vídeo de instruções.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/request-sign-off-four-connectors/) sobre esta versão.

### <a name="release-2018-06-08"></a>Versão 2018-06-08

- **Cmdlets do PowerShell** – Os criadores de fluxos e os administradores de inquilinos já podem utilizar o PowerShell para gerir os seus Fluxos de forma programática.
- **Melhorias ao bot de Fluxo de Equipas** – O bot de Fluxo de Equipas no Microsoft Teams pode executar botões de fluxo e descrever os seus fluxos.
- **Três novos conectores** – Foi adicionado suporte ao Marketo, ao ElasticOCR e ao DynamicSignal. 
- **Informações Adicionais de Partilha** – Foram adicionadas mais informações quando partilha – ou executa fluxos partilhados, para que saiba exatamente quais as permissões que as outras pessoas recebem.
- **URLs do SharePoint de limitação automática** – Quando copia e cola um URL do SharePoint no browser que pode conter texto adicional além do site, este texto será removido automaticamente, de modo a poder ligar-se apenas ao site.
- **Documentação sobre pedidos do RGPD** – Criamos um guia abrangente e um conjunto de ferramentas para que as organizações empresariais possam processar pedidos de Direitos dos Titulares dos Dados.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/powershell-flow-bot-marketo/) sobre esta versão.

### <a name="release-2018-05-21"></a>Versão 2018-05-21

- **Fluxos "propriedade de" listas e bibliotecas do SharePoint** – os fluxos que funcionam com listas e bibliotecas do SharePoint podem ser partilhados com essas listas ou bibliotecas. Por isso, em vez de serem partilhados com utilizadores individuais ou grupos, são partilhados com todas as pessoas que têm acesso à lista. Quando os utilizadores são adicionados ou removidos da lista ou da biblioteca, a respetiva associação é também alterada automaticamente.
- **Análise de detalhes de erros** – um novo relatório incorporado que fornece informações sobre todos os erros que ocorrem num fluxo.
- **Partilhar fluxos com grupos do Office 365** – pode tornar um grupo moderno do Office 365 proprietário de um fluxo e pode partilhar fluxos de botões com grupos do Office 365, para que qualquer pessoa no grupo possa executar o fluxo.
- **Melhorias no conector do SharePoint** – existem duas novas funcionalidades do conector de SharePoint: acionar fluxos quando são eliminados itens ou ficheiros e chamar qualquer ponto final de HTTP que suporte a API REST do SharePoint.
- **Dois novos conectores** – foi adicionado suporte para o Azure Data Factory e o MailParser

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/share-with-sharepoint-office-365/) sobre esta versão.

### <a name="release-2018-05-01"></a>Versão 2018-05-01

- **Texto formatado nas mensagens de Aprovação** – utilize Markdown para formatar os detalhes de aprovação que envia.
- **Botões com entradas de seleção múltipla**  – crie botões de fluxo que utilizem uma lista de seleção múltipla para recolher mais do que um valor de cada vez.
- **Trabalhar com fluxos mais amplos** – a aplicação móvel do Power Automate agora suporta a vista horizontal e o estruturador Web tem uma barra de deslocamento horizontal.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/rich-approvals-text-and-multiselect/) sobre esta versão.

### <a name="release-2018-04-12"></a>Versão 2018-04-12

- **Devolver dados de um fluxo para o Power Apps** – crie fluxos que possam ser chamados a partir de uma aplicação criada com o Power Apps e devolver os dados à aplicação. Utilize o estruturador de fluxos visual de arrastar e largar para criar a lógica de que precisa para as suas aplicações. 
- **Adicionar múltiplos registos a entradas de matriz** – adicionámos um construtor de listas ao Power Automate que pode ser utilizado para adicionar múltiplos anexos a um e-mail, por exemplo.
- **Testar fluxos com dados executados anteriormente** – adicionámos um novo botão Testar fluxo ao estruturador que lhe permite testar o seu fluxo com dados de acionador de execuções de fluxos anteriores.
- **Novos campos workflow()** – agora pode aceder ao nome do ambiente e nome a apresentar do fluxo com a expressão workflow().

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/return-data-to-powerapps/) sobre esta versão.

### <a name="release-2018-04-04"></a>Versão 2018-04-04

- **Aprovações no Common Data Service** – as aprovações modernas estão incorporadas na versão mais recente do Common Data Service. Isto significa que pode criar fluxos que leem o estado das aprovações que enviar ou receber com o conector do Common Data Service.
- **Encontrar erros na ação de ciclo Aplicar a cada um** – avance diretamente para os erros em ciclos na vista de execução do fluxo, mesmo se existirem centenas de itens no ciclo.
- **Reatribuir aprovações** – pode atribuir uma aprovação que recebeu a outra pessoa na sua organização para lhe delegar a aprovação. 
- **Listas de salas** – o conector do Outlook do Office 365 adicionou ações para obter dados de salas na sua organização.
- **Ver detalhes de botões de fluxos** – ao executar um fluxo que tenha sido partilhado consigo, agora pode ver todas as ações que o fluxo utiliza.
- **Região do Reino Unido** – agora os ambientes podem ser criados para armazenar os respetivos dados no Reino Unido.
- **Dois novos conectores** –adicionámos suporte para o AtBot Admin e Marketing Content Hub.
- **Nova página de destino da documentação** – atualizámos a página de destino da documentação para ter conteúdos agrupados de acordo com o utilizador, quer seja principiante, intermédio ou avançado. 

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/approvals-in-cds-and-seven-updates/) sobre esta versão.

### <a name="release-2018-03-13"></a>Versão 2018-03-13

- **Histórico de aprovações** – veja todos os pedidos de aprovação que enviou, incluindo as respostas, os comentários enviados e a hora exata em que ocorreram.
- **Quatro novos conectores** – adicionámos o Excel Online (Empresas), Excel Online (OneDrive), Azure SQL Data Warehouse e Pitney Bowes Tax Calculator.
- **Descrições de conteúdos dinâmicos** – paire o cursor sobre conteúdos dinâmicos para ver a respetiva origem nas ações e pré-visualize expressões sem ter de abrir o editor de expressões completo.
- **Controlo de simultaneidade** – ative o controlo de simultaneidade para fazer com que um determinado fluxo tenha apenas uma execução de cada vez.
- **Repetição exponencial** – um novo tipo de política de repetição que separa as repetições de forma exponencial ao longo do tempo.
- **Conformidade de acessibilidade** – lançámos novos documentos de conformidade que descrevem como o Power Automate cumpre os padrões de acessibilidade.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/approval-history-accessibility/) sobre esta versão.

### <a name="release-2018-02-09"></a>Versão 2018-02-09

- **Elevada Disponibilidade do Gateway** – crie clusters de elevada disponibilidade de gateways de dados no local para manter as ligações ativas quando os computadores individuais ficam inativos.
- **Melhorada a opção Aplicar a cada** – com o Plano Flow 1 ou o Plano Flow 2, processe até 100 000 itens numa execução única e 50 ações em paralelo em ciclos Aplicar a cada. 

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/) sobre esta versão.

### <a name="release-2018-01-29"></a>Versão 2018-01-29

- **Fluxo dentro do Microsoft Teams** – no Teams, pode criar e gerir fluxos, rever as aprovações recebidas e enviadas e iniciar fluxos diretamente na aplicação de ambiente de trabalho Teams ou em teams.microsoft.com – [saiba mais aqui](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/).
- **Notificações de edição partilhadas** – sempre que um fluxo seu for alterado por um colega, receberá uma notificação por e-mail a informá-lo de quem alterou determinado fluxo.
- **Novas expressões** – foram adicionados dois novos conjuntos de expressões: um para analisar URLs e outro para trabalhar com objetos JSON.
- **Três novos conectores** – esta semana, existem dois novos conectores Plumsail: Plumsail SP e Plumsail Forms e um novo conector para kintone.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/shared-notifications-and-expressions/) sobre esta versão.

### <a name="release-2018-01-17"></a>Versão 2018-01-17

- **Informações de perfil do Office 365** – adicionamos novas ações ao conector Utilizadores do Office 365 que funcionam com os perfis e as fotografias dos utilizadores.
- **Acrescentar a variáveis de cadeia** – pode adicionar a cadeias dentro de ciclos para criar tabelas ou outras listas.
- **Conector Infobip** – o Infobip é um serviço que permite a comunicação de nível empresarial, incluindo chamadas de voz e o acionamento na receção de SMS.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/o365-profile-infobip/) sobre esta versão.

### <a name="release-2017-12-20"></a>Versão 2017-12-20

O Power Automate Analytics está agora disponível em todas as regiões do Power Automate, ou seja, pode obter mais informações sobre o estado de funcionamento dos fluxos executados no ambiente.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/) sobre esta versão.


### <a name="release-2017-12-14"></a>Versão 2017-12-14

- **Melhorias do conector do Outlook** - pode guardar um e-mail como um ficheiro ".eml", responder automaticamente a convites de calendário e acionar fluxos quando é mencionado num thread de e-mail.
- **Melhorias das ligações** –o Power Automate lembra-se das ligações mais utilizadas por si e mostra-lhe todos os conectores recentemente adicionados.
- **Cinco novos conectores** - Instâncias de Contentor do Azure, Azure Kusto, Metatask, Microsoft To-Do e Plumsail Documents adicionados.
- **Melhorias do HTTP** - a ação do HTTP suporta agora codificação segmentada.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/outlook-connector-more/) sobre esta versão.

### <a name="release-2017-12-05"></a>Versão 2017-12-05

O Painel de Iniciação do Power Automate está agora disponível em todas as regiões. Este painel permite-lhe adicionar valores a um fluxo ao executá-lo na sua lista do SharePoint ou na biblioteca de documentos.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/) sobre esta versão.


### <a name="release-2017-11-28"></a>Versão 2017-11-28

- **Metadados Geridos** - leia dados e escreva em colunas no SharePoint que utilizam o tipo de Metadados Geridos (também conhecido como Taxonomia).
- **Acrescentar a Matrizes** - adicione itens ao fim das matrizes com um novo Anexo à ação variável de matriz.
- **Tago** - um novo conetor ao Tago, que oferece uma ligação simples dos dispositivos eletrónicos com dados externos para conduzir a decisões mais inteligentes com a análise contextual.
- **iPhone X** – uma nova versão da aplicação Power Automate que utiliza o ecrã completo no iPhone X e que tem uma melhoria de velocidade para carregamentos de imagem.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/managed-metadata-tago/) sobre esta versão.

### <a name="release-2017-11-09"></a>Versão 2017-11-09

- **Integração do OneDrive para Empresas** - existe [agora um botão de fluxo no OneDrive para Empresas](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/) que pode criar o acionar fluxos nos ficheiros e pastas selecionados.
- **Acionadores do Planner** - comece fluxos quando é criada uma nova tarefa, quando uma tarefa está atribuída a si ou quando uma estiver concluída.
- **Anexos do SharePoint** - trabalhe com anexos em itens de lista do SharePoint: listar, transferir, adicionar ou eliminar anexos.
- **Conector de gestão do fluxo** - crie fluxos que automatizam a gestão de outros fluxos no seu ambiente (por exemplo, adicionar permissões a fluxos automaticamente).
- **Quatro novos conectores** - Serviço de Visão Personalizada do Azure, D&B Optimizer, Enadoc e Derdak SIGNL4 adicionados. 
- **Mais ações de conector** - execute consultas de SQL, obtenha acionadores de e-mail mais rápidos, utilize qualquer método com HTTP com o Azure AD e muito mais.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/) sobre esta versão.

### <a name="release-2017-11-02"></a>Versão 2017-11-02

- **Registo de Auditoria** – os eventos de auditoria do Power Automate estão agora disponíveis no Centro de Segurança e Conformidade do Office 365 para todos os inquilinos.
- **Correções de widget de fluxo** - corrigiu um problema na aplicação móvel do Flow que fez com que os botões deixassem de carregar no widget.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/security-and-compliance-center/) sobre esta versão.

### <a name="release-2017-10-19"></a>Versão 2017-10-19

- **Aplicação aninhada em cada** – pode adicionar a aplicação a cada ação, filtrar e selecionar noutras aplicações a cada ação de contentor.
- **Ações de Data/Hora** - novas ações para obter horas locais, adicionar, subtrair ou formatar horas.
- **Quatro novos conectores** - Moderador de Conteúdo, Docparser, Microsoft Kaizala e Validação de Dados de Pitney Bowes adicionados.
- **Experiência de ligação melhorada** – notificações no portal do Power Automate quando uma ligação está quebrada e detalhes de ligação mais completos.
- **Coleção em qualquer lugar** - uma nova coleção de modelo para [trabalhadores sempre em movimento](https://flow.microsoft.com/collections/onthego/).
- **Entradas de botão do endereço de e-mail** - recolhe endereços de e-mail dos utilizadores quando executam botões.
- **Entradas de botão de ficheiros** - obter ficheiros carregados, como fotografias, dos utilizadores quando executam botões.
- **Primeira execução e início de sessão automático** - experiências de primeira execução melhoradas na aplicação móvel, incluindo o início de sessão automático.
- **Acionadores do Microsoft Forms mais rápidos** - o Forms vai acionar fluxos muito mais rapidamente do que antes (anteriormente uma vez por hora).
- **Entradas de botão entre sessões** - os botões acionados no seu telemóvel irão lembrar-se das entradas anteriores.
- **Feed de atividades móvel** - feed de atividades melhorado para incluir resumos de execução mais detalhados e detalhes de resolução de problemas.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/nested-apply-to-each/) sobre esta versão.

### <a name="release-2017-10-03"></a>Versão 2017-10-03

- **Todos têm de aprovar** - necessita de um pedido de aprovação enviado para mais do que uma pessoa para que todas as pessoas que receberam o pedido aprovem.
- **Novas ações do OneDrive para Empresas** - gere PDFs para ficheiros armazenados no OneDrive para Empresas e quatro outras novas ações.
- **Conector Apache Impala** - o Apache Impala (incubação) é a base de dados de open source e de análise nativa para o Apache Hadoop.
- **Adicionar descrições de fluxo** - conceda descrições aos fluxos, para que, quando as partilha com os seus colegas, eles possam ver um resumo do que o fluxo faz.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/) sobre esta versão.

### <a name="release-2017-09-25---q3-update-for-power-automate"></a>Versão 25-09-2017 – atualização do 3.º Trimestre do Power Automate

- **Integração mais profunda do SharePoint na Primeira Versão** - existem novos envios internos para fluxos de revisão e um painel de Fluxo para recolher entradas quando executa um fluxo para inquilinos da primeira versão.
- **Aplicações do Dynamics 365** – o Flow está agora integrado na IU das aplicações do Dynamics 365, como o Dynamics 365 for Sales e o Dynamics 365 for Customer Service.
- **Centro de Confiança da Microsoft** – o Power Automate está listado no Centro de Confiança da Microsoft, que mostra certificações como HIPAA, ISO e SOC.
- **Análise de utilização** - cada fluxo tem um dashboard incorporado do Power BI com análise de utilização básica.
- **Registo de Auditoria na Primeira Versão** - todos os eventos de gestão de fluxo são registados no Centro de Segurança e Conformidade do Office 365 para inquilinos da primeira versão.
- **Seis novos conectores** - LinkedIn, Grupos do Office 365, Skype para Empresas, Adobe Sign, Bizzy e Recolha de Dados do Azure Log Analytics adicionados.
- **Acionadores SQL** - execute fluxos quando é adicionada uma nova linha ou uma linha é atualizada numa tabela SQL.
- **Conectores personalizados no local** - os conectores personalizados podem agora utilizar o gateway de Dados no Local para estabelecer a ligação a pontos finais internos na sua rede.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/q3-2017-update/) sobre esta versão.

### <a name="release-2017-09-21"></a>Versão 2017-09-21

- **Transferir o Histórico do Fluxo** – transfira o histórico de execuções de um fluxo como um ficheiro CSV para abrir no Excel.
- **Periodicidade avançada**  - crie agendamentos periódicos para acionar os fluxos, por exemplo, acionar apenas em dias da semana.
- **IntelliSense** - quando escreve expressões, o IntelliSense irá apresentar sugestões para os parâmetros.
- **Quatro novos conectores** - conectores adicionados para serviços do Azure AD HTTP, Amazon Redshift, Azure Event Grid Publish e FlowForma adicionados.
- **Ligações de partilha** - uma nova ação para gerar ligações partilháveis para ficheiros do OneDrive ou Azure Storage Blobs.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/download-history-recurrence/) sobre esta versão.


### <a name="release-2017-08-25"></a>Versão 2017-08-25
* **Propriedades do documento e muito mais do SharePoint** - [Leia e defina as propriedades da biblioteca de documentos do SharePoint](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/)e utilize campos adicionais, como ligações para o item do SharePoint.
* **Coleções de fluxo** - coleções de fluxo são um conjunto de coleções de modelos organizados por função ou na vertical.
* **"Repartilha" de botões** - quando partilha botões com os seus colegas e estes podem partilhá-los novamente com outras pessoas.
* **Recolher listas de botões** - defina as listas pendentes de opções para os utilizadores à sua escolha quando estes tocam no botão.
* **Sete novos conectores** - AWeber, Azure Log Analytics, Tabelas do Azure, DocFusion365, Azure Event Grid, Hubs de Eventos do Azure e StaffHub. 
* **Melhorias do Slack e do MySQL** - crie ou adira a canais no Slack e pode escrever em bases de dados MySQL.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/button-updates-seven-connectors/) sobre esta versão.

### <a name="release-2017-08-02"></a>Versão 2017-08-02
* **Escrever para os campos Pessoa, Escolha e Pesquisa** - o item de Criação e Atualização do SharePoint [suporta agora a capacidade de](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/) definir os campos Pessoa, Escolha e Pesquisa.
* **Mais definições de ação** - agora tem mais controlo sobre como os acionadores e as ações são executados, incluindo a configuração de políticas de repetição e paginação.
* **Quatro novos conectores** - agora pode utilizar o Armazenamento de Ficheiros do Azure, os Formulários Elásticos, o Plivo e o Video Indexer.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/four-connector-action-settings/) sobre esta versão.

### <a name="release-2017-07-27---q2-update-for-power-automate"></a>Versão 27-07-2017 – Atualização do 2.º Trimestre do Power Automate
* **Importar e exportar** - soluções do fluxo de exportação e importação entre ambientes ou de teste para produção. 
* **Utilizar expressões nas ações** - introduza expressões em qualquer ação e obtenha ajuda inline sobre como utilizá-los.
* **Aumentar para o Azure Logic Apps** - guarde os fluxos como recurso do Azure Logic App que podem ser implementados através do Visual Studio ou do portal do Azure.
* **Visibilidade de administração** – transfira a utilização do Power Automate para o inquilino para compreender exatamente onde e como estão a ser utilizados os fluxos.
* **Fluxos no Dynamics 365** - utilize fluxos dentro do Dynamics 365 para Operações e Finanças, Business Edition.
* **Encontrar cenários mais facilmente** - procure tudo o que esse conector pode fazer e, em seguida, utilize qualquer acionador como ponto de partida para a criação de fluxos.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/q2-2017-update/) sobre esta versão.

### <a name="release-2017-07-13"></a>Versão 2017-07-13
* **Modelo de publicação melhorado** - publique qualquer fluxo criado por si, juntamente com as respetivas categorias, na galeria pública.
* **Obter eventos no seu Calendário do Outlook** - uma nova ação para devolver todos os eventos entre duas vezes no seu calendário.
* **Nova funcionalidade móvel** - execute fluxos a pedido e volte a submeter execuções com falhas na aplicação móvel.
* **Menus suspensos dinâmicos em Conectores personalizados** - crie menus suspensos dinâmicos, acionadores de consultas e teste os seus conectores personalizados.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/publishing-and-custom-connectors/) sobre esta versão.

### <a name="release-2017-06-28"></a>Versão 2017-06-28
* **Atualização das definições de idioma** – pode personalizar o Idioma e a Região que o Power Automate utiliza no menu Definições.
* **Cinco novos conectores** - foi adicionado suporte ao Adobe Creative Cloud, ao Bing Maps, ao Bing Search, ao JotForm e ao Freshservice.
* **Configurar tempos limite** - alterar o tempo de ações de longa duração, como aprovações, antes de terminarem o tempo limite e o fluxo continuar.
* **Incluir comentários no Outlook para aprovações** - quando recebe um pedido de aprovação pode deixar comentários sem sair do Outlook.
* **Personalizar cores de marca do conetor** - já pode introduzir uma cor nos seus Conectores Personalizados que será utilizada nas imagens de fundo.
* **Guardar Como para fluxos de equipa** -faça cópias de quaisquer fluxos, incluindo fluxos de Equipa
* **Eliminar informações de fluxo** - quando eliminar um fluxo, será apresentada a lista de todas as execuções pendentes desse fluxo.
* **Filtragem na página Conectores** -pesquise os conectores que pretende na página Conectores e filtre por tipo de conector.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/language-settings-3-connectors/) sobre esta versão.

### <a name="release-2017-06-19"></a>Versão 2017-06-19
Já pode ver o estado de todos os pedidos de aprovação pendente enviados. Além disso, pode procurar e atuar sobre todas as suas aprovações pendentes diretamente a partir do dispositivo móvel.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/sent-requests-flow-mobile/) sobre esta versão.

### <a name="release-2017-06-15"></a>Versão 2017-06-15
* **Conversão de conteúdo** - um novo conector pode converter conteúdo HTML para texto simples, útil para processar e-mails formatados em HTML.
* **Três novos conectores de base de dados** - suporte só de leitura adicionado para MySQL, PostgreSQL e Teradata. Estes conectores ligam através do gateway de dados No local.
* **Três outros conectores** - ligue ao Azure Application Insights, ao Calendly e ao Teamwork Projects.
* **Melhor visualização para processamento de erros** - os passos que são executados depois dos erros são agora apresentados com setas com pontos vermelhos para que os possa identificar facilmente.
* **Execute o painel de detalhes** - quando um fluxo falha, existe agora um novo painel do lado direito que contém alguns passos úteis para saber como corrigir o fluxo.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/seven-connectors-and-html/) sobre esta versão.

### <a name="release-2017-06-04"></a>Versão 2017-06-04
* **GA para Windows Phone** - [a aplicação móvel do Power Automate foi lançada para Disponibilidade Geral para Windows Phone](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/).
* **E-mails sobre falhas de fluxo** - seja notificado por e-mail quando tiver um fluxo que apresente falhas. Estes e-mails de falha serão apenas enviados uma vez por semana e podem ser ativados ou desativados pelo utilizador.
* **Ação Selecionar para tabelas** - utilize a nova ação Selecionar para alterar o conjunto de colunas que será incluído nas tabelas.
* **Conector do Microsoft Forms** - o Microsoft Forms é uma nova parte do Office 365 Education que permite aos professores e aos alunos criarem quizzes personalizados de forma rápida e simples, inquéritos, questionários, registos e muito mais.
* **Plano do Office 365 Enterprise K1** – o Power Apps e o Power Automate estão agora incluídos no plano do Office 365 Enterprise K1 com determinadas quotas.
* **Os cabeçalhos HTTP são mais fáceis** - tal como a ação Selecionar, pode apresentar um nome e um valor do cabeçalho, basta preencher as caixas de texto na ação.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/) sobre esta versão.

### <a name="release-2017-05-23"></a>Versão 2017-05-23
* **Conector Microsoft Teams** - [O Microsoft Teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/) é uma área de trabalho baseada em chat no Office 365 que junta pessoas, conversas e conteúdos, juntamente com as ferramentas de que as equipas precisam, de modo a que possam colaborar facilmente e obter mais resultados.
* **Widgets em iOS e Android** – os widgets do Power Automate são atalhos de botões que proporcionam uma forma mais fácil e rápida de acionar botões diretamente no ecrã principal.
* **Criar passos de "processamento de erros"** - defina um ou mais passos para execução após uma ação falhar. Por exemplo, receba uma notificação imediatamente se o seu fluxo não conseguir criar um registo no Dynamics 365.
* **Variáveis de número inteiro e número de vírgula flutuante** - inicialize e aumente ou diminua os contadores dentro de execuções de fluxos para contar quantas vezes é que um determinado conjunto de lógica é executado.
* **Página de detalhes de fluxo** - quando seleciona um fluxo na lista **Os meus fluxos**, verá uma página com detalhes acerca desse fluxo, como quem tem acesso e o histórico de execuções.
* **Quotas de execução de fluxos para administradores** - os administradores podem agora monitorizar a utilização das execuções de fluxos numa organização relativamente à quota de execuções empresariais comum e obter uma análise detalhada da quota, para saberem que licenças contribuem para a quota das respetivas organizações.
* **Melhoramentos ao acionador de pedidos HTTP** - utilize métodos HTTP diferentes e adicione segmentos de caminho ao acionador Pedido.
* **Dois conectores de parceiros**  – o Power Automate pode agora ser ligado ao Parserr, um serviço de análise de e-mails, e ao Cognito Forms, um serviço de formulários online.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/error-handling/) sobre esta versão.

### <a name="release-2017-05-12"></a>Versão 2017-05-12
* **Integração de Bibliotecas de Documentos do SharePoint** -pode selecionar qualquer ficheiro numa biblioteca de documentos e iniciar um fluxo, por exemplo para enviá-la ao seu gestor para aprovação, [e muito mais](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/).
* **Conector do Microsoft Planner** - O Microsoft Planner permite-lhe reunir facilmente as equipas, tarefas, documentos, e conversas para obter melhores resultados.
* **Vista de administração das licenças** – os administradores podem ver todas as licenças do Power Automate e do Power Apps (versão de avaliação e paga) no Centro de Administração do Power Automate.
* **Plano da Comunidade do Power Apps** – o plano da Comunidade do Power Apps é um plano gratuito para explorar, aprender e criar competências no Power Apps, Power Automate e Common Data Service.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/planner-community-and-licenses/) sobre esta versão.

### <a name="release-2017-05-09"></a>Versão 2017-05-09
* **Conector do Azure Active Directory** – existe um novo conector para efetuar ações administrativas a partir do Power Automate, incluindo criar utilizadores ou adicioná-los a grupos.
* **Melhoramentos do Outlook do Office 365** – Os fluxos podem agora ser acionados por Caixas de Correio Partilhadas e enviar correio para uma Caixa de Correio Partilhada. Também pode definir ou ler respostas automáticas.
* **Disponível no Canadá** – Agora, pode criar os seus fluxos no Canadá.
* **Criar webhooks de APIs personalizadas** – Os programadores de conectores personalizados podem agora adicionar acionadores às respetivas APIs personalizadas com webhooks.
* **Gerir proprietários de fluxos no centro de administração** – os administradores de ambientes podem gerir os proprietários de fluxos no centro de administração do Power Automate.
* **Referência de documentação do conector** – Temos agora uma [referência completa de conectores em docs.microsoft.com](https://docs.microsoft.com/Connectors/).
* **Dois serviços de parceiros** – foram lançados dois novos serviços de parceiros: Nexmo e Paylocity.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/canada-mailboxes-aad) sobre esta versão.

### <a name="release-2017-04-27"></a>Versão 2017-04-27
* **Construa fluxos com passos paralelos** - crie fluxos com execução paralela: o que significa que pode ter dois ou mais passos em execução exatamente ao mesmo tempo.
* **Cinco novos serviços suportados** – cinco novos serviços: Approvals, Benchmark Email, Capsule CRM, LiveChat e Outlook Customer Manager.
* **Monitorização das novas tentativas de ações** – o Power Automate tentará novamente quando ocorrerem falhas nos serviços. Agora pode ver quantas novas tentativas automáticas ocorreram e os detalhes do que aconteceu.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/parallel-actions/) sobre esta versão.

### <a name="release-2017-04-17---q1-update-for-power-automate"></a>Versão 17-04-2017 – Atualização do 1.º Trimestre do Power Automate
* **Experiência de aprovação moderna** – crie fluxos de trabalho em que os aprovadores podem aprovar em segurança a partir da aplicação móvel do Power Automate ou do centro de aprovações unificado no site do Power Automate
* **Disponibilidade geral dos fluxos de equipa**: várias pessoas podem ter e gerir um fluxo em conjunto com os fluxos de equipa, que agora estão geralmente disponíveis.
* **Criação de conectores para o Power Automate** - qualquer pessoa pode enviar o seu próprio conector do Power Automate gratuitamente para o resto do mundo.
* **Um estruturador mais leve** - para determinados modelos, uma nova versão do estruturador apresenta apenas os campos que são necessários para criar um fluxo, o que simplifica a experiência.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/q1-2017-update/) sobre esta versão.

### <a name="release-2017-04-11"></a>Versão 2017-04-11
* **Novas ações para criar tabelas e listas** - novas ações de criação de tabela HTML, criação de tabela CSV e associações que podem processar listas de itens (ao invés da anterior opção de apenas Aplicar a cada).
* **Inserir passos em qualquer lugar** -agora pode inserir um novo passo em qualquer lado no fluxo de trabalho sem precisar de arrastar e largar.
* **Quatro novos serviços** - o Flow agora suporta 10 to 8 Scheduling, Act!, Inoreader e a API de Imagem Digitalizada. Com a API de Imagem Digitalizada, pode processar imagens para obter o conteúdo do texto (conhecido como OCR), ou marcar automaticamente as imagens com base no seu conteúdo.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/) sobre esta versão.

### <a name="release-2017-04-03"></a>Versão 2017-04-03
* **Versão Beta do Windows Phone** - O programa beta da Aplicação do Windows Phone está disponível para que obtenha uma pré-visualização da aplicação no seu Windows Phone. [Saiba mais](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/).
* **Muhimbi PDF** - Agora, pode converter ficheiros do Microsoft Word para PDF, adicionar marcas d’água, intercalar documentos e muito mais com o Muhimbi PDF. [Saiba mais](https://flow.microsoft.com/blog/convert-files-using-muhimbi/).
* **Acionar fluxos a partir de botões físicos** – anunciamos parcerias com dois dos principais produtos da área dos botões físicos: Flic, da Shortcut Labs, e Bttn, da The Button Corporation. [Saiba mais](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>Versão 2017-03-22
* **Fazer uma cópia do seu fluxo** – Agora, pode fazer uma cópia do seu fluxo, para trabalhar em versões de rascunho, ou duplicar um fluxo que tenha criado no passado.
* **Dois novos serviços** - Adicionámos suporte para Toodledo, para que faça a gestão da sua lista de tarefas ao criar e atualizar tarefas, e para Zendesk, que fornece um serviço de atendimento ao cliente e uma plataforma de pedidos de suporte.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/make-a-copy/) sobre esta versão.

### <a name="release-2017-03-15"></a>Versão 2017-03-15
* **Partilhar botões com colegas** – os botões de fluxo podem agora ser partilhados com outras pessoas, facilitando a qualquer utilizador empresarial efetuar tarefas rápidas.
* **Acionar botões a partir do ecrã principal** – atalhos para os botões de fluxo a partir de ecrãs principais e bloqueados de dispositivos móveis tornando, mais rápido do que nunca, acionar um fluxo.
* **Fluxos da equipa na aplicação do Power Automate** – pode agora ver os fluxos com outros proprietários na aplicação do Power Automate para iOS ou Android.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/button-sharing/) sobre esta versão.

### <a name="release-2017-03-10"></a>Versão 2017-03-10
* **Experiência de conector personalizado melhorada** – Pode agora utilizar uma coleção de Postman para criar um conector personalizado e editar, adicionar e testar ações.
* **Dois novos serviços** – suporte extra para Notificações do Power Apps e PivotalTracker.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/new-updates-custom-api/) sobre esta versão.

### <a name="release-2017-02-27"></a>Versão 2017-02-27
* **Acionamento dos botões de fluxo** – agora, pode acionar botões de fluxo diretamente no Power Automate. Quando estiver a olhar para a lista de fluxos, basta selecionar o menu "…" e escolher o comando Executar agora.
* **Cinco novos serviços** – suporte extra para Base de Dados do Oracle, Intercom, FreshBooks, LeanKit e WebMerge.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/trigger-flow-buttons-web/) sobre esta versão.

### <a name="release-2017-02-21"></a>Versão 2017-02-21
* **Ver fluxos de ambiente** – os administradores de ambiente podem agora visualizar a lista completa de todos os fluxos dentro de um determinado ambiente, bem como ativar, desativar ou eliminar fluxos.
* **Dois novos serviços** – suporte extra para Automatização do Azure e Basecamp 2.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) sobre esta versão.

### <a name="release-2017-02-16"></a>Versão 2017-02-16
* **Cinco novos serviços** – suporte adicionado para Azure Data Lake, Bitbucket (serviço de alojamento para projetos que utilizar o controlo de revisão de GIT com base na Web), Eventbrite, Infusionsoft e Pipedrive.
* **Autenticação HTTP personalizada** – no estruturador de fluxo é, agora, possível utilizar a autenticação com pontos finais HTTP personalizados.
* **Analisar mensagens JSON** – pode analisar dados JSON a partir do acionador de Pedido de HTTP ou a partir do que é devolvido da ação de HTTP.
* **Filtragem de execuções de fluxo** – filtragem melhorada para execuções de fluxo, com opções mais específicas, incluindo ver Fluxos em execução ou Execuções canceladas.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) sobre esta versão.

### <a name="release-2017-02-06"></a>Versão 2017-02-06
* **Fluxos de equipa** - Os fluxos de equipa permitem que várias pessoas sejam proprietárias e colaborem na gestão de um fluxo. Se alguém deixar uma organização, os fluxos que criaram podem continuar a ser executados.
* **Partilhar conectores personalizados** – Os conectores personalizados, tal como os fluxos de equipa, podem ser partilhados e geridos coletivamente no âmbito de uma organização.
* **Gmail e suporte para LUIS** -Ligue-se ao Gmail e ao Language Understanding Intelligent Service dos Serviços Cognitivos do Azure.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/team-flows/) sobre esta versão.

### <a name="release-2017-01-30"></a>Versão 2017-01-30
* **Introduções dos botões do fluxo** - Agora, os botões do fluxo podem receber introduções de utilizador durante o tempo de execução, pelo que os autores do fluxo podem definir informação transmitida quando alguém toca no botão.
* **Tarefas do Outlook e HelloSign** - O serviço Tarefas do Outlook permite-lhe gerir tarefas, enquanto o HelloSign ativa assinaturas eletrónicas protegidas.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/button-user-inputs/) sobre esta versão.

### <a name="release-2017-01-23"></a>Versão 2017-01-23
* **Pesquisa por serviço** - pesquise por serviço quando adicionar um acionador ou uma ação para ver todas as ações de cada serviço.
* **Maiúsculas/minúsculas** - adicione Blocos do comutador para ter vários ramos de lógica paralela.
* **Mais ações de e-mail** - nova funcionalidade nos serviços do Office 365 Outlook e do Outlook.com para trabalhar com e-mails sinalizados.
* **Cinco novos serviços** - ligue a sistemas de ficheiros de rede ou local, a o serviço de pagamento Stripe, IBM Informix, IBM DB2 e UserVoice.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/search-by-service/) sobre esta versão.

### <a name="release-2017-01-14"></a>Versão 2017-01-14
* **Submeter execuções novamente** - se um fluxo falhar e quiser corrigi-lo e executá-lo outra vez, pode submeter novamente a execução que falhou.
* **Cancelar execuções** - quando um fluxo fica bloqueado, pode cancelar a execução explicitamente.
* **Dois novos serviços** - suporte adicional para GoToTraining e GoToWebinar.
* **Ligações móveis** - pode partilhar modelos diretamente a partir da aplicação móvel. Além disso, adicionámos uma ligação de transferência rápida para as aplicações na parte superior do site.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/managing-runs/) sobre esta versão.

### <a name="release-2016-12-29"></a>Versão de 2016-12-29
O Power Automate agora suporta o DocuSign, para processar eSignatures e a Gestão de Transações Digitais; o SurveyMonkey, para inquéritos baseados na Web; e a aplicação de criação de notas do OneNote (apenas para contas de empresas).

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/final-2016-services/) sobre esta versão.

### <a name="release-2016-12-20"></a>Versão de 2016-12-20
* **Executar agora** -pode agora desativar um acionador periódico a pedido - por exemplo, se tiver um relatório agendado todos os dias, mas precisa que o relatório seja executado **agora** também.
* **Seis novos serviços** - crie fluxos que estabelecem ligação ao MSN Meteorologia, Médio, Contactos do Google, Memória Intermédia, Harvest e TypeForm.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/run-now-and-six-more-services/) sobre esta versão.

### <a name="release-2016-12-14"></a>Versão de 2016-12-14
Agora pode aproveitar informações valiosas quando acionar um fluxo de botão, assim como de onde o botão foi acionado, por quem, em que o tempo e muito mais.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/button-trigger-tokens/) sobre esta versão.

### <a name="release-2016-12-06"></a>Versão 2016-12-06
* **Introdução à Aprendizagem Guiada** – introdução a uma coleção sequenciada de cursos que combinam vídeos com documentação para o ajudar a compreender as capacidades extensas e poderosas do Power Automate.
* **Dois novos serviços** - Agora os fluxos podem utilizar o Freshdesk, uma solução de suporte ao cliente e o GoToMeeting, uma ferramenta de reunião online.
* **Suporte de HTTP Webhook** - Um fluxo pode agora ser um ponto final para webhooks que irá registar e anular o registo do próprio automaticamente.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/guided-learning-and-two-services/) sobre esta versão.

### <a name="release-2016-11-23"></a>Versão 2016-11-23
* **Suporte de alerta do Power BI no Flow** - Transforme as informações em ação ao acionar fluxos a partir dos alertas de dados do Power BI.
* **Melhoramentos de aplicações móveis** - Adicionada a capacidade para criar fluxos de raiz, para além da já existente experiência de criação a partir de modelos. Também melhorámos o desempenho ao ver execuções de fluxo.
* **Oito novos serviços** - Agora pode ligar o Azure Resource Manager, as Filas do Azure, o Chatter, o Disqus, o Azure Cosmos DB, a API Face de Serviços Cognitivos, o HipChat e o Wordpress.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/) sobre esta versão.

### <a name="release-2016-11-15"></a>Versão 2016-11-15
* **Programa de Parceiros do Power Automate** – o Power Automate tem agora um programa de parceiros certificado para efetuar ligações e tirar partido dos diferentes talentos da empresa e da experiência com o Power Automate em todo o mundo.
* **Seis novos serviços** – também vamos lançar seis serviços esta semana: Asana, Campfire, EasyRedmine, JIRA, Redmine e Vimeo.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/partner-program-six-new-services/) sobre esta versão.

### <a name="release-2016-10-31---general-availability"></a>Versão de 31-10-2016 – Disponibilidade Geral
* **Preços e licenciamento** – agora disponíveis nos planos Gratuito e pago e incluídos no Office 365 e no Dynamics 365.
* **Centro de Administração do Power Automate** – preparado para empresas com o novo Centro de Administração. No Centro de Administração, pode gerir os ambientes dentro da organização.
* **Políticas de prevenção de perda de dados** – os administradores podem criar políticas de prevenção de perda de dados para controlar o fluxo de dados entre serviços.
* **Disponibilidade para o Android** – a aplicação para telemóvel do Power Automate está agora disponível para iOS e Android. A aplicação permite-lhe obter notificações, monitorizar a atividade e iniciar fluxos com o toque de um botão.
* **Novas experiências do estruturador** – pode agora pesquisar no conteúdo dinâmico transmitido passo a passo, acelerando o processo de referência dos dados que pretende.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/announcing-ga/) sobre esta versão.

### <a name="release-2016-10-26"></a>Versão de 26-10-2016
* **Fluxos de botões** – existem várias operações que desejaríamos acionar em qualquer altura e em qualquer lugar. Agora, com os Fluxos de Botões, pode aceder aos mesmos apenas com um clique de um botão, a partir do seu dispositivo móvel.
* **Apresentar ambientes** – os ambientes são espaços distintos para armazenar e gerir os fluxos da sua organização. Os ambientes estão localizados geograficamente, o que significa que os fluxos, as aplicações e os dados de negócio que se encontram num ambiente estarão na região onde está localizado o ambiente.
* **Seis novos serviços** – estamos a adicionar o suporte para Bit.ly, Análises de Texto de Serviços Cognitivos, Dynamics NAV, Dynamics 365 for Financials, Instapaper e Pinterest.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/environments-for-makers/) sobre esta versão.

### <a name="release-2016-10-16"></a>Versão 2016-10-16
* **Os conectores personalizados suportam mais tipos de autenticação** – Os conectores personalizados suportam agora a autenticação de chave de API e podem autenticar qualquer serviços que suporte a especificação OAuth 2.0 completa.
* **Três novos serviços suportados** - Adicionámos suporte para Basecamp 3, Blogger e PagerDuty.
* **Melhoramentos no estruturador** - Com um desempenho melhorado, pode agora atualizar e reparar as suas ligações diretamente a partir do menu "…" para todas as ações e adicionámos um novo passo denominado Terminar que pode utilizar para terminar a execução de um fluxo.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/early-october-updates/) sobre esta versão.

### <a name="release-2016-09-25"></a>Versão 2016-09-25
Criação de fluxos agora disponível a partir do seu telemóvel. Navegue na nossa galeria de modelos completa, navegue na nossa lista de serviços ou selecione uma categoria de modelo para explorar. [Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/mobile-creation/) sobre esta versão.

### <a name="release-2016-09-22"></a>Versão 2016-09-22
* **Selecionador de Pessoas do Microsoft Graph** – um novo selecionador de pessoas do Microsoft Graph está integrado diretamente na IU do Power Automate para ajudar a escolher o contacto ou endereço de e-mail certo.
* **Suporte do Microsoft Dynamics AX** - A partir de dentro dos seus fluxos, pode agora realizar ações nos seus dados de operações do Dynamics AX Online, desde criar novos registos até consultar dados.
* **Dois novos serviços de parceiros** - Utilize agora o appFigures ou o Insightly a partir dos seus fluxos.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/more-september-updates/) sobre esta versão.

### <a name="release-2016-09-14"></a>Versão 2016-09-14
* **Incorporação no site ou na aplicação** – os programadores podem agora incorporar o Power Automate diretamente nas aplicações ou os sites para proporcionar aos utilizadores uma forma simples de automatizar tarefas pessoais ou profissionais.
* **Utilizar um fluxo como um ponto final de HTTP** – Agora, pode utilizar um fluxo como uma API de HTTP. Existe um acionador denominado Pedido dentro do fluxo e pode optar por responder ao pedido recebido, adicionando um cartão de resposta.
* **Suporte de Todoist** - O Todoist dá-lhe uma perspetiva de todos os seus projetos, no trabalho e em casa.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/extend-web-site-application/) sobre esta versão.

### <a name="release-2016-09-01"></a>Versão 2016-09-01
O Power Automate está, agora, disponível para todos – inicialmente, abrimos a pré-visualização apenas para endereços de e-mail fornecidos pela sua empresa ou escola, como os utilizados com o Office 365 Empresas ou o Office 365 Enterprise. Hoje, estamos a anunciar que a pré-visualização está oficialmente disponível, de utilização gratuita, para todos os utilizadores, independentemente do e-mail que possam ter. [Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/available-for-everyone/) sobre esta versão.

### <a name="release-2016-08-31"></a>Versão 2016-08-31
* **Condicionais aninhadas** – Agora, pode adicionar uma segunda (ou terceira, etc.) condição dentro de outra.
* **Apply to each** - Um ciclo «apply to each» torna possível controlar a lista que repete continuamente.
* **Do-until** - Um ciclo «Do-until» permite repetir um passo até que uma determinada condição seja cumprida.
* **Filtrar matrizes** - Existe um passo único de filtro nativo que pode garantir que todos os itens na lista correspondem a uma expressão que definir.
* **Compor variáveis de cadeia** – Agora, pode compor uma variável de cadeia.
* **Âmbitos** - Os âmbitos são uma forma simples de agrupar duas ou mais ações.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/build-advanced-flows/) sobre esta versão.

### <a name="release-2016-08-27"></a>Versão 2016-08-27
* **Comentários sobre passos** - Os comentários facilitam a anotação de cada ação individual com notas, para que possa lembrar-se facilmente do que o fluxo precisa
* **Suporte de Smartsheet** - Esta semana, adicionámos suporte para ligação ao Smartsheet. O Smartsheet é um serviço que facilita a colaboração em folhas na nuvem.
* **Refinamentos na IU durante a criação de fluxos** - Colocámos o nome do fluxo à frente e no centro e deslocámos o botão Guardar para o início da página para facilitar o acesso.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/add-comments-smartsheet/) sobre esta versão.

### <a name="release-2016-08-18"></a>Versão 2016-08-18
Agora, pode pré-visualizar a nova experiência de listas modernas do SharePoint Online, que inclui a integração do Power Automate. [Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/) sobre esta versão.

### <a name="release-2016-08-13"></a>Versão 2016-08-13
* **Visual Studio Team Services** - Com o Flow, pode agora ligar o VSTS a um amplo leque de serviços, como o O365 Email, Slack, Trello e Wunderlist.
* **Melhoramentos ao SharePoint** - As listas do SharePoint suportam uma variedade de tipos de dados a partir de objetos simples como Linhas individuais de texto e Data e hora para objetos complexos, tais como Pessoa ou Grupo, Pesquisa e Escolha.
* **Testar as Ligações do O365 Outlook** - Sempre que cria uma nova ligação do O365 Outlook, iremos agora testá-la para garantir que está pronto a utilizá-lo.
* **Controlo Booleano** - Também adicionámos um controlo booleano para esclarecer que valores deve introduzir para campos de entrada booleanos, tais como Tem Anexos no acionador Ao receber um novo e-mail.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/) sobre esta versão.

### <a name="release-2016-08-08"></a>Versão 2016-08-08
Pré-visualização pública do Microsoft Common Data Service integrado no Power Automate. [Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/flow-and-common-data-model/) sobre esta versão.

### <a name="release-2016-08-05"></a>Versão 2016-08-05
* **SharePoint no local** - Tal como no SharePoint Online, pode criar fluxos em torno das suas listas e bibliotecas de documentos do SharePoint no local, utilizando modelos predefinidos ou criando-os do zero.
* **Bolhas de informação no estruturador** - Para explicar as funcionalidades de cada acionador e ação, adicionámos bolhas de informação acima de cada passo do seu fluxo.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/) sobre esta versão.

### <a name="release-2016-07-15"></a>Versão 2016-07-15
* **Quatro novos serviços adicionados** - Ligue-se ao Calendário Google, ao Google Tarefas, ao YouTube e ao SparkPost.
* **Mudar o nome das suas ações** - Agora, pode distinguir estas ações diferentes, mudando o nome das mesmas.
* **Atraso para diferentes períodos de tempo** - Agora, pode selecionar qualquer número de Segundos, Minutos, Horas ou Dias.
* **Mais fácil de utilizar o browser de pastas** - Simplificámos o browser de pastas. Agora, ao selecionar à esquerda escolherá essa pasta e selecionar à direita abrirá essa pasta para que possa escolher as subpastas no interior.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/new-google-services-rename-more/) sobre esta versão.

### <a name="release-2016-07-08"></a>Versão 2016-07-08
Conectividade no local para o Power Automate com o gateway de dados no local. Permite-lhe estabelecer ligações seguras ao SQL Server e integrá-las nos seus fluxos. [Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/on-premises-data-gateway/) sobre esta versão.

### <a name="release-2016-07-02"></a>Versão 2016-07-02
* **Suporte do Google Sheets** - No passado, podíamos utilizar o Excel e o Google Drive, mas esta semana estamos a adicionar suporte nativo do Google Sheets.
* **Comece a trabalhar mais rapidamente a partir de modelos** - Fizemos também algumas otimizações à forma como pode começar a partir de modelos. Agora, pode selecionar as contas que pretende utilizar para um modelo inline na página do modelo.
* **Sem necessidade de autorização ao expirar para o SharePoint e o Office 365** – agora, o Power Automate renovará automaticamente o acesso do utilizador aos serviços baseados no Azure Active Directory, para que todos os fluxos continuem a funcionar quando muda de palavra-passe.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/more-june-updates/) sobre esta versão.

### <a name="release-2016-06-20"></a>Versão 2016-06-20
* **Apresentação da nova aplicação móvel do Power Automate** – hoje, temos o prazer de apresentar outra peça importante da nossa oferta: uma aplicação móvel agora disponível para transferência no iOS (brevemente, também no Android) que lhe permite gerir, controlar e explorar os fluxos de trabalho automatizados em qualquer altura e em qualquer lugar.  
* **Início de sessão único** – implementámos o início de sessão que lhe permite fazer a autenticação no Power Automate com outros serviços Microsoft, como o Office 365.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/) sobre esta versão.

### <a name="release-2016-06-18"></a>Versão 2016-06-18
* **Novo Serviço de correio** – agora, pode enviar mensagens de e-mail diretamente a partir do Power Automate, sem precisar de ligar às contas de e-mail pessoais ou profissionais dentro do Power Automate.
* **Notificações no portal** - Agora, verá notificações na parte superior do portal sempre que houver algo de errado com os seus fluxos.
* **Toda a atividade no portal** - Agora, pode ver a atividade de todos os fluxos ao clicar no novo separador Atividade no site do fluxo.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/mail-and-all-activity/) sobre esta versão.

### <a name="release-2016-05-27"></a>Versão 2016-05-27
* **Procurar modelos por serviço** - Agora, há uma forma de ver todos os serviços que suportamos (sem ter de iniciar sessão). A partir desta página, pode ver uma descrição de cada um dos serviços e ver os modelos que temos para esse serviço.
* **Criação e utilização de conectores personalizados** – tal como pode criar conectores personalizados no Power Apps, também se pode ligar às suas próprias APIs diretamente em flow.microsoft.com:
* **Testar os fluxos antes de terminar** - Sempre que guardar um fluxo, pode agora ver os resultados da execução do fluxo em tempo real na página se executar a ação de início.

[Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/) sobre esta versão.

### <a name="release-2016-05-07"></a>Versão 2016-05-07
Adicionamos dois novos serviços: Microsoft Project Online e Mandrill da Mailchimp. [Leia mais informações e faça perguntas](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/) sobre esta versão.

### <a name="release-2016-04-27---public-preview"></a>Versão de 27-04-2016 – Pré-visualização Pública
Se tiver utilizado fluxos lógicos como parte do [Microsoft Power Apps](https://powerapps.microsoft.com), a versão de Pré-Visualização do Power Automate oferecerá várias funcionalidades novas:

* Agora pode procurar uma galeria de dezenas de modelos e ordenar por Popularidade, Nome ou Data da publicação.
* Pode [publicar os seus próprios modelos](publish-a-template.md) na galeria após personalizar um fluxo.
* Pode ver o histórico para cada verificação e execução do fluxo.
* Quando guarda um fluxo, pode [vê-lo em ação imediatamente](see-a-flow-run.md) bastando apenas efetuar a ação do acionador.
* Há uma [nova comunidade](https://go.microsoft.com/fwlink/?LinkID=787467) onde pode discutir fluxo ou [submeter as suas ideias](https://go.microsoft.com/fwlink/?LinkID=787474).

## <a name="next-steps"></a>Próximos passos
Se tiver quaisquer problemas que ainda não estejam abrangidos nestas notas de versão ou nas [FAQ](frequently-asked-questions.md), volte a [aderir à nossa comunidade](https://go.microsoft.com/fwlink/?LinkID=787467) para fazer perguntas, ou [contacte o suporte](https://go.microsoft.com/fwlink/?LinkID=787479).

