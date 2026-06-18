---
date: '2026-06-08'
description: Aprenda como adicionar séries ao gráfico e personalizar gráficos de colunas
  empilhadas em apresentações .NET usando Aspose.Slides for Java.
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: Adicionar Séries ao Gráfico com Aspose.Slides for Java no .NET
url: /pt/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Domínio da Personalização de Gráficos em Apresentações .NET Usando Aspose.Slides para Java

## Introdução
No universo das apresentações orientadas a dados, os gráficos são ferramentas indispensáveis que transformam números brutos em histórias visuais envolventes. Quando você precisa **adicionar séries ao gráfico** programaticamente, especialmente dentro de arquivos de apresentação .NET, a tarefa pode parecer assustadora. Felizmente, **Aspose.Slides para Java** oferece uma API poderosa e independente de linguagem que torna a criação e personalização de gráficos simples — mesmo quando o formato de destino é um PPTX .NET. Este guia orienta você a adicionar séries, construir um gráfico de colunas empilhadas e ajustar aspectos visuais como a largura do intervalo, para que possa gerar slides dinâmicos e ricos em dados, com aparência polida e profissional.

## Respostas Rápidas
A classe `Presentation` representa um arquivo PPTX, e `slide.getShapes().addChart(...)` insere um shape de gráfico. Use `chart.getChartData().getSeries().add(...)` para adicionar uma série, e `setGapWidth()` ajusta o espaçamento.

- **Qual é a classe principal para iniciar uma apresentação?** `Presentation` – representa um arquivo PPTX na memória.  
- **Qual método adiciona um gráfico a um slide?** `slide.getShapes().addChart(...)` cria o objeto de gráfico no slide.  
- **Como adicionar uma nova série?** `chart.getChartData().getSeries().add(...)` insere uma nova série de dados.  
- **É possível alterar a largura do intervalo entre as barras?** Sim—chame `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` (o valor é uma porcentagem).  
- **Preciso de licença para produção?** Absolutamente—uma licença válida do Aspose.Slides para Java desbloqueia todos os recursos e remove as marcas d'água de avaliação.

## O que significa “adicionar séries ao gráfico”?
Adicionar uma série a um gráfico significa inserir uma nova coleção de pontos de dados que o gráfico renderiza como um elemento visual distinto (por exemplo, um grupo de colunas separado). Cada série pode ter seus próprios valores, cores e formatações, permitindo a comparação lado a lado de múltiplos conjuntos de dados.

## Por que usar Aspose.Slides para Java para modificar apresentações .NET?
Aspose.Slides para Java permite gerar ou editar arquivos PPTX totalmente compatíveis com visualizadores PowerPoint .NET, sem necessidade de instalação do Microsoft Office. Use Aspose.Slides para Java quando precisar de uma solução server‑side, multiplataforma, que cria ou atualiza arquivos PPTX .NET, suporta mais de 50 tipos de gráficos e processa arquivos de até 500 MB sem carregar todo o documento na memória. Sua API funciona em Java, Kotlin, Scala ou qualquer linguagem JVM, entregando o mesmo resultado que desenvolvedores .NET esperam.

## Pré‑requisitos
- Biblioteca **Aspose.Slides para Java** (versão 25.4 ou posterior).  
- Maven, Gradle ou download manual do JAR.  
- Conhecimento básico de Java e familiaridade com a estrutura de arquivos PPTX.  

