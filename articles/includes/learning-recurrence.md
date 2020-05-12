Neste tópico, irá ver como executar fluxos previamente agendados utilizando um acionador chamado **Periodicidade**.  Irá criar um fluxo para a equipa de marketing da Contoso que obtém automaticamente endereços de e-mail de clientes a partir de uma tabela do Excel no OneDrive. Irá configurar o fluxo de modo a que, uma vez por dia, os novos endereços de e-mail que foram adicionados à folha de cálculo sejam então adicionados a uma lista de clientes do MailChimp. 

## <a name="create-a-scheduled-flow"></a>Criar um fluxo agendado
1. Abra o **Power Automate**, selecione **Os meus fluxos** e, em seguida, selecione **Criar do zero**. 
   
    ![](./media/learning-recurrence/flow-create-blank.png)
2. Selecione **Procurar entre centenas de conectores e acionadores**.
3. Procure o serviço **Agendamento**, selecione-o e selecione o acionador **Agendamento - Periodicidade**
   
    ![](./media/learning-recurrence/flow-recurrence-trigger.png)
4. Defina a **Frequência** para **Dia** e o **Intervalo** para **1**. Selecione **Novo passo** e selecione **Adicionar uma ação**. 
   
    ![](./media/learning-recurrence/frequency-interval.png)
5. Procure o **Excel**, selecione o serviço **Excel** e selecione a ação **Excel – Obter Linhas**. 
   
    ![](./media/learning-recurrence/excel-get-rows.png)
   
    **Nota**: certifique-se de que seleciona **Obter linhas**, e não **Obter linha**. 
6. Selecione **Nome de ficheiro** e navegue para a localização do ficheiro. Selecione **Nome da tabela** e selecione a tabela pretendida na folha de cálculo. 
   
    ![](./media/learning-recurrence/excel-get-file.png)
7. Adicione uma nova ação. 
   
    ![](./media/learning-recurrence/new-step.png)
8. Procure o serviço **MailChimp** e selecione a ação **MailChimp - Adicionar membro à lista**.
   
    ![](./media/learning-recurrence/select-mailchimp.png)
   
    **Nota:** o MailChimp é um conector *premium*. Dependendo da sua licença do Power Automate, poderá ter de se inscrever numa versão de avaliação para utilizar este conector.
9. Adicione os campos **Id da Lista** e **Estado** dos menus de lista pendente:
   
   * **Id da Lista** – Selecionar a sua lista de correio do MailChimp pretendida
   * **Estado** – Selecionar **Subscrito** 
     
     ![](./media/learning-recurrence/mailchimp-id-status.png)
10. No **Endereço de E-mail**, utilize a funcionalidade de conteúdo dinâmico para adicionar o campo **ContactEmail**. 
    
     ![](./media/learning-recurrence/mailchimp-address.png)
    
     Tenha em atenção que o fluxo cria automaticamente um passo adicional. O fluxo deteta que vai definir uma ação que requer uma ação adicional. Sempre que o fluxo lê um novo endereço de e-mail, cria também uma nova ação para cada linha. 
    
     ![](./media/learning-recurrence/mailchimp-for-each.png)
11. Utilize o conteúdo dinâmico para preencher os campos **Nome próprio** e **Apelido**:
    
    * **Nome próprio** – FirstName
    * **Apelido** – LastName
      
      ![](./media/learning-recurrence/mailchimp-names.png)

Este fluxo irá agora ser executado uma vez por dia e obter novas linhas desta tabela do Excel, captar o endereço de e-mail e o nome, e utilizá-los para preencher a lista de correio do MailChimp da Contoso, poupando tempo e dinheiro. 

