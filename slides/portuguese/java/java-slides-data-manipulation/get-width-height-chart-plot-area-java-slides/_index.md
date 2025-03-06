---
title: Obtenha largura e altura da área de plotagem do gráfico em slides Java
linktitle: Obtenha largura e altura da área de plotagem do gráfico em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como recuperar dimensões da área de plotagem do gráfico em Java Slides usando Aspose.Slides for Java. Aprimore suas habilidades de automação do PowerPoint.
weight: 21
url: /pt/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introdução

Os gráficos são uma forma poderosa de visualizar dados em apresentações do PowerPoint. Às vezes, você pode precisar saber as dimensões da área de plotagem de um gráfico por vários motivos, como redimensionar ou reposicionar elementos no gráfico. Este guia demonstrará como obter a largura e a altura da área de plotagem usando Java e Aspose.Slides para Java.

## Pré-requisitos

 Antes de mergulharmos no código, certifique-se de ter a biblioteca Aspose.Slides for Java instalada e configurada em seu projeto Java. Você pode baixar a biblioteca do site Aspose[aqui](https://releases.aspose.com/slides/java/).

## Etapa 1: Configurando o Ambiente

Certifique-se de ter a biblioteca Aspose.Slides for Java adicionada ao seu projeto Java. Você pode fazer isso incluindo a biblioteca nas dependências do seu projeto ou adicionando manualmente o arquivo JAR.

## Etapa 2: Criando uma apresentação em PowerPoint

Vamos começar criando uma apresentação em PowerPoint e adicionando um slide a ela. Isso servirá como contêiner para nosso gráfico.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

 Substituir`"Your Document Directory"` com o caminho para o diretório do seu documento.

## Etapa 3: adicionar um gráfico

Agora, vamos adicionar um gráfico de colunas agrupadas ao slide. Também validaremos o layout do gráfico.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Este código cria um gráfico de colunas agrupadas na posição (100, 100) com dimensões (500, 350).

## Etapa 4: obtendo as dimensões da área de plotagem

Para recuperar a largura e a altura da área de plotagem do gráfico, podemos usar o seguinte código:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

 Agora, as variáveis`x`, `y`, `w` , e`h` contêm os respectivos valores para a coordenada X, coordenada Y, largura e altura da área de plotagem.

## Etapa 5: salvando a apresentação

Por fim, salve a apresentação com o gráfico.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

 Certifique-se de substituir`"Chart_out.pptx"` com o nome do arquivo de saída desejado.

## Código-fonte completo para obter largura e altura da área de plotagem do gráfico em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Salvar apresentação com gráfico
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Neste artigo, abordamos como obter a largura e a altura da área de plotagem de um gráfico em Java Slides usando a API Aspose.Slides for Java. Essas informações podem ser valiosas quando você precisa ajustar dinamicamente o layout dos seus gráficos nas apresentações do PowerPoint.

## Perguntas frequentes

### Como posso alterar o tipo de gráfico para algo diferente de colunas agrupadas?

 Você pode alterar o tipo de gráfico substituindo`ChartType.ClusteredColumn` com a enumeração do tipo de gráfico desejado, como`ChartType.Line` ou`ChartType.Pie`.

### Posso modificar outras propriedades do gráfico?

Sim, você pode modificar várias propriedades do gráfico, como dados, rótulos e formatação, usando a API Aspose.Slides for Java. Consulte a documentação para obter mais detalhes.

### O Aspose.Slides for Java é adequado para automação profissional de PowerPoint?

Sim, Aspose.Slides for Java é uma biblioteca poderosa para automatizar tarefas do PowerPoint em aplicativos Java. Ele fornece recursos abrangentes para trabalhar com apresentações, slides, formas, gráficos e muito mais.

### Como posso aprender mais sobre Aspose.Slides para Java?

 Você pode encontrar documentação extensa e exemplos na página de documentação Aspose.Slides for Java[aqui](https://reference.aspose.com/slides/java/).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
