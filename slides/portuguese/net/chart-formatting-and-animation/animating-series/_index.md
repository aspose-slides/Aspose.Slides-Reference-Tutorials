---
title: Animar série de gráficos com Aspose.Slides para .NET
linktitle: Série de animação em gráfico
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como animar séries de gráficos com Aspose.Slides for .NET. Envolva seu público com apresentações dinâmicas. Comece agora!
weight: 12
url: /pt/net/chart-formatting-and-animation/animating-series/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Você deseja adicionar um toque especial às suas apresentações com gráficos animados? Aspose.Slides for .NET está aqui para dar vida aos seus gráficos. Neste guia passo a passo, mostraremos como animar séries em um gráfico usando Aspose.Slides for .NET. Mas antes de mergulharmos na ação, vamos abordar os pré-requisitos.

## Pré-requisitos

Para animar séries em um gráfico com sucesso usando Aspose.Slides for .NET, você precisará do seguinte:

### 1. Biblioteca Aspose.Slides para .NET

 Certifique-se de ter a biblioteca Aspose.Slides for .NET instalada. Se ainda não o fez, você pode baixá-lo no site[Site Aspose.Slides para .NET](https://releases.aspose.com/slides/net/).

### 2. Apresentação existente com gráfico

Prepare uma apresentação em PowerPoint (PPTX) com um gráfico existente que você deseja animar.

Agora que cobrimos os pré-requisitos, vamos dividir o processo em uma série de etapas para animar a série de gráficos.


## Etapa 1: importar namespaces necessários

Você precisará importar os namespaces necessários em seu código C# para trabalhar com Aspose.Slides for .NET:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Etapa 2: carregar a apresentação existente

Nesta etapa, carregue sua apresentação existente do PowerPoint (PPTX) que contém o gráfico que você deseja animar.

```csharp
// Caminho para o diretório do documento
string dataDir = "Your Document Directory";

// Instanciar a classe Presentation que representa um arquivo de apresentação
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Seu código vai aqui
}
```

## Etapa 3: Obtenha referência do objeto gráfico

Para trabalhar com o gráfico na sua apresentação, você precisará obter uma referência ao objeto gráfico:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## Etapa 4: anime a série

Agora é hora de adicionar efeitos de animação à sua série de gráficos. Adicionaremos um efeito fade-in a todo o gráfico e faremos com que cada série apareça uma por uma.

```csharp
// Animar o gráfico
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Adicione animação a cada série
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## Etapa 5: salve a apresentação modificada

Depois de adicionar os efeitos de animação ao gráfico, salve a apresentação modificada no disco.

```csharp
//Salve a apresentação modificada
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

É isso! Você animou séries em um gráfico com sucesso usando Aspose.Slides for .NET.

## Conclusão

Neste tutorial, orientamos você no processo de animação de séries em um gráfico usando Aspose.Slides for .NET. Com esta biblioteca poderosa, você pode criar apresentações envolventes e dinâmicas que cativam seu público.

 Se você tiver alguma dúvida ou precisar de mais assistência, não hesite em entrar em contato com a comunidade Aspose.Slides em seu site.[Fórum de suporte](https://forum.aspose.com/).

## Perguntas frequentes

### Posso animar outros elementos do gráfico além das séries usando Aspose.Slides for .NET?
Sim, você pode animar vários elementos do gráfico, incluindo pontos de dados, eixos e legendas, usando Aspose.Slides for .NET.

### O Aspose.Slides for .NET é compatível com as versões mais recentes do PowerPoint?
Aspose.Slides for .NET oferece suporte a várias versões do PowerPoint, incluindo PowerPoint 2007 e posteriores, garantindo compatibilidade com as versões mais recentes.

### Posso personalizar os efeitos de animação de cada série de gráficos individualmente?
Sim, você pode personalizar os efeitos de animação para cada série de gráficos para criar apresentações exclusivas e envolventes.

### Existe uma versão de teste disponível para Aspose.Slides for .NET?
 Sim, você pode experimentar a biblioteca com uma avaliação gratuita no[Site Aspose.Slides para .NET](https://releases.aspose.com/).

### Onde posso comprar uma licença do Aspose.Slides for .NET?
 Você pode adquirir uma licença do Aspose.Slides for .NET na página de compra[aqui](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
