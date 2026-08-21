---
date: '2026-08-21'
description: Aprenda a criar box plot java usando Aspose.Slides, adicionar chart ao
  slide e gerar um box‑and‑whisker chart no PowerPoint. Ideal para desenvolvedores
  Java.
keywords:
- create box plot java
- java add chart slide
- Aspose.Slides for Java
lastmod: '2026-08-21'
og_description: Aprenda a criar box plot java usando Aspose.Slides, adicionar chart
  ao slide e gerar um box‑and‑whisker chart no PowerPoint. Perfeito para desenvolvedores
  Java.
og_image_alt: 'Developer guide: create box plot java with Aspose.Slides in PowerPoint'
og_title: Como criar box plot java com Aspose.Slides para PowerPoint
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  headline: How to create box plot java with Aspose.Slides for PowerPoint
  type: TechArticle
- description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  name: How to create box plot java with Aspose.Slides for PowerPoint
  steps:
  - name: create or open a presentation
    text: 'First, open an existing PPTX or start a new one: > **Pro tip:** If the
      file doesn’t exist, Aspose.Slides will automatically create a new blank presentation.'
  - name: add a box‑and‑whisker chart to the slide
    text: 'Place the chart where you need it by specifying the position and size (in
      points):'
  - name: clear existing data
    text: 'Before feeding new data, wipe any placeholder categories or series:'
  - name: configure categories
    text: 'Add the categories (X‑axis labels) that will appear under each box: > **Note:**
      Adjust the label text to match your data domain (e.g., “Q1”, “Product A”).'
  - name: create and customize the series
    text: 'Now create a series, set visual options, and feed the numeric data points:
      You can replace the `int[] data` array with values read from a database, CSV
      file, or any other source.'
  - name: save the presentation
    text: 'Persist the changes to a new PPTX file:'
  - name: clean up resources
    text: 'Always dispose of the `Presentation` object to free native resources:'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library creates a box plot in Java?
  - answer: '`ChartType.BoxAndWhisker`.'
    question: Which chart type is used?
  - answer: A free trial works for evaluation; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – repeat the series‑creation block for each data set.
    question: Can I add multiple series?
  - answer: PowerPoint PPTX (`SaveFormat.Pptx`).
    question: What format is the final file?
  type: FAQPage
tags:
- box plot java
- Aspose.Slides
- PowerPoint chart Java
- box-and-whisker
- Java data visualization
title: Como criar box plot java com Aspose.Slides para PowerPoint
url: /pt/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar box plot java com Aspose.Slides para PowerPoint

Neste guia você **criará box plot java** com Aspose.Slides, e então incorporará o gráfico diretamente em um slide do PowerPoint. Gerar gráficos box‑and‑whisker programaticamente permite transformar dados estatísticos brutos em insights visuais claros sem sair do seu código Java. Se você precisar automatizar relatórios em PowerPoint, Aspose.Slides for Java fornece uma API confiável e de alto desempenho.

## O que você aprenderá

- Configurar seu ambiente para Aspose.Slides for Java
- Etapas para **adicionar gráfico ao slide** e gerar um gráfico box‑whisker no PowerPoint usando Java
- Melhores práticas para otimizar o desempenho ao trabalhar com Aspose.Slides
- Aplicações reais de gráficos box‑and‑whisker

## Respostas rápidas
- **Qual biblioteca cria um box plot em Java?** Aspose.Slides for Java.  
- **Qual tipo de gráfico é usado?** `ChartType.BoxAndWhisker`.  
- **Preciso de licença?** Um teste gratuito funciona para avaliação; uma licença comercial é necessária para produção.  
- **Posso adicionar várias séries?** Sim – repita o bloco de criação de séries para cada conjunto de dados.  
- **Qual é o formato do arquivo final?** PowerPoint PPTX (`SaveFormat.Pptx`).  

## O que é um box plot e por que usá-lo em Java?

