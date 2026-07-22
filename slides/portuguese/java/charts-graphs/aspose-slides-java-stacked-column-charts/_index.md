---
date: '2026-07-22'
description: Aprenda a Aspose Slides Maven Dependency para criar um gráfico de colunas
  empilhadas em Java, adicionar rótulos de dados, alterar o formato numérico do eixo
  vertical e exportar o resultado como um arquivo PPTX.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency permite criar um gráfico de colunas
  empilhadas em Java, personalizar rótulos de dados, ajustar o formato do eixo vertical
  e salvar como PPTX – tudo com código conciso e pronto para produção.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Gráfico de Colunas Empilhadas em Java'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Gráfico de Colunas Empilhadas em Java'
url: /pt/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dependência Maven do Aspose Slides: Gráfico de Colunas Empilhadas em Java

## Introdução

Eleve suas apresentações incorporando visualizações de dados perspicazes com o poder do **Aspose.Slides for Java**. Neste guia você **criará um gráfico de colunas empilhadas** que parece profissional, seja ao preparar relatórios de negócios ou ao exibir estatísticas de projetos. Ao final deste tutorial você será capaz de:

- Configurar seu ambiente com a **dependência Maven do Aspose Slides**
- Criar uma apresentação do zero
- **Adicionar um gráfico de colunas empilhadas em porcentagem** e personalizar sua aparência
- **Formatar rótulos de dados do gráfico** e **alterar o formato numérico do eixo vertical**
- **Salvar a apresentação como PPTX** com uma única linha de código

## Respostas Rápidas
- **Qual biblioteca eu preciso?** Adicione a dependência Maven/Gradle `aspose-slides` (veja “Dependência Maven do Aspose Slides” abaixo).  
- **Qual tipo de gráfico cria uma visualização empilhada?** Use `ChartType.PercentsStackedColumn` para um gráfico de colunas empilhadas em porcentagem.  
- **Como mudar o formato numérico do eixo?** Chame `IAxis.setNumberFormat()` e defina `setNumberFormatLinkedToSource(false)`.  
- **Posso personalizar os rótulos de dados?** Sim – itere por cada `IChartDataPoint` e atribua um `ITextFrame` personalizado.  
- **Como salvo o arquivo?** Invocar `presentation.save("output.pptx", SaveFormat.Pptx)`.

## O que é um gráfico de colunas empilhadas?
Um gráfico de colunas empilhadas visualiza várias séries de dados empilhadas verticalmente em cada coluna de categoria, com a variante **empilhada em porcentagem** normalizando cada coluna para 100 % para facilitar a comparação de proporções. Esse formato permite que os espectadores avaliem rapidamente como cada componente contribui para o todo em diferentes categorias, tornando tendências e tamanhos relativos instantaneamente claros.

## Por que usar Aspose.Slides para Java?
Aspose.Slides para Java permite gerar, editar e converter arquivos PowerPoint **sem precisar do Microsoft Office** e suporta **mais de 50 formatos de saída** em Windows, Linux e macOS. A biblioteca roda totalmente em uma JRE, possibilitando automação server‑side e geração de relatórios de alta taxa de transferência. Ela também fornece controle detalhado sobre objetos de gráfico, layouts de slides e propriedades de documentos, tornando‑a ideal para geração de apresentações em nível empresarial.

## Pré‑requisitos
- **Java Development Kit (JDK):** 8 ou superior  
- **IDE:** IntelliJ IDEA, Eclipse ou qualquer editor compatível com Java  
- **Ferramenta de Build:** Maven ou Gradle (opcional, mas recomendado)  
- **Conhecimento básico de Java** – você deve estar confortável com classes e métodos  

## Configurando Aspose.Slides para Java
Para começar, adicione a biblioteca Aspose.Slides ao seu projeto.

