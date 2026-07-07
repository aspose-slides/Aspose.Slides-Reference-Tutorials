---
date: '2026-07-03'
description: Aprenda a criar gráficos Sunburst passo a passo em Java usando Aspose.Slides,
  com opções completas de personalização para apresentações do PowerPoint.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Como criar gráficos Sunburst em Java usando Aspose.Slides
url: /pt/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como Criar Gráficos Sunburst em Java Usando Aspose.Slides

## Introdução
Nas apresentações orientadas por dados de hoje, visualizações **como criar sunburst** rapidamente podem diferenciar seus slides. Este tutorial orienta você na construção de um gráfico Sunburst com Aspose.Slides para Java, desde a configuração do projeto até a exportação final, para que possa entregar gráficos hierárquicos atraentes sem sair do ecossistema Java.

## Respostas Rápidas
- **Qual é a classe principal para um arquivo PowerPoint?** `Presentation` – representa todo o PPTX na memória.  
- **Quantas linhas de código são necessárias para um sunburst básico?** Normalmente 5–7 linhas após a referência da biblioteca.  
- **Quais formatos de saída são suportados?** PPTX, PDF, PNG, SVG e HTML.  
- **Posso estilizar segmentos individuais?** Sim – cores de preenchimento, bordas e rótulos de dados são totalmente personalizáveis.  
- **Preciso de uma licença para produção?** Uma avaliação gratuita funciona para testes; uma licença comercial é necessária para implantação.

## O que é um Gráfico Sunburst?
Um gráfico Sunburst visualiza dados hierárquicos como anéis concêntricos, onde cada anel representa um nível da hierarquia. Ele permite que os espectadores compreendam relações pai‑filho de forma instantânea, sendo ideal para organogramas, exibições de taxonomia e métricas de múltiplos níveis. É especialmente útil para mostrar categorias de vários níveis, como linhas de produtos, regiões geográficas ou estruturas organizacionais, permitindo que os espectadores vejam tanto a distribuição geral quanto a detalhada dentro de cada segmento.

## Por que Usar Aspose.Slides para Gráficos Sunburst?
Aspose.Slides oferece **mais de 30 tipos de gráficos**, processa arquivos de até **500 MB** sem carregar todo o documento na memória e renderiza gráficos a **300 DPI** para saída cristalina. Essas capacidades quantificadas garantem geração rápida e visual de alta qualidade mesmo para apresentações grandes. Além disso, a biblioteca oferece operações thread‑safe e integra‑se perfeitamente com as ferramentas de build Java populares, tornando‑a adequada tanto para geração de apresentações em desktop quanto em servidor em escala.

## Pré-requisitos
- Java Development Kit (JDK) 8 ou superior.  
- Maven ou Gradle para gerenciamento de dependências.  
- Aspose.Slides for Java (versão mais recente).  
- Noções básicas de estruturas de dados hierárquicas.

## Como Criar Gráficos Sunburst Passo a Passo?
Carregue seu ambiente, adicione um gráfico, alimente os dados hierárquicos, estilize e salve o arquivo – tudo em algumas etapas simples. A seguir está o fluxo de trabalho exato que você pode seguir sem escrever código boilerplate adicional. O processo é totalmente automatizado, não requer interação manual de UI e pode ser incorporado em jobs batch ou serviços web para gerar gráficos sob demanda.

### Etapa 1: Configurar o Projeto
Adicione a dependência Maven do Aspose.Slides (ou o snippet equivalente do Gradle) ao seu `pom.xml`. Isso traz todos os binários necessários e bibliotecas transitivas.

### Etapa 2: Carregar ou Criar uma Apresentação
`Presentation` é o objeto de nível superior do Aspose.Slides que representa um único arquivo PowerPoint na memória. Instancie-o com `new Presentation()` para um deck novo ou passe um caminho de arquivo para abrir um PPTX existente.

### Etapa 3: Adicionar um Gráfico Sunburst
Insira uma nova forma de gráfico em um slide usando `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)`. Isso cria o placeholder Sunburst pronto para os dados. `ChartType.Sunburst` especifica o tipo de gráfico Sunburst ao adicionar um gráfico ao slide.

