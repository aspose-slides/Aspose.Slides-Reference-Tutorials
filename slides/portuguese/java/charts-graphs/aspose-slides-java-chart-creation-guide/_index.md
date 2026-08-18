---
date: '2026-06-03'
description: Aprenda como criar um gráfico de colunas agrupadas em Java usando Aspose.Slides.
  Este guia cobre a dependência Maven, as etapas de criação do gráfico e o tratamento
  de dados.
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: Criar Gráfico de Colunas Agrupadas em Java com Aspose.Slides
url: /pt/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Criar Gráfico de Colunas Agrupadas em Java com Aspose.Slides

## Como Criar Gráficos em Java: Introdução
Criar apresentações dinâmicas frequentemente envolve a visualização de dados por meio de gráficos. Com **Aspose.Slides for Java**, você pode criar **gráficos de colunas agrupadas** de forma simples, melhorar a clareza e causar um impacto maior em sua audiência. Este tutorial orienta você na configuração da biblioteca, adição de um gráfico de colunas agrupadas, gerenciamento de séries e inversão condicional de pontos de dados negativos.

**O que você aprenderá**
- Como configurar o Aspose.Slides for Java.
- Passos para **criar um gráfico de colunas agrupadas** em sua apresentação.
- Técnicas para gerenciar séries e pontos de dados do gráfico.
- Métodos para inverter condicionalmente pontos de dados negativos para melhor visualização.
- Como salvar a apresentação de forma segura.

## Respostas Rápidas
- **Qual biblioteca é usada?** Aspose.Slides for Java.  
- **Qual tipo de gráfico é demonstrado?** Gráfico de colunas agrupadas.  
- **Posso inverter valores negativos?** Sim, usando `invertIfNegative`.  
- **Qual versão do Java é necessária?** JDK 16 ou posterior.  
- **É necessária licença para produção?** Sim, uma licença válida da Aspose.

## O que é um Gráfico de Colunas Agrupadas?
Um gráfico de colunas agrupadas é uma representação visual que coloca várias séries de dados lado a lado para cada categoria, permitindo rápida comparação entre grupos. É perfeito para relatórios financeiros, painéis de vendas e qualquer cenário onde você precise contrastar várias métricas simultaneamente.

## Por que usar Aspose.Slides para criação de gráficos?
Aspose.Slides permite gerar e personalizar totalmente gráficos programaticamente, eliminando a necessidade de edição manual no PowerPoint. Ele suporta **mais de 70 formatos de entrada e saída** e pode processar apresentações com **até 10.000 slides** sem carregar o arquivo inteiro na memória, garantindo alto desempenho para relatórios em grande escala.

## Pré-requisitos
1. **Bibliotecas Necessárias**  
   - Aspose.Slides for Java (versão 25.4 ou posterior).  

2. **Ambiente**  
   - JDK 16 ou mais recente.  
   - Maven ou Gradle para gerenciamento de dependências.  

3. **Conhecimento**  
   - Programação básica em Java.  
   - Familiaridade com ferramentas de build (Maven/Gradle).  

## Configurando Aspose.Slides para Java
### Instalação via Maven
Adicione a seguinte dependência ao seu arquivo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalação via Gradle
Adicione a seguinte linha ao seu arquivo `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download Direto
Alternativamente, faça o download da versão mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Aquisição de Licença
- **Teste Gratuito:** Explore os recursos sem licença.  
- **Licença Temporária:** Use durante a avaliação.  
- **Licença Completa:** Adquira para implantações em produção.

### Inicialização Básica
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Como adiciono um gráfico de colunas agrupadas a um slide?
`Presentation` é a classe principal que representa um arquivo PowerPoint. Carregue uma nova `Presentation`, adicione um slide e chame `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)`. Esta única chamada cria um gráfico de colunas agrupadas totalmente funcional posicionado nas coordenadas especificadas. Você pode então acessar o objeto do gráfico para modificar séries, pontos de dados e estilos visuais.

## Guia Passo a Passo

### Etapa 1: Criar uma Apresentação e Adicionar um Gráfico de Colunas Agrupadas
A classe `Presentation` representa um documento PowerPoint e permite criar slides.  
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Etapa 2: Gerenciar Séries do Gráfico
Agora vamos limpar quaisquer séries padrão, adicionar uma nova e preenchê‑la com valores positivos e negativos.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Etapa 3: Inverter Condicionalmente Pontos de Dados Negativos
O método `invertIfNegative` permite a inversão de valores negativos em uma série de gráfico.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

## Erros Comuns e Dicas
- **Esqueceu de liberar o objeto `Presentation`?** Sempre chame `dispose()` em um bloco `finally` para liberar recursos nativos.  
- **Valores negativos não aparecem invertidos?** Certifique‑se de chamar `invertIfNegative(true)` **depois** de adicionar o ponto de dados.  
- **Problemas de tamanho do gráfico:** As coordenadas (X, Y) e dimensões (largura, altura) estão em pontos; ajuste‑as para adequar ao layout do seu slide.  

## Perguntas Frequentes

**P:** Posso criar outros tipos de gráficos com a mesma abordagem?  
**R:** Sim, basta substituir `ChartType.ClusteredColumn` por qualquer outro valor do enum `ChartType` (por exemplo, `Line`, `Pie`).  

**P:** Preciso de licença para builds de desenvolvimento?  
**R:** Uma licença temporária ou de avaliação é necessária para acesso total aos recursos; caso contrário, a biblioteca funciona em modo de teste com limitações de marca d'água.  

**P:** Como exportar a apresentação para PDF após adicionar gráficos?  
**R:** `SaveFormat.Pdf` especifica PDF como formato de saída ao salvar uma apresentação. Use `pres.save("output.pdf", SaveFormat.Pdf);` depois de concluir a manipulação do gráfico.  

**P:** É possível estilizar colunas individuais (cor, borda)?  
**R:** `IChartDataPoint` representa um único ponto de dados em um gráfico e permite formatação. Cada `IChartDataPoint` oferece opções como `getFillFormat().setFillType(FillType.Solid)` e `getLineFormat()`.  

**P:** E se eu precisar atualizar os dados do gráfico após salvar a apresentação?  
**R:** Carregue a apresentação novamente com `new Presentation("file.pptx")`, modifique os dados do gráfico e salve novamente.  

---

**Última atualização:** 2026-06-03  
**Testado com:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose

## Tutoriais Relacionados

- [How to create stacked column chart in Java with Aspose.Slides – A Comprehensive Guide](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [How to Create Chart in Java with Aspose.Slides – Mastering Chart Creation and Validation](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [Create & Format Charts in Java Using Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}