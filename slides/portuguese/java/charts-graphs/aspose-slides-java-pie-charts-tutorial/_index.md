---
date: '2026-07-17'
description: Aprenda como rotacionar pie chart, personalizar cores de pie chart e
  exportar slide para PDF usando Aspose.Slides for Java – um guia completo de visualização
  de dados.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Rotacione pie chart e personalize cores de pie chart usando Aspose.Slides
  for Java. Aprenda a exportar slide para PDF e trabalhar com chart data worksheet.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Rotacionar Pie Chart e Personalizar Cores em Java – Guia Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Como Rotacionar Pie Chart e Personalizar Cores em Java com Aspose.Slides
url: /pt/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Criando Gráficos de Pizza com Aspose.Slides para Java: Um Tutorial Completo

## Introdução
Neste guia você aprenderá a **girar elementos de gráfico de pizza**, personalizar a cor de cada fatia e exportar o slide final para PDF — tudo com Aspose.Slides para Java. Seja construindo um painel de vendas, um relatório financeiro ou qualquer apresentação orientada a dados, dominar essas técnicas permite entregar visualizações claras e atraentes sem depender do Microsoft Office. Vamos preparar as ferramentas e mergulhar.

## Respostas Rápidas
- **Qual classe inicia uma nova apresentação?** `Presentation` de `com.aspose.slides`.
- **Qual chamada de API adiciona um gráfico de pizza?** `slide.addChart(ChartType.Pie, …)`.
- **Como você pode dar a cada fatia uma cor única?** Chame `series.setColorVaried(true)` e defina preenchimentos sólidos por ponto de dados.
- **Qual método gira o gráfico?** `chart.setRotationAngle(double)` – use graus de 0 a 360.
- **O slide pode ser exportado para PDF?** Sim, invoque `presentation.save("output.pdf", SaveFormat.Pdf)`.

## O que é “personalizar cores de gráfico de pizza”?
Personalizar cores de gráfico de pizza significa atribuir cores de preenchimento distintas a cada fatia, melhorando a legibilidade e o impacto visual. No Aspose.Slides isso é feito habilitando cores variadas e, em seguida, definindo cores de preenchimento sólido para pontos de dados individuais. Essa abordagem garante que cada segmento de dados se destaque claramente na apresentação.

## Por que usar Aspose.Slides para Java para criar gráficos de pizza?
Aspose.Slides oferece **mais de 150 tipos de gráficos** e pode renderizar uma apresentação de 300 páginas em menos de **5 segundos** em um servidor típico, tudo sem precisar do Microsoft Office instalado. A biblioteca funciona em Windows, Linux e macOS, proporcionando flexibilidade multiplataforma para qualquer projeto de visualização de dados baseado em Java.

## Pré-requisitos
- **Aspose.Slides para Java** ≥ 25.4
- **JDK** 16 ou mais recente
- IDE como IntelliJ IDEA, Eclipse ou NetBeans
- Conhecimento básico de Java e familiaridade com Maven ou Gradle

## Configurando Aspose.Slides para Java
Adicione a biblioteca à sua configuração de build.

**Maven**  
Adicione este trecho ao seu arquivo `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Inclua o seguinte no seu arquivo `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Download Direto**  
Se preferir uma abordagem manual, faça o download do JAR mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Etapas de Aquisição de Licença
- **Teste Gratuito** – explore todos os recursos sem custo.  
- **Licença Temporária** – estenda os limites do teste por um curto período.  
- **Compra** – obtenha uma licença permanente para uso em produção.

**Inicialização e Configuração Básicas**  
A classe `Presentation` representa um arquivo PowerPoint na memória e fornece métodos para manipular slides.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Guia de Implementação
A seguir, um passo‑a‑passo que cobre tudo, desde a criação de um slide até a rotação do gráfico de pizza final.

