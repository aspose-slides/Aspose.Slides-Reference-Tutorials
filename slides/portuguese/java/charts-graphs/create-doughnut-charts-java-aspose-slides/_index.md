---
date: '2026-08-16'
description: Aprenda a adicionar gráficos de rosca em Java usando Aspose.Slides. Este
  guia passo a passo cobre a configuração da dependência Maven, configuração do gráfico,
  cores, rótulos e salvamento do PPTX.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Como adicionar gráficos de rosca em Java usando Aspose.Slides. Siga
  este guia para configurar o Maven, personalizar cores, rótulos e gerar arquivos
  PPTX.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Como adicionar gráfico de rosca em Java com Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Como adicionar gráfico de rosca em Java com Aspose.Slides
url: /pt/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como adicionar um gráfico de rosca em Java com Aspose.Slides

## Introdução

Criar um **gráfico de rosca** programaticamente pode transformar números brutos em um visual atraente que conta uma história instantaneamente. Em Java, **Aspose.Slides** torna esse processo simples, permitindo gerar gráficos prontos para apresentação sem nunca abrir o PowerPoint. Neste tutorial você aprenderá **como adicionar gráficos de rosca** a um arquivo PPTX passo a passo — desde a configuração da dependência Maven Aspose Slides até a personalização de séries, categorias, cores e rótulos, e finalmente salvar a apresentação.

Ao final deste guia, você será capaz de incorporar gráficos de rosca dinâmicos em qualquer arquivo PPTX, perfeito para relatórios, painéis ou decks de slides automatizados.

### Respostas rápidas
- **Qual biblioteca é usada?** Aspose.Slides for Java  
- **Tarefa principal?** Adicionar um gráfico de rosca em um arquivo PPTX  
- **Como adicionar a biblioteca?** Use a dependência Maven Aspose Slides (ou Gradle)  
- **Versão mínima do Java?** JDK 16 ou superior  
- **Posso personalizar cores e rótulos?** Sim, a API fornece controle total de formatação  

## O que é um gráfico de rosca e por que usá-lo?

Um gráfico de rosca é uma variação de um gráfico de pizza com um centro vazio, permitindo que várias séries de dados sejam exibidas como anéis concêntricos. **Ele visualiza partes de um todo em várias categorias enquanto preserva espaço para informações adicionais no centro.** Isso o torna ideal para comparar vendas por região ao longo de vários trimestres, alocações de orçamento entre departamentos ou qualquer cenário em que seja necessário mostrar dados de proporção hierárquica.

## Por que usar Aspose.Slides para Java?

Você pode adicionar um gráfico de rosca sem instalar o Microsoft Office, e a biblioteca processa **mais de 50 + formatos de entrada e saída** enquanto manipula apresentações com mais de 500 slides. Aspose.Slides oferece **renderização até 3× mais rápida** comparada à automação nativa do Office no mesmo hardware, e funciona em Windows, Linux e macOS. Esses benefícios quantificados significam que você pode gerar grandes decks de slides em servidores sem interface gráfica com desempenho previsível.

## Pré-requisitos

- **Bibliotecas necessárias**  
  - Aspose.Slides for Java 25.4 ou posterior (a biblioteca que permite adicionar gráficos de rosca).  

- **Ambiente**  
  - JDK 16 ou superior instalado na sua máquina.  
  - Uma IDE como IntelliJ IDEA, Eclipse ou NetBeans.  

- **Conhecimento**  
  - Sintaxe básica de Java e conceitos orientados a objetos.  
  - Familiaridade com Maven ou Gradle para gerenciamento de dependências.  

## Dependência Maven Aspose Slides

Adicione a seguinte dependência Maven ao seu `pom.xml`. Esta é a **dependência maven aspose slides** que você precisa para incluir a biblioteca em seu projeto.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Se preferir Gradle, use o trecho equivalente abaixo.

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Você também pode baixar o JAR diretamente da página oficial de releases:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Obtendo uma licença

