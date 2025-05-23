---
"description": "Otimize seus slides em Java com opções personalizadas de marcadores de gráficos. Aprenda a aprimorar pontos de dados visualmente usando o Aspose.Slides para Java. Explore orientações passo a passo e perguntas frequentes."
"linktitle": "Opções de marcadores de gráfico em pontos de dados em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Opções de marcadores de gráfico em pontos de dados em slides Java"
"url": "/pt/java/data-manipulation/chart-marker-options-data-point-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Opções de marcadores de gráfico em pontos de dados em slides Java


## Introdução às opções de marcadores de gráfico em pontos de dados em slides Java

Quando se trata de criar apresentações impactantes, a capacidade de personalizar e manipular marcadores de gráfico em pontos de dados pode fazer toda a diferença. Com o Aspose.Slides para Java, você tem o poder de transformar seus gráficos em elementos dinâmicos e visualmente envolventes.

## Pré-requisitos

Antes de começarmos a codificação, certifique-se de ter os seguintes pré-requisitos em vigor:

- Ambiente de desenvolvimento Java
- Biblioteca Aspose.Slides para Java
- Um ambiente de desenvolvimento integrado Java (IDE)
- Documento de apresentação de exemplo (por exemplo, "Test.pptx")

## Etapa 1: Configurando o ambiente

Primeiro, certifique-se de ter as ferramentas necessárias instaladas e prontas. Crie um projeto Java no seu IDE e importe a biblioteca Aspose.Slides for Java.

## Etapa 2: Carregando a apresentação

Para começar, carregue seu documento de apresentação de exemplo. No código fornecido, presumimos que o documento se chama "Test.pptx".

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Etapa 3: Criando um gráfico

Agora, vamos criar um gráfico na apresentação. Usaremos um gráfico de linhas com marcadores neste exemplo.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Etapa 4: Trabalhando com dados do gráfico

Para manipular os dados do gráfico, precisamos acessar a pasta de trabalho de dados do gráfico e preparar a série de dados. Limparemos a série padrão e adicionaremos nossos dados personalizados.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Etapa 5: Adicionar marcadores personalizados

Aí vem a parte mais interessante: personalizar os marcadores nos pontos de dados. Usaremos imagens como marcadores neste exemplo.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Adicionar marcadores personalizados aos pontos de dados
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Repita para outros pontos de dados
// ...

// Alterando o tamanho do marcador da série do gráfico
series.getMarker().setSize(15);
```

## Etapa 6: Salvando a apresentação

Depois de personalizar seus marcadores de gráfico, salve a apresentação para ver as alterações em ação.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Código-fonte completo para opções de marcadores de gráfico em pontos de dados em slides Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Criando o gráfico padrão
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Obtendo o índice da planilha de dados do gráfico padrão
int defaultWorksheetIndex = 0;
//Obtendo a planilha de dados do gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Excluir série de demonstração
chart.getChartData().getSeries().clear();
//Adicionar nova série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Defina a imagem
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Defina a imagem
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Pegue a primeira série de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Adicione um novo ponto (1:3) aqui.
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//Alterando o marcador da série do gráfico
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Conclusão

Com o Aspose.Slides para Java, você pode aprimorar suas apresentações personalizando marcadores de gráfico em pontos de dados. Isso permite criar slides visualmente impressionantes e informativos que cativam seu público.

## Perguntas frequentes

### Como posso alterar o tamanho do marcador para pontos de dados?

Para alterar o tamanho do marcador para pontos de dados, use o `series.getMarker().setSize()` método e forneça o tamanho desejado como argumento.

### Posso usar imagens como marcadores personalizados?

Sim, você pode usar imagens como marcadores personalizados para pontos de dados. Defina o tipo de preenchimento como `FillType.Picture` e forneça a imagem que você deseja usar.

### O Aspose.Slides para Java é adequado para criar gráficos dinâmicos?

Com certeza! O Aspose.Slides para Java oferece amplos recursos para criar gráficos dinâmicos e interativos em suas apresentações.

### Posso personalizar outros aspectos do gráfico usando o Aspose.Slides?

Sim, você pode personalizar vários aspectos do gráfico, incluindo títulos, eixos, rótulos de dados e muito mais, usando o Aspose.Slides para Java.

### Onde posso acessar a documentação e os downloads do Aspose.Slides para Java?

Você pode encontrar a documentação em [aqui](https://reference.aspose.com/slides/java/) e baixe a biblioteca em [aqui](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}