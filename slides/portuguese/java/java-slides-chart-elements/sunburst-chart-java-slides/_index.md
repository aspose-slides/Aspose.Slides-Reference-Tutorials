---
"description": "Crie gráficos de explosão solar impressionantes em slides Java com Aspose.Slides. Aprenda passo a passo a criação de gráficos e manipulação de dados."
"linktitle": "Gráfico Sunburst em Slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Gráfico Sunburst em Slides Java"
"url": "/pt/java/chart-elements/sunburst-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Gráfico Sunburst em Slides Java


## Introdução ao Sunburst Chart em Slides Java com Aspose.Slides

Neste tutorial, você aprenderá a criar um gráfico Sunburst em uma apresentação do PowerPoint usando a API Aspose.Slides para Java. Um gráfico Sunburst é um gráfico radial usado para representar dados hierárquicos. Forneceremos instruções passo a passo juntamente com o código-fonte.

## Pré-requisitos

Antes de começar, certifique-se de ter a biblioteca Aspose.Slides para Java instalada e configurada em seu projeto Java. Você pode baixar a biblioteca em [aqui](https://releases.aspose.com/slides/java/).

## Etapa 1: Importar bibliotecas necessárias

Primeiro, importe as bibliotecas necessárias para trabalhar com o Aspose.Slides e crie um gráfico Sunburst no seu aplicativo Java.

```java
import com.aspose.slides.*;
```

## Etapa 2: Inicializar a apresentação

Inicialize uma apresentação do PowerPoint e especifique o diretório onde o arquivo da apresentação será salvo.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Etapa 3: Crie o gráfico Sunburst

Crie um gráfico Sunburst em um slide. Especificamos a posição (X, Y) e as dimensões (largura, altura) do gráfico.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Etapa 4: preparar dados do gráfico

Limpe quaisquer categorias e dados de séries existentes do gráfico e crie uma pasta de trabalho de dados para o gráfico.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Etapa 5: Definir a hierarquia do gráfico

Defina a estrutura hierárquica do gráfico Sunburst. Você pode adicionar ramos, caules e folhas como categorias.

```java
// Filial 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// Filial 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## Etapa 6: Adicionar dados ao gráfico

Adicione pontos de dados à série do gráfico Sunburst.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## Etapa 7: Salve a apresentação

Por fim, salve a apresentação com o gráfico Sunburst.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Código-fonte completo para o gráfico Sunburst em slides Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//filial 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//ramo 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Neste tutorial, você aprendeu a criar um gráfico Sunburst em uma apresentação do PowerPoint usando a API Aspose.Slides para Java. Você viu como inicializar a apresentação, criar o gráfico, definir a hierarquia do gráfico, adicionar pontos de dados e salvar a apresentação. Agora você pode usar esse conhecimento para criar gráficos Sunburst interativos e informativos em seus aplicativos Java.

## Perguntas frequentes

### Como posso personalizar a aparência do gráfico Sunburst?

Você pode personalizar a aparência do gráfico Sunburst modificando propriedades como cores, rótulos e estilos. Consulte a documentação do Aspose.Slides para obter opções detalhadas de personalização.

### Posso adicionar mais pontos de dados ao gráfico?

Sim, você pode adicionar mais pontos de dados ao gráfico usando o `series.getDataPoints().addDataPointForSunburstSeries()` método para cada ponto de dados que você deseja incluir.

### Como posso adicionar dicas de ferramentas ao gráfico Sunburst?

Para adicionar dicas de ferramentas ao gráfico Sunburst, você pode definir o formato do rótulo de dados para exibir informações adicionais, como valores ou descrições, ao passar o mouse sobre os segmentos do gráfico.

### É possível criar gráficos Sunburst interativos com hiperlinks?

Sim, você pode criar gráficos Sunburst interativos com hiperlinks adicionando-os a elementos ou segmentos específicos do gráfico. Consulte a documentação do Aspose.Slides para obter detalhes sobre como adicionar hiperlinks.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}