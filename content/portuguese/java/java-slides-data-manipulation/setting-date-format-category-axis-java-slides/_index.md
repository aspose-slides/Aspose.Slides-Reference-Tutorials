---
title: Configurando formato de data para eixo de categoria em slides Java
linktitle: Configurando formato de data para eixo de categoria em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como definir um formato de data para o eixo de categoria em um gráfico do PowerPoint usando Aspose.Slides para Java. Guia passo a passo com código-fonte.
type: docs
weight: 26
url: /pt/java/data-manipulation/setting-date-format-category-axis-java-slides/
---

## Introdução à configuração do formato de data para eixo de categoria em slides Java

Neste tutorial, aprenderemos como definir um formato de data para o eixo de categoria em um gráfico do PowerPoint usando Aspose.Slides para Java. Aspose.Slides for Java é uma biblioteca poderosa que permite criar, manipular e gerenciar apresentações do PowerPoint de forma programática.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

1.  Biblioteca Aspose.Slides para Java (você pode baixá-la em[aqui](https://releases.aspose.com/slides/java/).
2. Ambiente de desenvolvimento Java configurado.

## Etapa 1: crie uma apresentação em PowerPoint

Primeiro, precisamos criar uma apresentação em PowerPoint onde adicionaremos um gráfico. Certifique-se de ter importado as classes Aspose.Slides necessárias.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Etapa 2: adicionar um gráfico ao slide

Agora, vamos adicionar um gráfico ao slide do PowerPoint. Usaremos um gráfico de área neste exemplo.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Etapa 3: preparar dados do gráfico

Configuraremos os dados e categorias do gráfico. Neste exemplo, usaremos categorias de data.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Adicionando categorias de data
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// Adicionando série de dados
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Etapa 4: personalizar o eixo da categoria
Agora, vamos personalizar o eixo de categorias para exibir datas em um formato específico (por exemplo, aaaa).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Etapa 5: salve a apresentação
Finalmente, salve a apresentação do PowerPoint.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

É isso! Você definiu com sucesso um formato de data para o eixo de categoria em um gráfico do PowerPoint usando Aspose.Slides para Java.

## Código-fonte completo para definir o formato de data para o eixo de categoria em slides Java

```java
	// O caminho para o diretório de documentos.
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save(RunExamples.getOutPath() + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

##Conclusão

Você personalizou com sucesso o formato de data para o eixo de categoria em um gráfico Java Slides usando Aspose.Slides for Java. Isso permite apresentar valores de data no formato desejado em seus gráficos. Sinta-se à vontade para explorar outras opções de personalização com base em seus requisitos específicos.

## Perguntas frequentes

### Como altero o formato de data do eixo de categorias?

 Para alterar o formato de data do eixo de categoria, use o botão`setNumberFormat` no eixo de categoria e forneça o padrão de formato de data desejado, como "aaaa-MM-dd" ou "MM/aaaa". Certifique-se de definir`setNumberFormatLinkedToSource(false)` para substituir o formato padrão.

### Posso usar formatos de data diferentes para gráficos diferentes na mesma apresentação?

Sim, você pode definir diferentes formatos de data para eixos de categoria em diferentes gráficos na mesma apresentação. Basta personalizar o eixo de categoria de cada gráfico conforme necessário.

### Como adiciono mais pontos de dados ao gráfico?

 Para adicionar mais pontos de dados ao gráfico, use o`getDataPoints().addDataPointForLineSeries` método na série de dados e forneça os valores dos dados.