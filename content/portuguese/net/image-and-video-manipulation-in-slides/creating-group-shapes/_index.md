---
title: Aspose.Slides - Criando formas de grupo em .NET
linktitle: Criando formas de grupo em slides de apresentação com Aspose.Slides
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como criar formas de grupo no PowerPoint com Aspose.Slides for .NET. Siga nosso guia passo a passo para apresentações visualmente atraentes.
type: docs
weight: 11
url: /pt/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---
## Introdução
Se você deseja aprimorar o apelo visual dos slides da sua apresentação e organizar o conteúdo com mais eficiência, incorporar formas de grupo é uma solução poderosa. Aspose.Slides for .NET fornece uma maneira perfeita de criar e manipular formas de grupo em suas apresentações do PowerPoint. Neste tutorial, percorreremos o processo de criação de formas de grupo usando Aspose.Slides, dividindo-o em etapas fáceis de seguir.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter o seguinte:
-  Aspose.Slides para .NET: Certifique-se de ter a biblioteca Aspose.Slides instalada. Você pode baixá-lo no[local na rede Internet](https://releases.aspose.com/slides/net/).
- Ambiente de desenvolvimento: configure um ambiente de trabalho com um IDE compatível com .NET, como o Visual Studio.
- Conhecimento básico de C#: Familiarize-se com os fundamentos da linguagem de programação C#.
## Importar namespaces
No seu projeto C#, comece importando os namespaces necessários:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Etapa 1: instanciar aula de apresentação

 Crie uma instância do`Presentation` class e especifique o diretório onde seus documentos estão armazenados:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Continue com as etapas a seguir neste bloco de uso
}
```

## Etapa 2: acesse o primeiro slide

Recupere o primeiro slide da apresentação:

```csharp
ISlide sld = pres.Slides[0];
```

## Etapa 3: acessando a coleção de formas

Acesse a coleção de formas no slide:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Etapa 4: adicionar uma forma de grupo

Adicione uma forma de grupo ao slide:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Etapa 5: adicionar formas dentro da forma do grupo

Preencha a forma do grupo com formas individuais:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Etapa 6: adicionar quadro de forma de grupo

Defina a moldura para toda a forma do grupo:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Etapa 7: salve a apresentação

Salve a apresentação modificada no diretório especificado:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Repita essas etapas em seu aplicativo C# para criar formas de grupo com êxito em seus slides de apresentação usando Aspose.Slides.

## Conclusão
Neste tutorial, exploramos o processo de criação de formas de grupo com Aspose.Slides for .NET. Seguindo essas etapas, você pode aprimorar o apelo visual e a organização de suas apresentações em PowerPoint.
## perguntas frequentes
### O Aspose.Slides é compatível com a versão mais recente do .NET?
 Sim, o Aspose.Slides é atualizado regularmente para oferecer suporte às versões mais recentes do .NET. Verifica a[documentação](https://reference.aspose.com/slides/net/) para detalhes de compatibilidade.
### Posso experimentar o Aspose.Slides antes de comprar?
 Absolutamente! Você pode baixar uma versão de teste gratuita[aqui](https://releases.aspose.com/).
### Onde posso encontrar suporte para consultas relacionadas ao Aspose.Slides?
 Visite o Aspose.Slides[fórum](https://forum.aspose.com/c/slides/11) para apoio e discussões da comunidade.
### Como obtenho uma licença temporária para Aspose.Slides?
 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### Onde posso comprar uma licença completa do Aspose.Slides?
 Você pode comprar uma licença no[página de compra](https://purchase.aspose.com/buy).
