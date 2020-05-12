Num tópico anterior, vimos como criar um processo de aprovação de tweets armazenados numa lista do SharePoint.  Neste tópico, irá ver como pode ser a experiência do aprovador ao receber um novo pedido de aprovação. 

## <a name="create-and-process-a-request"></a>Criar e processar um pedido
Em primeiro lugar, temos de adicionar um item à lista do SharePoint, para podermos então processar um pedido de aprovação para esse item.

1. Abra a lista **Tweets da Contoso** do SharePoint configurada num tópico anterior.  Selecione **Novo** para criar um novo tweet. 
   
    ![lista SharePoint](./media/learning-approval-request/sharepoint-list-home.png)
2. Adicione os seguintes valores aos campos e selecione **Guardar**.
   
   * **Título** – Promoções
   * **TweetContent** – Conheça a nova linha da Contoso Flooring #ohsocontoso
   * **TweetDate** – data atual
     
     ![Novo item do SharePoint](./media/learning-approval-request/sharepoint-new-tweet.png)
3. Em **Power Automate**, selecione **Os Meus Fluxos**. 
4. Selecione o fluxo **Publicar itens de lista no Twitter após a aprovação**, que foi configurado no tópico anterior, e selecione o fluxo em execução em **HISTÓRICO DE EXECUÇÕES**.
   
    ![Histórico de execuções](./media/learning-approval-request/run-history.png)
5. Selecione o acionador **Quando é criado um novo item**. Certifique-se de que as informações do item de lista que acabou de criar são apresentadas.
   
    ![Acionador de fluxo](./media/learning-approval-request/approval-flow.png)
6. No **Outlook**, abra o e-mail de aprovação automática na caixa de entrada e selecione **Aprovar**. 
   
    ![Pedido do Outlook](./media/learning-approval-request/outlook-mail.png)
7. No **Centro de Aprovação**, veja os detalhes do pedido, adicione um comentário e selecione **Confirmar**. 
   
    ![Centro de aprovação](./media/learning-approval-request/approval-center.png)
8. No **SharePoint**, atualize a lista **Tweets da Contoso** e certifique-se de que **Estado da Aprovação** está definido como **Sim** e que o comentário que introduziu é apresentado. 
   
    ![Atualizar lista do SharePoint](./media/learning-approval-request/sharepoint-list-approved.png)

Neste tópico, vimos a experiência do ponto de vista do aprovador: desde a receção do e-mail do pedido de aprovação ao processamento do pedido no Centro de Aprovação.