### Dependência Maven do Aspose Slides
Adicione o seguinte ao seu `pom.xml` (esta é a **dependência maven do aspose slides** que você precisará):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Alternativa Gradle
Se preferir Gradle, inclua esta linha em `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download Direto
Alternativamente, faça o download do JAR mais recente em [lançamentos do Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Aquisição de Licença
Você pode começar com um teste gratuito para explorar os recursos do Aspose.Slides. Para remover as limitações de avaliação, considere obter uma licença temporária ou comprada.

- **Teste Gratuito:** Acesse recursos limitados sem custos imediatos.  
- **Licença Temporária:** Solicite via [site da Aspose](https://purchase.aspose.com/temporary-license/).  
- **Compra:** Visite a página de compra para acesso total.

### Inicialização Básica
`Presentation` é a classe central do Aspose.Slides que representa um arquivo PowerPoint na memória. O snippet mínimo a seguir mostra como criar um objeto `Presentation`:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Guia de Implementação

### Criando uma Apresentação e Adicionando um Slide
**Visão geral:**  
Primeiro, criaremos uma apresentação em branco e verificaremos se um slide existe.

#### Etapa 1: Inicializar o Objeto Presentation
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Etapa 2: Salvar a Apresentação
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Adicionando Gráfico de Colunas Empilhadas em Porcentagem a um Slide
**Visão geral:**  
Agora colocaremos um **gráfico empilhado em porcentagem** no primeiro slide.

`ChartType.PercentsStackedColumn` especifica um tipo de gráfico de colunas empilhadas em porcentagem.

#### Etapa 1: Inicializar e Acessar o Slide
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Etapa 2: Adicionar Gráfico ao Slide
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Personalizando o Formato Numérico do Eixo do Gráfico
**Visão geral:**  
Para melhor legibilidade, **alteraremos o formato do eixo vertical** para exibir porcentagens.

`IAxis` é a interface que representa um eixo de gráfico, permitindo ajustes de formato e escala.

#### Etapa 1: Adicionar e Acessar o Gráfico
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Etapa 2: Definir Formato Numérico Personalizado
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Adicionando Séries e Pontos de Dados ao Gráfico
**Visão geral:**  
Popularemos o gráfico com séries de dados de exemplo.

#### Etapa 1: Inicializar Apresentação e Gráfico
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Etapa 2: Adicionar Séries de Dados
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Formatando a Cor de Preenchimento das Séries
**Visão geral:**  
Dê a cada série uma cor distinta para tornar o gráfico mais fácil de ler.

#### Etapa 1: Inicializar e Acessar o Gráfico
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Etapa 2: Definir Cores de Preenchimento
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Formatando Rótulos de Dados
**Visão geral:**  
Agora **formataremos os rótulos de dados do gráfico** para que exibam texto personalizado.

`IChartDataPoint` representa um ponto de dado individual dentro de uma série de gráfico, e `ITextFrame` contém o texto do rótulo.

#### Etapa 1: Acessar Séries do Gráfico e Pontos de Dados
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Etapa 2: Personalizar Rótulos de Dados
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Problemas Comuns e Soluções
- **O gráfico aparece vazio:** Certifique‑se de que adicionou ao menos uma série de dados e um ponto de dado antes de salvar.  
- **Números do eixo não mostram porcentagens:** Lembre‑se de definir `verticalAxis.setNumberFormatLinkedToSource(false)`; caso contrário, o formato personalizado será ignorado.  
- **Mensagem de avaliação da licença:** Aplique um arquivo de licença válido antes de criar o objeto `Presentation` para suprimir a faixa de avaliação.

## Perguntas Frequentes

**P: Posso usar este código com Java 11 ou superior?**  
R: Sim. A biblioteca suporta JDK 8+; basta usar o classificador apropriado (por exemplo, `jdk16` para JDK 16 ou posterior).

**P: Como exportar o gráfico como imagem em vez de PPTX?**  
R: Use `chart.getImage().save("chart.png", ImageFormat.Png);` após adicionar o gráfico ao slide.

**P: É possível adicionar uma legenda ao gráfico de colunas empilhadas?**  
R: Absolutamente. Chame `chart.getChartTitle().addTextFrameForOverriding("My Chart");` e configure `chart.getLegend()` conforme necessário.

**P: E se eu precisar atualizar os dados após a apresentação ser gerada?**  
R: Você pode modificar as células do `ChartDataWorkbook` e então chamar `chart.refresh();` para refletir as alterações.

**P: O Aspose.Slides funciona em servidores Linux?**  
R: Sim. A biblioteca é pura Java e roda em qualquer SO com uma JRE compatível.

## Conclusão
Seguindo este guia, você aprendeu a **criar um gráfico de colunas empilhadas** em Java usando a **dependência Maven do Aspose Slides**, desde a configuração do ambiente até o estilo visual refinado. Experimente diferentes conjuntos de dados, cores e formatos de rótulo para fazer seus relatórios realmente se destacarem.

---

**Última atualização:** 2026-07-22  
**Testado com:** Aspose.Slides 25.4 (classificador jdk16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Como criar gráfico de colunas agrupadas em Java com Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Como Definir Formatos Numéricos em Pontos de Dados de Gráficos Usando Aspose.Slides para Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [Como Adicionar e Configurar Gráficos em Apresentações Usando Aspose.Slides para Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}