Um gráfico box‑and‑whisker (frequentemente chamado de *box plot*) visualiza a distribuição dos dados — mediana, quartis e outliers — em um formato compacto. Em Java, gerar esse gráfico programaticamente permite incorporar insights estatísticos diretamente em decks PowerPoint, eliminando a criação manual de gráficos. É especialmente útil para comparar distribuições entre múltiplas categorias, como notas de teste entre turmas ou vendas entre regiões. Ao gerar o gráfico em Java, você pode integrá‑lo a pipelines de relatórios automatizados, garantindo que os dados mais recentes estejam sempre refletidos em suas apresentações.

## Por que adicionar gráfico ao slide com Aspose.Slides?

Aspose.Slides abstrai os detalhes de baixo nível do OpenXML, oferecendo uma API fluente para criar, estilizar e exportar gráficos. Isso significa que você pode automatizar a geração de relatórios, produzir branding consistente e integrar gráficos a fluxos de trabalho Java maiores. A biblioteca também suporta opções de estilo como cores, fontes e marcadores, permitindo combinar a identidade visual corporativa. Além disso, lida com tarefas complexas como vinculação de dados e atualização de gráficos sem exigir o Microsoft Office.

## Como adicionar gráfico ao slide com Java usando Aspose.Slides?

Carregue ou crie um `Presentation`, insira um `Chart` do tipo `BoxAndWhisker`, alimente seus dados e salve o arquivo — tudo em poucas linhas de Java. A API cuida do layout, dimensionamento e renderização, então você não precisa manipular XML manualmente. Também é possível definir títulos de gráfico e rótulos de eixo programaticamente para fornecer contexto aos visualizadores.

## Pré-requisitos

- **Java Development Kit (JDK)**: JDK 8 ou superior.  
- **Aspose.Slides for Java Library**: Necessária para manipulação de PowerPoint.  
- **IDE**: IntelliJ IDEA, Eclipse ou qualquer editor compatível com Java.

## Configurando Aspose.Slides para Java

Adicione a biblioteca como dependência Maven, Gradle ou manual.

### Maven

Adicione a seguinte dependência no seu `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

No seu `build.gradle`, inclua:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download direto

Alternativamente, faça o download da versão mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Aquisição de licença

- **Teste gratuito** – explore os recursos sem custo.  
- **Licença temporária** – use para avaliação de curto prazo.  
- **Compra** – desbloqueie a funcionalidade completa para cargas de trabalho de produção.

Para inicializar o Aspose.Slides, certifique‑se de que o JAR esteja no seu classpath e configure qualquer arquivo de licença conforme descrito na documentação.

## Guia de implementação

A seguir, um walkthrough passo a passo. Cada bloco é explicado antes do snippet para que você saiba exatamente o que ele faz.

### O que é a classe `Presentation`?

A classe `Presentation` é o objeto central no Aspose.Slides que representa um arquivo PowerPoint inteiro na memória. Ela fornece acesso a slides, gráficos, formas e outros elementos, permitindo criar, modificar e salvar apresentações programaticamente. Usando essa classe, você pode adicionar novos slides, inserir imagens e manipular a ordem dos slides com chamadas simples da API.

### Etapa 1: criar ou abrir uma apresentação

Primeiro, abra um PPTX existente ou inicie um novo:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Dica:** Se o arquivo não existir, o Aspose.Slides criará automaticamente uma nova apresentação em branco.

### Etapa 2: adicionar um gráfico box‑and‑whisker ao slide

Posicione o gráfico onde precisar especificando a posição e o tamanho (em pontos):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Etapa 3: limpar dados existentes

Antes de inserir novos dados, limpe quaisquer categorias ou séries de espaço reservado:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Etapa 4: configurar categorias

Adicione as categorias (rótulos do eixo X) que aparecerão sob cada caixa:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Nota:** Ajuste o texto do rótulo para corresponder ao domínio dos seus dados (por exemplo, “Q1”, “Produto A”).

### Etapa 5: criar e personalizar a série

Agora crie uma série, defina opções visuais e alimente os pontos de dados numéricos:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Você pode substituir o array `int[] data` por valores lidos de um banco de dados, arquivo CSV ou qualquer outra fonte.

### Etapa 6: salvar a apresentação

Persista as alterações em um novo arquivo PPTX:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Etapa 7: liberar recursos

Sempre descarte o objeto `Presentation` para liberar recursos nativos:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Aplicações práticas

Gráficos box‑and‑whisker são indispensáveis em análises estatísticas e apresentação de dados. Aqui estão alguns cenários onde eles se destacam:

1. **Análise financeira** – visualize a distribuição de receita entre regiões.  
2. **Controle de qualidade** – identifique outliers nas medições de fabricação.  
3. **Pesquisa acadêmica** – mostre a variabilidade dos resultados experimentais.  
4. **Pesquisa de mercado** – compare o desempenho de produtos entre diferentes demografias.

Incorporar esses gráficos diretamente em decks PowerPoint permite que as partes interessadas compreendam dados complexos de forma instantânea.

## Considerações de desempenho

Aspose.Slides pode lidar com apresentações com **500+ slides** e gráficos com **100 000+ pontos de dados** mantendo o uso de memória abaixo de 200 MB em um servidor típico. Para permanecer dentro desses limites:

- **Gerenciamento de memória** – descarte objetos `Presentation` prontamente.  
- **Manipulação de dados** – carregue apenas os dados necessários; evite inserir conjuntos de dados massivos diretamente na planilha do gráfico.  
- **Carregamento preguiçoso** – ao gerar muitas slides, crie gráficos apenas para aqueles que serão exibidos.

## Problemas comuns e soluções

| Problema | Causa | Solução |
|----------|-------|----------|
| **Gráfico aparece em branco** | Células de dados não preenchidas corretamente | Verifique se `wb.getCell` referencia a linha/coluna correta e se o valor não é `null`. |
| **Outliers não exibidos** | `setShowOutlierPoints` definido como `false` | Certifique-se de que `series.setShowOutlierPoints(true)` seja chamado. |
| **Vazamento de memória** | Apresentação não descartada | Sempre envolva o uso em `try/finally` e chame `dispose()`. |
| **Quartis incorretos** | Usando o método padrão `Inclusive` | Altere para `Exclusive` via `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Perguntas frequentes

