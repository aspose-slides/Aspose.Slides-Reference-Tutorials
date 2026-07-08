---
date: '2026-07-08'
description: Aprenda como usar Aspose para criar um Doughnut Chart no PowerPoint com
  Java. Este guia passo a passo mostra como adicionar pontos de dados ao gráfico programaticamente,
  personalizar rótulos e salvar o PPTX com alta fidelidade.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Como usar Aspose permite criar um Doughnut Chart no PowerPoint usando
  Java. Siga este tutorial para adicionar pontos de dados, personalizar rótulos e
  salvar o PPTX com alta fidelidade.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Como usar Aspose: criar Doughnut Chart no PowerPoint (Java)'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Como usar Aspose para criar um Doughnut Chart no PowerPoint (Java)
url: /pt/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como Usar Aspose para Criar Gráfico de Rosquinha no PowerPoint (Java)

## Introdução
Criar apresentações impactantes frequentemente requer mais do que apenas texto e imagens; gráficos podem melhorar significativamente a narrativa ao visualizar dados de forma eficaz. **Como usar Aspose** para geração de gráficos oferece controle programático sem precisar abrir o PowerPoint. Este tutorial orienta você na construção de um gráfico de rosquinha, na configuração de seus pontos de dados e na gravação de um PPTX de alta fidelidade. Você precisará apenas de conhecimentos básicos de Java e alguns minutos para a configuração.

`Aspose.Slides for Java` é uma biblioteca Java que permite a criação, manipulação e conversão de arquivos PowerPoint sem o Microsoft Office.

## Respostas Rápidas
- **Qual biblioteca cria gráfico de rosquinha no PowerPoint?** Aspose.Slides for Java  
- **Posso adicionar pontos de dados ao gráfico programaticamente?** Sim, usando a API de gráficos  
- **Preciso de uma licença para produção?** É necessária uma licença válida do Aspose.Slides  
- **Quais versões do Java são suportadas?** Java 8 e posteriores (classificador JDK 16 mostrado)  
- **Quantas séries posso adicionar?** O exemplo adiciona até 15 séries, mas você pode ajustar conforme necessário  

## O que é um gráfico de rosquinha no PowerPoint?
Um gráfico de rosquinha é um gráfico circular semelhante a um gráfico de pizza, mas com um centro vazio, permitindo que várias séries sejam exibidas simultaneamente. Ele enfatiza as relações parte‑para‑todo enquanto mantém o layout visual compacto e fácil de ler.

## Por que usar Aspose.Slides para Java para criar gráficos de rosquinha?
Aspose.Slides for Java lida com mais de 50 formatos de entrada e saída e pode gerar apresentações de até 500 MB sem carregar o arquivo inteiro na memória. Ele fornece controle programático total sobre a aparência, os dados e o layout dos gráficos em qualquer plataforma Java, elimina a interoperação COM e pode renderizar 100 slides ricos em gráficos em menos de dois segundos em um servidor típico.

## Pré-requisitos
- Conhecimento básico de programação Java.  
- Uma IDE como IntelliJ IDEA ou Eclipse.  
- Maven ou Gradle para gerenciamento de dependências.  
- Uma licença válida do Aspose.Slides para Java (versão de avaliação gratuita disponível).

## Configurando Aspose.Slides para Java
Escolha o gerenciador de dependências que se adequa ao seu projeto.

**Maven**  
Adicione a seguinte dependência ao seu `pom.xml` (substitua a versão pela última release):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Adicione esta linha ao seu `build.gradle`:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Se preferir baixar diretamente, visite a página de [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) .

