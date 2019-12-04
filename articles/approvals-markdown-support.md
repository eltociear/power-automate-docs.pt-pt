---
title: Utilizar o markdown para formatar aprovações do Power Automate | Microsoft Docs
description: Saiba como utilizar o markdown para formatar pedidos de aprovação do Power Automate.
services: ''
suite: flow
documentationcenter: na
author: gcorvera
manager: kfile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/23/2018
ms.author: gcorvera
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 34689f9f153f8c1b68be3631eac6664561e987ce
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74357456"
---
# <a name="use-markdown-in-power-automate-approval-requests"></a>Utilizar o Markdown em pedidos de aprovação do Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Este artigo mostra como utilizar a sintaxe de [Markdown](https://en.wikipedia.org/wiki/Markdown) para adicionar formatação avançada aos pedidos de aprovação.

> [!IMPORTANT]
> Os e-mails de pedidos de aprovação são *mensagens acionáveis*. Se o [cliente do Microsoft Outlook](https://docs.microsoft.com/outlook/actionable-messages/#outlook-version-requirements-for-actionable-messages) não suportar mensagens acionáveis, apresentará os pedidos de aprovação no formato HTML. 

## <a name="headers"></a>Cabeçalhos

Estruture os seus comentários com cabeçalhos. Os cabeçalhos segmentam comentários mais extensos, tornando mais fácil a sua leitura.

Inicie uma linha com um caráter de hash `#` para definir um cabeçalho. Organize os seus comentários com subcabeçalhos ao iniciar uma linha com carateres de hash adicionais, por exemplo, `####`. São suportados até seis níveis de cabeçalhos.

**Exemplo:**

```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**Resultado:**

![Exportar fluxo](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>Parágrafos e quebras de linha

Torne a leitura do texto mais fácil ao dividi-lo com parágrafos ou quebras de linha. Introduza dois espaços antes da quebra de linha para iniciar um novo parágrafo ou introduza duas quebras de linha consecutivamente para iniciar um novo parágrafo.   
   
**Exemplo**

Adicione linhas entre o texto com a tecla Enter.
Esta ação dá um melhor espaçamento ao texto e faz com que seja mais fácil de ler.

**Resultado:**    
Adicione linhas entre o texto com a tecla Enter.      
Esta ação dá um melhor espaçamento ao texto e faz com que seja mais fácil de ler.


**Exemplo 2**

Adicione dois espaços antes do final da linha. (Espaço, espaço)     
Esta ação adiciona um espaço entre os parágrafos.

**Resultado:**  
Adicione dois espaços antes do final da linha.   

Esta ação adiciona um espaço entre os parágrafos.
  

## <a name="lists"></a>Listas

Organize os itens relacionados através de listas. Pode adicionar listas ordenadas com números ou listas não ordenadas com marcas apenas.

As listas ordenadas começam com um número seguido por um ponto final para cada item da lista. As listas não ordenadas começam com um `*`. Comece cada item da lista numa nova linha. Num widget ou ficheiro de Markdown, introduza dois espaços antes da quebra de linha para iniciar um novo parágrafo ou introduza duas quebras de linha consecutivamente para iniciar um novo parágrafo.   

### <a name="ordered-or-numbered-lists"></a>Listas ordenadas ou numeradas

**Exemplo:**

```Markdown
0. First item.
0. Second item.
0. Third item.
```

**Resultado:**

1. First item.
2. Second item.
3. Third item.

### <a name="bullet-lists"></a>Listas com marcas

**Exemplo:**

<pre>

- Item 1
- Item 2
- Item 3

</pre>

**Resultado:**

- Item 1
- Item 2
- Item 3

### <a name="nested-lists"></a>Listas aninhadas

**Exemplo:**
<pre>

1. First item.
   - Item 1
   - Item 2
   - Item 3
1. Second item.
   - Nested item 1
   - Nested item 2
   - Nested item 3

</pre>

**Resultado:**  

1. First item.

    - Item 1
    - Item 2
    - Item 3
2. Second item.
    - Nested item 1
    - Nested item 2
    - Nested item 3


## <a name="links"></a>Ligações

Os URLs HTTP e HTTPS são automaticamente formatados como ligações. 

Pode definir as hiperligações de texto do URL com a sintaxe de ligação de markdown padrão:

```Markdown
[Link Text](Link URL)
```

**Exemplo:**
<pre>
&#91;Power Automate](https://flow.microsoft.com)
</pre>

**Resultado:**

[Power Automate](https://flow.microsoft.com)

### <a name="anchor-links"></a>Ligações de âncora

Os IDs de âncora são atribuídos a todos os cabeçalhos quando compostos como HTML. O ID é o texto do cabeçalho, com os espaços substituídos por traços (-) e todas as letras em minúsculas.

**Exemplo:**

<pre>
###Link to a heading in the page
</pre>

<br/>

**Resultado:**

A sintaxe de uma ligação de âncora para uma secção...

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre> 
<br/>
O ID é todo em minúsculas e a ligação é sensível às maiúsculas e minúsculas, pelo que não se esqueça de utilizar minúsculas, apesar de o próprio cabeçalho utilizar maiúsculas.


## <a name="tables"></a>Tabelas

Organize os dados estruturados através de tabelas. 

- Coloque cada linha da tabela na sua própria linha 
- Separe as células da tabela com o caráter de pipe `|` 
- As primeiras duas linhas de uma tabela definem os cabeçalhos das colunas e o alinhamento dos elementos na tabela
- Utilize dois pontos (`:`) ao dividir o cabeçalho e o corpo de tabelas para especificar o alinhamento das colunas (à esquerda, ao centro, à direita) 
- Para iniciar uma nova linha, utilize a etiqueta de quebra HTML (`<br/>`) (funciona apenas num Wiki)  
- Confirme que termina cada linha com um CR ou LF. 

**Exemplo:**

```
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
```




**Resultado:**  

| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:---------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>Ênfase (negrito, itálico, rasurado)  

Pode realçar o texto ao aplicar negrito, itálico ou rasurado aos carateres: 
- Para aplicar itálico: rodeie o texto com um asterisco `*` ou um caráter de sublinhado `_`   
- Para aplicar negrito: rodeie o texto com asteriscos duplos `**`.    
- Para aplicar rasurado: rodeie o texto com carateres de til duplos `~~`.   

Combine estes elementos para aplicar várias ênfases no texto.    

**Exemplo:**

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

<br/>

**Resultado:**

Use _emphasis_ in comments to express **strong** opinions and point out <s>corrections</s>   
**_Bold, italicized text_**    
**~~Bold, strike-through text~~**  


## <a name="special-characters"></a>Carateres especiais

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">Sintaxe</th>
<th width="350px">Exemplo/notas</th>
</tr>



<tr>
<td>
<p>Para inserir um dos seguintes carateres, adicione um prefixo com uma barra invertida:</p>

<p style="margin-bottom:2px;">```\   backslash ``` </p>
<p style="margin-bottom:2px;"><code>\`</code>   `backtick`</p>
<p style="margin-bottom:2px;">```_   underscore  ```</p>
<p style="margin-bottom:2px;">```{}  curly braces  ``` </p>
<p style="margin-bottom:2px;">```[]  square brackets ```</p>
<p style="margin-bottom:2px;">```()  parentheses  ```</p>
<p style="margin-bottom:2px;">```#   hash mark  ``` </p>
<p style="margin-bottom:2px;">```+   plus sign  ```</p>
<p style="margin-bottom:2px;">```-   minus sign (hyphen) ```</p>
<p style="margin-bottom:2px;">```.   dot  ``` </p>
<p style="margin-bottom:2px;">```!   exclamation mark ```</p>


</td>
<td>Alguns exemplos de introdução de carateres especiais
<p>Introduza ```\\``` para obter \\ </p>
<p>Introduza ```\_``` para obter _ </p>
<p>Introduza ```\#``` para obter \# </p>
<p>Introduza ```\(``` para obter \( </p>
<p>Introduza ```\.``` para obter \. </p>
<p>Introduza ```\!``` para obter \! </p>
</td>
</tr>

</tbody>
</table>
