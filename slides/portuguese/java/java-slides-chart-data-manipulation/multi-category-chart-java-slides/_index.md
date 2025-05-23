---
"description": "Crie gráficos multicategoria em slides Java usando o Aspose.Slides para Java. Guia passo a passo com código-fonte para uma visualização de dados impressionante em apresentações."
"linktitle": "Gráfico de múltiplas categorias em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Gráfico de múltiplas categorias em slides Java"
"url": "/pt/java/chart-data-manipulation/multi-category-chart-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Gráfico de múltiplas categorias em slides Java


## Introdução ao Gráfico Multicategoria em Slides Java com Aspose.Slides

Neste tutorial, aprenderemos a criar um gráfico multicategoria em slides Java usando a API Aspose.Slides para Java. Este guia fornecerá instruções passo a passo, juntamente com o código-fonte, para ajudar você a criar um gráfico de colunas agrupadas com múltiplas categorias e séries.

## Pré-requisitos
Antes de começar, certifique-se de ter a biblioteca Aspose.Slides para Java instalada e configurada em seu ambiente de desenvolvimento Java.

## Etapa 1: Configurando o ambiente
Primeiro, importe as classes necessárias e crie um novo objeto Presentation para trabalhar com slides.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Etapa 2: Adicionar um slide e um gráfico
Em seguida, crie um slide e adicione um gráfico de colunas agrupadas a ele.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Etapa 3: Limpando dados existentes
Limpe todos os dados existentes do gráfico.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Etapa 4: Configurando categorias de dados
Agora, vamos configurar categorias de dados para o gráfico. Criaremos várias categorias e as agruparemos.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Adicione categorias e agrupe-as
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## Etapa 5: Adicionando Séries
Agora, vamos adicionar uma série ao gráfico junto com pontos de dados.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## Etapa 6: Salvando a apresentação
Por fim, salve a apresentação com o gráfico.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Pronto! Você criou com sucesso um gráfico multicategoria em um slide Java usando o Aspose.Slides. Você pode personalizar ainda mais este gráfico para atender às suas necessidades específicas.

## Código-fonte completo para gráfico multicategoria em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
//            Adicionando Séries
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Salvar apresentação com gráfico
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusão

Neste tutorial, aprendemos a criar um gráfico multicategoria em slides Java usando a API Aspose.Slides para Java. Seguimos um guia passo a passo com código-fonte para criar um gráfico de colunas agrupadas com múltiplas categorias e séries.

## Perguntas frequentes

### Como posso personalizar a aparência do gráfico?

Você pode personalizar a aparência do gráfico modificando propriedades como cores, fontes e estilos. Consulte a documentação do Aspose.Slides para obter opções detalhadas de personalização.

### Posso adicionar mais séries ao gráfico?

Sim, você pode adicionar séries adicionais ao gráfico seguindo um processo semelhante ao mostrado na Etapa 5.

### Como altero o tipo de gráfico?

Para alterar o tipo de gráfico, substitua `ChartType.ClusteredColumn` com o tipo de gráfico desejado ao adicionar o gráfico na Etapa 2.

### Como posso adicionar um título ao gráfico?

Você pode adicionar um título ao gráfico usando o `ch.getChartTitle().getTextFrame().setText("Chart Title");` método.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}