---
date: '2026-06-03'
description: Aprenda como adicionar charts com a dependência Maven do Aspose.Slides,
  configurar data labels e gerar dynamic charts em apresentações Java.
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: 'dependência Maven do Aspose.Slides: adicionar e configurar charts em apresentações
  usando Aspose.Slides para Java'
url: /pt/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# dependência maven aspose slides: adicionar e configurar gráficos em apresentações usando Aspose.Slides para Java

## Introdução
A **aspose slides maven dependency** permite que desenvolvedores Java criem, modifiquem e enriqueçam arquivos PowerPoint programaticamente, sem nunca abrir o PowerPoint. Em muitos cenários empresariais e acadêmicos, inserir gráficos manualmente consome tempo e é propenso a erros. Este tutorial mostra passo a passo como adicionar um Gráfico de Bolhas, vincular rótulos de dados a células de planilha e salvar o resultado — tudo aproveitando a aspose slides maven dependency de forma limpa e repetível.

**O que você aprenderá**
- Como adicionar gráficos com a aspose slides maven dependency
- Configuração de um projeto Java usando Maven ou Gradle
- Carregamento de uma apresentação existente e inserção de um Gráfico de Bolhas
- Configuração de rótulos de dados usando referências de células (add data labels chart)
- Salvamento do arquivo atualizado para distribuição posterior
- Casos de uso reais, como geração dinâmica de gráficos e fluxos de trabalho de criação de gráficos em apresentações

## Respostas rápidas
- **Qual artefato Maven adiciona recursos de gráficos?** `com.aspose:aspose-slides:25.4` (ou mais recente)  
- **Posso vincular rótulos de dados a células no estilo Excel?** Sim – use `ChartDataLabel` com `setDataLabelFormat` e referências de célula.  
- **É necessária licença para produção?** Uma licença completa remove a marca d'água de avaliação e desbloqueia todos os recursos.  
- **Isso funciona em Java 11+?** Absolutamente; a biblioteca é compatível com Java 8 até Java 21.  
- **Quantos tipos de gráficos são suportados?** Mais de 70 tipos distintos, incluindo Bubble, Radar e Stock.

## O que é a dependência maven aspose slides?
A **aspose slides maven dependency** é um pacote compatível com Maven que fornece uma API completa para criar e editar arquivos PowerPoint (PPTX, PPT, ODP) em Java. Ao adicionar esta dependência ao seu `pom.xml` ou `build.gradle`, você obtém acesso a mais de 70 tipos de gráficos, mais de 150 layouts de slide e a capacidade de manipular formas, animações e metadados sem precisar do Office instalado.

## Por que usar a dependência maven aspose slides para automação de gráficos?
Aspose.Slides processa decks com milhares de slides em menos de um segundo em hardware de servidor padrão, suporta **mais de 70 tipos de gráficos** e pode renderizar apresentações de até **10.000 slides** sem carregar o arquivo inteiro na memória. Essas capacidades quantificadas a tornam ideal para geração dinâmica de gráficos em nível empresarial, onde desempenho e escalabilidade são indispensáveis.

## Pré-requisitos
- **Java Development Kit (JDK)** 8 ou superior (Java 11+ recomendado).  
- **Maven** 3.6+ **ou** **Gradle** 6+.  
- Biblioteca **Aspose.Slides for Java** (a aspose slides maven dependency, versão 25.4 ou posterior).  
- Familiaridade básica com coleções Java e I/O de arquivos.  
- Arquivo de licença de avaliação ou completa (`license.json`) se você pretender executar o código além do período de teste.

## Como adicionar um gráfico a um slide usando Aspose.Slides?
Carregue a apresentação alvo, crie uma nova forma de gráfico no slide desejado e especifique o tipo de gráfico (Bubble neste exemplo). Toda a operação pode ser realizada em **três linhas concisas de código** uma vez que a biblioteca esteja referenciada, tornando-a perfeita para prototipagem rápida e pipelines de produção.

### Etapa 1: adicionar a dependência maven aspose slides
**Maven:**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle:**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
Esses trechos trazem a API completa do Aspose.Slides — incluindo suporte a gráficos — diretamente do Maven Central.

### Etapa 2: carregar a apresentação e inserir um gráfico de bolhas
**Implementação:**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Etapa 3: configurar a série de dados e rótulos do gráfico
**Implementação:**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Etapa 4: salvar a apresentação modificada
**Implementação:**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## Como configurar rótulos de dados usando referências de células?
Os rótulos de dados podem ser vinculados a valores de células externas, espelhando o recurso “Link to Cell” do Excel. Essa abordagem elimina valores codificados e permite **geração dinâmica de gráficos** onde o conteúdo dos rótulos é atualizado automaticamente conforme os dados subjacentes mudam. Ao vincular cada rótulo a uma célula específica da planilha, você garante que qualquer modificação nos dados de origem seja refletida instantaneamente na apresentação, reduzindo esforço de manutenção e minimizando o risco de informações desatualizadas.

### Resposta direta
Chame `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` e passe um `DataLabelFormat` que referencia um endereço de célula como `"Sheet1!A2"`. Aspose.Slides resolve a referência em tempo de execução, inserindo o valor atual da célula no rótulo do gráfico.

