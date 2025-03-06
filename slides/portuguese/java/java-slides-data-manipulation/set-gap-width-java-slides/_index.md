---
title: Definir largura da lacuna em slides Java
linktitle: Definir largura da lacuna em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como definir a largura da lacuna em slides Java com Aspose.Slides para Java. Aprimore o visual dos gráficos para suas apresentações em PowerPoint.
weight: 21
url: /pt/java/data-manipulation/set-gap-width-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introdução à configuração da largura da lacuna em Aspose.Slides para Java

Neste tutorial, iremos guiá-lo através do processo de configuração da largura do intervalo para um gráfico em uma apresentação do PowerPoint usando Aspose.Slides para Java. A largura do intervalo determina o espaçamento entre as colunas ou barras em um gráfico, permitindo controlar a aparência visual do gráfico.

## Pré-requisitos

 Antes de começar, certifique-se de ter a biblioteca Aspose.Slides for Java instalada. Você pode baixá-lo no site Aspose[aqui](https://releases.aspose.com/slides/java/).

## Guia passo a passo

Siga estas etapas para definir a largura do intervalo em um gráfico usando Aspose.Slides para Java:

### 1. Crie uma apresentação vazia

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";

// Criando uma apresentação vazia
Presentation presentation = new Presentation();
```

### 2. Acesse o primeiro slide

```java
// Acesse o primeiro slide
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Adicione um gráfico com dados padrão

```java
// Adicione um gráfico com dados padrão
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Defina o índice da planilha de dados do gráfico

```java
// Configurando o índice da planilha de dados do gráfico
int defaultWorksheetIndex = 0;
```

### 5. Obtenha a apostila de dados do gráfico

```java
// Obtendo a planilha de dados do gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Adicione séries ao gráfico

```java
// Adicione séries ao gráfico
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Adicione categorias ao gráfico

```java
// Adicione categorias ao gráfico
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Preencher dados de série

```java
// Preencher dados de série
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Preenchendo pontos de dados de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Defina a largura do espaço

```java
// Defina o valor da largura do intervalo
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Salve a apresentação

```java
// Salve a apresentação com o gráfico
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Código-fonte completo para definir a largura da lacuna em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Criando apresentação vazia
Presentation presentation = new Presentation();
// Acesse o primeiro slide
ISlide slide = presentation.getSlides().get_Item(0);
// Adicionar gráfico com dados padrão
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Configurando o índice da planilha de dados do gráfico
int defaultWorksheetIndex = 0;
// Obtendo a planilha de dados do gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Adicionar série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Adicionar categorias
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Veja a segunda série de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Agora preenchendo dados de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Definir valor GapWidth
series.getParentSeriesGroup().setGapWidth(50);
// Salvar apresentação com gráfico
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Conclusão

Neste tutorial, você aprendeu como definir a largura do intervalo para um gráfico em uma apresentação do PowerPoint usando Aspose.Slides para Java. Ajustar a largura do intervalo permite controlar o espaçamento entre colunas ou barras no gráfico, melhorando a representação visual dos seus dados.

## Perguntas frequentes

### Como altero o valor da largura do intervalo?

 Para alterar a largura do intervalo, use o`setGapWidth` método no`ParentSeriesGroup`da série de gráficos. No exemplo fornecido, definimos a largura do intervalo como 50, mas você pode ajustar esse valor para o espaçamento desejado.

### Posso personalizar outras propriedades do gráfico?

Sim, Aspose.Slides for Java oferece amplos recursos para personalização de gráficos. Você pode modificar várias propriedades do gráfico, como cores, rótulos, títulos e muito mais. Verifique a Referência da API para obter informações detalhadas sobre as opções de personalização do gráfico.

### Onde posso encontrar mais recursos e documentação?

 Você pode encontrar documentação abrangente e recursos adicionais em Aspose.Slides for Java na página[Aspor site](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