### Inicializar Apresentação e Slide
Crie uma nova instância `Presentation` e recupere o primeiro slide para servir como tela do gráfico.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Adicionar Gráfico de Pizza ao Slide
`addChart` adiciona uma forma de gráfico do tipo especificado ao slide nas coordenadas fornecidas.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Definir Título do Gráfico
`setTitle` atribui um título de texto ao gráfico e o posiciona centralmente.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Configurar Rótulos de Dados para a Série
`setShowValue(true)` habilita rótulos de valor numérico em cada ponto de dados da série.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Preparar Planilha de Dados do Gráfico
`ChartDataWorkbook` armazena a tabela de dados subjacente que alimenta as séries e categorias do gráfico.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Adicionar Categorias ao Gráfico
`addCategory` cria um novo rótulo de categoria para as séries de dados do gráfico.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Adicionar Série e Preencher Pontos de Dados
`addSeries` cria uma série de dados, e `addDataPointForBarSeries` insere valores numéricos para cada categoria.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Personalizar Cores e Bordas da Série
`setColorVaried(true)` habilita cores por fatia, e `setFillFormat` atribui um preenchimento sólido a cada ponto de dados.  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Configurar Rótulos de Dados Personalizados
`setDataLabelFormat` personaliza a aparência, posição e fonte dos rótulos para anotações de gráfico mais claras.  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Definir Ângulo de Rotação e Salvar Apresentação
`setRotationAngle` gira todo o gráfico de pizza, e `save` grava a apresentação em um arquivo.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Como girar o gráfico de pizza?
Carregue o objeto do gráfico, chame `chart.setRotationAngle(45.0)` (ou qualquer valor em graus) e, em seguida, salve a apresentação. Girar um gráfico de pizza altera o ângulo inicial, permitindo enfatizar um segmento específico sem mudar os dados. Essa única chamada de método funciona para qualquer instância `Chart` no Aspose.Slides. Você também pode combinar rotação com cores variadas nas fatias para chamar atenção ao ponto de dado mais importante.

## Problemas Comuns e Soluções
| Problema | Causa | Solução |
|----------|-------|---------|
| **Todas as fatias aparecem com a mesma cor** | `setColorVaried(true)` não chamado | Certifique‑se de habilitar cores variadas no grupo de séries. |
| **Rótulos de dados não aparecem** | `showValue` desativado | Chame `setShowValue(true)` no formato do rótulo. |
| **Rotação não tem efeito** | Usando uma versão mais antiga do Aspose.Slides | Atualize para a versão 25.4 ou posterior. |
| **Exceção de licença em tempo de execução** | Arquivo de licença ausente ou inválido | Carregue sua licença com `License license = new License(); license.setLicense("Aspose.Slides.lic");` antes de criar a `Presentation`. |

## Perguntas Frequentes

**Q: Como obtenho uma licença Aspose.Slides para Java?**  
A: Solicite um teste gratuito no site da Aspose, depois compre uma licença permanente. Carregue‑a em tempo de execução conforme mostrado na tabela de Problemas Comuns.

**Q: Posso usar este código com versões mais antigas do JDK?**  
A: A API requer JDK 16 ou superior; versões mais antigas não são suportadas.

**Q: É possível exportar o gráfico como imagem em vez de PPTX?**  
A: Sim—após renderizar, chame `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`.

**Q: E se eu precisar de mais de uma série em um gráfico de pizza?**  
A: Gráficos de pizza são projetados para uma única série de dados; para múltiplas séries, considere usar um gráfico de rosca.

**Q: O Aspose.Slides funciona em servidores Linux?**  
A: Absolutamente—Aspose.Slides para Java é independente de plataforma e funciona em qualquer SO com um JDK compatível.

---

**Última atualização:** 2026-07-17  
**Testado com:** Aspose.Slides para Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Como Criar Gráficos de Pizza em Apresentações Java Usando Aspose.Slides: Um Guia Abrangente](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Domine Gráficos de Pizza em Java Usando Aspose.Slides: Um Guia Abrangente](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Girar Textos de Gráficos em Java com Aspose.Slides: Um Guia Abrangente](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}