---
date: '2026-09-17'
description: Aprenda como adicionar clustered column chart a uma apresentação PowerPoint,
  personalizar o gráfico PowerPoint e inserir gráfico de data series usando Aspose.Slides
  para Java.
keywords:
- add clustered column chart
- add chart to powerpoint
- save presentation as pptx
- java create powerpoint presentation
lastmod: '2026-09-17'
og_description: Aprenda como adicionar clustered column chart a uma apresentação PowerPoint
  usando Aspose.Slides para Java, incluindo etapas para inserir data series, personalizar
  grouping e salvar o arquivo como PPTX.
og_image_alt: Guide showing clustered column chart creation in PowerPoint with Aspose.Slides
  Java
og_title: Adicionar clustered column chart ao PowerPoint usando Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to add clustered column chart to a PowerPoint presentation,
    customize PowerPoint chart, and insert data series chart using Aspose.Slides for
    Java.
  headline: How to add clustered column chart in PowerPoint using Aspose.Slides for
    Java
  type: TechArticle
- questions:
  - answer: '`Presentation` from `com.aspose.slides`.'
    question: "Add chart to slide** and configure it as a clustered column chart.
      \ \n- **Create grouped column chart** by defining grouping levels for categories.
      \ \n- **Insert data series chart** so your data is displayed correctly.  \n-
      Save the finished presentation as a PPTX file.\n\n## Quick answers\n- **What
      is the primary class?"
  - answer: '`ChartType.ClusteredColumn`.'
    question: Which chart type is used?
  - answer: A free trial works, but a license removes evaluation limits.
    question: Do I need a license for testing?
  - answer: JDK 16 or newer (the example uses JDK 16).
    question: What Java version is supported?
  - answer: Add the Maven/Gradle dependency, compile, and run the `main` method.
    question: How to run the sample?
  type: FAQPage
tags:
- add clustered column chart
- aspose.slides
- java powerpoint automation
- chart generation
title: Como adicionar clustered column chart no PowerPoint usando Aspose.Slides para
  Java
url: /pt/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como adicionar gráfico de colunas agrupadas no PowerPoint usando Aspose.Slides for Java

## Introdução

Quando você precisa **adicionar um gráfico de colunas agrupadas** a uma apresentação PowerPoint, um visual claro pode transformar números brutos em uma história instantaneamente compreensível. Fazer isso manualmente no PowerPoint pode consumir tempo, especialmente quando você precisa gerar muitos slides programaticamente. **Aspose.Slides for Java** elimina a fricção – permite criar, personalizar gráficos do PowerPoint e inserir gráficos de série de dados com apenas algumas linhas de código.

Neste tutorial você aprenderá a:
- Inicializar uma nova apresentação PowerPoint com Aspose.Slides for Java.  
- **Adicionar gráfico ao slide** e configurá-lo como um gráfico de colunas agrupadas.  
- **Criar gráfico de colunas agrupadas** definindo níveis de agrupamento para categorias.  
- **Inserir gráfico de série de dados** para que seus dados sejam exibidos corretamente.  
- Salvar a apresentação final como um arquivo PPTX.

## Respostas rápidas
- **Qual é a classe principal?** `Presentation` de `com.aspose.slides`.  
- **Qual tipo de gráfico é usado?** `ChartType.ClusteredColumn`.  
- **Preciso de uma licença para testes?** Uma avaliação gratuita funciona, mas uma licença remove os limites de avaliação.  
- **Qual versão do Java é suportada?** JDK 16 ou mais recente (o exemplo usa JDK 16).  
- **Como executar o exemplo?** Adicione a dependência Maven/Gradle, compile e execute o método `main`.

## O que é “adicionar gráfico de colunas agrupadas”?

Um gráfico de colunas agrupadas exibe várias séries de dados lado a lado para cada categoria, permitindo comparar valores entre grupos em um único visual. É ideal para vendas trimestrais, resultados de pesquisas ou qualquer cenário em que você precise contrastar vários conjuntos de dados dentro da mesma categoria.

## Por que usar Aspose.Slides para adicionar gráfico de colunas agrupadas?

Você pode gerar dezenas de slides automaticamente, personalizar cada elemento visual e executar o código em qualquer SO que suporte Java — sem necessidade de instalação do Microsoft Office. Aspose.Slides suporta **mais de 50 tipos de gráficos** e pode processar apresentações com **até 500 slides** sem carregar todo o arquivo na memória, tornando‑o adequado para pipelines de relatórios em grande escala.

## Pré-requisitos

- **Biblioteca Aspose.Slides for Java** (versão mais recente recomendada).  
- JDK 16 ou posterior.  
- Ferramenta de build Maven ou Gradle (ou você pode adicionar o JAR manualmente).  
- Uma IDE ou editor de texto para executar código Java.

## Configurando Aspose.Slides para Java

Adicione a biblioteca ao seu projeto usando um dos scripts de build a seguir.

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