Para remover a marca d'água de avaliação e desbloquear o conjunto completo de recursos:

- **Teste gratuito** – comece com uma licença temporária.  
- **Licença temporária** – solicite uma no [site da Aspose](https://purchase.aspose.com/temporary-license/).  
- **Licença comercial** – adquira para uso em produção.  

Aplicar a licença no seu código:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## Guia de implementação

### Inicializando uma apresentação e adicionando um gráfico de rosca

Presentation é a classe Aspose.Slides que representa uma apresentação PowerPoint.  
Carregue um PPTX existente ou crie um novo objeto `Presentation`, então adicione um gráfico de rosca ao primeiro slide.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### Configurando a planilha de dados do gráfico e limpando dados existentes

A planilha é uma planilha interna que armazena os dados do gráfico.  
Obtenha a planilha que suporta o gráfico, então limpe quaisquer séries ou categorias padrão para que você possa começar com uma página limpa.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Adicionando séries ao gráfico

Uma série representa uma coleção de pontos de dados plotados no gráfico.  
Você pode adicionar até 15 séries. Cada série pode ser personalizada — aqui definimos a explosão, o tamanho do buraco da rosca e o ângulo da primeira fatia.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### Adicionando categorias e pontos de dados

Categorias são os rótulos para cada ponto de dado ao longo do eixo do gráfico.  
Crie 15 categorias e preencha cada série com um ponto de dado. A última série recebe formatação especial de rótulo.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### Personalizando cores e rótulos de dados

`FillType.Solid` especifica uma cor de preenchimento sólido para os elementos do gráfico.  
Defina uma cor de preenchimento sólido para cada série e habilite os rótulos de dados. Para a série final, também alteramos a cor da fonte do rótulo.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### Salvando a apresentação

`save` grava a apresentação em um arquivo no formato escolhido.  
Grave a apresentação atualizada no disco em formato PPTX, ou exporte para PDF se necessário.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## Problemas comuns e soluções

- **Licença não encontrada** – Verifique se o caminho para `license.lic` está correto e o arquivo é legível.  
- **Gráfico aparece em branco** – Certifique-se de ter limpado as séries/categorias existentes antes de adicionar novas.  
- **Cores incorretas** – Confirme que `FillType.Solid` está definido tanto para preenchimento quanto para formatos de linha.  
- **Desempenho com muitas séries** – Limite o número de séries/categorias ou reutilize células da planilha para manter o uso de memória sob controle.  

## Perguntas frequentes

**Q: Posso gerar um gráfico de rosca sem um arquivo PPTX pré‑existente?**  
A: Sim, instancie `new Presentation()` para começar a partir de um deck de slides em branco, então adicione um gráfico como mostrado acima.

**Q: O Aspose.Slides suporta exportação para PDF?**  
A: Absolutamente. Após criar o gráfico, chame `pres.save("output.pdf", SaveFormat.Pdf);` para obter uma versão PDF do slide.

**Q: Como altero o tamanho do buraco da rosca?**  
A: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` onde `value` varia de 0 a 100.

**Q: É possível adicionar rótulos de dados a todas as séries, não apenas à última?**  
A: Sim, mova o bloco de formatação de rótulo para fora da condição `if (i == ...)` e aplique-o a cada `dataPoint`.

**Q: Quais versões do Java são suportadas?**  
A: Aspose.Slides 25.4 suporta JDK 16 e mais recentes. JDKs anteriores requerem o classificador apropriado na dependência Maven.

---

**Última atualização:** 2026-08-16  
**Testado com:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Tutoriais relacionados

- [Como adicionar gráfico ao PowerPoint usando Aspose.Slides para Java: Um guia passo a passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Como personalizar cores de gráfico de pizza em Java com Aspose.Slides – Um guia completo](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Animar categorias de gráfico PowerPoint com Aspose.Slides para Java | Guia passo a passo](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}