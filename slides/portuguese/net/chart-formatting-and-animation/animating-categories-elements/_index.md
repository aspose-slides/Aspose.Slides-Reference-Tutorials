---
title: Animações de gráficos poderosas com Aspose.Slides para .NET
linktitle: Animando elementos de categorias no gráfico
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda a animar elementos gráficos no PowerPoint com Aspose.Slides for .NET. Guia passo a passo para apresentações impressionantes.
weight: 11
url: /pt/net/chart-formatting-and-animation/animating-categories-elements/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


No mundo das apresentações, as animações podem dar vida ao seu conteúdo, principalmente quando se trata de gráficos. Aspose.Slides for .NET oferece uma variedade de recursos poderosos que permitem criar animações impressionantes para seus gráficos. Neste guia passo a passo, orientaremos você no processo de animação de elementos de categoria em um gráfico usando Aspose.Slides for .NET.

## Pré-requisitos

Antes de mergulharmos no tutorial, você deve ter os seguintes pré-requisitos em vigor:

-  Aspose.Slides for .NET: Certifique-se de ter o Aspose.Slides for .NET instalado em seu ambiente de desenvolvimento. Se ainda não o fez, você pode baixá-lo em[aqui](https://releases.aspose.com/slides/net/).

- Apresentação existente: você deve ter uma apresentação em PowerPoint com um gráfico que deseja animar. Se você não tiver um, crie um exemplo de apresentação com um gráfico para fins de teste.

Agora que você tem tudo no lugar, vamos começar a animar esses elementos do gráfico!

## Importar namespaces

primeiro passo é importar os namespaces necessários para acessar a funcionalidade do Aspose.Slides. Adicione os seguintes namespaces ao seu projeto:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## Etapa 1: carregar a apresentação

```csharp
// Caminho para o diretório do seu documento
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Obtenha referência do objeto gráfico
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
```

Nesta etapa, carregamos a apresentação existente do PowerPoint contendo o gráfico que você deseja animar. Em seguida, acessamos o objeto gráfico no primeiro slide.

## Etapa 2: animar os elementos das categorias

```csharp
// Animar elementos de categorias
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Esta etapa adiciona um efeito de animação “Fade” a todo o gráfico, fazendo com que ele apareça após a animação anterior.

A seguir, adicionaremos animação a elementos individuais dentro de cada categoria do gráfico. É aqui que a verdadeira magia acontece.

## Etapa 3: animar elementos individuais

Dividiremos a animação de elementos individuais dentro de cada categoria nas seguintes etapas:

### Passo 3.1: Animando Elementos na Categoria 0

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Aqui, estamos animando elementos individuais dentro da categoria 0 do gráfico, fazendo com que apareçam um após o outro. O efeito "Aparecer" é usado para esta animação.

### Etapa 3.2: Animando Elementos na Categoria 1

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

O processo é repetido para a categoria 1, animando seus elementos individuais usando o efeito “Aparecer”.

### Etapa 3.3: Animando Elementos na Categoria 2

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

O mesmo processo continua para a categoria 2, animando seus elementos individualmente.

## Etapa 4: salve a apresentação

```csharp
// Grave o arquivo de apresentação no disco
presentation.Save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
```

Na etapa final, salvamos a apresentação com as animações recém-adicionadas. Agora, os elementos do seu gráfico serão lindamente animados quando você executar a apresentação.

## Conclusão

animação de elementos de categoria em um gráfico pode melhorar o apelo visual de suas apresentações. Com Aspose.Slides for .NET, esse processo se torna simples e eficiente. Você aprendeu como importar namespaces, carregar uma apresentação e adicionar animações ao gráfico inteiro e a seus elementos individuais. Seja criativo e torne suas apresentações mais envolventes com Aspose.Slides for .NET.

## Perguntas frequentes

### 1. Como posso baixar o Aspose.Slides para .NET?
 Você pode baixar Aspose.Slides para .NET em[esse link](https://releases.aspose.com/slides/net/).

### 2. Preciso de experiência em codificação para usar Aspose.Slides for .NET?
Embora a experiência em codificação seja útil, Aspose.Slides for .NET fornece extensa documentação e exemplos para ajudar usuários em todos os níveis de habilidade.

### 3. Posso usar Aspose.Slides for .NET com qualquer versão do PowerPoint?
Aspose.Slides for .NET foi projetado para funcionar com várias versões do PowerPoint, garantindo compatibilidade.

### 4. Como posso obter uma licença temporária do Aspose.Slides for .NET?
 Você pode obter uma licença temporária para Aspose.Slides for .NET[aqui](https://purchase.aspose.com/temporary-license/).

### 5. Existe um fórum da comunidade para suporte do Aspose.Slides for .NET?
 Sim, você pode encontrar um fórum da comunidade de apoio para Aspose.Slides for .NET[aqui](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
