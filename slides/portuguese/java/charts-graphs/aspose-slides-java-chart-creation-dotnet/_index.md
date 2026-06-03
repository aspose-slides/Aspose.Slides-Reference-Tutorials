---
date: '2026-06-03'
description: Aprenda como criar gráficos em apresentações .NET e adicionar gráfico
  ao slide com Aspose.Slides for Java. Siga este guia passo a passo para visualização
  de dados.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: Criar gráficos em .NET usando Aspose.Slides for Java
url: /pt/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Criar gráficos em .NET usando Aspose.Slides for Java

## Introdução
Criar apresentações impactantes frequentemente envolve a integração de representações visuais de dados, como gráficos, para melhorar a compreensão e o engajamento do público. **Se você deseja criar gráficos em .NET**, Aspose.Slides for Java oferece uma API poderosa e independente de linguagem que funciona perfeitamente dentro de aplicações .NET. Neste tutorial você aprenderá como inicializar uma apresentação, adicionar diversos tipos de gráficos, gerenciar a planilha de dados do gráfico e formatar os dados das séries — incluindo o tratamento de valores negativos. Ao final, você será capaz de gerar gráficos em arquivos de apresentação programaticamente e adicionar um gráfico ao slide com apenas algumas linhas de código.

## Respostas rápidas
- **Qual é o objetivo principal?** Criar gráficos em apresentações .NET usando Aspose.Slides for Java.  
- **Qual versão da biblioteca é necessária?** Aspose.Slides for Java 25.4 ou posterior.  
- **Preciso de uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Posso usar Maven ou Gradle?** Sim — ambos os sistemas de construção são suportados.  
- **Quais tipos de gráficos estão disponíveis?** Coluna agrupada, linha, pizza, barra, área e mais.

## Como criar gráficos em apresentações .NET com Aspose.Slides for Java?
A classe `Presentation` representa um arquivo PowerPoint e fornece métodos para manipular seus slides. Carregue um novo objeto `Presentation`, chame `slides.addEmptySlide()` para obter um slide e, em seguida, use `slide.getShapes().addChart()` para inserir o tipo de gráfico desejado nas coordenadas especificadas. Após o gráfico ser adicionado, preencha sua planilha de dados com séries e categorias, aplique qualquer formatação (como cores para valores negativos) e, finalmente, salve a apresentação em um arquivo .pptx. Esse fluxo permite que você **crie gráficos em .NET** com um conjunto conciso de chamadas de API.

## O que é Aspose.Slides for Java?
Aspose.Slides for Java é uma API multiplataforma que permite aos desenvolvedores criar, modificar e renderizar arquivos PowerPoint sem o Microsoft Office. Ela suporta **mais de 50 formatos de entrada e saída** e pode processar apresentações com milhares de slides mantendo o uso de memória abaixo de 200 MB.

## Por que usar Aspose.Slides for Java em um projeto .NET?
Aspose.Slides for Java roda na Java Virtual Machine e pode ser chamado a partir do .NET através de um wrapper nativo, proporcionando aos desenvolvedores .NET acesso a um motor de gráficos maduro, processamento de alto desempenho de grandes conjuntos de dados e total compatibilidade com código Java existente sem a necessidade de reescrever a lógica.

## Pré-requisitos
Antes de mergulhar na criação de gráficos com Aspose.Slides for Java, vamos delinear o que você precisa:

### Bibliotecas e versões necessárias
- **Aspose.Slides for Java**: Versão 25.4 ou posterior.

### Requisitos de configuração do ambiente
- Um ambiente de desenvolvimento que suporte aplicações .NET.  
- Compreensão básica dos conceitos de programação Java.

### Pré-requisitos de conhecimento
- Familiaridade com a criação de apresentações em um contexto de aplicação .NET.  
- Entendimento das dependências Java e seu gerenciamento (Maven/Gradle).

## Configurando Aspose.Slides for Java
Para começar a usar Aspose.Slides, você precisa incluí-lo como dependência em seu projeto. Veja como fazer isso:

### Maven
O trecho de dependência Maven adiciona Aspose.Slides for Java ao seu projeto.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Inclua esta linha no seu arquivo `build.gradle` para obter a biblioteca do Maven Central.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download direto
Alternativamente, você pode baixar a versão mais recente em [lançamentos do Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

#### Etapas de aquisição de licença
- **Teste gratuito**: Comece com uma licença temporária para explorar os recursos.  
- **Compra**: Adquira uma licença para uso de produção sem restrições.

#### Inicialização e configuração básicas
A inicialização de `Slides` requer a definição da licença e a criação de uma instância `Presentation`.

```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

Esta configuração garante que o gerenciamento de recursos seja tratado de forma eficaz.

## Guia de implementação
Vamos guiá-lo na implementação dos recursos passo a passo.

### Inicializando a apresentação
**Visão geral:**  
Criar uma instância de apresentação define o cenário para todas as operações subsequentes. Este recurso mostra como começar do zero usando Aspose.Slides.

#### Etapa 1: Importar pacotes necessários
`Presentation` e classes relacionadas fazem parte do namespace `com.aspose.slides`.

```java
import com.aspose.slides.Presentation;
```

#### Etapa 2: Criar um novo objeto Presentation
Instancie um objeto `Presentation` e envolva-o em um bloco try‑with‑resources para garantir a liberação.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*Isso garante que o objeto de apresentação seja descartado corretamente após o uso, evitando vazamentos de memória.*

### Adicionando gráfico ao slide
**Visão geral:**  
Adicionar um gráfico ao seu slide pode tornar a visualização de dados mais eficaz e envolvente.

#### Etapa 1: Importar pacotes necessários
A classe `Chart` representa uma forma de gráfico que pode ser colocada em um slide e personalizada.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Etapa 2: Inicializar a apresentação e adicionar o gráfico
Crie um slide e, em seguida, chame `addChart` com `ChartType.ClusteredColumn` e a posição e tamanho desejados.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```

*Aqui, adicionamos um gráfico de coluna agrupada ao primeiro slide nas coordenadas e dimensões especificadas.*

### Gerenciando a planilha de dados do gráfico
**Visão geral:**  
Gerenciar eficientemente a planilha de dados do seu gráfico permite manipular séries e categorias de forma fluida.

#### Etapa 1: Importar pacotes necessários
`IChartDataWorkbook` fornece acesso à planilha subjacente semelhante ao Excel usada pelos gráficos.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Etapa 2: Acessar e limpar a planilha de dados
Recupere a planilha do gráfico e limpe quaisquer dados existentes para começar do zero.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

*Limpar a planilha é crucial para começar com uma base limpa ao adicionar novas séries e categorias.*

### Adicionando séries e categorias ao gráfico
**Visão geral:**  
Este recurso mostra como você pode adicionar pontos de dados significativos gerenciando séries e categorias.

#### Etapa 1: Adicionar séries e categorias
Use `chart.getChartData().getSeries().add()` e `chart.getChartData().getCategories().add()` para definir a estrutura.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```

*Adicionar séries e categorias permite uma apresentação de dados mais organizada.*

### Populando dados da série e formatando
**Visão geral:**  
Preencha seu gráfico com pontos de dados e formate a aparência para melhorar a legibilidade, especialmente ao lidar com valores negativos.

#### Etapa 1: Popular dados da série
Atribua valores numéricos a cada célula na planilha e aplique um preenchimento vermelho para números negativos.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

*Esta seção demonstra como popular dados e aplicar formatação de cor para melhor visualização.*

## Problemas comuns e soluções
- **LicenseNotFoundException** – Certifique-se de que o caminho do arquivo de licença está correto e que o arquivo está acessível em tempo de execução.  
- **NullPointerException on chart data** – Sempre limpe a planilha antes de adicionar novas séries para evitar dados residuais.  
- **Chart not rendering in .NET** – Verifique se você está usando a versão compatível com .NET do JAR Aspose.Slides e se o runtime Java está configurado corretamente em seu projeto .NET.

## Perguntas frequentes

**Q: Posso gerar um gráfico em arquivos de apresentação sem uma interface gráfica?**  
A: Sim, Aspose.Slides for Java é totalmente sem interface gráfica (headless) e funciona em servidores sem componentes gráficos.

**Q: Quais versões do .NET são suportadas?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5 e .NET 6 são todas suportadas.

**Q: Quantos tipos de gráficos posso adicionar?**  
A: Mais de 20 tipos de gráficos estão disponíveis, incluindo coluna, linha, pizza, área e radar.

**Q: É possível estilizar pontos de dados individuais?**  
A: Absolutamente — você pode definir cores de preenchimento, bordas e marcadores para cada ponto de dados via a API `IDataPoint`.

**Q: Preciso converter objetos Java para tipos .NET manualmente?**  
A: Não, o wrapper .NET do Aspose.Slides for Java lida com a conversão de tipos automaticamente.

---

**Última atualização:** 2026-06-03  
**Testado com:** Aspose.Slides for Java 25.4  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais relacionados

- [Como incorporar gráficos em apresentações .NET usando Aspose.Slides para visualização eficaz de dados](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [Como recuperar o tipo de origem de dados do gráfico usando Aspose.Slides para .NET - Gráficos e Diagramas](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [Domine a criação e manipulação de séries de gráficos com Aspose.Slides .NET para visualização eficaz de dados](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}