### Aquisição de Licença
Você pode começar com uma avaliação gratuita para explorar os recursos do Aspose.Slides. Para uso prolongado, adquira uma licença ou solicite uma temporária em [Aspose's website](https://purchase.aspose.com/temporary-license/). Siga as instruções fornecidas para configurar seu ambiente e inicializar o Aspose.Slides em sua aplicação.

## Como criar um gráfico de rosquinha no PowerPoint usando Aspose.Slides para Java
Para criar um gráfico de rosquinha, comece carregando ou criando uma `Presentation`, adicione uma forma de gráfico do tipo `ChartType.Doughnut`, limpe as séries padrão, defina o tamanho do buraco e, em seguida, preencha a planilha do gráfico com nomes de categorias e valores numéricos. Por fim, ajuste a formatação dos rótulos e salve o PPTX.

### Etapa 1: Inicializar a apresentação
Crie uma nova apresentação ou abra um arquivo existente para obter a coleção de slides.

`Presentation` é a classe principal que representa um arquivo PowerPoint.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Etapa 2: Adicionar um gráfico de rosquinha ao slide
Insira uma forma de gráfico, remova as séries/categorias padrão e configure as definições visuais básicas, como o tamanho do buraco da rosquinha.

`Chart` (ou forma de gráfico) representa um objeto de gráfico colocado em um slide.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Etapa 3: Adicionar pontos de dados ao gráfico e personalizar rótulos
Preencha os nomes das categorias, adicione pontos de dados para cada série e ajuste finamente a formatação dos rótulos (fonte, cor, posição). Esta etapa demonstra a capacidade de “adicionar pontos de dados ao gráfico”.

`Workbook` fornece acesso aos dados de planilha subjacentes ao gráfico onde as células são preenchidas.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Etapa 4: Salvar a apresentação atualizada
Grave as alterações em um novo arquivo PPTX no disco.

`save` grava a apresentação em um arquivo no formato escolhido.  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## Aplicações Práticas
- **Relatórios Financeiros:** Visualizar alocações de orçamento ou detalhamentos de despesas.  
- **Análise de Mercado:** Mostrar a distribuição de participação de mercado entre concorrentes.  
- **Resultados de Pesquisa:** Apresentar dados categóricos de pesquisa de forma compacta.  
- **Geração de Painéis:** Combinar com consultas ao banco de dados para produzir slides que se atualizam em tempo real.

## Considerações de Desempenho
- **Liberar recursos:** Chame `pres.dispose()` após salvar para liberar memória nativa.  
- **Limitar a quantidade de gráficos:** Adicionar centenas de gráficos pode aumentar o uso de memória; processe em lotes se necessário.  
- **Usar streaming:** Para conjuntos de dados massivos, preencha a planilha diretamente a partir de streams em vez de arrays na memória.  

## Problemas Comuns e Soluções
| Problema | Causa | Solução |
|----------|-------|---------|
| **Gráfico aparece em branco** | Células de dados não preenchidas corretamente | Verifique se `workBook.getCell(...)` referencia os índices corretos de linha/coluna. |
| **Rótulos sobrepostos** | Muitas categorias em espaço limitado | Aumente `DoughnutHoleSize` ou ajuste `FirstSliceAngle`. |
| **OutOfMemoryError** | Apresentações grandes sem liberar recursos | Chame `pres.dispose()` após salvar e considere aumentar o tamanho do heap da JVM. |

## Perguntas Frequentes

**Q: Posso usar Aspose.Slides para Java em aplicações comerciais?**  
A: Sim, mas você precisa de uma licença comercial válida. Uma avaliação gratuita está disponível para avaliação.

**Q: Como adiciono mais de 15 séries?**  
A: Aumente o limite do loop na etapa “Add Doughnut Chart” e certifique-se de que sua planilha de dados contém linhas suficientes.

**Q: É possível alterar o tamanho do buraco da rosquinha após a criação?**  
A: Sim, chame `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` antes de salvar.

**Q: Posso exportar o gráfico como imagem em vez de PPTX?**  
A: Absolutamente. Use `chart.getImage()` e salve o `java.awt.image.BufferedImage` retornado no formato de sua preferência.

**Q: O Aspose.Slides suporta gráficos animados?**  
A: Animações podem ser adicionadas via a API `ISlide.getTimeline()`, embora isso esteja fora do escopo deste tutorial.

## Conclusão
Agora você tem um método completo e pronto para produção para **criar arquivos PowerPoint com gráfico de rosquinha** usando Aspose.Slides para Java, incluindo como **adicionar pontos de dados ao gráfico**, personalizar rótulos e lidar com considerações de desempenho. Experimente diferentes cores, fontes de dados e tipos de gráficos para fazer suas apresentações realmente se destacarem.

---

**Última Atualização:** 2026-07-08  
**Testado com:** Aspose.Slides for Java 25.4 (classificador JDK 16)  
**Autor:** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Tutoriais Relacionados

- [Como Adicionar Gráficos ao PowerPoint Usando Aspose.Slides para Java: Um Guia Passo a Passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Como Editar Dados de Gráficos do PowerPoint Usando Aspose.Slides para Java: Um Guia Abrangente](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Animar Gráficos no PowerPoint Usando Aspose.Slides para Java – Um Guia Passo a Passo](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}