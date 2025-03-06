---
title: Definir sinal de porcentagem de rótulos de dados em slides Java
linktitle: Definir sinal de porcentagem de rótulos de dados em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como definir rótulos de dados com sinais de porcentagem em apresentações do PowerPoint usando Aspose.Slides para Java. Crie gráficos envolventes com orientação passo a passo e código-fonte.
weight: 17
url: /pt/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definir sinal de porcentagem de rótulos de dados em slides Java


## Introdução ao conjunto de sinal de porcentagem de rótulos de dados em Aspose.Slides para Java

Neste guia, orientaremos você no processo de configuração de rótulos de dados com um sinal de porcentagem usando Aspose.Slides para Java. Criaremos uma apresentação em PowerPoint com um gráfico de colunas empilhadas e configuraremos rótulos de dados para exibir porcentagens.

## Pré-requisitos

 Antes de começar, certifique-se de ter a biblioteca Aspose.Slides para Java adicionada ao seu projeto. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/java/).

## Etapa 1: crie uma nova apresentação

Primeiro, criamos uma nova apresentação em PowerPoint usando Aspose.Slides.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie uma instância da classe Presentation
Presentation presentation = new Presentation();
```

## Etapa 2: adicionar um slide e um gráfico

A seguir, adicionamos um slide e um gráfico de colunas empilhadas à apresentação.

```java
// Obtenha referência do slide
ISlide slide = presentation.getSlides().get_Item(0);

// Adicionar gráfico PercentsStackedColumn em um slide
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Etapa 3: configurar o formato do número do eixo

Para exibir porcentagens, precisamos configurar o formato numérico do eixo vertical do gráfico.

```java
// Defina NumberFormatLinkedToSource como falso
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Etapa 4: adicionar dados do gráfico

Adicionamos dados ao gráfico criando séries e pontos de dados. Neste exemplo, adicionamos duas séries com seus respectivos pontos de dados.

```java
// Obtendo a planilha de dados do gráfico
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Adicionar nova série
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Adicionar nova série
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## Etapa 5: personalizar rótulos de dados

Agora, vamos personalizar a aparência dos rótulos de dados.

```java
// Configurando propriedades LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## Etapa 6: salve a apresentação

Finalmente, salvamos a apresentação em um arquivo PowerPoint.

```java
// Gravar apresentação em disco
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

É isso! Você criou com sucesso uma apresentação do PowerPoint com um gráfico de colunas empilhadas e configurou rótulos de dados para exibir porcentagens usando Aspose.Slides para Java.

## Código-fonte completo para definir sinal de porcentagem de rótulos de dados em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie uma instância da classe Presentation
Presentation presentation = new Presentation();
// Obtenha referência do slide
ISlide slide = presentation.getSlides().get_Item(0);
// Adicionar gráfico PercentsStackedColumn em um slide
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Defina NumberFormatLinkedToSource como falso
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Obtendo a planilha de dados do gráfico
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Adicionar nova série
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Configurando a cor de preenchimento da série
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Configurando propriedades LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Adicionar nova série
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Configurando tipo e cor de preenchimento
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Gravar apresentação em disco
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Conclusão

Seguindo este guia, você aprendeu como criar apresentações envolventes com rótulos de dados baseados em porcentagem, que podem ser particularmente úteis para transmitir informações de maneira eficaz em relatórios de negócios, materiais educacionais e muito mais.

## Perguntas frequentes

### Como posso alterar as cores da série do gráfico?

 Você pode alterar a cor de preenchimento da série do gráfico usando o`setFill` método como mostrado no exemplo.

### Posso personalizar o tamanho da fonte dos rótulos de dados?

Sim, você pode personalizar o tamanho da fonte dos rótulos de dados definindo o`setFontHeight` propriedade conforme demonstrado no código.

### Como posso adicionar mais séries ao gráfico?

 Você pode adicionar séries adicionais ao gráfico usando o`add` método no`IChartSeriesCollection` objeto.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