## Configurando Aspose.Slides para Java
### Instalação via Maven
Adicione a dependência a seguir ao seu `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalação via Gradle
Inclua esta linha no seu arquivo `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download Direto
Alternativamente, obtenha o JAR mais recente na página oficial de lançamentos: [Lançamentos do Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

**Aquisição de Licença**  
Comece com um teste gratuito baixando uma licença temporária de [aqui](https://purchase.aspose.com/temporary-license/). Para uso em produção, adquira uma licença completa para desbloquear todos os recursos e remover as marcas d'água de avaliação.

## Guia de Implementação Passo a Passo
Abaixo de cada passo você encontrará um trecho de código conciso (mantido do tutorial original) seguido de uma explicação do que ele faz.

### Passo 1: Criar uma Apresentação Vazia
`Presentation` é a classe de ponto de entrada que representa um arquivo PowerPoint na memória.  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*Iniciamos com um arquivo PPTX limpo, que nos fornece uma tela para adicionar gráficos.*

### Passo 2: Adicionar um Gráfico de Colunas Empilhadas ao Slide
`Chart` representa um shape de gráfico dentro de um slide. `ChartType.StackedColumn` especifica um gráfico de colunas empilhadas.  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*O método `addChart` cria um **gráfico de colunas empilhadas** e o posiciona no canto superior esquerdo do slide.*

### Passo 3: Adicionar Séries ao Gráfico (Objetivo Principal)
`Series` encapsula uma única série de dados em um gráfico.  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*Aqui **adicionamos séries ao gráfico** – cada chamada cria uma nova série de dados que aparecerá como um grupo de colunas separado.*

### Passo 4: Adicionar Categorias ao Gráfico
`Category` define um rótulo do eixo X para os dados do gráfico.  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*As categorias atuam como rótulos do eixo X, dando significado a cada coluna.*

### Passo 5: Preencher Dados da Série
`DataPoint` contém um valor numérico para uma série em uma categoria específica.  
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```  
*Os pontos de dados fornecem a cada série seus valores numéricos, que o gráfico renderiza como alturas de barra.*

### Passo 6: Definir Largura do Intervalo para o Grupo de Séries do Gráfico
`SeriesGroup` controla propriedades de layout para um grupo de séries, como a largura do intervalo.  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*Ajustar a largura do intervalo melhora a legibilidade, especialmente quando há muitas categorias.*

## Casos de Uso Comuns
- **Relatórios financeiros** – comparar a receita trimestral entre unidades de negócio.  
- **Painéis de projetos** – mostrar percentuais de conclusão de tarefas por equipe.  
- **Análises de marketing** – visualizar o desempenho de campanhas lado a lado.  
Esses cenários se beneficiam do **exemplo de gráfico de colunas empilhadas** porque destacam as contribuições de categorias individuais para um total.

## Dicas de Performance
- **Reutilize o objeto `Presentation`** ao criar múltiplos gráficos para reduzir a sobrecarga de memória.  
- **Limite o número de pontos de dados** apenas ao necessário para a história visual; Aspose.Slides pode lidar com 10.000 pontos, mas a velocidade de renderização diminui após ~5.000.  
- **Dispose dos objetos** (`presentation.dispose()`) após salvar para liberar recursos e evitar vazamentos de memória.  

## Perguntas Frequentes
**P: Posso adicionar outros tipos de gráfico além de colunas empilhadas?**  
R: Sim, Aspose.Slides suporta linha, pizza, área, radar, bolha e mais de 50 outros tipos de gráfico, todos acessíveis através do mesmo método `addChart`.

**P: Preciso de licença separada para saída .NET?**  
R: Não, a mesma licença Java funciona para todos os formatos de saída, incluindo arquivos PPTX .NET.

**P: Como altero a paleta de cores do gráfico?**  
R: Use `series.getFormat().getFill().setFillType(FillType.Solid)` e então defina o objeto `Color` desejado para cada série.

**P: É possível adicionar rótulos de dados programaticamente?**  
R: Absolutamente. Chame `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` para exibir o valor numérico em cada coluna.

**P: E se eu precisar atualizar uma apresentação existente?**  
R: Carregue o arquivo com `new Presentation("existing.pptx")`, modifique o gráfico usando as mesmas chamadas de API e salve-o novamente no disco.

## Conclusão
Agora você tem um guia completo, de ponta a ponta, sobre como **adicionar séries ao gráfico**, criar um **gráfico de colunas empilhadas** e ajustar sua aparência em apresentações .NET usando Aspose.Slides para Java. Experimente diferentes tipos de gráfico, cores e fontes de dados para construir relatórios visuais atraentes que impressionam as partes interessadas e impulsionam decisões orientadas a dados.

---

**Última atualização:** 2026-06-08  
**Testado com:** Aspose.Slides para Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Como Criar Gráficos de Colunas Empilhadas Baseados em Percentual em .NET usando Aspose.Slides](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [Domínio da Criação e Manipulação de Séries de Gráficos com Aspose.Slides .NET para Visualização Eficaz de Dados](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Limpar Pontos de Dados Específicos de Séries de Gráfico com Aspose.Slides .NET](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}