---
date: '2026-09-12'
description: Aprenda como criar um clustered column chart no PowerPoint usando Aspose.Slides
  for Java, recuperar seu data range e exportar chart images de forma eficiente.
keywords:
- create clustered column chart
- update powerpoint chart data
- export powerpoint chart image
- create pie chart java
- create powerpoint presentation java
- author: Aspose
  dateModified: '2026-09-12'
  description: Master creating and retrieving PowerPoint charts using Aspose.Slides
    for Java. Learn to generate professional visuals efficiently.
  headline: Creating PowerPoint Charts Using Aspose.Slides for Java — A Comprehensive
    Guide
  type: TechArticle
- description: Master creating and retrieving PowerPoint charts using Aspose.Slides
    for Java. Learn to generate professional visuals efficiently.
  name: Creating PowerPoint Charts Using Aspose.Slides for Java — A Comprehensive
    Guide
  steps:
  - name: Create the Presentation
    text: The `Presentation` class is Aspose.Slides' top‑level object that represents
      a PowerPoint file in memory.
  - name: Add a Clustered Column Chart
    text: 'Use the `addChart` method to insert a chart into your presentation. Specify
      its type, position (x and y coordinates), and size. - **Parameters Explained**:
      - `ChartType.ClusteredColumn`: Defines the type of chart. - `(10, 10)`: X and
      Y coordinates for positioning the chart on the slide. - `(400, 300)`: Width
      and height of the chart.'
  - name: Retrieve the Data Range
    text: 'Use `getChartData().getRange()` to get a string representation of the data
      range. - **Retrieving Data**: This method gives you a snapshot of your chart''s
      data, useful for debugging or display purposes.'
  type: HowTo
