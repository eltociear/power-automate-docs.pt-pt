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
ms.date: 4/27/2020
ms.author: gcorvera
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 739d407df91661a6a82aa72f2891a3dac3bda3cf
ms.sourcegitcommit: 28adfdffc00c149bc46fab85b7307e4e819000c8
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/28/2020
ms.locfileid: "82189617"
---
# <a name="use-markdown-in-power-automate-approval-requests"></a>Utilizar o Markdown em pedidos de aprovação do Power Automate


Este artigo mostra como utilizar a sintaxe de [Markdown](https://en.wikipedia.org/wiki/Markdown) para adicionar formatação avançada aos pedidos de aprovação.

> [!IMPORTANT]
> Os e-mails de pedidos de aprovação são *mensagens acionáveis*. Se o [cliente do Microsoft Outlook](https://docs.microsoft.com/outlook/actionable-messages/#outlook-version-requirements-for-actionable-messages) não suportar mensagens acionáveis, apresentará os pedidos de aprovação no formato HTML. 

> [!IMPORTANT]
> Todos os compositores de Markdown têm diferenças de implementação. Reveja a secção [Suporte a Clientes](#client-support) para obter mais detalhes.

## <a name="client-support"></a>Suporte a Clientes

O suporte de markdown entre clientes é inconsistente. A equipa do Power Automate trabalha para resolver estas inconsistências, mas continuam a existir inconsistências. A seguinte tabela estabelece as limitações conhecidas entre os clientes suportados.

| Funcionalidade | Power Automate | Aplicação móvel do Power Automate | Outlook para computador | Outlook Web | Teams | Aplicação móvel do Teams |  
|---------|--------|---------------|-----------------|-------------|-------|--------------|
| **Headers** (Cabeçalhos) | Sim | Sim | Sim | Sim | **_Não_** | **_Não_** |
| **Listas Numeradas** | Sim | Sim | **_Não_** | Sim | Sim | Sim |
| **Listas Numeradas Aninhadas** | Sim | Sim | **_Não_** | Sim | Sim | Sim |
| **Tabelas** | Sim | Sim | Sim | Sim | **_Não_** | **_Não_** |
| **Imagens** | **_Não_** | **_Não_** | **_Não_** | **_Não_** | **_Não_** | **_Não_** |
| **Quebras de Linha Forçadas** | Sim | Sim | **_Não_** (utilizar uma linha em branco em alternativa) | Sim | Sim | Sim |
| **Linhas Em Branco** | **_Não_** | **_Não_** | Sim | Sim | **_Não_** | Sim |

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

Torne a leitura do texto mais fácil ao dividi-lo com parágrafos ou quebras de linha. Introduza dois espaços antes da quebra de linha para forçar a maioria dos clientes a iniciar uma nova linha.  
   
**Exemplo:**  
```Markdown
This is line 1.(space, space)
Now text will appear on the next line.
```

**Resultado:**    
esta é a linha 1.  
Agora, o texto aparecerá na próxima linha. 

**Exemplo 2**  
```Markdown
This is line 1.(space, space)  

Line 2 has extra space before it.
```

**Resultado:**  
esta é a linha 1.  

A linha 2 tem espaço extra antes.
  

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
```Markdown
- Item 1
- Item 2
- Item 3
```

**Resultado:**  
- Item 1
- Item 2
- Item 3

### <a name="nested-lists"></a>Listas aninhadas

**Exemplo:**  
```Markdown
1. First item.
   - Item 1
   - Item 2
   - Item 3
1. Second item.
   - Nested item 1
   - Nested item 2
   - Nested item 3
```

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
```Markdown
[Power Automate](https://flow.microsoft.com)
```

**Resultado:**  
[Power Automate](https://flow.microsoft.com)

## <a name="tables"></a>Tabelas

Organize os dados estruturados através de tabelas. 

- Coloque cada linha da tabela na sua própria linha 
- Separe as células da tabela com o caráter de pipe `|` 
- As primeiras duas linhas de uma tabela definem os cabeçalhos das colunas e o alinhamento dos elementos na tabela
- Utilize dois pontos (`:`) ao dividir o cabeçalho e o corpo de tabelas para especificar o alinhamento das colunas (à esquerda, ao centro, à direita) 
- Para iniciar uma nova linha, utilize a etiqueta de quebra HTML (`<br/>`)
- Confirme que termina cada linha com um CR ou LF. 

**Exemplo:**  
```Markdown
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
```Markdown
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
```

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
