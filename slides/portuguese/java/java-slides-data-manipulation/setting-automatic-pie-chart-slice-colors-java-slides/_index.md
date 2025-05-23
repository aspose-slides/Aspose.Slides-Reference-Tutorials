---
"description": "Aprenda a criar gráficos de pizza dinâmicos com cores de fatias automáticas em apresentações do PowerPoint em Java usando o Aspose.Slides para Java. Guia passo a passo com código-fonte."
"linktitle": "Configurando cores automáticas de fatias de gráfico de pizza em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Configurando cores automáticas de fatias de gráfico de pizza em slides Java"
"url": "/pt/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/"
"weight": 24
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Configurando cores automáticas de fatias de gráfico de pizza em slides Java


## Introdução à configuração automática de cores de fatias de gráficos de pizza em slides Java

Neste tutorial, exploraremos como criar um gráfico de pizza em uma apresentação do PowerPoint usando o Aspose.Slides para Java e definir cores de fatias automáticas para o gráfico. Forneceremos instruções passo a passo, juntamente com o código-fonte.

## Pré-requisitos

Antes de começar, certifique-se de ter a biblioteca Aspose.Slides para Java instalada e configurada no seu projeto Java. Você pode baixar a biblioteca no site da Aspose: [Baixe Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

## Etapa 1: Importar os pacotes necessários

Primeiro, você precisa importar os pacotes necessários do Aspose.Slides para Java:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## Etapa 2: Crie uma apresentação do PowerPoint

Instanciar o `Presentation` classe para criar uma nova apresentação do PowerPoint:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Etapa 3: Adicionar um slide

Acesse o primeiro slide da apresentação e adicione um gráfico com dados padrão:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Etapa 4: definir título do gráfico

Defina um título para o gráfico:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Etapa 5: Configurar dados do gráfico

Defina o gráfico para mostrar valores para a primeira série e configure os dados do gráfico:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Etapa 6: Adicionar categorias e séries

Adicione novas categorias e séries ao gráfico:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Etapa 7: preencher dados da série

Preencha os dados da série para o gráfico de pizza:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Etapa 8: Habilitar cores variadas de fatias

Habilitar cores variadas de fatias para o gráfico de pizza:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Etapa 9: Salve a apresentação

Por fim, salve a apresentação em um arquivo do PowerPoint:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Código-fonte completo para definir cores automáticas de fatias de gráfico de pizza em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Instanciar classe de apresentação que representa arquivo PPTX
Presentation presentation = new Presentation();
try
{
	// Acesse o primeiro slide
	ISlide slides = presentation.getSlides().get_Item(0);
	// Adicionar gráfico com dados padrão
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Título do gráfico de configuração
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// Defina a primeira série para Mostrar Valores
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Definindo o índice da planilha de dados do gráfico
	int defaultWorksheetIndex = 0;
	// Obtendo a planilha de dados do gráfico
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Excluir séries e categorias geradas por padrão
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// Adicionando novas categorias
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Adicionando novas séries
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// Agora preenchendo dados de série
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusão

Você criou com sucesso um gráfico de pizza em uma apresentação do PowerPoint usando o Aspose.Slides para Java e o configurou para ter cores de fatias automáticas. Este guia passo a passo fornece o código-fonte necessário para isso. Você pode personalizar ainda mais o gráfico e a apresentação conforme necessário.

## Perguntas frequentes

### Como posso personalizar as cores de fatias individuais no gráfico de pizza?

Para personalizar as cores de fatias individuais no gráfico de pizza, você pode usar o `getAutomaticSeriesColors` Método para recuperar o esquema de cores padrão e, em seguida, modificar as cores conforme necessário. Veja um exemplo:

```java
// Obtenha o esquema de cores padrão
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Modifique as cores conforme necessário
colors.get_Item(0).setColor(Color.RED); // Defina a cor da primeira fatia para vermelho
colors.get_Item(1).setColor(Color.BLUE); // Defina a cor da segunda fatia para azul
// Adicione mais modificações de cor conforme necessário
```

### Como posso adicionar uma legenda ao gráfico de pizza?

Para adicionar uma legenda ao gráfico de pizza, você pode usar o `getLegend` método e configure-o da seguinte maneira:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Defina a posição da legenda
legend.setOverlay(true); // Exibir a legenda sobre o gráfico
```

### Posso alterar a fonte e o estilo do título?

Sim, você pode alterar a fonte e o estilo do título. Use o seguinte código para definir a fonte e o estilo do título:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Definir tamanho da fonte
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Deixe o título em negrito
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Coloque o título em itálico
```

Você pode ajustar o tamanho da fonte, o negrito e o estilo itálico conforme necessário.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}