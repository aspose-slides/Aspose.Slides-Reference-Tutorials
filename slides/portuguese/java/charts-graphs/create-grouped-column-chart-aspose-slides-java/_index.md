---
date: '2026-03-20'
description: Aprenda a adicionar um gráfico de colunas agrupadas a uma apresentação
  do PowerPoint, personalizar o gráfico do PowerPoint e inserir um gráfico de série
  de dados usando o Aspose.Slides para Java.
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: Como adicionar um gráfico de colunas agrupadas no PowerPoint usando Aspose.Slides
  para Java
url: /pt/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como adicionar um gráfico de colunas agrupadas no PowerPoint usando Aspose.Slides para Java

## Introduction

Quando você precisa **adicionar um gráfico de colunas agrupadas** a um deck do PowerPoint, um visual claro pode transformar números brutos em uma história instantaneamente compreensível. Fazer isso manualmente no PowerPoint pode ser demorado, especialmente quando você tem que gerar muitos slides programaticamente. **Aspose.Slides for Java** remove a fricção – permite criar, personalizar gráficos do PowerPoint e inserir gráficos de série de dados com apenas algumas linhas de código.

Neste tutorial você aprenderá a:
- Inicializar uma nova apresentação PowerPoint com Aspose.Slides for Java.
- **Adicionar gráfico ao slide** e configurá-lo como um gráfico de colunas agrupadas.
- **Criar gráfico de colunas agrupadas** definindo níveis de agrupamento para categorias.
- **Inserir gráfico de série de dados** para que seus dados sejam exibidos corretamente.
- Salvar a apresentação final como um arquivo PPTX.

Vamos garantir que você tem tudo o que precisa antes de mergulharmos no código.

## Quick Answers
- **Qual é a classe principal?** `Presentation` from `com.aspose.slides`.
- **Qual tipo de gráfico é usado?** `ChartType.ClusteredColumn`.
- **Preciso de uma licença para teste?** A free trial works, but a license removes evaluation limits.
- **Qual versão do Java é suportada?** JDK 16 or newer (the example uses JDK 16).
- **Como executar o exemplo?** Add the Maven/Gradle dependency, compile, and run the `main` method.

## What is “add clustered column chart”?

Um *gráfico de colunas agrupadas* (também chamado de gráfico de colunas agrupadas) exibe várias séries de dados lado a lado para cada categoria, facilitando a comparação de valores entre grupos. No PowerPoint esse tipo de gráfico é ideal para vendas trimestrais, resultados de pesquisas ou qualquer cenário em que você precise contrastar vários conjuntos de dados dentro da mesma categoria.

## Why use Aspose.Slides to add clustered column chart?

- **Full automation** – gerar dezenas de slides sem esforço manual.
- **Fine‑grained customization** – controlar cores, rótulos, níveis de agrupamento e mais.
- **Cross‑platform** – funciona em qualquer SO que suporte Java.
- **No Office installation required** – gerar arquivos PPTX em servidores ou pipelines de CI.

## Prerequisites

- **Aspose.Slides for Java** library (a versão mais recente é recomendada).  
- JDK 16 ou posterior.  
- Ferramenta de build Maven ou Gradle (ou você pode adicionar o JAR manualmente).  
- Uma IDE ou editor de texto para executar código Java.

## Setting Up Aspose.Slides for Java

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

Alternativamente, você pode baixar diretamente a versão mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition

Before deploying to production, obtain a license:
- **Free trial** – explore todos os recursos sem compra.
- **Temporary license** – avalie recursos estendidos por um curto período.
- **Full license** – desbloqueie uso ilimitado. Obtenha em [Aspose's purchase page](https://purchase.aspose.com/buy).

## Implementation Guide

Percorreremos cada passo, explicando **como adicionar gráfico** e **personalizar o gráfico do PowerPoint** ao longo do caminho.

### Initialize Presentation

Primeiro, crie um novo objeto `Presentation` e obtenha o slide padrão.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Add Chart to Slide

Agora nós **adicionamos gráfico ao slide** usando o tipo `ClusteredColumn` e limpamos quaisquer dados padrão.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Prepare Chart Data Workbook

O gráfico armazena seus dados em uma planilha interna. Nós a limpamos para começar do zero.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Add Categories with Grouping Levels

Agrupar categorias cria o efeito de **gráfico de colunas agrupadas**. Cada categoria pode pertencer a um grupo lógico.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Add Data Series to Chart

Aqui nós **inserimos entradas de série de dados no gráfico** que serão visualizadas como colunas separadas.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Save Presentation with Chart

Finalmente, grave o arquivo PPTX no disco.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Practical Applications

- **Business Reports** – comparar a receita trimestral entre regiões.  
- **Academic Research** – mostrar resultados experimentais agrupados por condições de teste.  
- **Project Management** – visualizar taxas de conclusão de tarefas para várias equipes em um único slide.

## Performance Considerations

- **Memory management** – liberar planilhas grandes após o uso.  
- **Batch operations** – evitar atualizar o gráfico dentro de loops apertados; coletar os dados primeiro, depois aplicá-los.  
- **Built‑in optimizations** – Aspose.Slides fornece métodos como `Presentation.optimize()` para arquivos grandes.

## Common Pitfalls & Tips

- **Pitfall:** Esquecer de limpar as séries/categorias existentes pode gerar dados duplicados.  
  **Tip:** Sempre chame `clear()` antes de preencher novos dados.  
- **Pitfall:** Usar o endereço de célula errado (ex., `"c2"` ao invés de `"C2"`).  
  **Tip:** Referências de célula não diferenciam maiúsculas de minúsculas, mas mantenha-as consistentes para legibilidade.  
- **Tip:** Use `setGroupingItem` para criar rótulos de grupo significativos; eles aparecem automaticamente na legenda do gráfico.

## Frequently Asked Questions

**Q1: Como posso adicionar várias séries ao meu gráfico?**  
A1: Chame `ch.getChartData().getSeries().add()` repetidamente, fornecendo um nome exclusivo e pontos de dados para cada série.

**Q2: Quais são alguns problemas comuns com gráficos do Aspose.Slides?**  
A2: Os problemas geralmente decorrem de intervalos de dados incompatíveis ou células de planilha ausentes. Verifique se cada categoria e ponto de dados tem uma célula correspondente.

**Q3: Posso usar Aspose.Slides com outras linguagens de programação?**  
A3: Sim, a Aspose fornece bibliotecas equivalentes para .NET, C++, Python e mais.

**Q4: Como atualizo um gráfico existente em uma apresentação?**  
A4: Carregue a apresentação, localize o gráfico via `slide.getShapes().get_Item(index)`, então modifique suas séries ou formatação conforme necessário.

**Q5: Existem limitações nos tipos de gráfico com Aspose.Slides?**  
A5: A biblioteca suporta uma ampla variedade de tipos de gráfico, mas sempre verifique a documentação mais recente para quaisquer tipos recém‑adicionados ou depreciados.

## Resources

- **Documentação**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)
- **Download**: [Latest Releases](https://releases.aspose.com/slides/java/)
- **Compra**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)
- **Teste Gratuito**: [Start Your Free Trial](https://releases.aspose.com/slides/java/)
- **Licença Temporária**: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- **Fórum de Suporte**: [Aspose Support](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2026-03-20  
**Testado com:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose