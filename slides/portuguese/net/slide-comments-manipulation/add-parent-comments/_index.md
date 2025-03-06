---
title: Adicionar comentários dos pais ao slide usando Aspose.Slides
linktitle: Adicionar comentários dos pais ao slide
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como adicionar comentários e respostas interativos às suas apresentações do PowerPoint usando Aspose.Slides for .NET. Aumente o envolvimento e a colaboração.
weight: 12
url: /pt/net/slide-comments-manipulation/add-parent-comments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar comentários dos pais ao slide usando Aspose.Slides


Você deseja aprimorar suas apresentações em PowerPoint com recursos interativos? Aspose.Slides for .NET permite incorporar comentários e respostas, criando uma experiência dinâmica e envolvente para o seu público. Neste tutorial passo a passo, mostraremos como adicionar comentários principais aos slides usando Aspose.Slides for .NET. Vamos mergulhar e explorar esse recurso interessante.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:

1.  Aspose.Slides for .NET: Certifique-se de ter o Aspose.Slides for .NET instalado. Você pode baixá-lo[aqui](https://releases.aspose.com/slides/net/).

2. Visual Studio: você precisará do Visual Studio para criar e executar seu aplicativo .NET.

3. Conhecimento básico de C#: Este tutorial pressupõe que você tenha um conhecimento básico de programação C#.

Agora que cobrimos os pré-requisitos, vamos importar os namespaces necessários.

## Importando Namespaces

Primeiro, você precisará importar os namespaces relevantes para o seu projeto. Esses namespaces fornecem as classes e métodos necessários para trabalhar com Aspose.Slides for .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

Com os pré-requisitos e namespaces em vigor, vamos dividir o processo em várias etapas para adicionar comentários principais a um slide.

## Etapa 1: crie uma apresentação

Para começar, você precisa criar uma nova apresentação usando Aspose.Slides for .NET. Esta apresentação será a tela na qual você adicionará seus comentários.

```csharp
// O caminho para o diretório de saída.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // Seu código para adicionar comentários irá aqui.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

 No código acima, substitua`"Output Path"` com o caminho desejado para sua apresentação de saída.

## Etapa 2: adicionar autores de comentários

Antes de adicionar comentários, você precisa definir os autores desses comentários. Neste exemplo, temos dois autores, "Autor_1" e "Autor_2", cada um representado por uma instância de`ICommentAuthor`.

```csharp
// Adicionar comentário
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// Adicionar resposta ao comentário1
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

Nesta etapa, criamos dois autores de comentários e adicionamos o comentário inicial e uma resposta ao comentário.

## Etapa 3: adicionar mais respostas

Para criar uma estrutura hierárquica de comentários, você pode adicionar mais respostas aos comentários existentes. Aqui, adicionamos uma segunda resposta a “comment1”.

```csharp
// Adicionar resposta ao comentário1
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

Isso estabelece um fluxo de conversa em sua apresentação.

## Etapa 4: adicionar respostas aninhadas

Os comentários também podem ter respostas aninhadas. Para demonstrar isso, adicionamos uma resposta à “resposta 2 para o comentário 1”, criando uma sub-resposta.

```csharp
// Adicionar resposta à resposta
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

Esta etapa destaca a versatilidade do Aspose.Slides for .NET no gerenciamento de hierarquias de comentários.

## Etapa 5: mais comentários e respostas

Você pode continuar adicionando mais comentários e respostas conforme necessário. Neste exemplo, adicionamos mais dois comentários e uma resposta a um deles.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

Esta etapa demonstra como você pode criar conteúdo envolvente e interativo para suas apresentações.

## Etapa 6: exibir a hierarquia

Para visualizar a hierarquia de comentários, você pode exibi-la no console. Esta etapa é opcional, mas pode ser útil para depurar e compreender a estrutura.

```csharp
ISlide slide = pres.Slides[0];
var comments = slide.GetSlideComments(null);
for (int i = 0; i < comments.Length; i++)
{
    IComment comment = comments[i];
    while (comment.ParentComment != null)
    {
        Console.Write("\t");
        comment = comment.ParentComment;
    }

    Console.Write("{0} : {1}", comments[i].Author.Name, comments[i].Text);
    Console.WriteLine();
}
```

## Etapa 7: remover comentários

Em alguns casos, pode ser necessário remover comentários e suas respostas. O trecho de código abaixo demonstra como remover “comment1” e todas as suas respostas.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

Esta etapa é útil para gerenciar e atualizar o conteúdo da sua apresentação.

Com essas etapas, você pode criar apresentações com comentários e respostas interativos usando Aspose.Slides for .NET. Esteja você procurando envolver seu público ou colaborar com membros da equipe, esse recurso oferece uma ampla gama de possibilidades.

## Conclusão

Aspose.Slides for .NET fornece um poderoso conjunto de ferramentas para aprimorar suas apresentações em PowerPoint. Com a capacidade de adicionar comentários e respostas, você pode criar conteúdo dinâmico e interativo que cative seu público. Este guia passo a passo mostrou como adicionar comentários principais aos slides, estabelecer hierarquias e até mesmo remover comentários quando necessário. Seguindo estas etapas e explorando a documentação do Aspose.Slides[aqui](https://reference.aspose.com/slides/net/), você pode levar suas apresentações para o próximo nível.

## Perguntas frequentes

### Posso adicionar comentários a slides específicos da minha apresentação?
Sim, você pode adicionar comentários a qualquer slide da sua apresentação especificando o slide de destino ao criar um comentário.

### É possível personalizar a aparência dos comentários na apresentação?
Aspose.Slides for .NET permite personalizar a aparência dos comentários, incluindo texto, informações do autor e posição no slide.

### Posso exportar os comentários e respostas para um arquivo separado?
Sim, você pode exportar comentários e respostas para um arquivo de apresentação separado, conforme demonstrado na etapa 7.

### O Aspose.Slides for .NET é compatível com as versões mais recentes do PowerPoint?
Aspose.Slides for .NET foi projetado para funcionar com uma ampla variedade de versões do PowerPoint, garantindo compatibilidade com os lançamentos mais recentes.

### Há alguma opção de licenciamento disponível para Aspose.Slides for .NET?
 Sim, você pode explorar opções de licenciamento, incluindo licenças temporárias, no site Aspose[aqui](https://purchase.aspose.com/buy) ou experimente o teste gratuito[aqui](https://releases.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
