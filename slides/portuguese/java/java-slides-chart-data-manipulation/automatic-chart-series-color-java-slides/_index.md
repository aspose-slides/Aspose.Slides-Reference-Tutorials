---
"description": "Aprenda a criar gráficos dinâmicos com cores de série automáticas em apresentações do PowerPoint usando o Aspose.Slides para Java. Aprimore suas visualizações de dados sem esforço."
"linktitle": "Série de gráficos automáticos coloridos em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Série de gráficos automáticos coloridos em slides Java"
"url": "/pt/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Série de gráficos automáticos coloridos em slides Java


## Introdução à coloração automática de séries de gráficos no Aspose.Slides para Java

Neste tutorial, exploraremos como criar uma apresentação do PowerPoint com um gráfico usando o Aspose.Slides para Java e definir cores de preenchimento automático para séries de gráficos. As cores de preenchimento automático podem tornar seus gráficos mais atraentes visualmente e economizar seu tempo, permitindo que a biblioteca escolha as cores para você.

## Pré-requisitos

Antes de começar, certifique-se de ter a biblioteca Aspose.Slides para Java instalada em seu projeto. Você pode baixá-la em [aqui](https://releases.aspose.com/slides/java/).

## Etapa 1: Crie uma nova apresentação

Primeiro, criaremos uma nova apresentação do PowerPoint e adicionaremos um slide a ela.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie uma instância da classe Presentation
Presentation presentation = new Presentation();
```

## Etapa 2: adicione um gráfico ao slide

Em seguida, adicionaremos um gráfico de colunas agrupadas ao slide. Também definiremos a primeira série para exibir valores.

```java
// Acesse o primeiro slide
ISlide slide = presentation.getSlides().get_Item(0);
// Adicionar gráfico com dados padrão
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Defina a primeira série para Mostrar Valores
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Etapa 3: preencher dados do gráfico

Agora, preencheremos o gráfico com dados. Começaremos excluindo as séries e categorias geradas por padrão e, em seguida, adicionaremos novas séries e categorias.

```java
// Definindo o índice da planilha de dados do gráfico
int defaultWorksheetIndex = 0;
// Obtendo a planilha de dados do gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Excluir séries e categorias geradas por padrão
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Adicionando novas séries
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Adicionando novas categorias
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Etapa 4: preencher dados da série

Preencheremos os dados da série 1 e da série 2.

```java
// Pegue a primeira série de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Agora preenchendo dados de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Pegue a segunda série de gráficos
series = chart.getChartData().getSeries().get_Item(1);
// Agora preenchendo dados de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Etapa 5: definir cor de preenchimento automático para séries

Agora, vamos definir cores de preenchimento automático para a série do gráfico. Isso fará com que a biblioteca escolha as cores para nós.

```java
// Configurando a cor de preenchimento automático para séries
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Etapa 6: Salve a apresentação

Por fim, salvaremos a apresentação com o gráfico em um arquivo do PowerPoint.

```java
// Salvar apresentação com gráfico
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Código-fonte completo para colorir séries de gráficos automaticamente em slides Java

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
	// Definindo o índice da planilha de dados do gráfico
	int defaultWorksheetIndex = 0;
	// Obtendo a planilha de dados do gráfico
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Excluir séries e categorias geradas por padrão
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// Adicionando novas séries
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// Adicionando novas categorias
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// Pegue a primeira série de gráficos
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// Agora preenchendo dados de série
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Configurando a cor de preenchimento automático para séries
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Pegue a segunda série de gráficos
	series = chart.getChartData().getSeries().get_Item(1);
	// Agora preenchendo dados de série
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Definindo cor de preenchimento para séries
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

Neste tutorial, aprendemos a criar uma apresentação do PowerPoint com um gráfico usando o Aspose.Slides para Java e a definir cores de preenchimento automáticas para séries de gráficos. Cores automáticas podem aprimorar o apelo visual dos seus gráficos e tornar suas apresentações mais envolventes. Você pode personalizar ainda mais o gráfico conforme necessário, de acordo com suas necessidades específicas.

## Perguntas frequentes

### Como defino cores de preenchimento automático para séries de gráficos no Aspose.Slides para Java?

Para definir cores de preenchimento automático para séries de gráficos no Aspose.Slides para Java, use o seguinte código:

```java
// Configurando a cor de preenchimento automático para séries
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Este código permitirá que a biblioteca escolha cores automaticamente para a série de gráficos.

### Posso personalizar as cores do gráfico, se necessário?

Sim, você pode personalizar as cores do gráfico conforme necessário. No exemplo fornecido, usamos cores de preenchimento automático, mas você pode definir cores específicas modificando o `FillType` e `SolidFillColor` propriedades do formato da série.

### Como posso adicionar séries ou categorias adicionais ao gráfico?

Para adicionar séries ou categorias adicionais ao gráfico, use o `getSeries()` e `getCategories()` métodos do gráfico `ChartData` objeto. Você pode adicionar novas séries e categorias especificando seus dados e rótulos.

### É possível formatar ainda mais o gráfico e os rótulos?

Sim, você pode formatar o gráfico, as séries e os rótulos conforme necessário. O Aspose.Slides para Java oferece diversas opções de formatação para gráficos, incluindo fontes, cores, estilos e muito mais. Você pode consultar a documentação para obter mais detalhes sobre as opções de formatação.

### Onde posso encontrar mais informações sobre como trabalhar com o Aspose.Slides para Java?

Para obter mais informações e documentação detalhada sobre Aspose.Slides para Java, você pode visitar a documentação de referência [aqui](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}