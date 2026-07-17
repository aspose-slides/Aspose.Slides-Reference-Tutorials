---
date: '2026-07-17'
description: Aprenda como adicionar um gráfico ao PowerPoint criando um gráfico Pie
  of Pie usando Aspose.Slides para Java. Inclui configuração, código, personalização
  e salvamento como PPTX.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Adicione um gráfico ao PowerPoint com Aspose.Slides para Java. Este
  guia mostra como criar, personalizar e salvar um gráfico Pie of Pie como PPTX em
  minutos.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: Adicionar Gráfico ao PowerPoint – Criar um Gráfico Pie of Pie em Java
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: Adicionar Gráfico ao PowerPoint – Criar um Gráfico Pie of Pie em Java com Aspose.Slides
url: /pt/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Adicionar Gráfico ao PowerPoint – Criar um Gráfico Pie of Pie em Java com Aspose.Slides

## Gráficos e Diagramas

### Introdução

Em apresentações modernas orientadas por dados, **adicionar um gráfico ao PowerPoint** costuma ser a maneira mais rápida de transformar números brutos em insights visuais. Um gráfico de pizza tradicional funciona bem para algumas categorias, mas quando algumas fatias são muito pequenas elas se tornam ilegíveis. Um gráfico *Pie of Pie* resolve esse problema extraindo essas pequenas fatias para uma pizza secundária, mantendo o gráfico principal limpo e os detalhes acessíveis.

Neste tutorial você aprenderá a **adicionar gráfico ao PowerPoint** criando um gráfico Pie of Pie com Aspose.Slides para Java. Percorreremos a configuração do ambiente, criação do gráfico, personalização de rótulos, ajuste da posição da divisão e, finalmente, a gravação da apresentação como arquivo PPTX. Ao final, você estará pronto para incorporar gráficos sofisticados em qualquer conjunto de slides.

## Respostas Rápidas
No Aspose.Slides, `Presentation` representa um arquivo PPTX, `ChartType.PieOfPie` seleciona o gráfico Pie of Pie, `setShowValue(true)` exibe valores nos rótulos e `save` grava o arquivo.