- questions:
  - answer: Use Maven, Gradle, or download the JAR from the [Aspose.Slides for Java
      releases](https://releases.aspose.com/slides/java/).
    question: How do I install Aspose.Slides for Java?
  - answer: Yes, Aspose.Slides supports over 50 chart types, including bar, line,
      pie, and radar charts.
    question: Can I create other types of charts?
  - answer: Ensure you dispose of resources properly and wrap your code in try‑catch
      blocks to handle `IOException` and `Exception`.
    question: What if my presentation crashes during processing?
  - answer: There is a free trial available. For continued use, consider purchasing
      a license or requesting a temporary one.
    question: Are there licensing costs for using Aspose.Slides?
  - answer: Visit [Aspose's support forum](https://forum.aspose.com/c/slides/11) for
      assistance from the community and Aspose experts.
    question: How do I get support if I encounter issues?
  type: FAQPage
lastmod: '2026-09-12'
og_description: Aprenda como criar um clustered column chart no PowerPoint usando
  Aspose.Slides for Java, recuperar seu data range e exportar chart images de forma
  eficiente. Suporta update PowerPoint chart data e export chart image.
og_image_alt: 'Developer guide: create clustered column chart in PowerPoint using
  Aspose.Slides for Java'
og_title: Como criar clustered column chart com Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to create a clustered column chart in PowerPoint using Aspose.Slides
    for Java, retrieve its data range, and export chart images efficiently.
  headline: How to create clustered column chart with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create a clustered column chart in PowerPoint using Aspose.Slides
    for Java, retrieve its data range, and export chart images efficiently.
  name: How to create clustered column chart with Aspose.Slides for Java
  steps:
  - name: create the presentation
    text: The `Presentation` class is Aspose.Slides' top‑level object that represents
      a PowerPoint file in memory.
  - name: add a clustered column chart
    text: Use the `addChart` method to insert a chart into your presentation. Specify
      its type, position (x and y coordinates), and size. - **Parameters explained**
      - `ChartType.ClusteredColumn` – selects the clustered column visual. - `(10,
      10)` – X and Y coordinates (points) for the chart’s top‑left corner.
  - name: add a clustered column chart
    text: Firstly, add a clustered column chart as described previously.
  - name: retrieve the data range
    text: Use `getChartData().getRange()` to get a string representation of the data
      range. - **Retrieving data** – this method gives you a snapshot of your chart's
      data, useful for debugging or display purposes.
  type: HowTo
- questions:
  - answer: Use Maven, Gradle, or download the JAR from the [Aspose.Slides for Java
      releases](https://releases.aspose.com/slides/java/).
    question: How do I install Aspose.Slides for Java?
  - answer: Yes, Aspose.Slides supports over 50 chart types, including bar, line,
      pie, and radar charts.
    question: Can I create other types of charts?
  - answer: Ensure you dispose of resources properly and wrap your code in try‑catch
      blocks to handle `IOException` and `Exception`.
    question: What if my presentation crashes during processing?
  - answer: There is a free trial available. For continued use, consider purchasing
      a license or requesting a temporary one.
    question: Are there licensing costs for using Aspose.Slides?
  - answer: Visit [Aspose's support forum](https://forum.aspose.com/c/slides/11) for
      assistance from the community and Aspose experts.
    question: How do I get support if I encounter issues?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides Java
- PowerPoint chart generation
- Java presentation automation
- chart data retrieval
title: Como criar clustered column chart com Aspose.Slides for Java
url: /pt/java/charts-graphs/create-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar um gráfico de colunas agrupadas no PowerPoint com Aspose.Slides para Java

Criar um gráfico de colunas agrupadas em um arquivo PowerPoint costumava exigir manipulação tediosa de XML ou uma instalação completa do Office. Com **Aspose.Slides for Java** você pode gerar o gráfico programaticamente, ajustar seus dados e exportar a visualização em segundos. Este tutorial orienta você na criação de uma apresentação, inserção de um gráfico de colunas agrupadas e leitura da faixa de dados subjacente para que possa validar ou registrá‑la posteriormente. Para mais informações, visite o [Aspose website](https://releases.aspose.com/slides/java/).

## Respostas rápidas
- **Qual biblioteca cria gráficos PowerPoint em Java?** Aspose.Slides for Java.  
- **Qual tipo de gráfico o exemplo usa?** Um gráfico de colunas agrupadas.  
- **Preciso de uma licença para executar o exemplo?** Um teste gratuito funciona para avaliação; uma licença comercial é necessária para produção.  
- **Posso recuperar os dados do gráfico após a criação?** Sim – chame `getChartData().getRange()` no objeto do gráfico.  
- **Qual versão do Java é suportada?** JDK 16 e posteriores.

## O que é Aspose.Slides para Java?

`Aspose.Slides for Java` é uma **API independente** que permite criar, editar e renderizar arquivos PowerPoint sem o Microsoft Office. Suporta **mais de 50 formatos de entrada e saída** e pode lidar com apresentações com **centenas de slides usando menos de 200 MB de RAM**.

## Por que usar Aspose.Slides para Java para gerar gráficos?

Aspose.Slides processa **mais de 50 tipos de gráficos**, renderiza‑os a **até 30 fps** em hardware de servidor típico e manipula apresentações **sem carregar o arquivo inteiro na memória**. Isso o torna ideal para pipelines de relatórios automatizados que precisam gerar milhares de gráficos diariamente, mantendo baixa utilização de CPU e memória.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- **Java Development Kit (JDK)** 16 ou posterior instalado.  
- Uma IDE como **IntelliJ IDEA** ou **Eclipse**.  
- **Maven** ou **Gradle** para gerenciamento de dependências.  

### Bibliotecas e dependências necessárias

Adicione Aspose.Slides ao seu projeto com um dos trechos a seguir.

**Maven**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativamente, faça o download do JAR mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Aquisição de licença

Comece com um teste gratuito ou solicite uma licença temporária para desbloquear todos os recursos. Para uso em produção, compre uma licença na [página de compras da Aspose](https://purchase.aspose.com/buy).

## Configurando Aspose.Slides para Java

A classe `Presentation` é o ponto de entrada principal para criar e manipular arquivos PowerPoint. Após adicionar a dependência, inicialize a API no seu código.

1. **Adicione a dependência** usando Maven ou Gradle conforme mostrado acima.  
2. **Crie uma instância `Presentation`** – este objeto conterá seus slides e gráficos.  

```java
Presentation pres = new Presentation();
```  

3. **Libere a apresentação** quando terminar para liberar recursos nativos.  

```java
if (pres != null) pres.dispose();
```  

## Como criar uma apresentação PowerPoint com um gráfico de colunas agrupadas em Java?

Carregue uma nova `Presentation`, adicione um slide e insira um gráfico de colunas agrupadas em uma única chamada fluente. O objeto `Presentation` representa todo o arquivo PowerPoint na memória, enquanto o método `addChart` cria uma forma de gráfico no slide especificado. Abaixo estão as etapas principais, que podem ser realizadas em menos de dez linhas de código.

### Etapa 1: criar a apresentação  

A classe `Presentation` é o objeto de nível superior do Aspose.Slides que representa um arquivo PowerPoint na memória.  

```java
Presentation pres = new Presentation();
```  

### Etapa 2: adicionar um gráfico de colunas agrupadas  

Use o método `addChart` para inserir um gráfico na sua apresentação. Especifique seu tipo, posição (coordenadas x e y) e tamanho.  

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 10, 10, 400, 300);
```  

- **Parâmetros explicados**  
  - `ChartType.ClusteredColumn` – seleciona o visual de coluna agrupada.  
  - `(10, 10)` – coordenadas X e Y (pontos) para o canto superior esquerdo do gráfico.  
  - `(400, 300)` – largura e altura do gráfico em pontos.

## Como recuperar a faixa de dados de um gráfico em uma apresentação PowerPoint usando Aspose.Slides para Java?

Chame `getChartData().getRange()` no objeto do gráfico; ele retorna instantaneamente uma string como `"Sheet1!A1:B5"` que espelha a faixa no estilo Excel que sustenta o gráfico. Este método fornece uma representação textual concisa da fonte de dados sem carregar a planilha completa, tornando‑o ideal para registro, depuração ou validação rápida em pipelines automatizados.

### Etapa 1: adicionar um gráfico de colunas agrupadas  

Primeiro, adicione um gráfico de colunas agrupadas conforme descrito anteriormente.  

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 10, 10, 400, 300);
```  

### Etapa 2: recuperar a faixa de dados  

Use `getChartData().getRange()` para obter uma representação em string da faixa de dados.  

```java
String result = chart.getChartData().getRange();
// Output omitted for clarity
```  

- **Recuperação de dados** – este método fornece uma captura instantânea dos dados do seu gráfico, útil para depuração ou exibição.

## Aplicações práticas

1. **Relatórios empresariais** – gerar painéis de KPI que são atualizados automaticamente quando os dados de origem mudam.  
2. **Apresentações orientadas a dados** – criar decks de slides que refletem os números mais recentes de vendas ou inventário sem edição manual.  
3. **Ferramentas educacionais** – criar gráficos dinâmicos para tutoriais, questionários ou livros didáticos interativos.

## Considerações de desempenho

- **Liberar objetos prontamente** – chame `presentation.dispose()` em um bloco `finally` para liberar a memória nativa.  
- **Evitar carregamento de documento completo** – use APIs de streaming ao trabalhar com apresentações maiores que 200 MB.  
- **Recuperar apenas as faixas necessárias** – `getChartData().getRange()` evita carregar todo o conjunto de dados do gráfico, mantendo baixo o uso de CPU.

## Problemas comuns e soluções

- **Falhas na apresentação** – sempre envolva I/O de arquivos em blocos `try‑catch` e garanta que `dispose()` seja executado em uma cláusula `finally`.  
- **Dimensões incorretas do gráfico** – verifique se os valores de X, Y, largura e altura permanecem dentro da tela de 960 × 720 pontos do slide.  
- **Erros de licença** – carregue o arquivo de licença antes de criar quaisquer objetos `Presentation`: `License license = new License(); license.setLicense("Aspose.Slides.lic");`.

## Perguntas frequentes

**Q: Como instalo o Aspose.Slides para Java?**  
A: Use Maven, Gradle ou faça o download do JAR em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Q: Posso criar outros tipos de gráficos?**  
A: Sim, Aspose.Slides suporta mais de 50 tipos de gráficos, incluindo barras, linhas, pizza e radar.

**Q: E se minha apresentação travar durante o processamento?**  
A: Certifique‑se de liberar os recursos adequadamente e envolva seu código em blocos try‑catch para tratar `IOException` e `Exception`.

**Q: Existem custos de licenciamento para usar o Aspose.Slides?**  
A: Há um teste gratuito disponível. Para uso contínuo, considere comprar uma licença ou solicitar uma temporária.

**Q: Como obtenho suporte se encontrar problemas?**  
A: Visite o [fórum de suporte da Aspose](https://forum.aspose.com/c/slides/11) para assistência da comunidade e dos especialistas da Aspose.

## Recursos
- **Documentação**: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **Compra**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Teste gratuito**: [Get a Free Trial](https://releases.aspose.com/slides/java/)  
- **Licença temporária**: [Request Temporary License](https://purchase.aspose.com/temporary-license/)

Boa criação de gráficos com Aspose.Slides para Java!

---

**Última atualização:** 2026-09-12  
**Testado com:** Aspose.Slides for Java 24.12 (mais recente no momento da escrita)  
**Autor:** Aspose  

## Tutoriais relacionados

- [Domine a Manipulação de PowerPoint com Aspose.Slides Java: Guia Abrangente para Operações de Apresentação](/slides/java/presentation-operations/aspose-slides-java-manipulate-pptx-presentations/)
- [Domine a Automação de Slides PowerPoint com Aspose.Slides Java: Guia Abrangente para Processamento em Lote](/slides/java/batch-processing/automate-powerpoint-slides-aspose-slides-java/)
- [Crie Gráficos Sunburst em Java Usando Aspose.Slides: Guia Abrangente](/slides/java/charts-graphs/create-sunburst-charts-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}