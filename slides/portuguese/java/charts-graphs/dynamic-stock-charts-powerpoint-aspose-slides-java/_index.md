---
date: '2026-09-12'
description: Aprenda a usar Maven Aspose Slides para adicionar e personalizar dynamic
  stock charts no PowerPoint com Java. Inclui setup, adding data series, formatting
  lines e saving.
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Tutorial Maven Aspose Slides mostra como criar e personalizar dynamic
  stock charts no PowerPoint usando Java, abordando data series, line formatting e
  saving.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Guia Maven Aspose Slides: criar dynamic stock charts no PowerPoint'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides: criar dynamic stock charts no PowerPoint com Java'
url: /pt/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: crie gráficos de ações dinâmicos no PowerPoint com Java

## Introdução

**Maven Aspose Slides** permite que você gere programaticamente apresentações sofisticadas do PowerPoint a partir de Java. Neste tutorial você aprenderá como criar gráficos de ações dinâmicos, adicionar e formatar séries de dados, personalizar linhas do gráfico e, finalmente, salvar o arquivo. Seja você um analista financeiro preparando relatórios trimestrais ou um desenvolvedor construindo decks de slides automatizados, os passos abaixo fornecem uma solução completa e pronta para produção.

**O que você aprenderá**
- Como configurar o Maven com Aspose.Slides para Java  
- Como adicionar um gráfico de ações e limpar os dados padrão  
- Como **adicionar série de dados ao gráfico** e **formatar linhas do gráfico**  
- Como **personalizar elementos visuais específicos do Java** no gráfico  
- Como salvar a apresentação atualizada

Pronto para transformar números brutos em visualizações de ações atraentes? Vamos começar!

## Respostas rápidas
- **Qual artefato Maven eu preciso?** `aspose-slides` version 25.4 (or newer).  
- **Posso executar isso em qualquer SO?** Sim – a biblioteca é puro Java e funciona no Windows, macOS e Linux.  
- **Preciso de licença para desenvolvimento?** Uma licença temporária gratuita funciona para testes; uma licença completa é necessária para produção.  
- **Quais tipos de gráfico são suportados?** Mais de 70 tipos de gráfico incorporados, incluindo Stock, Line e Bar.  
- **Qual o tamanho máximo de uma apresentação que posso processar?** Aspose.Slides pode lidar com arquivos com mais de 500 slides sem carregar todo o arquivo na memória.

## O que é Maven Aspose Slides?

`Aspose.Slides for Java` é uma API Java que permite a criação, manipulação e conversão de arquivos PowerPoint sem o Microsoft Office. A integração com Maven simplifica o gerenciamento de dependências, permitindo que você obtenha a biblioteca diretamente do Maven Central.

## Por que usar Maven Aspose Slides para gráficos de ações?

Aspose.Slides suporta **mais de 70 tipos de gráfico** e pode renderizar apresentações com centenas de páginas em menos de um segundo em hardware de servidor típico. Seus recursos de **linha high‑low** e **barra up/down** dão controle preciso sobre visualizações financeiras, muito além do que a interface do PowerPoint oferece.

## Pré-requisitos

- **Java Development Kit (JDK)** – versão 11 ou superior.  
- **IDE** – IntelliJ IDEA, Eclipse ou qualquer editor de sua preferência.  
- **Aspose.Slides for Java** – versão 25.4 (a mais recente no momento da escrita).  

### Configurando Aspose.Slides para Java

#### Maven
Para integrar Aspose.Slides ao seu projeto usando Maven, adicione a seguinte dependência ao seu `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Para usuários do Gradle, inclua isto no seu `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Download direto
Alternativamente, faça o download do JAR mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Aquisição de licença** – comece com um teste gratuito ou solicite uma licença temporária. Para uso comercial, adquira uma licença completa.