### Passo a passo
1. Identifique a série que deseja rotular.  
2. Recupere o objeto `IDataLabel` para cada ponto de dados.  
3. Use `setDataLabelFormat` com `DataLabelFormat` configurado para `CellReference`.  
4. Opcionalmente personalize fonte, cor e opções de exibição.

## Como salvar a apresentação modificada?
Salvar consiste em uma única chamada de método que grava o objeto `Presentation` em memória para um caminho de arquivo ou fluxo de saída. Você também pode escolher o formato de saída (PPTX, PDF, ODP) passando o enum `SaveFormat` apropriado. Essa operação transmite o resultado diretamente para o disco, liberando todos os recursos nativos automaticamente quando a instância `Presentation` é fechada ou sai de escopo, o que ajuda a manter o uso de memória baixo mesmo para decks grandes.

### Resposta direta
Execute `presentation.save("output.pptx", SaveFormat.Pptx)`; a biblioteca transmite o resultado diretamente para o disco, liberando todos os recursos nativos automaticamente quando a instância `Presentation` é fechada ou sai de escopo.

## Aplicações práticas
1. **Relatórios empresariais:** gerar gráficos de vendas trimestrais automaticamente a partir de um dump de banco de dados.  
2. **Aulas acadêmicas:** inserir dados de pesquisa ao vivo nos slides de aula para cada sessão.  
3. **Propostas de vendas:** construir dashboards de desempenho específicos para cada cliente em tempo real.  
4. **Gerenciamento de projetos:** visualizar cronogramas estilo Gantt com rótulos de dados dinâmicos.  
5. **Analytics de marketing:** incorporar KPIs de campanhas em apresentações que se atualizam à medida que novas métricas chegam.

## Considerações de desempenho
- **Gerenciamento de memória:** use try‑with‑resources ou `presentation.dispose()` explícito para liberar a memória nativa prontamente.  
- **Conjuntos de dados grandes:** ao lidar com mais de 10.000 pontos, preencha os dados do gráfico via `ChartDataWorkbook` para evitar carregar todo o conjunto em objetos Java.  
- **Segurança de threads:** cada thread deve trabalhar com sua própria instância `Presentation`; a API não é thread‑safe para objetos compartilhados.  

## Problemas comuns e soluções
- **Problema:** “Arquivo de licença não encontrado.”  
  **Solução:** Coloque `license.json` no classpath e chame `License license = new License(); license.setLicense("license.json");` antes de usar qualquer API.  
- **Problema:** O gráfico aparece em branco após salvar.  
  **Solução:** Certifique‑se de que o workbook de dados do gráfico seja salvo com a apresentação (`presentation.getCharts().setDataWorkbook(chartWorkbook);`).  
- **Problema:** Rótulos de dados mostram erros “#REF!”.  
  **Solução:** Verifique se a string de referência de célula corresponde exatamente ao nome da planilha e ao endereço, e se o workbook referenciado está anexado ao gráfico.  

## Perguntas frequentes

**P: Posso adicionar outros tipos de gráficos além de Bubble?**  
R: Sim, a enumeração `ChartType` inclui linha, barra, pizza, radar, estoque e mais de 70 tipos adicionais.

**P: A dependência maven aspose slides funciona com OpenJDK?**  
R: Absolutamente; é totalmente compatível com OpenJDK 8‑21 e roda em todos os principais sistemas operacionais.

**P: Como incorporar um gráfico a partir de um arquivo Excel existente?**  
R: Carregue a planilha Excel com `WorkbookFactory.create(new FileInputStream("data.xlsx"))`, então vincule o `ChartDataWorkbook` do gráfico ao workbook antes de definir referências de célula.

**P: Existe um limite para o número de gráficos por slide?**  
R: Praticamente não — Aspose.Slides pode lidar com dezenas de gráficos por slide, limitado apenas pela memória disponível.

**P: Em quais formatos posso exportar a apresentação final?**  
R: PPTX, PPT, ODP, PDF, XPS, HTML e até formatos de imagem como PNG e JPEG são suportados.

## Recursos
- [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) – baixe os binários mais recentes da biblioteca.  
- [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) – referência completa da API e guias.  
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/) – página de download direto dos pacotes Maven/Gradle.  
- [Purchase a License](https://purchase.aspose.com/buy) – obtenha uma licença comercial completa.  
- [Free Trial](https://releases.aspose.com/slides/java/) – comece com um trial para avaliar os recursos.  
- [Temporary License](https://purchase.aspose.com/temporary-license/) – solicite uma chave temporária para avaliação estendida.  
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11) – obtenha ajuda da comunidade e dos engenheiros da Aspose.

## Conclusão
Agora você tem um guia completo, de ponta a ponta, para usar a **aspose slides maven dependency** a fim de adicionar, configurar e persistir gráficos em apresentações Java. Seguindo os passos acima, você pode automatizar a criação de gráficos, vincular rótulos a valores de célula ao vivo e gerar decks de nível profissional em escala. Experimente outros tipos de gráficos, explore as APIs de animação e integre esse fluxo de trabalho em seus pipelines de relatório para obter o máximo impacto.

---  
**Última atualização:** 2026-06-03  
**Testado com:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## Tutoriais relacionados

- [How to Create and Configure Presentations with Aspose.Slides Java&#58; A Step-by-Step Guide](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [Create PPTX Java with Aspose.Slides Maven – Automation Guide](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [How to Create Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}