- **Qual é a classe principal para manipulação do PowerPoint?** `Presentation` – representa um arquivo PPTX inteiro na memória.  
- **Qual tipo de gráfico cria uma pizza secundária para fatias pequenas?** `ChartType.PieOfPie`.  
- **Como exibir valores em cada fatia?** Defina `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`.  
- **É possível salvar o arquivo diretamente como PPTX?** Sim – chame `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **É necessário uma licença para desenvolvimento?** Um teste gratuito de 30 dias funciona para testes; uma licença permanente remove as marcas d'água de avaliação.

## O que é um Gráfico Pie of Pie?
Um **Pie of Pie chart** é uma visualização de pizza em dois níveis que isola uma ou mais fatias pequenas em uma pizza separada e vinculada, facilitando a leitura. O Aspose.Slides oferece suporte a esse tipo de gráfico nativamente, permitindo controlar o tamanho da divisão, a posição e a formatação dos rótulos.

## Por que adicionar gráfico ao PowerPoint com Aspose.Slides?
Aspose.Slides pode gerar, editar e renderizar arquivos PowerPoint sem a necessidade do Microsoft Office instalado. Ele suporta **mais de 50 formatos de entrada e saída**, processa apresentações com **até 500 slides** em menos de um segundo em hardware de servidor típico e oferece **controle total da API** sobre estilo de gráficos, rótulos de dados e layout — perfeito para pipelines de relatórios automatizados.

## Pré-requisitos

- **Java Development Kit (JDK) 16+** instalado.
- Uma IDE como **IntelliJ IDEA**, **Eclipse** ou **NetBeans**.
- Maven ou Gradle para gerenciamento de dependências (veja as seções abaixo).
- Conhecimento básico de Java e familiaridade com construção de projetos.

## Configurando Aspose.Slides para Java

### Informações de Instalação

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**Download Direto:** Você pode baixar a versão mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Etapas de Aquisição de Licença
- **Teste Gratuito:** Comece com um teste de 30 dias para explorar todos os recursos.  
- **Licença Temporária:** Solicite uma chave temporária para avaliação estendida.  
- **Compra:** Obtenha uma licença permanente para uso em produção e remover as marcas d'água de avaliação.

### Inicialização e Configuração Básicas
`Presentation` é o objeto principal para criar arquivos PowerPoint, e `Chart` representa uma forma de gráfico dentro de um slide.

```java
Presentation presentation = new Presentation();
```  

Isso cria uma apresentação vazia pronta para slides e gráficos.

## Guia de Implementação

### Como adicionar um gráfico ao PowerPoint usando Aspose.Slides para Java?

Carregue uma nova `Presentation`, adicione um slide e insira um `Chart` do tipo `PieOfPie`. A cadeia de chamadas da API é concisa: crie o gráfico, preencha os dados da série, ajuste a visibilidade dos rótulos, configure o tamanho da pizza secundária e, finalmente, salve. Todo o processo normalmente cabe em menos de 20 linhas de código, tornando-o ideal para geração automatizada de relatórios.

### Criando um Gráfico 'Pie of Pie'

#### Visão Geral
Construiremos um gráfico Pie of Pie no primeiro slide, separando as menores fatias e rotulando cada segmento com seu valor.

#### Etapa 1: Criar uma Instância da Classe Presentation
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
Isso inicializa o contêiner para todos os slides e gráficos subsequentes.

#### Etapa 2: Adicionar um Gráfico 'Pie of Pie' no Primeiro Slide
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
Aqui especificamos `ChartType.PieOfPie` e definimos a posição (X, Y) e o tamanho (largura, altura) do gráfico na tela do slide.

#### Etapa 3: Definir Rótulos de Dados para Mostrar Valores da Série
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
Habilitar `showValue` faz com que cada fatia exiba seu valor numérico, essencial para interpretação rápida dos dados.

#### Etapa 4: Configurar o Tamanho do Segundo Gráfico e Dividir por Percentual
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
Essas opções permitem decidir quanto do gráfico será alocado à pizza secundária e quais fatias serão movidas com base em um limite percentual.

#### Etapa 5: Salvar a Apresentação no Disco em Formato PPTX
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Dica Pro:** Use um caminho absoluto ou `Paths.get()` do Java para evitar separadores específicos da plataforma.

## Problemas Comuns e Soluções

A classe `License` carrega um arquivo de licença para remover restrições de avaliação.

- **Aviso de licença ausente:** Se você vir “Evaluation Only” no gráfico, certifique-se de aplicar um arquivo de licença válido via `License license = new License(); license.setLicense("Aspose.Slides.lic");`.
- **Divisão de fatia incorreta:** Verifique se a propriedade `splitBy` está definida como `SplitBy.Percentage` e se `secondPieSize` tem um valor entre 0 e 100.
- **Dados não exibidos:** Confirme que a série do gráfico contém ao menos um ponto de dados; caso contrário, o gráfico será vazio.

## Perguntas Frequentes

`IChart` representa um objeto de gráfico que pode ser adicionado a um slide.

**Q: Posso gerar múltiplos gráficos em uma única apresentação?**  
A: Sim, instancie um novo `IChart` para cada slide ou local; a API permite objetos de gráfico ilimitados por arquivo.

`SaveFormat.Pdf` especifica o formato de saída PDF para gravação.

**Q: O Aspose.Slides suporta salvar como PDF também?**  
A: Absolutamente – chame `presentation.save("output.pdf", SaveFormat.Pdf)` para exportar o mesmo conjunto de slides para PDF.

`IPortion` representa uma fatia individual de um gráfico de pizza.

**Q: Qual é o número máximo de pontos de dados que um gráfico Pie of Pie pode manipular?**  
A: A biblioteca suporta até **10 000** pontos de dados por série, limitado apenas pela memória disponível.

**Q: É possível personalizar as cores de fatias individuais?**  
A: Sim, acesse cada `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()` e defina `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.

**Q: Como incorporar o PPTX gerado em uma aplicação web?**  
A: Após salvar o arquivo, faça o streaming direto ao cliente usando `HttpServletResponse` com `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.

## Conclusão

Agora você tem uma receita completa e pronta para produção para **adicionar gráfico ao PowerPoint** criando um gráfico Pie of Pie com Aspose.Slides para Java. Experimente diferentes limites de divisão, formatos de rótulo e esquemas de cores para adequar às diretrizes da sua marca. Em seguida, explore outros tipos de gráficos — como barras empilhadas ou radar — para enriquecer ainda mais seus decks de slides automatizados.

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## Tutoriais Relacionados

- [Criar Gráfico Dinâmico Java – Tutoriais de Gráficos PowerPoint para Aspose.Slides](/slides/java/charts-graphs/)
- [Como adicionar gráfico de pizza ao PowerPoint com Aspose.Slides para Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Como Adicionar Gráficos ao PowerPoint Usando Aspose.Slides para Java: Um Guia Passo a Passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}