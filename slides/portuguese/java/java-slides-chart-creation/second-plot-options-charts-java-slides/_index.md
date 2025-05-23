---
"description": "Aprenda a personalizar gráficos no Java Slides usando o Aspose.Slides para Java. Explore opções de gráficos secundários e aprimore suas apresentações."
"linktitle": "Opções de segundo gráfico para gráficos em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Opções de segundo gráfico para gráficos em slides Java"
"url": "/pt/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Opções de segundo gráfico para gráficos em slides Java


## Introdução às opções de segundo gráfico para gráficos em slides Java

Neste tutorial, exploraremos como adicionar opções de segundo gráfico a gráficos usando o Aspose.Slides para Java. As opções de segundo gráfico permitem personalizar a aparência e o comportamento dos gráficos, especialmente em cenários como gráficos de pizza. Forneceremos instruções passo a passo e exemplos de código-fonte para isso. 

## Pré-requisitos
Antes de começar, certifique-se de ter o Aspose.Slides para Java instalado e configurado no seu projeto Java.

## Etapa 1: Crie uma apresentação
Vamos começar criando uma nova apresentação:

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie uma instância da classe Presentation
Presentation presentation = new Presentation();
```

## Etapa 2: adicionar um gráfico a um slide
Em seguida, adicionaremos um gráfico a um slide. Neste exemplo, criaremos um gráfico de pizza:

```java
// Adicionar gráfico no slide
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Etapa 3: personalizar as propriedades do gráfico
Agora, vamos definir propriedades diferentes para o gráfico, incluindo opções de segundo gráfico:

```java
// Mostrar rótulos de dados para a primeira série
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Defina o tamanho da segunda torta (em porcentagem)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Dividir a torta por porcentagem
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Defina a posição da divisão
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Etapa 4: Salve a apresentação
Por fim, salve a apresentação com o gráfico e as opções do segundo gráfico:

```java
// Gravar apresentação no disco
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Código-fonte completo para opções de segundo enredo

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie uma instância da classe Presentation
Presentation presentation = new Presentation();
// Adicionar gráfico no slide
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Definir propriedades diferentes
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Gravar apresentação no disco
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Conclusão

Neste tutorial, aprendemos como adicionar opções de segundo gráfico a gráficos no Java Slides usando o Aspose.Slides para Java. Você pode personalizar diversas propriedades para aprimorar a aparência e a funcionalidade dos seus gráficos, tornando suas apresentações mais informativas e visualmente atraentes.

## Perguntas frequentes

### Como posso alterar o tamanho da segunda pizza em um gráfico de pizza?

Para alterar o tamanho da segunda pizza em um gráfico de pizza, use o `setSecondPieSize` método, conforme mostrado no exemplo de código acima. Ajuste o valor para especificar o tamanho em porcentagem.

### que faz `PieSplitBy` controle em um gráfico de pizza ou pizza?

O `PieSplitBy` propriedade controla como o gráfico de pizza é dividido. Você pode defini-lo como `PieSplitType.ByPercentage` ou `PieSplitType.ByValue` para dividir o gráfico por porcentagem ou por um valor específico, respectivamente.

### Como defino a posição da divisão em um gráfico de pizza?

Você pode definir a posição da divisão em um gráfico de pizza usando o `setPieSplitPosition` método. Ajuste o valor para especificar a posição desejada.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}