Alternativamente, você pode baixar diretamente a versão mais recente em [lançamentos do Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Aquisição de licença

Antes de implantar em produção, obtenha uma licença:
- **Teste gratuito** – explore todos os recursos sem compra.  
- **Licença temporária** – avalie recursos avançados por um curto período.  
- **Licença completa** – desbloqueie uso ilimitado. Obtenha-a na [página de compra da Aspose](https://purchase.aspose.com/buy).

## Como adicionar um gráfico de colunas agrupadas no PowerPoint usando Aspose.Slides for Java?

Carregue uma nova `Presentation`, adicione um slide, insira um `Chart` do tipo `ChartType.ClusteredColumn`, preencha sua planilha interna com categorias e séries e, em seguida, salve o arquivo como PPTX. Essa sequência cria um gráfico de colunas agrupadas totalmente funcional com apenas algumas chamadas de API.

### Inicializar apresentação

`Presentation` é a classe que representa um arquivo PowerPoint na memória, permitindo adicionar slides, formas e gráficos programaticamente.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Adicionar gráfico ao slide

`ChartType.ClusteredColumn` indica ao Aspose.Slides para renderizar um gráfico de colunas agrupadas.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Preparar a planilha de dados do gráfico

O gráfico armazena seus dados em uma planilha interna. Limpar essa planilha fornece uma base limpa para dados personalizados.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Adicionar categorias com níveis de agrupamento

Agrupar categorias cria o efeito de gráfico de colunas agrupadas. Cada categoria pode pertencer a um grupo lógico que aparece nos rótulos dos eixos.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Adicionar séries de dados ao gráfico

Objetos `Series` representam colunas individuais no gráfico. Adicionar várias séries resulta em colunas lado a lado para cada categoria.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Salvar apresentação com o gráfico

Salvar a `Presentation` grava um arquivo PPTX padrão que pode ser aberto em qualquer visualizador de PowerPoint.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Aplicações práticas

- **Relatórios de negócios** – compare a receita trimestral entre regiões.  
- **Pesquisa acadêmica** – mostre resultados experimentais agrupados por condições de teste.  
- **Gerenciamento de projetos** – visualize as taxas de conclusão de tarefas para várias equipes em um único slide.

## Considerações de desempenho

- **Gerenciamento de memória** – libere planilhas grandes após o uso.  
- **Operações em lote** – evite atualizar o gráfico dentro de loops apertados; colete os dados primeiro e depois aplique-os.  
- **Otimizações embutidas** – Aspose.Slides fornece métodos como `Presentation.optimize()` para arquivos grandes, reduzindo o consumo de memória em até **30 %**.

## Armadilhas comuns e dicas

- **Armadilha:** Esquecer de limpar séries/categorias existentes pode gerar dados duplicados.  
  **Dica:** Sempre chame `clear()` antes de preencher novos dados.  
- **Armadilha:** Usar o endereço de célula errado (por exemplo, `"c2"` em vez de `"C2"`).  
  **Dica:** As referências de célula não diferenciam maiúsculas de minúsculas, mas mantenha-as consistentes para legibilidade.  
- **Dica:** Use `setGroupingItem` para criar rótulos de grupo significativos; eles aparecem automaticamente na legenda do gráfico.

## Perguntas frequentes

**Q1: Como posso adicionar várias séries ao meu gráfico?**  
A1: Chame `ch.getChartData().getSeries().add()` repetidamente, fornecendo um nome único e pontos de dados para cada série.

**Q2: Quais são alguns problemas comuns com gráficos do Aspose.Slides?**  
A2: Os problemas geralmente decorrem de intervalos de dados incompatíveis ou células de planilha ausentes. Verifique se cada categoria e ponto de dados tem uma célula correspondente.

**Q3: Posso usar Aspose.Slides com outras linguagens de programação?**  
A3: Sim, a Aspose fornece bibliotecas equivalentes para .NET, C++, Python e mais.

**Q4: Como atualizo um gráfico existente em uma apresentação?**  
A4: Carregue a apresentação, localize o gráfico via `slide.getShapes().get_Item(index)`, então modifique suas séries ou formatação conforme necessário.

**Q5: Existem limitações nos tipos de gráficos com Aspose.Slides?**  
A5: A biblioteca suporta mais de **50 tipos de gráficos** e adiciona novos continuamente; sempre verifique a documentação mais recente para a lista mais atualizada.

## Recursos

- **Documentação:** [Referência Aspose.Slides](https://reference.aspose.com/slides/java/)  
- **Download:** [Últimos lançamentos](https://releases.aspose.com/slides/java/)  
- **Compra:** [Comprar Aspose.Slides](https://purchase.aspose.com/buy)  
- **Teste gratuito:** [Inicie seu teste gratuito](https://releases.aspose.com/slides/java/)  
- **Licença temporária:** [Solicitar uma licença temporária](https://purchase.aspose.com/temporary-license/)  
- **Fórum de suporte:** [Suporte Aspose](https://forum.aspose.com/c/slides/11)

---

**Última atualização:** 2026-09-17  
**Testado com:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose

## Tutoriais relacionados

- [Guia de Criação de Gráficos em Java com Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [Como adicionar gráfico ao PowerPoint usando Aspose.Slides para Java: um guia passo a passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Adicionar animação ao gráfico do PowerPoint usando Aspose.Slides para Java – um guia passo a passo](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}