---
title: Gráfico de pizza em slides Java
linktitle: Gráfico de pizza em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como criar gráficos de pizza impressionantes em apresentações do PowerPoint usando Aspose.Slides para Java. Guia passo a passo com código-fonte para desenvolvedores Java.
weight: 23
url: /pt/java/chart-data-manipulation/pie-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introdução à criação de um gráfico de pizza em slides Java usando Aspose.Slides

Neste tutorial, demonstraremos como criar um gráfico de pizza em uma apresentação do PowerPoint usando Aspose.Slides para Java. Forneceremos instruções passo a passo e código-fonte Java para ajudá-lo a começar. Este guia pressupõe que você já configurou seu ambiente de desenvolvimento com Aspose.Slides for Java.

## Pré-requisitos

 Antes de começar, certifique-se de ter a biblioteca Aspose.Slides for Java instalada e configurada em seu projeto. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/java/).

## Etapa 1: importar bibliotecas necessárias

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Certifique-se de importar as classes necessárias da biblioteca Aspose.Slides.

## Etapa 2: inicializar a apresentação

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";

// Instancie a classe Presentation que representa o arquivo PPTX
Presentation presentation = new Presentation();
```

 Crie um novo objeto Presentation para representar seu arquivo PowerPoint. Substituir`"Your Document Directory"` com o caminho real onde você deseja salvar a apresentação.

## Etapa 3: adicionar um slide

```java
// Acesse o primeiro slide
ISlide slide = presentation.getSlides().get_Item(0);
```

Obtenha o primeiro slide da apresentação onde deseja adicionar o gráfico de pizza.

## Etapa 4: adicionar um gráfico de pizza

```java
// Adicione um gráfico de pizza com dados padrão
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Adicione um gráfico de pizza ao slide na posição e tamanho especificados.

## Etapa 5: definir o título do gráfico

```java
// Definir título do gráfico
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Defina um título para o gráfico de pizza. Você pode personalizar o título conforme necessário.

## Etapa 6: personalizar os dados do gráfico

```java
//Defina a primeira série para mostrar valores
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Configurando o índice da planilha de dados do gráfico
int defaultWorksheetIndex = 0;

// Obtendo a planilha de dados do gráfico
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Excluir séries e categorias geradas padrão
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Adicionando novas categorias
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Adicionando nova série
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Preenchendo dados de série
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Personalize os dados do gráfico adicionando categorias e séries e definindo seus valores. Neste exemplo, temos três categorias e uma série com pontos de dados correspondentes.

## Etapa 7: personalizar setores do gráfico de pizza

```java
// Definir cores do setor
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Personalize a aparência de cada setor
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Personalize a borda do setor
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Personalize outros setores de maneira semelhante
```

Personalize a aparência de cada setor no gráfico de pizza. Você pode alterar as cores, estilos de borda e outras propriedades visuais.

## Etapa 8: personalizar rótulos de dados

```java
// Personalize rótulos de dados
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Personalize rótulos de dados para outros pontos de dados de maneira semelhante
```

Personalize rótulos de dados para cada ponto de dados no gráfico de pizza. Você pode controlar quais valores são exibidos no gráfico.

## Etapa 9: mostrar linhas líderes

```java
// Mostrar linhas líderes do gráfico
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Habilite linhas líderes para conectar rótulos de dados aos seus setores correspondentes.

## Etapa 10: definir o ângulo de rotação do gráfico de pizza

```java
// Defina o ângulo de rotação para setores do gráfico de pizza
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Defina o ângulo de rotação para os setores do gráfico de pizza. Neste exemplo, definimos para 180 graus.

## Etapa 11: salve a apresentação

