---
title: Definir dados do gráfico da pasta de trabalho em slides Java
linktitle: Definir dados do gráfico da pasta de trabalho em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como definir dados de gráfico de uma pasta de trabalho do Excel em Java Slides usando Aspose.Slides. Guia passo a passo com exemplos de código para apresentações dinâmicas.
weight: 15
url: /pt/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introdução à definição de dados de gráfico da pasta de trabalho em slides Java

Aspose.Slides for Java é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com apresentações do PowerPoint de forma programática. Ele fornece recursos abrangentes para criar, manipular e gerenciar slides do PowerPoint. Um requisito comum ao trabalhar com apresentações é definir dados de gráfico dinamicamente a partir de uma fonte de dados externa, como uma pasta de trabalho do Excel. Neste tutorial, demonstraremos como fazer isso usando Java.

## Pré-requisitos

Antes de mergulharmos na implementação, certifique-se de ter os seguintes pré-requisitos:

- Java Development Kit (JDK) instalado em seu sistema.
- Biblioteca Aspose.Slides para Java adicionada ao seu projeto.
- Uma pasta de trabalho do Excel com os dados que você deseja usar no gráfico.

## Etapa 1: crie uma apresentação

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

Começamos criando uma nova apresentação em PowerPoint usando Aspose.Slides para Java.

## Etapa 2: adicionar um gráfico

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

A seguir, adicionamos um gráfico a um dos slides da apresentação. Neste exemplo, estamos adicionando um gráfico de pizza, mas você pode escolher o tipo de gráfico que atende às suas necessidades.

## Etapa 3: limpar os dados do gráfico

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Limpamos todos os dados existentes do gráfico para prepará-los para novos dados da pasta de trabalho do Excel.

## Etapa 4: carregar a pasta de trabalho do Excel

```java
Workbook workbook = new Workbook("Your Document Directory";
```

 Carregamos a pasta de trabalho do Excel que contém os dados que queremos usar para o gráfico. Substituir`"book1.xlsx"` com o caminho para o seu arquivo Excel.

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

Especificamos o intervalo de células da pasta de trabalho do Excel que deve ser usado como dados para o gráfico. Ajuste o intervalo conforme necessário para seus dados.

## Etapa 7: personalizar a série de gráficos

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Você pode personalizar diversas propriedades da série de gráficos para atender às suas necessidades. Neste exemplo, habilitamos cores variadas para a série de gráficos.

## Etapa 8: salve a apresentação

```java
pres.save(outPath, SaveFormat.Pptx);
```

Finalmente, salvamos a apresentação com os dados atualizados do gráfico no caminho de saída especificado.

## Código-fonte completo para definir dados de gráfico da pasta de trabalho em slides Java

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

Neste tutorial, aprendemos como definir dados de gráfico de uma pasta de trabalho do Excel em Java Slides usando a biblioteca Aspose.Slides para Java. Seguindo o guia passo a passo e usando os exemplos de código-fonte fornecidos, você pode integrar facilmente dados de gráficos dinâmicos em suas apresentações do PowerPoint.

## Perguntas frequentes

### Como posso personalizar a aparência do gráfico na minha apresentação?

Você pode personalizar a aparência do gráfico modificando propriedades como cores, fontes, rótulos e muito mais. Consulte a documentação do Aspose.Slides para Java para obter informações detalhadas sobre as opções de personalização do gráfico.

### Posso usar dados de um arquivo Excel diferente para o gráfico?

Sim, você pode usar dados de qualquer arquivo Excel especificando o caminho correto do arquivo ao carregar a pasta de trabalho no código.

### Que outros tipos de gráficos posso criar com Aspose.Slides for Java?

Aspose.Slides for Java oferece suporte a vários tipos de gráficos, incluindo gráficos de barras, gráficos de linhas, gráficos de dispersão e muito mais. Você pode escolher o tipo de gráfico que melhor atende às suas necessidades de representação de dados.

### É possível atualizar os dados do gráfico dinamicamente em uma apresentação em execução?

Sim, você pode atualizar os dados do gráfico dinamicamente em uma apresentação, modificando a pasta de trabalho subjacente e, em seguida, atualizando os dados do gráfico.

### Onde posso encontrar mais exemplos e recursos para trabalhar com Aspose.Slides for Java?

 Você pode explorar exemplos e recursos adicionais no site[Aspor site](https://www.aspose.com/). Além disso, a documentação do Aspose.Slides para Java fornece orientação abrangente sobre como trabalhar com a biblioteca.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
