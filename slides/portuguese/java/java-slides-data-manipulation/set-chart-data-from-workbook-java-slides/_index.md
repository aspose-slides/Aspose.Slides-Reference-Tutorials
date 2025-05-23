---
"description": "Aprenda a definir dados de gráficos de uma pasta de trabalho do Excel em Slides Java usando o Aspose.Slides. Guia passo a passo com exemplos de código para apresentações dinâmicas."
"linktitle": "Definir dados do gráfico da pasta de trabalho em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Definir dados do gráfico da pasta de trabalho em slides Java"
"url": "/pt/java/data-manipulation/set-chart-data-from-workbook-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Definir dados do gráfico da pasta de trabalho em slides Java


## Introdução aos dados do gráfico de conjuntos da pasta de trabalho em slides Java

Aspose.Slides para Java é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com apresentações do PowerPoint programaticamente. Ela oferece recursos abrangentes para criar, manipular e gerenciar slides do PowerPoint. Um requisito comum ao trabalhar com apresentações é definir dados de gráfico dinamicamente a partir de uma fonte de dados externa, como uma pasta de trabalho do Excel. Neste tutorial, demonstraremos como fazer isso usando Java.

## Pré-requisitos

Antes de começarmos a implementação, certifique-se de ter os seguintes pré-requisitos:

- Java Development Kit (JDK) instalado no seu sistema.
- Biblioteca Aspose.Slides para Java adicionada ao seu projeto.
- Uma pasta de trabalho do Excel com os dados que você deseja usar para o gráfico.

## Etapa 1: Crie uma apresentação

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

Começamos criando uma nova apresentação do PowerPoint usando o Aspose.Slides para Java.

## Etapa 2: Adicionar um gráfico

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Em seguida, adicionamos um gráfico a um dos slides da apresentação. Neste exemplo, estamos adicionando um gráfico de pizza, mas você pode escolher o tipo de gráfico que melhor se adapta às suas necessidades.

## Etapa 3: Limpar dados do gráfico

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Limpamos todos os dados existentes do gráfico para prepará-lo para novos dados da pasta de trabalho do Excel.

## Etapa 4: Carregar pasta de trabalho do Excel

```java
Workbook workbook = new Workbook("Your Document Directory";
```

Carregamos a pasta de trabalho do Excel que contém os dados que queremos usar para o gráfico. Substituir `"book1.xlsx"` com o caminho para seu arquivo Excel.

## Etapa 5: gravar o fluxo da pasta de trabalho nos dados do gráfico

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Convertemos os dados da pasta de trabalho do Excel em um fluxo e os gravamos nos dados do gráfico.

## Etapa 6: definir intervalo de dados do gráfico

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Especificamos o intervalo de células da pasta de trabalho do Excel que deve ser usado como dados para o gráfico. Ajuste o intervalo conforme necessário para os seus dados.

## Etapa 7: personalizar séries de gráficos

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Você pode personalizar diversas propriedades da série de gráficos para atender às suas necessidades. Neste exemplo, habilitamos cores variadas para a série de gráficos.

## Etapa 8: Salve a apresentação

```java
pres.save(outPath, SaveFormat.Pptx);
```

Por fim, salvamos a apresentação com os dados do gráfico atualizados no caminho de saída especificado.

## Código-fonte completo para dados de gráficos de conjuntos de planilhas em slides Java

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## Conclusão

Neste tutorial, aprendemos como definir dados de gráficos de uma pasta de trabalho do Excel no Java Slides usando a biblioteca Aspose.Slides para Java. Seguindo o guia passo a passo e usando os exemplos de código-fonte fornecidos, você pode integrar facilmente dados dinâmicos de gráficos às suas apresentações do PowerPoint.

## Perguntas frequentes

### Como posso personalizar a aparência do gráfico na minha apresentação?

Você pode personalizar a aparência do gráfico modificando propriedades como cores, fontes, rótulos e muito mais. Consulte a documentação do Aspose.Slides para Java para obter informações detalhadas sobre as opções de personalização de gráficos.

### Posso usar dados de um arquivo Excel diferente para o gráfico?

Sim, você pode usar dados de qualquer arquivo do Excel especificando o caminho correto do arquivo ao carregar a pasta de trabalho no código.

### Que outros tipos de gráficos posso criar com o Aspose.Slides para Java?

O Aspose.Slides para Java suporta vários tipos de gráficos, incluindo gráficos de barras, gráficos de linhas, gráficos de dispersão e muito mais. Você pode escolher o tipo de gráfico que melhor se adapta às suas necessidades de representação de dados.

### É possível atualizar os dados do gráfico dinamicamente em uma apresentação em execução?

Sim, você pode atualizar os dados do gráfico dinamicamente em uma apresentação modificando a pasta de trabalho subjacente e atualizando os dados do gráfico.

### Onde posso encontrar mais exemplos e recursos para trabalhar com o Aspose.Slides para Java?

Você pode explorar exemplos e recursos adicionais no [Site Aspose](https://www.aspose.com/). Além disso, a documentação do Aspose.Slides para Java fornece orientação abrangente sobre como trabalhar com a biblioteca.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}