Para referência detalhada da API, veja a [Aspose.Slides documentation](https://docs.aspose.com/slides/java/).

## Como criar um gráfico de ações dinâmico passo a passo

Carregue sua apresentação, adicione um gráfico de ações, limpe os dados padrão e, em seguida, injete suas próprias séries e categorias. A resposta direta à questão central é:

> Carregue um PPTX existente com `new Presentation("template.pptx")`, adicione um `Chart` do tipo `ChartType.Stock`, limpe suas séries e categorias padrão e, então, preencha com seus próprios pontos de dados e opções de formatação. Finalmente, chame `presentation.save("output.pptx", SaveFormat.Pptx)`.

### Inicializar apresentação
#### Visão geral
Comece carregando um arquivo PowerPoint existente para que você possa modificá‑lo in‑place.

#### Passo a passo
1. **Import the library** – the `Presentation` class is the entry point for all slide operations.  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Load the presentation file** – provide the path to your template PPTX.  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Adicionar gráfico de ações ao slide
#### Visão geral
Insira um gráfico Stock no primeiro slide da apresentação.

A classe `Chart` representa uma forma de gráfico que pode ser adicionada a um slide.

#### Resposta direta
You add a stock chart by calling `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)`. This creates a chart object that you can immediately manipulate.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Limpar séries de dados e categorias existentes no gráfico
#### Visão geral
Remova quaisquer séries ou categorias pré‑populadas para que você possa iniciar com um conjunto de dados limpo.

O objeto `ChartData` contém as séries e categorias de um gráfico.

#### Resposta direta
Invoke `chart.getChartData().getSeries().clear()` and `chart.getChartData().getCategories().clear()` to wipe the default content before adding your own.

   ```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Adicionar categorias aos dados do gráfico
#### Visão geral
Defina as categorias do eixo X (por exemplo, datas) que agrupam os valores das ações.

Um `ChartCategory` representa um rótulo do eixo X para um gráfico.

#### Resposta direta
Create a new `ChartCategory` for each label using `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")`, repeating for each month or period.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Adicionar séries de dados ao gráfico
#### Visão geral
Adicione as quatro séries essenciais: Open, High, Low e Close.

Um `ChartSeries` contém uma coleção de pontos de dados para uma série específica no gráfico.

#### Resposta direta
For each series, call `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())`. This registers the series with the chart’s data workbook.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Adicionar pontos de dados à série
#### Visão geral
Preencha cada série com valores numéricos que representam os preços das ações.

Um `DataPoint` representa um único valor em uma série.

#### Resposta direta
Loop through your data collection and use `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (or the appropriate method for the series type) to insert each point.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Formatar linhas high‑low e barras up/down
#### Visão geral
Ajuste o estilo visual dos conectores high‑low e dos preenchimentos das barras up/down.

Um `Marker` define o símbolo visual para um ponto de dados.

#### Resposta direta
Set `chart.getChartData().getSeries().get(0).getMarker().setSize(10)` and configure `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)` to control line thickness and color.

   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### Exibir barras up/down
Use the chart’s `setShowUpDownBars(true)` method to make the up/down bars visible.

   ```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Personalizar rótulos de dados nas linhas high‑low
#### Visão geral
Mostre valores numéricos diretamente nas linhas high‑low para referência rápida.

Um `DataLabel` controla a aparência dos rótulos anexados aos pontos de dados.

#### Resposta direta
Enable data labels with `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` and style them as needed.

   ```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Definir cor de preenchimento das barras up/down
#### Visão geral
Dê às barras de alta um preenchimento verde e às barras de baixa um preenchimento vermelho para transmitir intuitivamente o movimento do mercado.

O objeto `UpDownBars` fornece acesso à formatação das barras up e down.

#### Resposta direta
Apply `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` and set the solid color to `Color.GREEN`; repeat for the down bar with `Color.RED`.

   ```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### Salvar o arquivo PowerPoint
#### Visão geral
Persista suas alterações em um novo arquivo PPTX.

O método `save` grava a apresentação no disco no formato especificado.

#### Resposta direta
Call `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` – this writes the modified presentation to disk in the standard PowerPoint format.

   ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Problemas comuns e solução de problemas

- **Chart not appearing** – ensure the chart’s X/Y coordinates and dimensions are within the slide bounds.  
- **Data points missing** – verify that the data workbook cell indices match the series/row you intend to populate.  
- **License exception** – a temporary trial license expires after 30 days; replace it with a permanent license for production builds.  
- **Performance slowdown on large files** – use `Presentation.setCacheSize(0)` to disable caching if you process thousands of slides in a batch.

## Perguntas frequentes

**Q: Posso usar este código em uma aplicação web?**  
A: Sim. A biblioteca é puro Java, portanto você pode executá‑la em qualquer contêiner servlet ou serviço Spring Boot.

**Q: O Aspose.Slides suporta outros tipos de gráfico além de Stock?**  
A: Absolutamente. Ele suporta mais de 70 tipos de gráfico, incluindo Line, Bar, Pie e Radar.

**Q: Como adiciono um título ao gráfico programaticamente?**  
A: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")` e então formate o título conforme necessário.

**Q: Existe um limite para o número de pontos de dados por série?**  
A: Na prática, você pode adicionar dezenas de milhares de pontos; o uso de memória escala linearmente, e a biblioteca transmite dados para manter a pegada baixa.

**Q: Quais coordenadas Maven devo usar para a versão mais recente?**  
A: A versão mais recente está sempre disponível em `com.aspose:aspose-slides:25.4` (ou mais nova) no Maven Central.

---

**Última atualização:** 2026-09-12  
**Testado com:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

## Tutoriais relacionados

- [dependência maven do aspose slides: Adicionar e Configurar Gráficos em Apresentações Usando Aspose.Slides para Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Criar Gráfico PowerPoint Java – Salvar Apresentações com Gráficos Usando Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Criar e Formatar Gráficos PowerPoint Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}