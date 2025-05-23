---
"description": "Aprimore apresentações do PowerPoint com o Aspose.Slides para Java. Aprenda a personalizar o tamanho das fontes das legendas e muito mais em nosso guia passo a passo."
"linktitle": "Legenda do tamanho da fonte em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Legenda do tamanho da fonte em slides Java"
"url": "/pt/java/chart-elements/font-size-legend-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Legenda do tamanho da fonte em slides Java


## Introdução à legenda do tamanho da fonte em slides Java

Neste tutorial, você aprenderá a personalizar o tamanho da fonte da legenda em um slide do PowerPoint usando o Aspose.Slides para Java. Forneceremos instruções passo a passo e o código-fonte para realizar essa tarefa.

## Pré-requisitos

Antes de começar, certifique-se de ter a biblioteca Aspose.Slides para Java instalada e configurada em seu projeto Java. Você pode baixar a biblioteca em [aqui](https://releases.aspose.com/slides/java/).

## Etapa 1: Inicializar a apresentação

Primeiro, importe as classes necessárias e inicialize sua apresentação do PowerPoint.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Substituir `"Your Document Directory"` com o caminho real para o seu arquivo do PowerPoint.

## Etapa 2: Adicionar um gráfico

Em seguida, adicionaremos um gráfico ao slide e definiremos o tamanho da fonte da legenda.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

Neste código, criamos um gráfico de colunas agrupadas no primeiro slide e definimos o tamanho da fonte do texto da legenda para 20 pontos. Você pode ajustar o tamanho da fonte. `setFontHeight` valor para alterar o tamanho da fonte conforme necessário.

## Etapa 3: personalizar os valores do eixo

Agora, vamos personalizar os valores do eixo vertical do gráfico.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Aqui, definimos os valores mínimo e máximo para o eixo vertical. Você pode modificar os valores conforme suas necessidades de dados.

## Etapa 4: Salve a apresentação

Por fim, salve a apresentação modificada em um novo arquivo.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Este código salva a apresentação modificada como "output.pptx" no diretório especificado.

## Código-fonte completo para legenda de tamanho de fonte em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Você personalizou com sucesso o tamanho da fonte da legenda em um slide do PowerPoint em Java usando o Aspose.Slides para Java. Você pode explorar ainda mais os recursos do Aspose.Slides para criar apresentações interativas e visualmente atraentes.

## Perguntas frequentes

### Como altero o tamanho da fonte do texto da legenda em um gráfico?

Para alterar o tamanho da fonte do texto da legenda em um gráfico, você pode usar o seguinte código:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

Neste código, criamos um gráfico e definimos o tamanho da fonte do texto da legenda para 20 pontos. Você pode ajustar o `setFontHeight` valor para alterar o tamanho da fonte.

### Posso personalizar outras propriedades da legenda em um gráfico?

Sim, você pode personalizar várias propriedades da legenda em um gráfico usando o Aspose.Slides. Algumas das propriedades comuns que você pode personalizar incluem formatação de texto, posição, visibilidade e muito mais. Por exemplo, para alterar a posição da legenda, você pode usar:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Este código define que a legenda apareça na parte inferior do gráfico. Explore a documentação do Aspose.Slides para mais opções de personalização.

### Como defino valores mínimos e máximos para o eixo vertical em um gráfico?

Para definir valores mínimos e máximos para o eixo vertical em um gráfico, você pode usar o seguinte código:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Aqui, desabilitamos o dimensionamento automático dos eixos e especificamos os valores mínimo e máximo para o eixo vertical. Ajuste os valores conforme necessário para os dados do seu gráfico.

### Onde posso encontrar mais informações e documentação sobre o Aspose.Slides?

Você pode encontrar documentação completa e referências de API para Aspose.Slides para Java no site de documentação do Aspose. Visite [aqui](https://reference.aspose.com/slides/java/) para obter informações detalhadas sobre como usar a biblioteca.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}