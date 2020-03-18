---
title: Utilize expressões com condições. | Microsoft Docs
description: Utilize expressões avançadas como “e”, “ou”, “vazio”, “menos” e “maior” com as Condições do Power Automate.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/15/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3c1eb0f208f964f2a41e26ca831c60edef0d747c
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195980"
---
# <a name="use-expressions-in-conditions-to-check-multiple-values"></a>Utilize expressões nas condições para verificar valores múltiplos

Nestas instruções, irá aprender a utilizar expressões e **Condições** para comparar valores múltiplos no **Modo avançado**.

Ao criar um fluxo, pode utilizar o cartão [**Condição**](add-condition.md#add-a-condition) no modo básico para rapidamente comparar um valor único com outro valor. No entanto, por vezes terá de comparar valores múltiplos. Por exemplo, poderá verificar o valor de algumas colunas numa folha de cálculo ou numa tabela de base de dados.

Pode utilizar qualquer combinação das seguintes expressões lógicas nas suas condições.

Expressão|Descrição|Exemplo
--------|-----------|-------
|[and](#use-the-and-expression)|Precisa de dois argumentos e devolve verdadeiro se ambos os valores forem verdadeiros.<br><b>Nota</b>: ambos os argumentos têm de ser Booleanos.|Esta expressão devolve falso: <br>and(greater(1,10),equals(0,0))
|[or](#use-the-or-expression)|Recebe dois argumentos e devolve verdadeiro se um dos argumentos for verdadeiro. <br><b>Nota</b>: ambos os argumentos têm de ser Booleanos.|Esta expressão devolve verdadeiro:<br>or(greater(1,10),equals(0,0))
|equals|Devolve verdadeiro se dois valores forem iguais.|Por exemplo, se parâmetro1 for someValue, esta expressão devolve verdadeiro:<br>equals(parameters('parameter1'), 'someValue')
|[less](#use-the-less-expression)|Precisa de dois argumentos e devolve verdadeiro se o primeiro argumento for menor que o segundo argumento. <br><b>Nota</b>: os tipos suportados são números inteiros, flutuantes e cadeias.|Esta expressão devolve verdadeiro:<br>less(10,100)
|lessOrEquals|Precisa de dois argumentos e devolve verdadeiro se o primeiro argumento for menor ou igual ao segundo argumento. <br><b>Nota</b>: os tipos suportados são números inteiros, flutuantes e cadeias.|Esta expressão devolve verdadeiro:<br>lessOrEquals(10,10)
|[greater](#use-the-greater-expression)|Recebe dois argumentos e devolve verdadeiro se o primeiro argumento for maior que o segundo argumento. <br><b>Nota</b>: os tipos suportados são números inteiros, flutuantes e cadeias.|Esta expressão devolve falso:<br>greater(10,10)
|greaterOrEquals|Recebe dois argumentos e devolve verdadeiro se o primeiro argumento for maior ou igual ao segundo argumento. <br><b>Nota</b>: os tipos suportados são números inteiros, flutuantes e cadeias.|Esta expressão devolve falso:<br>greaterOrEquals(10,100)
|[empty](#use-the-empty-expression)|Devolve verdadeiro se o objeto, matriz ou cadeia estiverem vazios.|Esta expressão devolve verdadeiro:<br>empty('')
|not|Devolve o oposto de um valor booleano. |Esta expressão devolve verdadeiro:<br>not(contains('200 Success','Fail'))
|if|Devolve um valor específico se a expressão resultar em verdadeiro ou falso.|Esta expressão devolve “sim”:<br>if(equals(1, 1), 'yes', 'no')

## <a name="prerequisites"></a>Pré-requisitos
* Acesso ao Power Automate.
* Uma folha de cálculo com as tabelas descritas mais tarde nestas instruções. Lembre-se de guardar a folha de cálculo numa localização como o Dropbox ou o Microsoft OneDrive para que o Power Automate possa aceder à mesma.
* Microsoft Office 365 Outlook (apesar de utilizarmos o Office 365 Outlook, pode utilizar qualquer serviço de e-mail suportado nos seus fluxos).

## <a name="use-the-or-expression"></a>Utilize a expressão or
Por vezes, o fluxo de trabalho precisa de realizar uma ação se o valor de um item for valorA **or** valorB. Por exemplo, poderá estar a controlar o estado das tarefas numa tabela de folha de cálculo. Assumindo que a tabela tem uma coluna chamada *Estado* e os valores possíveis na coluna *Estado* são:

* **concluído**
* **bloqueado**
* **desnecessário**
* **não iniciado**

Eis um exemplo de como a folha de cálculo pode ser:

![folha de cálculo de exemplo](./media/use-expressions-in-conditions/spreadsheet-table.png)

Tendo em conta a folha de cálculo anterior, deve utilizar o Power Automate para remover todas as linhas com uma coluna *Estado* que está definida como *concluído* ou *desnecessário*.

Vamos criar o fluxo.

### <a name="start-with-a-blank-flow"></a>Comece com um fluxo em branco
1. Inicie sessão no [Power Automate](https://flow.microsoft.com).

    ![iniciar sessão](includes/media/modern-approvals/sign-in.png)
2. Selecione o separador **Os meus fluxos**.

    ![selecione os meus fluxos](includes/media/modern-approvals/select-my-flows.png)
3. Selecione **Criar do zero**.

    ![criar a partir de um valor em branco](includes/media/modern-approvals/blank-template.png)

### <a name="add-a-trigger-to-your-flow"></a>Adicionar o acionador ao fluxo
1. Procure por **Agenda** e, em seguida, selecione o acionador **Agenda - Periodicidade**

    ![acionador da agenda](includes/media/schedule-trigger/schedule-trigger.png)
2. Defina a agenda para execução única diária.

    ![definir agenda](includes/media/schedule-trigger/set-schedule.png)

### <a name="select-the-spreadsheet-and-get-all-rows"></a>Selecione a folha de cálculo e obtenha todas as linhas
1. Selecione **Novo passo** > **Adicionar uma ação**.

    ![novo passo](includes/media/new-step/action.png)
2. Procure por **linhas** e, em seguida, selecione **Excel - Obter linhas**.

    Nota: selecione a ação "obter linhas" que corresponde à folha de cálculo que está a utilizar. Por exemplo, se estiver a utilizar o Google Sheets, selecione **Google Sheets - Obter linhas**.

    ![obter Linhas](includes/media/new-step/get-excel-rows.png)
3. Selecione o ícone de pasta na caixa **Nome de ficheiro**, procure e, em seguida, selecione a folha de cálculo que contém os seus dados.

    ![selecionar folha de cálculo](includes/media/new-step/select-spreadsheet.png)
4. Selecione a tabela que contém os dados a partir da lista **Nome da tabela**.

    ![selecionar tabela](includes/media/new-step/select-table.png)

### <a name="check-the-status-column-of-each-row"></a>Verifique a coluna de estado de cada linha
1. Selecione **Novo passo** > **Mais** > **Adicionar um aplicar a cada**.

    ![selecionar tabela](includes/media/new-step/apply-to-each.png)
2. Adicione o token **Valor** à caixa **Selecionar uma saída dos passos anteriores**.

    ![selecionar tabela](includes/media/apply-to-each/add-value-token.png)
3. Selecione **Adicionar uma condição** > **Editar no modo avançado**.
4. Adicione a seguinte expressão **or**. Esta expressão **or** verifica o valor de cada linha na tabela (uma linha é conhecida como um item quando acede a uma expressão). Se o valor da coluna **estado** for *concluído* **ou** *desnecessário*, a expressão **or** avalia como "verdadeiro".

    A expressão **or** aparece conforme mostrado aqui:

    ````@or(equals(item()?['status'], 'unnecessary'), equals(item()?['status'], 'completed'))````

    O cartão **Condição** é semelhante a esta imagem:

    ![imagem da expressão or](./media/use-expressions-in-conditions/or-expression.png)

### <a name="delete-matching-rows-from-the-spreadsheet"></a>Eliminar linhas correspondentes da folha de cálculo
1. Selecione **Adicionar uma ação** no ramo **SE SIM, NÃO FAZER NADA** da condição.
2. Procure por **Eliminar linha**e, em seguida, selecione **Excel - Eliminar linha**.

    ![eliminar imagem de linha](includes/media/new-step/select-delete-excel-row.png)
3. Na caixa **Nome de ficheiro**, procure e selecione o ficheiro de folha de cálculo que contém os dados que pretende eliminar.
4. Na lista **Nome da tabela**, selecione a tabela que contém os dados.
5. Coloque o token **ID da linha** na caixa **ID da linha**.

    ![ficheiro da folha de cálculo](includes/media/new-step/delete-excel-row.png)

### <a name="name-the-flow-and-save-it"></a>Nomeie o fluxo e guarde-o
1. Dê um nome ao fluxo e, em seguida, selecione o botão **Criar fluxo**.

    ![guardar o fluxo](./media/use-expressions-in-conditions/name-and-save.png)

### <a name="run-the-flow-with-the-or-expression"></a>Executar o fluxo com a expressão or
O fluxo é executado depois de o guardar. Se criou a folha de cálculo mostrada anteriormente nestas instruções, eis como aparece depois de a execução estar concluída:

![expressão or concluída](./media/use-expressions-in-conditions/spreadsheet-table-after-or-expression-runs.png)

Observe que todos os dados de linhas que tinham "concluído" ou "desnecessário" na coluna Estado foram eliminados.

## <a name="use-the-and-expression"></a>Utilizar a expressão or
Suponha que tem uma tabela de folha de cálculo com duas colunas. Os nomes das colunas são Estado e Atribuído. Suponha também que pretende eliminar todas as linhas se o valor da coluna Estado for "bloqueado" e o valor da coluna Atribuído for "John Wonder".  Para realizar esta tarefa, siga todos os passos anteriores nestas instruções, no entanto, ao editar o cartão **Condição** no modo avançado, utilize a expressão **and** mostrada aqui:

````@and(equals(item()?['Status'], 'blocked'), equals(item()?['Assigned'], 'John Wonder'))````

O cartão **Condição** é semelhante a esta imagem:

![imagem da expressão and](./media/use-expressions-in-conditions/and-expression.png)

### <a name="run-the-flow-with-the-and-expression"></a>Executar o fluxo com a expressão and
Se seguiu o procedimento, a folha de cálculo é semelhante a esta imagem:

![antes da execução de and](./media/use-expressions-in-conditions/spreadsheet-table-before-and-expression-runs.png)

Após a execução do fluxo, a folha de cálculo é semelhante a esta imagem:

![após a execução de and](./media/use-expressions-in-conditions/spreadsheet-table-after-and-expression-runs.png)

## <a name="use-the-empty-expression"></a>Utilizar a expressão empty
Observe que agora existem várias linhas vazias na folha de cálculo. Para removê-las, utilize a expressão **empty** para identificar todas as linhas que não têm qualquer texto nas colunas Atribuído e Estado.

Para realizar esta tarefa, siga todos os passos listados na secção anterior **Utilizar a expressão and** destas instruções, no entanto, ao editar o cartão **Condição** no modo avançado, utilize a expressão empty desta forma:

````@and(empty(item()?['Status']), empty(item()?['Assigned']))````

O cartão **Condição** é semelhante a esta imagem:

![imagem da expressão empty](./media/use-expressions-in-conditions/empty-expression.png)

Após a execução do fluxo, a folha de cálculo é semelhante a esta imagem:

![após a execução de empty](./media/use-expressions-in-conditions/spreadsheet-table-after-empty-expression-runs.png)

Observe que as linhas adicionais são removidas da tabela.

## <a name="use-the-greater-expression"></a>Utilizar a expressão greater
Imagine que comprou bilhetes de basebol para os seus colegas de trabalho e está a utilizar uma folha de cálculo para se certificar de que cada um o irá reembolsar. Pode criar rapidamente um fluxo que envia um e-mail diário a cada pessoa que não tenha pago a quantia total.

Utilize a expressão **greater** para identificar os empregados que ainda não tenham pago a quantia total. Pode, em seguida, enviar automaticamente por e-mail um lembrete amigável a quem ainda não tenha pago tudo.

Eis uma vista da folha de cálculo:

![vista da folha de cálculo](./media/use-expressions-in-conditions/tickets-spreadsheet-table.png)

Eis a implementação da expressão **greater** que identifica todas as pessoas que pagaram menos do que a quantia devida:

````@greater(item()?['Due'], item()?['Paid'])````

## <a name="use-the-less-expression"></a>Utilizar a expressão less
Imagine que comprou bilhetes de basebol para os seus colegas de trabalho e está a utilizar uma folha de cálculo para se certificar de que cada um o irá reembolsar até à data acordada por todos. Pode criar um fluxo que envia por e-mail um lembrete a cada pessoa que não tenha pago a quantia total se a data atual corresponder a menos de um dia da data combinada.

Utilize a expressão **and** juntamente com a expressão **less** uma vez que existem duas condições a ser validadas:


|          Condição a validar          | expressão a utilizar |                    Exemplo                     |
|-----------------------------------------|-------------------|------------------------------------------------|
|   A quantia total devida foi paga?    |      greater      |   @greater(item()?['Due'], item()?['Paid'])    |
| A data de vencimento corresponde a menos de um dia da data atual? |       less        | @less(item()?['DueDate'], addDays(utcNow(),1)) |

## <a name="combine-the-greater-and-less-expressions-in-an-and-expression"></a>Combine as expressões greater e less numa expressão and
Utilize a expressão **greater** para identificar os empregados que pagaram menos do que a quantia total devida e utilize a expressão **less** para determinar se a data de vencimento corresponde a menos de um dia da data atual. Pode, em seguida, utilizar a função **Enviar um e-mail** para enviar por e-mail um lembrete amigável a quem não tenha pago tudo e cuja data de vencimento corresponda a menos de um dia da data atual.

Eis uma vista da tabela da folha de cálculo:

![vista da folha de cálculo](./media/use-expressions-in-conditions/spreadsheet-table-due-date.png)

Eis a implementação da expressão **and** que identifica todas as pessoas que pagaram menos do que a quantia devida e cuja data de vencimento corresponde a menos de um dia da data atual:

````@and(greater(item()?['Due'], item()?['Paid']), less(item()?['dueDate'], addDays(utcNow(),1)))````

## <a name="use-functions-in-expressions"></a>Use functions in expressions (Referência: utilizar funções em expressões)

Algumas expressões obtêm os respetivos valores a partir de ações de runtime que poderão ainda não existir no momento em que um fluxo começa a ser executado. Para fazer referência a ou trabalhar com estes valores em expressões, pode utilizar as funções fornecidas pela Linguagem de Definição do Fluxo de Trabalho. Mais informações: [Referência às funções da Linguagem de Definição do Fluxo de Trabalho no Power Automate](https://docs.microsoft.com/azure/logic-apps/workflow-definition-language-functions-reference)