```java
// Salve a apresentação com o gráfico de pizza
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Salve a apresentação com o gráfico de pizza no diretório especificado.

## Código-fonte completo para gráfico de pizza em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Instancie a classe Presentation que representa o arquivo PPTX
Presentation presentation = new Presentation();
// Acesse o primeiro slide
ISlide slides = presentation.getSlides().get_Item(0);
// Adicionar gráfico com dados padrão
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Configurando o título do gráfico
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Defina a primeira série para Mostrar Valores
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Configurando o índice da planilha de dados do gráfico
int defaultWorksheetIndex = 0;
// Obtendo a planilha de dados do gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Excluir séries e categorias geradas padrão
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Adicionando novas categorias
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Adicionando nova série
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Agora preenchendo dados de série
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Não funciona na nova versão
// Adicionando novos pontos e definindo a cor do setor
// série.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Configurando a fronteira do setor
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Configurando a fronteira do setor
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Configurando a fronteira do setor
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Crie rótulos personalizados para cada uma das categorias de novas séries
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Mostrando linhas líderes para gráfico
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Configurando o ângulo de rotação para setores do gráfico de pizza
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Salvar apresentação com gráfico
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Conclusão

Você criou com sucesso um gráfico de pizza em uma apresentação do PowerPoint usando Aspose.Slides para Java. Você pode personalizar a aparência e os rótulos de dados do gráfico de acordo com seus requisitos específicos. Este tutorial fornece um exemplo básico e você pode aprimorar e personalizar ainda mais seus gráficos conforme necessário.

## Perguntas frequentes

### Como posso alterar as cores de setores individuais no gráfico circular?

 Para alterar as cores de setores individuais no gráfico de pizza, você pode personalizar a cor de preenchimento de cada ponto de dados. No exemplo de código fornecido, demonstramos como definir a cor de preenchimento para cada setor usando o`getSolidFillColor().setColor()` método. Você pode modificar os valores das cores para obter a aparência desejada.

### Posso adicionar mais categorias e séries de dados ao gráfico de pizza?

 Sim, você pode adicionar categorias e séries de dados adicionais ao gráfico de pizza. Para fazer isso, você pode usar o`getChartData().getCategories().add()` e`getChartData().getSeries().add()` métodos, como mostrado no exemplo. Basta fornecer os dados e rótulos apropriados para as novas categorias e séries para expandir seu gráfico.

### Como posso personalizar a aparência dos rótulos de dados?

 Você pode personalizar a aparência dos rótulos de dados usando o`getDataLabelFormat()` método no rótulo de cada ponto de dados. No exemplo, demonstramos como mostrar o valor nos rótulos de dados usando`getDataLabelFormat().setShowValue(true)`. Você pode personalizar ainda mais os rótulos de dados controlando quais valores são exibidos, mostrando chaves de legenda e ajustando outras opções de formatação.

### Posso alterar o título do gráfico de pizza?

 Sim, você pode alterar o título do gráfico de pizza. No código fornecido, definimos o título do gráfico usando`chart.getChartTitle().addTextFrameForOverriding("Sample Title")` . Você pode substituir`"Sample Title"` com o texto do título desejado.

### Como faço para salvar a apresentação gerada com o Gráfico de Pizza?

 Para salvar a apresentação com o gráfico de pizza, use o`presentation.save()` método. Forneça o caminho e o nome do arquivo desejado junto com o formato no qual deseja salvar a apresentação. Por exemplo:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Certifique-se de especificar o caminho e o formato corretos do arquivo.

### Posso criar outros tipos de gráficos usando Aspose.Slides for Java?

Sim, Aspose.Slides for Java oferece suporte a vários tipos de gráficos, incluindo gráficos de barras, gráficos de linhas e muito mais. Você pode criar diferentes tipos de gráficos alterando o`ChartType` ao adicionar um gráfico. Consulte a documentação do Aspose.Slides para obter mais detalhes sobre a criação de diferentes tipos de gráficos.

### Como posso encontrar mais informações e exemplos para trabalhar com Aspose.Slides for Java?

 Para obter mais informações, documentação detalhada e exemplos adicionais, você pode visitar o[Documentação Aspose.Slides para Java](https://reference.aspose.com/slides/java/). Ele fornece recursos abrangentes para ajudá-lo a usar a biblioteca de maneira eficaz.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
