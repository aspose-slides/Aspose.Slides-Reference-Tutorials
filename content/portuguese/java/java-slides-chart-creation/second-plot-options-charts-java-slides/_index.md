---
title: Segundas opções de plotagem para gráficos em slides Java
linktitle: Segundas opções de plotagem para gráficos em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como personalizar gráficos em Java Slides usando Aspose.Slides for Java. Explore opções de segundo enredo e aprimore suas apresentações.
type: docs
weight: 12
url: /pt/java/chart-creation/second-plot-options-charts-java-slides/
---

## Introdução às opções de segundo gráfico para gráficos em slides Java

Neste tutorial, exploraremos como adicionar segundas opções de plotagem a gráficos usando Aspose.Slides para Java. As segundas opções de plotagem permitem personalizar a aparência e o comportamento dos gráficos, especialmente em cenários como gráficos de pizza ou pizza. Forneceremos instruções passo a passo e exemplos de código-fonte para conseguir isso. 

## Pré-requisitos
Antes de começar, certifique-se de ter o Aspose.Slides for Java instalado e configurado em seu projeto Java.

## Etapa 1: crie uma apresentação
Vamos começar criando uma nova apresentação:

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie uma instância da classe Presentation
Presentation presentation = new Presentation();
```

## Etapa 2: adicionar um gráfico a um slide
A seguir, adicionaremos um gráfico a um slide. Neste exemplo, criaremos um gráfico de pizza:

```java
// Adicionar gráfico no slide
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Etapa 3: personalizar as propriedades do gráfico
Agora, vamos definir diferentes propriedades para o gráfico, incluindo as segundas opções de plotagem:

```java
// Mostrar rótulos de dados para a primeira série
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Defina o tamanho da segunda torta (em porcentagem)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Divida a torta por porcentagem
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Defina a posição da divisão
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Etapa 4: salve a apresentação
Por fim, salve a apresentação com o gráfico e as segundas opções de plotagem:

```java
// Gravar apresentação em disco
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Código fonte completo para opções de segundo gráfico

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie uma instância da classe Presentation
Presentation presentation = new Presentation();
// Adicionar gráfico no slide
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Defina propriedades diferentes
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Gravar apresentação em disco
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Conclusão

Neste tutorial, aprendemos como adicionar segundas opções de plotagem a gráficos em Java Slides usando Aspose.Slides for Java. Você pode personalizar diversas propriedades para aprimorar a aparência e a funcionalidade de seus gráficos, tornando suas apresentações mais informativas e visualmente atraentes.

## Perguntas frequentes

### Como posso alterar o tamanho da segunda pizza em um gráfico de pizza?

 Para alterar o tamanho da segunda pizza em um gráfico de pizza, use o botão`setSecondPieSize` método conforme mostrado no exemplo de código acima. Ajuste o valor para especificar o tamanho em porcentagem.

###  O que`PieSplitBy` control in a Pie of Pie chart?

 O`PieSplitBy`propriedade controla como o gráfico de pizza é dividido. Você pode configurá-lo para`PieSplitType.ByPercentage` ou`PieSplitType.ByValue` para dividir o gráfico por porcentagem ou por um valor específico, respectivamente.

### Como defino a posição da divisão em um gráfico de pizza?

 Você pode definir a posição da divisão em um gráfico de pizza usando o botão`setPieSplitPosition` método. Ajuste o valor para especificar a posição desejada.