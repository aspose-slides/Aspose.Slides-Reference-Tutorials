---
"description": "Aprenda a definir um formato de data para o eixo de categorias em um gráfico do PowerPoint usando o Aspose.Slides para Java. Guia passo a passo com código-fonte."
"linktitle": "Definindo o formato de data para o eixo de categoria em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Definindo o formato de data para o eixo de categoria em slides Java"
"url": "/pt/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Definindo o formato de data para o eixo de categoria em slides Java


## Introdução à configuração do formato de data para o eixo de categoria em slides Java

Neste tutorial, aprenderemos como definir um formato de data para o eixo de categorias em um gráfico do PowerPoint usando o Aspose.Slides para Java. O Aspose.Slides para Java é uma biblioteca poderosa que permite criar, manipular e gerenciar apresentações do PowerPoint programaticamente.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

1. Biblioteca Aspose.Slides para Java (você pode baixá-la em [aqui](https://releases.aspose.com/slides/java/).
2. Ambiente de desenvolvimento Java configurado.

## Etapa 1: Crie uma apresentação do PowerPoint

Primeiro, precisamos criar uma apresentação do PowerPoint onde adicionaremos um gráfico. Certifique-se de ter importado as classes Aspose.Slides necessárias.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Etapa 2: adicione um gráfico ao slide

Agora, vamos adicionar um gráfico ao slide do PowerPoint. Usaremos um gráfico de área neste exemplo.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Etapa 3: preparar dados do gráfico

Configuraremos os dados e as categorias do gráfico. Neste exemplo, usaremos categorias de data.

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

// Adicionando séries de dados
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Etapa 4: personalizar o eixo de categoria
Agora, vamos personalizar o eixo de categorias para exibir datas em um formato específico (por exemplo, aaaa).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Etapa 5: Salve a apresentação
Por fim, salve a apresentação do PowerPoint.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Pronto! Você definiu com sucesso um formato de data para o eixo de categorias em um gráfico do PowerPoint usando o Aspose.Slides para Java.

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
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
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

Você personalizou com sucesso o formato de data para o eixo de categorias em um gráfico do Java Slides usando o Aspose.Slides para Java. Isso permite que você apresente valores de data no formato desejado em seus gráficos. Sinta-se à vontade para explorar outras opções de personalização com base em suas necessidades específicas.

## Perguntas frequentes

### Como altero o formato de data para o eixo de categorias?

Para alterar o formato da data do eixo da categoria, use o `setNumberFormat` método no eixo das categorias e forneça o padrão de formato de data desejado, como "aaaa-MM-dd" ou "MM/aaaa". Certifique-se de definir `setNumberFormatLinkedToSource(false)` para substituir o formato padrão.

### Posso usar formatos de data diferentes para gráficos diferentes na mesma apresentação?

Sim, você pode definir formatos de data diferentes para eixos de categoria em diferentes gráficos na mesma apresentação. Basta personalizar o eixo de categoria para cada gráfico conforme necessário.

### Como adiciono mais pontos de dados ao gráfico?

Para adicionar mais pontos de dados ao gráfico, use o `getDataPoints().addDataPointForLineSeries` método na série de dados e fornecer os valores dos dados.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}