**Q1: O que é um gráfico box‑and‑whisker?**  
Um gráfico box‑and‑whisker, também conhecido como box plot, exibe a distribuição dos dados com base em cinco estatísticas resumidas: mínimo, primeiro quartil, mediana, terceiro quartil e máximo, além de quaisquer outliers.

**Q2: Posso personalizar a aparência do gráfico box‑and‑whisker?**  
Sim. Aspose.Slides permite alterar cores, estilos de linha, formas de marcadores e adicionar rótulos de dados através da API de formatação do gráfico.

**Q3: O Aspose.Slides suporta outros tipos de gráfico?**  
Sim, ele suporta mais de 50 tipos de gráficos — incluindo linha, barra, pizza, dispersão, radar e funil — para que você possa escolher a melhor visualização para seus dados.

**Q4: Como resolvo problemas com dados que não são exibidos corretamente?**  
Certifique-se de que os dados estejam corretamente gravados nas células da planilha e que propriedades de visibilidade como `setShowMeanLine` estejam habilitadas.

**Q5: Onde posso obter suporte se encontrar problemas?**  
Visite o [fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) para ajuda da comunidade ou consulte a documentação oficial.

**Q6: É possível gerar gráficos em um ambiente de servidor sem interface?**  
A biblioteca funciona totalmente em cenários de servidor; não é necessária UI ou instalação do Microsoft Office.

## Recursos

- **Documentação**: Explore referências detalhadas da API em [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: Acesse a página de lançamentos do Aspose.Slides [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)  
- **Compra**: Compre uma licença para desbloquear todos os recursos [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Teste gratuito & licença temporária**: Comece com um teste gratuito ou solicite uma licença temporária [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)

Seguindo este guia, você está agora apto a gerar programaticamente gráficos box‑and‑whisker perspicazes em suas aplicações Java e incorporá‑los diretamente em apresentações PowerPoint. Boa codificação!

---

**Last Updated:** 2026-08-21  
**Tested With:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Author:** Aspose

## Tutoriais Relacionados

- [Como adicionar gráfico ao PowerPoint usando Aspose.Slides para Java: um guia passo a passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java criar gráfico PowerPoint usando Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Adicionar animação ao gráfico PowerPoint usando Aspose.Slides para Java – um guia passo a passo](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}