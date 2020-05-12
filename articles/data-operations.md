---
title: Compreender as operações de dados | Microsoft Docs
description: Saiba como realizar operações, como criar tabelas HTML, criar tabelas CSV, compor, associar, selecionar e filtrar matrizes com o Power Automate.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/02/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0541a89ad0fe5f8d7dae0acfc6f257be7532ef15
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297566"
---
# <a name="use-data-operations-with-power-automate"></a>Utilizar operações de dados com o Power Automate

Nestas instruções, pode saber mais sobre algumas das operações de dados populares do Power Automate, como compor, associar, selecionar, filtrar matrizes, criar tabelas e analisar JSON que estão disponíveis para manipular dados ao criar fluxos.

## <a name="prerequisites"></a>Pré-requisitos
* Acesso ao Power Automate.
* Uma ferramenta como o [PostMan](https://www.getpostman.com/postman) para enviar pedidos de HTTP POST com uma matriz JSON para o seu fluxo.

## <a name="use-the-compose-action"></a>Utilizar a ação de composição
Utilize a ação **Operações de Dados - Compor** (compor) para impedir que introduza dados idênticos várias vezes ao criar um fluxo. Por exemplo, se precisar de introduzir uma matriz de dígitos: ````[0,1,2,3,4,5,6,7,8,9]```` várias vezes ao criar o seu fluxo, pode utilizar a ação de composição para guardar a matriz desta forma:

1. Procure **Compor** e, em seguida, selecione a ação **Operações de Dados - Compor** (compor).
   
    ![procure e selecione a ação de composição](./media/data-operations/search-select-compose.png)
2. Introduza a matriz na caixa **Entradas** que pretende referenciar mais tarde:
   
    ![configure a ação de composição](./media/data-operations/add-array-compose.png)

> [!TIP]
> Para facilitar a referência mais tarde, mude o nome do cartão **Compor** ao clicar no texto "Compor" na barra de título do cartão **Compor**.
> 
> 

Quando precisar de aceder a conteúdos da ação de composição, faça-o através do token **Saída** na lista **Adicionar conteúdo dinâmico a partir das aplicações e dos conectores utilizados neste fluxo** ao seguir estes passos:

1. Adicione uma ação, como **Operações de Dados – Associar**.
2. Selecione o controlo ao qual pretende adicionar os conteúdos guardados na ação de composição.
   
    A lista **Adicionar conteúdo dinâmico a partir das aplicações e dos conectores utilizados neste fluxo** é aberta.
3. Na lista **Adicionar conteúdo dinâmico a partir das aplicações e dos conectores utilizados neste fluxo**, selecione o token **Saída** que se encontra sob a categoria **Compor** do separador **Conteúdo dinâmico**.
   
    ![utilize a saída da ação de composição](./media/data-operations/use-compose-output.png)

## <a name="use-the-join-action"></a>Utilize a ação de associação
Utilize a ação **Operações de Dados - Associar** (Associar) para delimitar uma matriz com um separador à sua escolha. Por exemplo, suponha que o fluxo de recebe um pedido Web que inclui a seguinte matriz de endereços de e-mail: ````["d@example.com", "k@example.com", "dal@example.com"]````. No entanto, o programa de e-mail precisa que os endereços sejam uma cadeia única que é separada por ponto e vírgula. Para realizar esta ação, utilize a ação **Operações de Dados - Associar** (associar) para alterar o delimitador de vírgulas para um ponto e vírgula ";", ao seguir estes passos:

1. Adicione uma nova ação, procure por **Associar** e, em seguida, selecione **Operações de Dados - Associar** (associar).
   
    ![procure e selecione a ação de associação](./media/data-operations/search-select-join.png)
2. Introduza a matriz na caixa **De** e, em seguida, introduza o novo delimitador que pretende utilizar na caixa **Associar a**.
   
    Aqui, utilizei o ponto e vírgula (;) como o novo delimitador.
   
    ![configure a ação de associação](./media/data-operations/add-array-join.png)
3. Guarde o fluxo e volte a testá-lo.
4. Após as execuções de fluxo, a saída da ação **Operações de Dados – Associar** será:
   
    ![saída da associação](./media/data-operations/join-output.png)

## <a name="use-the-select-action"></a>Utilize a ação de seleção
Utilize a ação **Operações de Dados – Selecionar** (selecionar) para transformar a forma dos objetos numa matriz. Por exemplo, pode adicionar, remover ou mudar o nome de elementos em cada objeto numa matriz.

> [!NOTE]
> Apesar de poder adicionar ou remover elementos com a ação de seleção, não pode alterar o número de objetos na matriz.
> 
> 

Por exemplo, pode utilizar a ação de seleção se os dados introduzirem o seu fluxo através de um pedido Web neste formato:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

e gostaria de voltar a formar os dados de entrada ao mudar o nome de "primeiro" para "NomePróprio", "último" para "Apelido" e adicionar um novo membro com o nome "NomeDeFamília" que combina "primeiro" e "último" (separados com um espaço):

````[ { "FirstName": "Deon", "FamilyName": "Herb", "FullName": "Deon Herb" }, { "FirstName": "K", "FamilyName": "Herb", "FullName": "K Herb" } ]````.

Para tal:

1. Adicione a ação **Pedido/Resposta – Resposta** (pedido) ao fluxo.
2. Selecione **Utilizar payload de amostra para gerar o esquema** a partir do cartão **Pedido**.
3. Na caixa apresentada, cole uma amostra da sua matriz de dados de origem e, em seguida, selecione o botão **Concluído**.
4. Adicione a ação **Operações de Dados – Selecionar** (selecionar) e, em seguida, configure-a como a imagem seguinte.
   
    ![configure a ação de seleção](./media/data-operations/select-card.png)
   
   > [!TIP]
   > A saída da ação de seleção é uma matriz que contém os objetos formados recentemente. Pode, em seguida, utilizar esta matriz em qualquer outra ação, como **Compor**, conforme referido anteriormente.
   > 
   > 

## <a name="use-the-filter-array-action"></a>Utilize a ação de matriz de filtro
Utilize **Operações de Dados - Matriz de filtro** (matriz de filtro) para reduzir o número de objetos numa matriz para um subconjunto que corresponde aos critérios fornecidos.

> [!NOTE]
> A matriz de filtro não pode ser utilizada para alterar a forma dos objetos numa matriz. Além disso, o texto em que filtrar é sensível a maiúsculas e minúsculas.
> 
> 

Por exemplo, pode utilizar a matriz de filtro nesta matriz:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

para criar uma nova matriz que contém apenas os objetos na qual *primeiro* está definido como "Deon".

Vamos realizar este procedimento.

1. Encontre e, em seguida, adicione a ação **Operações de Dados - Matriz de filtro** (matriz de filtro) ao seu fluxo.
2. Configure a ação de matriz de filtro como na imagem seguinte.
   
    ![configure a ação de matriz de filtro](./media/data-operations/add-configure-filter-array.png)
3. Guarde o fluxo e volte a executá-lo.
   
    Pode utilizar o [PostMan](https://www.getpostman.com/postman) para gerar um pedido Web que envia uma matriz JSON para o fluxo.
4. Quando o fluxo é executado, partindo do princípio que a entrada JSON é semelhante a esta matriz:
   
    ````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````,
   
    a saída é semelhante a esta matriz (tenha em atenção que apenas os objetos na qual *primeiro* está definido como "Deon" estão incluídos na saída da ação):
   
    ````[ { "first": "Deon", "last": "Herb" } ]````

## <a name="use-the-create-csv-table-action"></a>Utilize a ação de criação de tabela csv
Utilize a ação **Operações de Dados - Criar tabela CSV** (criar tabela csv) para alterar uma entrada de matriz JSON para uma tabela (CSV) com valores separados por vírgulas. Opcionalmente, pode manter os cabeçalhos visíveis na saída CSV. Por exemplo, pode converter a matriz seguinte numa tabela CSV através da seguinte ação **Criar tabela CSV**:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

1. Encontre, adicione e, em seguida, configure a ação **Operações de Dados - Criar tabela CSV** para assemelhar-se à imagem seguinte.
   
    ![configure a ação de criação de tabela csv](./media/data-operations/create-csv-table.png)
   
    Nota: O token **Corpo** nesta imagem é proveniente de uma ação **Pedido/Resposta – Resposta**, no entanto, pode obter a entrada da ação **Criar tabela CSV** a partir da saída de qualquer ação anterior no seu fluxo ou pode introduzi-lo diretamente para a caixa **De**.
2. Guarde o fluxo e volte a executá-lo.
   
    Quando executa o fluxo, a saída **Criar tabela CSV** é semelhante a esta imagem:
   
    ![criar saída da tabela csv](./media/data-operations/create-csv-table-output.png)

## <a name="use-the-create-html-table-action"></a>Utilize a ação de criação de tabela html
Utilize a ação **Operações de Dados - Criar tabela HTML** para alterar uma entrada de matriz JSON para uma tabela HTML. Opcionalmente, pode manter os cabeçalhos visíveis na saída HTML.

Para o fazer, siga os passos na [secção de criação da tabela csv](#use-the-create-csv-table-action) para obter um exemplo detalhado. Certifique-se de utiliza a ação **Operações de Dados - Criar tabela HTML**, em vez da ação **Operações de Dados - Criar tabela CSV**.

> [!TIP]
> Se pretender enviar a tabela HTML por e-mail, lembre-se de selecionar "IsHtml" na ação do e-mail.
> 
> 

