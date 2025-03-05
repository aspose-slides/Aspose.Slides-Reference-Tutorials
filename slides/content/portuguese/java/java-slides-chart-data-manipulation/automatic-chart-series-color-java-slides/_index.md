---
title: Cor automática da série de gráficos em slides Java
linktitle: Cor automática da série de gráficos em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como criar gráficos dinâmicos com cores de série automáticas em apresentações do PowerPoint usando Aspose.Slides para Java. Aprimore suas visualizações de dados sem esforço.
type: docs
weight: 14
url: /pt/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

## Introdução à cor automática da série de gráficos em Aspose.Slides para Java

Neste tutorial, exploraremos como criar uma apresentação em PowerPoint com um gráfico usando Aspose.Slides para Java e definir cores de preenchimento automático para séries de gráficos. As cores de preenchimento automático podem tornar seus gráficos mais atraentes visualmente e economizar tempo, permitindo que a biblioteca escolha as cores para você.

## Pré-requisitos

 Antes de começar, certifique-se de ter a biblioteca Aspose.Slides for Java instalada em seu projeto. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/java/).

## Etapa 1: crie uma nova apresentação

Primeiro, criaremos uma nova apresentação em PowerPoint e adicionaremos um slide a ela.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie uma instância da classe Presentation
Presentation presentation = new Presentation();
```

## Etapa 2: adicionar um gráfico ao slide

A seguir, adicionaremos um gráfico de colunas agrupadas ao slide. Também definiremos a primeira série para mostrar valores.

```java
// Acesse o primeiro slide
ISlide slide = presentation.getSlides().get_Item(0);
// Adicionar gráfico com dados padrão
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Defina a primeira série para Mostrar Valores
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Etapa 3: preencher os dados do gráfico

Agora, preencheremos o gráfico com dados. Começaremos excluindo as séries e categorias geradas padrão e, em seguida, adicionaremos novas séries e categorias.

```java
// Configurando o índice da planilha de dados do gráfico
int defaultWorksheetIndex = 0;
// Obtendo a planilha de dados do gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Excluir séries e categorias geradas padrão
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Adicionando nova série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Adicionando novas categorias
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Etapa 4: preencher os dados da série

Preenchemos os dados da série para a Série 1 e a Série 2.

```java
// Veja a primeira série de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Agora preenchendo dados de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Veja a segunda série de gráficos
series = chart.getChartData().getSeries().get_Item(1);
// Agora preenchendo dados de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Etapa 5: definir cor de preenchimento automático para séries

Agora, vamos definir cores de preenchimento automático para a série do gráfico. Isso fará com que a biblioteca escolha as cores para nós.

```java
// Configurando cor de preenchimento automático para séries
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Etapa 6: salve a apresentação

Por fim, salvaremos a apresentação com o gráfico em um arquivo PowerPoint.

```java
// Salvar apresentação com gráfico
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Código-fonte completo para cores automáticas de séries de gráficos em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie uma instância da classe Presentation
Presentation presentation = new Presentation();
try
{
	// Acesse o primeiro slide
	ISlide slide = presentation.getSlides().get_Item(0);
	// Adicionar gráfico com dados padrão
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// Defina a primeira série para Mostrar Valores
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Configurando o índice da planilha de dados do gráfico
	int defaultWorksheetIndex = 0;
	// Obtendo a planilha de dados do gráfico
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Excluir séries e categorias geradas padrão
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// Adicionando nova série
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// Adicionando novas categorias
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// Veja a primeira série de gráficos
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// Agora preenchendo dados de série
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Configurando cor de preenchimento automático para séries
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Veja a segunda série de gráficos
	series = chart.getChartData().getSeries().get_Item(1);
	// Agora preenchendo dados de série
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Definir cor de preenchimento para séries
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Salvar apresentação com gráfico
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusão

Neste tutorial, aprendemos como criar uma apresentação em PowerPoint com um gráfico usando Aspose.Slides para Java e definir cores de preenchimento automático para séries de gráficos. As cores automáticas podem melhorar o apelo visual dos seus gráficos e tornar as suas apresentações mais envolventes. Você pode personalizar ainda mais o gráfico conforme necessário para seus requisitos específicos.

## Perguntas frequentes

### Como defino cores de preenchimento automático para séries de gráficos em Aspose.Slides for Java?

Para definir cores de preenchimento automático para séries de gráficos em Aspose.Slides for Java, use o seguinte código:

```java
// Configurando cor de preenchimento automático para séries
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Este código permitirá que a biblioteca escolha as cores automaticamente para a série de gráficos.

### Posso personalizar as cores do gráfico, se necessário?

 Sim, você pode personalizar as cores do gráfico conforme necessário. No exemplo fornecido, usamos cores de preenchimento automático, mas você pode definir cores específicas modificando o`FillType` e`SolidFillColor` propriedades do formato da série.

### Como posso adicionar séries ou categorias adicionais ao gráfico?

 Para adicionar séries ou categorias adicionais ao gráfico, use o`getSeries()` e`getCategories()` métodos do gráfico`ChartData` objeto. Você pode adicionar novas séries e categorias especificando seus dados e rótulos.

### É possível formatar ainda mais o gráfico e os rótulos?

Sim, você pode formatar ainda mais o gráfico, as séries e os rótulos conforme necessário. Aspose.Slides for Java oferece amplas opções de formatação para gráficos, incluindo fontes, cores, estilos e muito mais. Você pode explorar a documentação para obter mais detalhes sobre as opções de formatação.

### Onde posso encontrar mais informações sobre como trabalhar com Aspose.Slides for Java?

 Para obter mais informações e documentação detalhada sobre Aspose.Slides for Java, você pode visitar a documentação de referência[aqui](https://reference.aspose.com/slides/java/).