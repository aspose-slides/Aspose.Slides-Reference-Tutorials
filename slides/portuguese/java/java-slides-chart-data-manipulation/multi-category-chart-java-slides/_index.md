---
title: Gráfico multicategoria em slides Java
linktitle: Gráfico multicategoria em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Crie gráficos multicategorias em slides Java usando Aspose.Slides para Java. Guia passo a passo com código-fonte para visualização impressionante de dados em apresentações.
weight: 20
url: /pt/java/chart-data-manipulation/multi-category-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introdução ao gráfico de múltiplas categorias em slides Java com Aspose.Slides

Neste tutorial, aprenderemos como criar um gráfico de múltiplas categorias em slides Java usando a API Aspose.Slides for Java. Este guia fornecerá instruções passo a passo junto com o código-fonte para ajudá-lo a criar um gráfico de colunas agrupadas com várias categorias e séries.

## Pré-requisitos
Antes de começar, certifique-se de ter a biblioteca Aspose.Slides para Java instalada e configurada em seu ambiente de desenvolvimento Java.

## Etapa 1: Configurando o Ambiente
Primeiro, importe as classes necessárias e crie um novo objeto Presentation para trabalhar com slides.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Etapa 2: adicionar um slide e um gráfico
Em seguida, crie um slide e adicione um gráfico de colunas agrupadas a ele.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Etapa 3: limpar os dados existentes
Limpe todos os dados existentes do gráfico.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Etapa 4: configurar categorias de dados
Agora, vamos configurar categorias de dados para o gráfico. Criaremos várias categorias e as agruparemos.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Adicione categorias e agrupe-as
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## Etapa 5: adicionar séries
Agora, vamos adicionar uma série ao gráfico junto com os pontos de dados.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## Etapa 6: salvando a apresentação
Por fim, salve a apresentação com o gráfico.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

É isso! Você criou com sucesso um gráfico de múltiplas categorias em um slide Java usando Aspose.Slides. Você pode personalizar ainda mais este gráfico para atender às suas necessidades específicas.

## Código-fonte completo para gráfico de múltiplas categorias em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
// Adicionando Série
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Salvar apresentação com gráfico
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusão

Neste tutorial, aprendemos como criar um gráfico de múltiplas categorias em slides Java usando a API Aspose.Slides for Java. Seguimos um guia passo a passo com código-fonte para criar um gráfico de colunas agrupado com várias categorias e séries.

## Perguntas frequentes

### Como posso personalizar a aparência do gráfico?

Você pode personalizar a aparência do gráfico modificando propriedades como cores, fontes e estilos. Consulte a documentação do Aspose.Slides para opções de personalização detalhadas.

### Posso adicionar mais séries ao gráfico?

Sim, você pode adicionar séries adicionais ao gráfico seguindo um processo semelhante ao mostrado na Etapa 5.

### Como altero o tipo de gráfico?

 Para alterar o tipo de gráfico, substitua`ChartType.ClusteredColumn` com o tipo de gráfico desejado ao adicionar o gráfico na Etapa 2.

### Como posso adicionar um título ao gráfico?

 Você pode adicionar um título ao gráfico usando o`ch.getChartTitle().getTextFrame().setText("Chart Title");` método.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
