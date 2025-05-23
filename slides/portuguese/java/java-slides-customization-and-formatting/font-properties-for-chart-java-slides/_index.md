---
"description": "Aprimore as propriedades da fonte do gráfico em slides Java com o Aspose.Slides para Java. Personalize o tamanho, o estilo e a cor da fonte para apresentações impactantes."
"linktitle": "Propriedades de fonte para gráficos em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Propriedades de fonte para gráficos em slides Java"
"url": "/pt/java/customization-and-formatting/font-properties-for-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Propriedades de fonte para gráficos em slides Java


## Introdução às propriedades de fonte para gráficos em slides Java

Este guia explicará como definir as propriedades da fonte para um gráfico no Java Slides usando o Aspose.Slides. Você pode personalizar o tamanho da fonte e a aparência do texto do gráfico para aprimorar o apelo visual das suas apresentações.

## Pré-requisitos

Antes de começar, certifique-se de ter o Aspose.Slides para API Java integrado ao seu projeto. Se ainda não o fez, você pode baixá-lo do site [Documentação do Aspose.Slides para Java](https://reference.aspose.com/slides/java/).

## Etapa 1: Crie uma apresentação

Primeiro, crie uma nova apresentação usando o seguinte código:

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Etapa 2: Adicionar um gráfico

Agora, vamos adicionar um gráfico de colunas agrupadas à sua apresentação:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Aqui, estamos adicionando um gráfico de colunas agrupadas ao primeiro slide nas coordenadas (100, 100) com uma largura de 500 unidades e uma altura de 400 unidades.

## Etapa 3: personalizar as propriedades da fonte

Em seguida, personalizaremos as propriedades da fonte do gráfico. Neste exemplo, estamos definindo o tamanho da fonte como 20 para todo o texto do gráfico:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Este código define o tamanho da fonte para 20 pontos para todo o texto no gráfico.

## Etapa 4: Mostrar rótulos de dados

Você também pode mostrar rótulos de dados no gráfico usando o seguinte código:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Esta linha de código habilita rótulos de dados para a primeira série no gráfico, exibindo os valores nas colunas do gráfico.

## Etapa 5: Salve a apresentação

Por fim, salve a apresentação com suas propriedades de fonte de gráfico personalizadas:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Este código salvará a apresentação no diretório especificado com o nome de arquivo "FontPropertiesForChart.pptx".

## Código-fonte completo para propriedades de fonte para gráficos em slides Java

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

Neste tutorial, você aprendeu a personalizar as propriedades da fonte de um gráfico no Java Slides usando o Aspose.Slides para Java. Você pode aplicar essas técnicas para aprimorar a aparência dos seus gráficos e apresentações. Explore mais opções no [Documentação do Aspose.Slides para Java](https://reference.aspose.com/slides/java/).

## Perguntas frequentes

### Como posso alterar a cor da fonte?

Para alterar a cor da fonte do texto do gráfico, use `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`, substituindo `Color.RED` com a cor desejada.

### Posso alterar o estilo da fonte (negrito, itálico, etc.)?

Sim, você pode alterar o estilo da fonte. Use `chart.getTextFormat().getPortionFormat().setFontBold(true);` para deixar a fonte em negrito. Da mesma forma, você pode usar `setFontItalic(true)` para torná-lo itálico.

### Como posso personalizar as propriedades da fonte para elementos específicos do gráfico?

Para personalizar as propriedades da fonte para elementos específicos do gráfico, como rótulos de eixo ou texto de legenda, você pode acessar esses elementos e definir suas propriedades de fonte usando métodos semelhantes aos mostrados acima.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}