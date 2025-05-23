---
"description": "Aprenda a definir a largura da lacuna em slides Java com o Aspose.Slides para Java. Aprimore os visuais dos gráficos para suas apresentações do PowerPoint."
"linktitle": "Definir largura de lacuna em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Definir largura de lacuna em slides Java"
"url": "/pt/java/data-manipulation/set-gap-width-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Definir largura de lacuna em slides Java


## Introdução à configuração de largura de lacuna no Aspose.Slides para Java

Neste tutorial, guiaremos você pelo processo de definição da Largura da Lacuna para um gráfico em uma apresentação do PowerPoint usando o Aspose.Slides para Java. A Largura da Lacuna determina o espaçamento entre as colunas ou barras de um gráfico, permitindo que você controle a aparência visual do gráfico.

## Pré-requisitos

Antes de começar, certifique-se de ter a biblioteca Aspose.Slides para Java instalada. Você pode baixá-la do site da Aspose. [aqui](https://releases.aspose.com/slides/java/).

## Guia passo a passo

Siga estas etapas para definir a largura da lacuna em um gráfico usando o Aspose.Slides para Java:

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
// Adicionar um gráfico com dados padrão
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Defina o índice da planilha de dados do gráfico

```java
// Definindo o índice da planilha de dados do gráfico
int defaultWorksheetIndex = 0;
```

### 5. Obtenha a pasta de trabalho de dados do gráfico

```java
// Obtendo a planilha de dados do gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Adicionar séries ao gráfico

```java
// Adicionar séries ao gráfico
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Adicionar categorias ao gráfico

```java
// Adicionar categorias ao gráfico
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

### 9. Defina a largura da lacuna

```java
// Defina o valor da largura da lacuna
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Salve a apresentação

```java
// Salvar a apresentação com o gráfico
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Código-fonte completo para definir largura de lacuna em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Criando uma apresentação vazia 
Presentation presentation = new Presentation();
// Acesse o primeiro slide
ISlide slide = presentation.getSlides().get_Item(0);
// Adicionar gráfico com dados padrão
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Definindo o índice da planilha de dados do gráfico
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
// Pegue a segunda série de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Agora preenchendo dados de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Definir valor de GapWidth
series.getParentSeriesGroup().setGapWidth(50);
// Salvar apresentação com gráfico
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Conclusão

Neste tutorial, você aprendeu a definir a Largura da Lacuna para um gráfico em uma apresentação do PowerPoint usando o Aspose.Slides para Java. Ajustar a Largura da Lacuna permite controlar o espaçamento entre colunas ou barras no gráfico, aprimorando a representação visual dos seus dados.

## Perguntas frequentes

### Como altero o valor da Largura da Lacuna?

Para alterar a largura da lacuna, use o `setGapWidth` método sobre o `ParentSeriesGroup` da série do gráfico. No exemplo fornecido, definimos a Largura da Lacuna como 50, mas você pode ajustar esse valor de acordo com o espaçamento desejado.

### Posso personalizar outras propriedades do gráfico?

Sim, o Aspose.Slides para Java oferece amplos recursos para personalização de gráficos. Você pode modificar diversas propriedades do gráfico, como cores, rótulos, títulos e muito mais. Consulte a Referência da API para obter informações detalhadas sobre as opções de personalização de gráficos.

### Onde posso encontrar mais recursos e documentação?

Você pode encontrar documentação abrangente e recursos adicionais no Aspose.Slides para Java no [Site Aspose](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}