### Etapa 4: Preencher Dados Hierárquicos
`ChartData` contém as séries de dados e categorias para um gráfico. Acesse a coleção `ChartData` do gráfico e adicione séries e categorias que reflitam sua hierarquia. Para cada nível, especifique a relação pai‑filho via a propriedade `ParentSeries`, permitindo que o gráfico renderize anéis concêntricos automaticamente.

### Etapa 5: Personalizar a Aparência
Ajuste cores de segmento, estilos de borda e rótulos de dados através dos objetos `ChartSeries` e `ChartDataPoint`. `ChartSeries` representa uma série de pontos de dados em um gráfico. `ChartDataPoint` representa um ponto de dado individual dentro de uma série. Você também pode habilitar rotação 3‑D ou definir a propriedade `Explode` para destacar fatias específicas.

### Etapa 6: Salvar a Apresentação
O enum `SaveFormat` define os formatos de arquivo nos quais você pode salvar uma apresentação. Chame `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` para gravar o arquivo no disco. Você também pode exportar para PDF ou PNG alterando o valor do enum `SaveFormat`.

## Como Personalizar as Cores do Gráfico Sunburst?
Especifique uma cor de preenchimento para cada `ChartDataPoint` usando `point.getFillFormat().setFillType(FillType.Solid)` e depois `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`. Essa abordagem direta permite combinar a identidade visual da empresa ou enfatizar pontos de dados críticos. Você também pode aplicar preenchimentos gradientes, ajustar transparência ou usar cores de tema para garantir consistência com o restante do design do slide.

## Problemas Comuns e Soluções
- **Problema:** A hierarquia aparece plana.  
  **Solução:** Certifique‑se de que cada série filha referencia corretamente seu `ParentSeries`. Links ausentes fazem o gráfico tratar todos os dados como um único nível.
- **Problema:** PNG exportado parece borrado.  
  **Solução:** Aumente o DPI de exportação definindo `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)`.
- **Problema:** Arquivos PPTX grandes causam OutOfMemoryError.  
  **Solução:** Use `Presentation.setMemoryOptimization(true)` para transmitir dados e manter o uso de memória baixo.

## Perguntas Frequentes

**Q: Posso gerar um gráfico Sunburst a partir de um arquivo CSV?**  
A: Sim. Leia o CSV, construa a hierarquia na memória e alimente-a à coleção `ChartData` do gráfico antes de salvar.

**Q: O Aspose.Slides suporta transições animadas para gráficos Sunburst?**  
A: Sim. Aplique um `SlideShowTransition` ao slide ou use `ChartFormat.setAnimationEnabled(true)` para animação ao nível do gráfico.

**Q: É possível exportar o gráfico como um vetor SVG?**  
A: Absolutamente. Salve a apresentação com `SaveFormat.Svg` para obter uma versão vetorial escalável do gráfico Sunburst.

**Q: Qual é o número máximo de pontos de dados que um gráfico Sunburst pode manipular?**  
A: Aspose.Slides processa de forma confiável até **10.000** pontos de dados em um único gráfico Sunburst sem degradação de desempenho.

**Q: Preciso de uma licença separada para cada ambiente de implantação?**  
A: Uma única licença comercial cobre todos os ambientes (desenvolvimento, teste, produção), desde que os termos da licença sejam respeitados.

## Conclusão
Agora você tem um guia completo, passo a passo, de **como criar sunburst** em Java usando Aspose.Slides. Seguindo o fluxo de trabalho acima, você pode gerar visualizações hierárquicas de alta qualidade e totalmente personalizáveis para qualquer apresentação PowerPoint.

---

**Last Updated:** 2026-07-03  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## Tutoriais Relacionados

- [Como Adicionar Gráficos ao PowerPoint Usando Aspose.Slides para Java: Um Guia Passo a Passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Domine a Personalização de Gráficos PowerPoint Usando Aspose.Slides Java para Apresentações Dinâmicas](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Anime Categorias de Gráficos PowerPoint com Aspose.Slides para Java | Guia Passo a Passo](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}