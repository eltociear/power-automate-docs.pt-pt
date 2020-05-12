Com uma lista em expansão de [serviços](https://flow.microsoft.com/services) disponíveis para criar fluxos de trabalho com o [Power Automate](https://flow.microsoft.com), poderá precisar de salvaguardar dados de negócio críticos ou confidenciais armazenados em serviços empresariais como o SharePoint ou o Salesforce. Pode chegar à conclusão de que a sua organização precisa de criar uma política que garanta que os dados de negócio confidenciais não são publicados em serviços de consumidor como o Twitter e o Facebook. Com o Power Automate, pode criar facilmente políticas de **prevenção de perda de dados** (DLP) para exercer um controlo rigoroso sobre os serviços de consumidor com os quais os dados da empresa podem ser partilhados quando os utilizadores criam fluxos.  

## <a name="terms-you-should-get-familiar-with"></a>Termos com os quais deverá familiarizar-se

| Termo | Descrição |
| --- | --- |
| **DLP** |A abreviatura de prevenção de perda de dados. Terá de criar uma política DLP para gerir a partilha dos dados entre **serviços**. |
| **Serviços** |[Serviços](https://flow.microsoft.com/services) são aplicações como o Salesforce, o SharePoint e o Twitter. Estes serviços e muitos outros são utilizados para criar fluxos. |
| **Grupo de dados** |Um agrupamento lógico de serviços. Coloque os serviços que têm permissão para partilhar dados no mesmo grupo de dados. Existem dois grupos de dados: **apenas dados de negócio** e o grupo de dados **dados de negócio não permitidos**. |
| **Ambiente** |Uma DLP é aplicada a um [ambiente](../environments-overview-admin.md). Um ambiente contém utilizadores. |
| **Utilizadores** |Os utilizadores são membros da sua organização aos quais será aplicada uma política DLP, com base na respetiva associação num ambiente. |
| **Fluxo** |Um fluxo é uma aplicação de fluxo de trabalho que utiliza qualquer combinação dos serviços disponíveis. |

## <a name="all-about-how-dlp-policies-work"></a>Tudo sobre o funcionamento das políticas DLP
Uma política DLP é simplesmente uma regra com nome que coloca cada serviço num de dois grupos de dados mutuamente exclusivos. Esta regra é, então, aplicada a um ambiente. Um ambiente consiste num agrupamento lógico de utilizadores. Os utilizadores não têm permissão para criar fluxos que partilhem dados entre os serviços que colocou em grupos de dados diferentes. Por outras palavras, os utilizadores apenas podem criar fluxos que partilhem dados entre os serviços que se encontrem num **único** grupo de dados. Não é permitida a partilha entre grupos de dados.  

| **Nome do grupo de dados** | **Descrição do grupo de dados** |
| --- | --- |
| **Apenas dados de negócio** |Todos os serviços neste grupo podem partilhar dados entre si. Não podem partilhar dados com o grupo de dados de **dados de negócio não permitidos**. |
| **Dados de negócio não permitidos** |Todos os serviços neste grupo podem partilhar dados entre si. Não podem partilhar dados com o grupo de dados de **apenas dados de negócio**. |

**Atenção**: adicionar um serviço a um grupo de dados remove-o automaticamente do outro grupo de dados. Por exemplo, se o Twitter estiver no grupo de dados **apenas dados de negócio** e não quiser permitir que os dados de negócio sejam partilhados com o Twitter, basta adicionar o serviço Twitter ao grupo de **dados de negócio não permitidos**. Desta forma, o Twitter é removido do grupo de dados de **apenas dados de negócio**.

## <a name="heres-what-you-need-to-create-a-dlp"></a>Eis o que precisa para criar uma DLP
* Aceder ao [centro de administração](https://admin.flow.microsoft.com) do Power Automate  
* Uma conta na função de Administrador do Ambiente  
* Um ambiente com utilizadores atribuídos ao mesmo  

## <a name="create-a-dlp-policy"></a>Criar uma política DLP
Eis uma rápida descrição geral sobre como criar uma política DLP:  

1. Dê um nome à política
2. Selecione o ambiente ao qual a política será aplicada
3. Adicione os serviços a um dos dois grupos de dados. Lembre-se de que apenas os serviços localizados num grupo específico podem partilhar dados, pelo que qualquer fluxo que seja criado para partilhar dados entre serviços localizados nos dois grupos de dados será automaticamente bloqueado quando o criador o guardar.  

Também existem [instruções mais detalhadas](../prevent-data-loss.md) sobre as políticas DLP disponíveis.  

## <a name="examples"></a>Exemplos
* Se precisasse de criar uma política destinada a restringir a partilha de dados de negócio por parte dos fluxos apenas entre o SharePoint, os utilizadores do Office 365, o Office 365 Outlook, o OneDrive para Empresas, o Dynamics 365, o SQL Server e o Salesforce, esta teria o seguinte aspeto:  
  ![](./media/learning-data-loss-prevention/a-few-business-centric-services.png)  
* Este seria o aspeto da mesma se decidisse criar uma política para não permitir que nenhum membro de um ambiente específico crie um fluxo que partilhe dados do SharePoint. Tenha em atenção que o SharePoint é o único serviço no grupo de dados **apenas dados de negócio**:  
  ![apenas dados de negócio](./media/learning-data-loss-prevention/sharepoint-only-no-sharing-guided-learning.png)

