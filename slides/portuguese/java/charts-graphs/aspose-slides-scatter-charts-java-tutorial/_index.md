---
date: '2026-07-27'
description: Como personalizar gráficos usando Aspose.Slides for Java. Aprenda a criar
  gráficos no PowerPoint, estilizar séries de dispersão e salvar apresentações de
  forma eficiente.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: Como personalizar gráficos com Aspose.Slides for Java. Este guia mostra
  como criar um gráfico no PowerPoint, estilizar pontos de dispersão e exportar apresentações.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'Como Personalizar Gráfico: Gráfico de Dispersão Aspose em Java'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'Como Personalizar Gráfico: Gráfico de Dispersão Aspose em Java'
url: /pt/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Personalizar Gráfico de Dispersão Aspose em Java

Neste tutorial você descobrirá **como personalizar um gráfico** — especificamente um gráfico de dispersão — usando a poderosa biblioteca Aspose.Slides for Java. Vamos percorrer a configuração do projeto, a criação de um gráfico de dispersão, o ajuste dos tipos de séries e marcadores, e, finalmente, a gravação da apresentação. Ao final, você será capaz de gerar gráficos de dispersão com aparência profissional programaticamente e adaptar cada detalhe visual para corresponder à sua marca ou necessidades de relatório.

## Respostas Rápidas
- **Qual biblioteca eu preciso?** Aspose.Slides for Java (v25.4+).  
- **Qual versão do Java é suportada?** JDK 8 ou superior.  
- **Posso mudar as formas dos marcadores?** Sim – use `MarkerStyleType` para escolher estrelas, círculos, etc.  
- **Como salvo o arquivo?** Chame `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **É necessária uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.

## Como Personalizar Gráficos em Java com Aspose.Slides?
`Presentation` é a classe Aspose.Slides que representa um arquivo PowerPoint inteiro na memória. Carregue uma nova `Presentation`, adicione um gráfico de dispersão no primeiro slide, configure séries e estilos de marcadores, então chame `save`. Esse fluxo único cria um gráfico totalmente estilizado em apenas algumas linhas de código Java, pronto para inclusão em qualquer apresentação PowerPoint.

## O que é “personalizar gráfico de dispersão Aspose”?
Personalizar um gráfico de dispersão com Aspose significa definir programaticamente os dados, a aparência e o comportamento do gráfico — tudo, desde as coordenadas dos pontos até os símbolos dos marcadores — sem abrir o PowerPoint manualmente. Essa abordagem é ideal para relatórios automatizados, apresentações orientadas a dados ou qualquer cenário onde você precise de visualizações repetíveis e de alta qualidade.

## Por que personalizar gráficos de dispersão com Aspose.Slides?
Aspose.Slides oferece aos desenvolvedores controle total programático sobre a aparência dos gráficos, permitindo a criação automatizada de visualizações de alta qualidade, integração perfeita em pipelines de relatório e a capacidade de personalizar cada elemento visual sem abrir o PowerPoint manualmente, economizando tempo e garantindo consistência nas apresentações.

- **Controle total** – modifique tipos de séries, estilos de marcadores, cores e mais via código Java.  
- **Automação** – gere dezenas de gráficos instantaneamente para painéis ou relatórios em lote.  
- **Multiplataforma** – funciona em qualquer SO que suporte Java, sem necessidade de instalação do Office.  
- **Desempenho** – API leve que processa **mais de 150 tipos de gráficos** e lida com apresentações de centenas de páginas sem carregar todo o arquivo na memória.

## Pré-requisitos

- **Aspose.Slides for Java** (v25.4 ou posterior).  
- **Java Development Kit (JDK)** 8 + instalado.  
- Maven ou Gradle para gerenciamento de dependências (ou você pode baixar o JAR manualmente).  
- Conhecimento básico de Java e familiaridade com sua ferramenta de construção preferida.

## Configurando Aspose.Slides para Java

Integre a biblioteca ao seu projeto usando um dos métodos abaixo.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Ou obtenha a versão mais recente em [Lançamentos Aspose](https://releases.aspose.com/slides/java/).

#### Aquisição de Licença
- **Teste Gratuito** – avaliação de 30 dias.  
- **Licença Temporária** – período de teste estendido.  
- **Licença Completa** – uso em produção com suporte premium.

## Guia Passo a Passo para Personalizar Gráfico de Dispersão Aspose

### 1️⃣ Prepare uma pasta para seus arquivos de apresentação
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*Por que isso importa:* Garantir que a pasta de saída exista evita `FileNotFoundException` quando você salvar o PPTX posteriormente.

### 2️⃣ Crie uma nova apresentação e obtenha o primeiro slide
`Presentation` representa um documento PowerPoint e fornece acesso a slides e formas. A classe `Presentation` representa um arquivo PowerPoint completo na memória.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ Adicione um gráfico de dispersão com linhas suaves
`ChartType.ScatterWithSmoothLines` cria um gráfico de dispersão onde os pontos são conectados por linhas suaves.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ Limpe quaisquer séries padrão e adicione as suas
`IChartSeries` representa uma série de dados dentro de um gráfico.  
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### 5️⃣ Preencha a primeira série com pontos de dados
`addDataPointForScatterSeries` adiciona um único ponto X‑Y a uma série de dispersão.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ Personalize o tipo de série e a aparência do marcador
`Marker` controla o símbolo visual usado para cada ponto de dados em uma série de gráfico.  
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### 7️⃣ Salve a apresentação
`save` grava a apresentação em um arquivo no formato especificado.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Casos de Uso Comuns para Gráficos de Dispersão Personalizados
- **Painéis financeiros** – plotar preço de ações vs. volume.  
- **Pesquisa científica** – exibir medições experimentais com marcadores de erro.  
- **Gerenciamento de projetos** – comparar esforço planejado vs. real em tarefas.  

## Dicas de Desempenho
- Chame `pres.dispose()` após salvar para liberar memória nativa.  
- Para grandes conjuntos de dados, preencha a planilha primeiro e depois vincule as séries para evitar atualizações repetidas da UI.  
- Reutilize uma única instância de `IChartDataWorkbook` ao adicionar muitas séries para manter o uso de memória baixo.

## Perguntas Frequentes

**Q: Como altero a cor dos marcadores?**  
A: Use `series.getMarker().getFillFormat().setFillColor(Color)` onde `Color` é uma instância de `java.awt.Color` como `Color.RED`.

**Q: Posso adicionar mais de duas séries a um gráfico de dispersão?**  
A: Sim. Chame `chart.getChartData().getSeries().add(...)` para cada série adicional e preencha seus pontos conforme necessário.

**Q: É possível definir uma legenda personalizada para cada série?**  
A: Absolutamente. Após criar uma série, invoque `series.getLegend().setText("Your Legend Text")` para sobrescrever o nome padrão.

**Q: Como posso exportar o gráfico como imagem em vez de PPTX?**  
A: Chame `chart.getImage().save("chart.png", ImageFormat.Png)` após configurar o gráfico. Isso produz um arquivo PNG independente.

**Q: E se eu precisar animar os pontos de dispersão?**  
A: Aspose.Slides suporta efeitos de animação. Use `chart.getTimeline().getMainSequence().addEffect(...)` para adicionar animações de entrada ou ênfase ao gráfico ou às séries individuais.

---

**Última atualização:** 2026-07-27  
**Testado com:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Criar e Personalizar Gráficos PowerPoint em Java Usando Aspose.Slides](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [Como Criar Gráfico de Bolhas no PowerPoint Usando Aspose.Slides para Java (Tutorial)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [Criar e Personalizar Gráficos com Linhas de Tendência no Aspose.Slides para Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}