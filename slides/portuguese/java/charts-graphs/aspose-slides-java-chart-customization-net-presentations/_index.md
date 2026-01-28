---
date: '2026-01-17'
description: Aprenda a adicionar séries a um gráfico e personalizar gráficos de colunas
  empilhadas em apresentações .NET usando Aspose.Slides para Java.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: Adicionar Séries ao Gráfico com Aspose.Slides para Java em .NET
url: /pt/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dominando a Personalização de Gráficos em Apresentações .NET Usando Aspose.Slides para Java

## Introdução
No universo das apresentações orientadas a dados, os gráficos são ferramentas indispensáveis que transformam números brutos em histórias visuais envolventes. Quando você precisa **adicionar séries ao gráfico** programaticamente, especialmente dentro de arquivos de apresentação .NET, a tarefa pode parecer assustadora. Felizmente, **Aspose.Slides para Java** oferece uma API poderosa e independente de linguagem que torna a criação e personalização de gráficos simples — mesmo quando o formato de destino é um PPTX .NET.

Neste tutorial você descobrirá como **adicionar séries ao gráfico**, como **adicionar um gráfico** do tipo coluna empilhada e como ajustar detalhes visuais como a largura do espaçamento. Ao final, você será capaz de gerar slides dinâmicos e ricos em dados, com aparência polida e profissional.

**O que você aprenderá**
- Como criar uma apresentação vazia usando Aspose.Slides  
- Como **adicionar um gráfico de coluna empilhada** a um slide  
- Como **adicionar séries ao gráfico** e definir categorias  
- Como preencher pontos de dados e ajustar configurações visuais  

Vamos preparar seu ambiente de desenvolvimento.

## Respostas Rápidas
- **Qual é a classe principal para iniciar uma apresentação?** `Presentation`  
- **Qual método adiciona um gráfico a um slide?** `slide.getShapes().addChart(...)`  
- **Como você adiciona uma nova série?** `chart.getChartData().getSeries().add(...)`  
- **É possível alterar a largura do espaçamento entre as barras?** Sim, usando `setGapWidth()` no grupo de séries  
- **Preciso de uma licença para produção?** Sim, é necessária uma licença válida do Aspose.Slides para Java  

## O que significa “adicionar séries ao gráfico”?
Adicionar uma série a um gráfico significa inserir uma nova coleção de dados que o gráfico renderizará como um elemento visual distinto (por exemplo, uma nova barra, linha ou fatia). Cada série pode ter seu próprio conjunto de valores, cores e formatação, permitindo comparar vários conjuntos de dados lado a lado.

## Por que usar Aspose.Slides para Java para modificar apresentações .NET?
- **Multiplataforma**: escreva código Java uma única vez e direcione arquivos PPTX usados por aplicações .NET.  
- **Sem dependências de COM ou Office**: funciona em servidores, pipelines CI e contêineres.  
- **API rica de gráficos**: suporta mais de 50 tipos de gráficos, incluindo gráficos de coluna empilhada.  

## Pré‑requisitos
1. Biblioteca **Aspose.Slides para Java** (versão 25.4 ou superior).  
2. Ferramenta de build Maven ou Gradle, ou download manual do JAR.  
3. Conhecimento básico de Java e familiaridade com a estrutura PPTX.  

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
Alternativamente, obtenha o JAR mais recente na página oficial de lançamentos: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Aquisição de Licença**  
Comece com um teste gratuito baixando uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/). Para uso em produção, adquira uma licença completa para desbloquear todos os recursos.

## Guia de Implementação Passo a Passo
Abaixo de cada passo você encontrará um trecho de código conciso (mantido inalterado em relação ao tutorial original) seguido de uma explicação do que ele faz.

### Passo 1: Criar uma Apresentação Vazia
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

### Passo 2: Adicionar um Gráfico de Coluna Empilhada ao Slide
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*O método `addChart` cria um **gráfico de coluna empilhada** e o posiciona no canto superior esquerdo do slide.*

### Passo 3: Adicionar Séries ao Gráfico (Objetivo Principal)
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
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*As categorias funcionam como rótulos do eixo X, dando significado a cada coluna.*

### Passo 5: Preencher Dados das Séries
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
*Os pontos de dados fornecem a cada série seus valores numéricos, que o gráfico renderiza como alturas de barras.*

### Passo 6: Definir Largura do Espaçamento para o Grupo de Séries do Gráfico
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*Ajustar a largura do espaçamento melhora a legibilidade, especialmente quando há muitas categorias.*

## Casos de Uso Comuns
- **Relatórios financeiros** – comparar receita trimestral entre unidades de negócio.  
- **Painéis de projetos** – mostrar percentuais de conclusão de tarefas por equipe.  
- **Análises de marketing** – visualizar desempenho de campanhas lado a lado.

## Dicas de Performance
- **Reutilize o objeto `Presentation`** ao criar múltiplos gráficos para reduzir o consumo de memória.  
- **Limite o número de pontos de dados** apenas ao necessário para a história visual.  
- **Descarte objetos** (`presentation.dispose()`) após salvar para liberar recursos.

## Perguntas Frequentes
**P: Posso adicionar outros tipos de gráfico além de coluna empilhada?**  
R: Sim, Aspose.Slides suporta linha, pizza, área e muitos outros tipos de gráfico.

**P: Preciso de uma licença separada para saída .NET?**  
R: Não, a mesma licença Java funciona para todos os formatos de saída, incluindo arquivos PPTX .NET.

**P: Como altero a paleta de cores do gráfico?**  
R: Use `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` e defina a `Color` desejada.

**P: É possível adicionar rótulos de dados programaticamente?**  
R: Absolutamente. Chame `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` para exibir os valores.

**P: E se eu precisar atualizar uma apresentação existente?**  
R: Carregue o arquivo com `new Presentation("existing.pptx")`, modifique o gráfico e salve novamente.

## Conclusão
Agora você tem um guia completo, de ponta a ponta, sobre como **adicionar séries ao gráfico**, criar um **gráfico de coluna empilhada** e ajustar sua aparência em apresentações .NET usando Aspose.Slides para Java. Experimente diferentes tipos de gráfico, cores e fontes de dados para construir relatórios visuais atraentes que impressionem as partes interessadas.

---

**Última atualização:** 2026-01-17  
**Testado com:** Aspose.Slides para Java 25.4 (jdk16)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
