---
"description": "Aprenda a definir cores de preenchimento invertidas para gráficos Java Slides usando o Aspose.Slides. Aprimore suas visualizações de gráficos com este guia passo a passo e código-fonte."
"linktitle": "Definir gráfico de cores de preenchimento invertido em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Definir gráfico de cores de preenchimento invertido em slides Java"
"url": "/pt/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Definir gráfico de cores de preenchimento invertido em slides Java


## Introdução ao gráfico de cores de preenchimento invertido em slides Java

Neste tutorial, demonstraremos como definir a cor de preenchimento invertida para um gráfico no Java Slides usando o Aspose.Slides para Java. Inverter a cor de preenchimento é um recurso útil quando você deseja destacar valores negativos em um gráfico com uma cor específica. Forneceremos instruções passo a passo e o código-fonte para isso.

## Pré-requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Biblioteca Aspose.Slides para Java instalada.
2. Ambiente de desenvolvimento Java configurado.

## Etapa 1: Crie uma apresentação

Primeiro, precisamos criar uma apresentação para adicionar nosso gráfico. Você pode usar o seguinte código para criar uma apresentação:

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Etapa 2: Adicionar um gráfico

Em seguida, adicionaremos um gráfico de colunas agrupadas à apresentação. Veja como fazer isso:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Etapa 3: Configurar dados do gráfico

Agora, vamos configurar os dados do gráfico, incluindo séries e categorias:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Adicionando novas séries e categorias
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Etapa 4: preencher dados da série

Agora, vamos preencher os dados da série para o gráfico:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Etapa 5: definir cor de preenchimento invertida

Para definir a cor de preenchimento invertida para a série do gráfico, você pode usar o seguinte código:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

No código acima, definimos a série para inverter a cor de preenchimento para valores negativos e especificamos a cor para o preenchimento invertido.

## Etapa 6: Salve a apresentação

Por fim, salve a apresentação com o gráfico:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Código-fonte completo para o gráfico de cores de preenchimento invertido em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Adicionando novas séries e categorias
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// Pegue a primeira série de gráficos e preencha os dados da série.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Conclusão

Neste tutorial, mostramos como definir a cor de preenchimento invertida para um gráfico no Java Slides usando o Aspose.Slides para Java. Esse recurso permite destacar valores negativos em seus gráficos com uma cor específica, tornando seus dados visualmente mais informativos.

## Perguntas frequentes

Nesta seção, abordaremos algumas perguntas comuns relacionadas à definição da cor de preenchimento invertida para um gráfico no Java Slides usando o Aspose.Slides para Java.

### Como instalo o Aspose.Slides para Java?

Você pode instalar o Aspose.Slides para Java incluindo os arquivos JAR do Aspose.Slides no seu projeto Java. Você pode baixar a biblioteca do [Página de download do Aspose.Slides para Java](https://releases.aspose.com/slides/java/). Siga as instruções de instalação fornecidas na documentação para seu ambiente de desenvolvimento específico.

### Posso personalizar a cor do preenchimento invertido na série de gráficos?

Sim, você pode personalizar a cor do preenchimento invertido na série do gráfico. No exemplo de código fornecido, o `series.getInvertedSolidFillColor().setColor(Color.RED)` a linha define a cor para vermelho para o preenchimento invertido. Você pode substituir `Color.RED` com qualquer outra cor de sua escolha.

### Como posso modificar o tipo de gráfico no Aspose.Slides para Java?

Você pode modificar o tipo de gráfico alterando o `ChartType` parâmetro ao adicionar um gráfico à apresentação. No exemplo de código, usamos `ChartType.ClusteredColumn`. Você pode explorar outros tipos de gráficos, como gráficos de linhas, gráficos de barras, gráficos de pizza, etc., especificando o apropriado `ChartType` valor de enumeração.

### Como adiciono várias séries de dados a um gráfico?

Para adicionar várias séries de dados a um gráfico, você pode usar o `chart.getChartData().getSeries().add(...)` para cada série que você deseja adicionar. Certifique-se de fornecer os pontos de dados e rótulos apropriados para cada série para preencher seu gráfico com várias séries.

### Existe uma maneira de personalizar outros aspectos da aparência do gráfico?

Sim, você pode personalizar vários aspectos da aparência do gráfico, incluindo rótulos de eixo, títulos, legendas e muito mais, usando o Aspose.Slides para Java. Consulte a documentação para obter orientações detalhadas sobre como personalizar os elementos e a aparência do gráfico.

### Posso salvar o gráfico em formatos diferentes?

Sim, você pode salvar o gráfico em diferentes formatos usando o Aspose.Slides para Java. No exemplo de código fornecido, salvamos a apresentação como um arquivo PPTX. Você pode usar diferentes `SaveFormat` opções para salvá-lo em outros formatos, como PDF, PNG ou SVG, dependendo de suas necessidades.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}