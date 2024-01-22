---
title: Propriedades de fonte para gráfico em slides Java
linktitle: Propriedades de fonte para gráfico em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprimore as propriedades da fonte do gráfico em slides Java com Aspose.Slides para Java. Personalize o tamanho, o estilo e a cor da fonte para apresentações impactantes.
type: docs
weight: 11
url: /pt/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

## Introdução às propriedades de fonte para gráfico em slides Java

Este guia orientará você na configuração de propriedades de fonte para um gráfico em Java Slides usando Aspose.Slides. Você pode personalizar o tamanho da fonte e a aparência do texto do gráfico para melhorar o apelo visual de suas apresentações.

## Pré-requisitos

 Antes de começar, certifique-se de ter a API Aspose.Slides for Java integrada ao seu projeto. Se ainda não o fez, você pode baixá-lo no site[Documentação Aspose.Slides para Java](https://reference.aspose.com/slides/java/).

## Etapa 1: crie uma apresentação

Primeiro, crie uma nova apresentação usando o seguinte código:

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Etapa 2: adicionar um gráfico

Agora, vamos adicionar um gráfico de colunas agrupadas à sua apresentação:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Aqui, estamos adicionando um gráfico de colunas agrupadas ao primeiro slide nas coordenadas (100, 100) com largura de 500 unidades e altura de 400 unidades.

## Etapa 3: personalizar as propriedades da fonte

A seguir, personalizaremos as propriedades da fonte do gráfico. Neste exemplo, estamos definindo o tamanho da fonte como 20 para todo o texto do gráfico:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Este código define o tamanho da fonte em 20 pontos para todo o texto do gráfico.

## Etapa 4: mostrar rótulos de dados

Você também pode mostrar rótulos de dados no gráfico usando o seguinte código:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Esta linha de código permite rótulos de dados para a primeira série do gráfico, exibindo os valores nas colunas do gráfico.

## Etapa 5: salve a apresentação

Por fim, salve a apresentação com as propriedades de fonte do gráfico personalizadas:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Este código salvará a apresentação no diretório especificado com o nome de arquivo “FontPropertiesForChart.pptx”.

## Código-fonte completo para propriedades de fonte para gráfico em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Neste tutorial, você aprendeu como personalizar as propriedades da fonte para um gráfico no Java Slides usando Aspose.Slides for Java. Você pode aplicar essas técnicas para melhorar a aparência de seus gráficos e apresentações. Explore mais opções no[Documentação Aspose.Slides para Java](https://reference.aspose.com/slides/java/).

## Perguntas frequentes

### Como posso alterar a cor da fonte?

 Para alterar a cor da fonte do texto do gráfico, use`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` , substituindo`Color.RED` com a cor desejada.

### Posso alterar o estilo da fonte (negrito, itálico, etc.)?

 Sim, você pode alterar o estilo da fonte. Usar`chart.getTextFormat().getPortionFormat().setFontBold(true);` para deixar a fonte em negrito. Da mesma forma, você pode usar`setFontItalic(true)` para colocá-lo em itálico.

### Como posso personalizar as propriedades da fonte para elementos específicos do gráfico?

Para personalizar as propriedades da fonte para elementos específicos do gráfico, como rótulos de eixo ou texto de legenda, você pode acessar esses elementos e definir suas propriedades de fonte usando métodos semelhantes aos mostrados acima.